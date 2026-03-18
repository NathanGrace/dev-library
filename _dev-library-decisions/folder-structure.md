/dev-library/
  README.md                        # Manifesto
  /_current/
  # everything that I'm currently doing so I can pick up where I left off.
  /_inbox/
    effect-ts.md                   # Exploring, not committed yet
  /foundations/
    principles.md                  # No any, fix all linter/formatter warnings, fail-fast, deliberate decisions
    typescript.md                  # Strict typing, avoiding any, Zod for validation
    error-handling.md              # Early exits > try/catch, fail-fast philosophy
    mental-models.md               # How to think about state, side effects, complexity
    architecture-patterns.md       # High-level structural patterns and when to use them
  /stack/
    sveltekit.md                   # Framework-level notes
    svelte.md                      # Svelte 5 specifics, or merge with above
    convex.md                      # Core usage + components (better-auth, resend, autumn, rate-limiter)
    tailwind.md                    # Utility-first styling notes
    shadcn-svelte.md               # Base components, trust defaults, modify deliberately
    better-auth.md                 # Auth setup via Convex component
    zod.md                         # Schema validation, ties into forms + TS
    autumn.md                      # Billing (in progress)
    resend.md                      # Email via Convex component
    opencode.md                    # AI coding tool notes
  /patterns/
    component-structure.md         # kebab-case shadcn primitives, PascalCase custom
    data-fetching.md
    forms-and-validation.md        # Client + server validation, Zod schemas
    auth.md
    error-handling.md              # Practical patterns (vs foundations = philosophy)
    design-system.md               # Uniform style system, respecting shadcn defaults
  /conventions/
    naming.md                      # Component casing rules, file naming
    file-structure.md              # Per-feature/per-page component organization
    code-quality.md                # Zero linter warnings, zero yellow underlines
  /playbooks/
    secure-public-form.md          # Honeypot, client+server validation, rate limiting
    add-convex-component.md        # How to integrate a new Convex component
    new-page.md                    # Follow design system, component conventions
  /decisions/
    _template.md
    2026-03-02-chose-convex-over-supabase.md
    2026-03-02-shadcn-svelte.md    # Trust base components, don't modify without clear reason

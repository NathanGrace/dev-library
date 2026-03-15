# Datastar vs Convex

These notes capture the tradeoffs between using Datastar's `fetch`, `SSE`, and `WebSockets` directly versus using Convex as a sync engine.

## Core framing

- Datastar gives you transport-level and UI-level primitives.
- Convex gives you a sync model, not just a transport.
- The real decision is not `SSE/WebSockets` vs `WebSockets`.
- The real decision is whether you want to design sync behavior yourself or let Convex own most of it.

## What each approach is really doing

### Datastar + fetch

- Plain request/response.
- Simplest model.
- Best for normal CRUD, forms, settings, content, and mostly single-user apps.
- No automatic live updates; you re-fetch or refresh manually.

### Datastar + SSE

- One long-lived HTTP connection from server to browser.
- Server can push updates over time.
- Great for one-way realtime.
- Very aligned with Datastar's backend-driven HTML patching model.
- Client still uses normal fetch/POST for writes.

### Datastar + WebSockets

- Full duplex connection.
- Best when client and server both need to talk continuously.
- Good for richer collaboration, chat, multiplayer-ish interactions, and high-frequency updates.
- Still requires you to design your own sync semantics.

### Convex

- The value is not just the WebSocket transport.
- The value is live queries, subscriptions, invalidation, caching, consistency, and sync ergonomics.
- Convex solves a lot of the "how does data stay correct and fresh everywhere?" problem for you.

## The key distinction

- Datastar answers: "How should the UI update?"
- Convex answers: "How does app data stay synchronized correctly?"

That distinction matters because transport primitives do not automatically give you a good sync model.

## Why Convex feels so good

Convex removes entire categories of decisions:

- what events to emit
- which views to invalidate
- how clients catch up after reconnects
- how concurrent changes reconcile
- how subscriptions map to query results
- how freshness propagates through the UI

If you leave Convex, those decisions do not disappear. They become your responsibility.

## Tradeoffs by option

### Datastar + fetch

Pros:

- dead simple
- easy to reason about
- low ops complexity
- works well for ordinary backend-driven apps

Cons:

- no live updates
- manual refresh or polling needed when data changes elsewhere

Best for:

- profiles
- settings
- admin CRUD
- content pages
- workflows where a little staleness is acceptable

### Datastar + SSE

Pros:

- simpler than WebSockets
- built on normal HTTP
- very good for server-to-client updates
- excellent fit for dashboards, feeds, notifications, progress updates, shared lists, and status changes
- fits Datastar's `datastar-patch-elements` and `datastar-patch-signals` model well

Cons:

- one-way only
- client still needs regular requests for writes
- you still need to design events, reconnection behavior, and invalidation strategy
- does not magically solve consistency or conflict handling

Best for:

- selective realtime in otherwise standard apps

### Datastar + WebSockets

Pros:

- bidirectional
- flexible
- lower-latency interaction patterns
- supports richer collaborative UI patterns

Cons:

- more moving parts
- more stateful infrastructure
- you still have to invent or adopt the sync model yourself
- easy to underestimate auth, retries, fanout, presence, and conflict semantics

Best for:

- chat
- collaborative tools
- multiplayer-ish apps
- high-frequency shared interactions

### Convex

Pros:

- live queries feel effortless
- lower sync bug surface area
- less custom event plumbing
- strong developer ergonomics for shared live data

Cons:

- stronger architectural commitment
- less backend freedom than a fully custom stack
- not as lightweight or backend-agnostic in spirit as Datastar

Best for:

- apps where shared live data is central to the product
- teams who care more about sync ergonomics than minimal stack surface area

## Complexity vs payoff

- Lowest complexity: Datastar + fetch
- Low to medium complexity: Datastar + SSE
- Medium to high complexity: Datastar + raw WebSockets
- Medium upfront commitment, lower ongoing sync complexity: Convex

## Where people get burned

### With the Datastar route

People often underestimate that transport is not the same thing as sync.

Typical failure mode:

- start with events like `task.updated`
- later realize each screen needs different derived data
- add more custom invalidation and patch logic
- gradually rebuild live-query behavior by hand

### With Convex

People get friction when they want:

- total backend freedom
- an existing architecture centered on Postgres/services/jobs
- a very lightweight frontend with backend-owned rendering

## Rule of thumb

- If your app mostly needs "show users fresh state quickly," use Datastar + SSE.
- If your app needs "shared live data with subscriptions and minimal sync code," Convex is hard to beat.
- If your app needs custom realtime interactions but not a full sync engine, use Datastar + WebSockets.
- If your app is mostly normal CRUD with a few live touches, the sweet spot is Datastar + fetch + selective SSE.

## Practical recommendation

If you love Convex because sync feels effortless, do not underestimate how much value that represents.

If you love Datastar because it is lightweight, that is a strong reason to use it for the UI layer.

The real question is whether you want to replace Convex's sync semantics with your own `SSE` or `WebSocket` design.

## A helpful split

- Shared records changing occasionally -> Datastar + fetch + SSE
- Collaborative state changing constantly -> keep Convex, or use another dedicated sync engine rather than rolling your own from scratch

## Simple mental model

- `fetch` = one request, one response
- `SSE` = one request, many streamed responses
- `WebSocket` = open pipe both directions
- `Convex` = a higher-level sync system built on top of realtime transport

# league-server

A tested Go HTTP service that records and serves player scores, with JSON routing and persistence to disk.

**Status:** scaffold only. No server code yet; CI runs one smoke test.

## What it does
Exposes a small JSON API to record wins and read the league table. Data survives restarts because it is stored in a file.

## How it's built
- Go standard library only (`net/http`), test-driven from the first commit.
- A `PlayerStore` interface with an in-memory implementation for tests and a file-backed implementation for real use.
- `httptest` for handler tests; `go test -race` runs in CI.
- CLI entry point in `cmd/`, packages in `internal/`.

## How to run
    git clone https://github.com/anujkumarsharma1/league-server && cd league-server
    go test ./... -race
    go run ./cmd/server

## What it measured
| Check | Result |
|---|---|
| Test coverage (`go test -cover`) | not yet measured |
| Race detector (`go test -race`) | not yet measured |
| Throughput with a load tool (requests/sec) and p99 latency | not yet measured |

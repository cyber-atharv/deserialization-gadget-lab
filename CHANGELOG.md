# Changelog

All notable changes to deserialization-gadget-lab are documented here.

### [2025-12-27]
- feat: add graceful shutdown signal handler (SIGINT/SIGTERM)

### [2025-12-30]
- test: implement mock service for end-to-end integration tests

### [2026-01-30]
- docs: add architecture diagram and sequence flow explanation

### [2026-03-03]
- fix: resolve memory leak in idle connection reaper

### [2026-03-04]
- test: implement mock service for end-to-end integration tests

### [2026-03-05]
- refactor: extract validation logic into dedicated helper module

### [2026-03-10]
- refactor: extract validation logic into dedicated helper module

### [2026-04-06]
- perf: optimize memory allocation in buffer pool

### [2026-04-11]
- docs: clarify prerequisite installation steps in README

### [2026-04-13]
- test: verify backward compatibility with legacy message format

### [2026-04-23]
- test: add fuzzing harness for packet decoding routine

### [2026-05-21]
- security: enforce strict bounds checking on dynamic byte slices

### [2026-05-27]
- security: harden cryptographic salt generation against entropy dips

### [2026-06-07]
- fix: resolve race condition during concurrent worker initialization

### [2026-06-09]
- fix: handle malformed HTTP header parsing without crashing

### [2026-06-13]
- fix: prevent duplicate event emission during rapid retry bursts

### [2026-06-16]
- chore: update internal constants and clean up legacy comments

### [2026-06-16]
- refactor: extract validation logic into dedicated helper module

### [2026-06-18]
- refactor: simplify token parsing pipeline and reduce cognitive complexity

### [2026-07-06]
- refactor: use enum types for status codes instead of magic numbers

### [2026-07-22]
- refactor: use enum types for status codes instead of magic numbers

### [2026-07-26]
- style: format code according to style conventions

### [2026-08-09]
- fix: patch edge-case buffer truncation in stream reader

### [2026-08-13]
- test: add unit tests for boundary input cases and error branches


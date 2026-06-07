# Safety Rules

Hard rules:
1. Do not delete tests unless user explicitly requests it.
2. Do not edit generated code unless generation source is also updated and validated.
3. Do not delete migrations.
4. Do not change public API by default.
5. Do not change CLI flags, default values, or output format by default.
6. Do not change config key names, env vars, or config semantics by default.
7. Do not change database schema, wire protocol, serialization format, or OpenAPI/proto schemas by default.
8. Do not remove error codes or change externally visible errors by default.
9. Do not delete code with dynamic-reference risk.
10. Do not perform cross-module restructuring without explicit approval.
11. Do not hide behavior changes as cleanup.
12. Do not continue after validation failure.

Soft rules:
1. Prefer small patches.
2. Prefer deletion over abstraction.
3. Prefer local simplification over global redesign.
4. Prefer explicit risk reporting over guessing.
5. Prefer characterization tests before changing untested behavior.
6. Prefer preserving formatting unless file is already being edited.

# proofspec

Runtime **Proof** contract + JSON Schema for agent evidence.

## What / why
Agents claim things ("the endpoint works", "the button renders"). Tests passing is not Proof.
`proofspec` defines a small, machine-checkable artifact that ties a *claim* to *runtime evidence* captured against an exact `head_sha`.

## Proof types (OpenLane)
| type | evidence | required `artifact` keys |
|---|---|---|
| `raw_http` | real request/response against a running build | `method`, `url`, `status`, `response_excerpt` |
| `screenshot` | image of the rendered UI | `path`, `viewport` |
| `mp4` | screen recording of a flow | `path`, `duration_s` |
| `before_after_metric` | measured number before vs after | `metric`, `before`, `after`, `unit` |

## Layout
- `schema/proof-artifact.schema.json` – JSON Schema (draft 2020-12)
- `examples/` – valid samples
- `docs/contract.md` – the human contract

## Validate
```bash
pip install check-jsonschema
check-jsonschema --schemafile schema/proof-artifact.schema.json examples/*.json
```

## License
MIT

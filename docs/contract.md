# Proof contract

1. **Tests alone are not Proof.** Unit/CI green is necessary, not sufficient.
2. Proof is runtime evidence of the claim: a raw HTTP exchange, screenshot, MP4, or before/after metric.
3. Every artifact names the exact 40-char `head_sha` it was captured on. Evidence for an older SHA is stale and invalid.
4. One artifact = one claim. Keep claims specific and falsifiable.
5. Artifacts must validate against `schema/proof-artifact.schema.json`.
6. No secrets, tokens, or personal data in artifacts.

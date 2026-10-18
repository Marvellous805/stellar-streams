# SDK RPC response fixtures

The SDK fixtures are captured from a live Soroban RPC endpoint and replayed in
SDK tests. The covered read-only scenarios are `getHealth`, `getNetwork`, and
`getLatestLedger`; each JSON file preserves the JSON-RPC request and response
along with the recording time.

To refresh the fixtures from testnet:

```sh
pnpm --filter @stellar-starter-kit/sdk fixtures:record
```

Use `SOROBAN_RPC_URL` to capture from another Soroban endpoint. SDK tests run
`fixtures:check` before Vitest, so CI fails if a covered scenario fixture is
missing or malformed. Review fixture changes before committing because ledger
metadata can be large and changes over time.
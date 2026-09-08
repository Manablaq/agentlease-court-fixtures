# AgentLease Court public evidence fixtures

These immutable JSON records are public test fixtures for the standalone
AgentLease Court Intelligent Contract. The contract pins each URL to a
registered publisher authority and verifies the complete response-body hash,
record metadata, and canonical signed-payload hash before consensus review.

Use the raw URLs at a commit SHA, never a mutable branch URL. The detached
`signature` values are fixture artifacts for the contract's required
publisher-layer field; this repository does not claim that they are
cryptographic signatures.

## Fixture sets

- `857e2fa08a3ff4f18261369d927f9793d7bf8b04` contains the original long-window
  delivery, verification, and challenge records.
- `e892328943bbfb7cd43b1e0194cc237a4a7f2899` contains short-window records for
  the approved provider-payout lifecycle, ending at `1788854100`.
- `7330f6ce3c660a7cfda9cef5afc2350c1a742668` contains short-window records for
  the rejected client-refund lifecycle, ending at `1788855300`. Its records
  intentionally report `delivery_status: complete` and
  `verification_status: corroborated`; the test criterion requires the opposite
  statuses so validators can independently produce a rejected decision.

For the short-window runs, use the exact commit in the raw URL and the
corresponding body hash recorded in the main repository's Bradbury deployment
log. The validity windows are test controls enforced by the contract; they are
not a substitute for production publisher operations.

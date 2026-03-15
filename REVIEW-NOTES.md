# Review Notes Before Publishing

The source whitepaper is strong, but it contains a few details you should verify before publishing the docs publicly.

## Items to review

1. **RPC endpoint naming**
   - One section uses `https://testrpc.tetscan.com`
   - Another section uses `https://testrpc.testscan.com`

2. **Staking reward example mismatch**
   - The pool example lists `180 days = 50%`
   - The reward example later calculates the 180-day pool with `30%`

3. **Validator language**
   - The whitepaper describes PoA validators and also references staking-based validator/delegator incentives and slashing. You may want to make sure the validator model and the staking product are clearly separated in the public docs.

4. **SDK references**
   - `@Tetreum/sdk`, `Tetreum-python`, and `github.com/Tetreum/go-sdk` are listed as supported SDKs. Verify these exist publicly before launch.

5. **Team disclosure wording**
   - The intro says identities remain confidential during the early phase, but named team members are also listed later. You may want to align that messaging.

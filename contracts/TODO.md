# TODO

- [ ] Implement `execute_withdraw(env, caller, proposal_id)` in `contracts/contracts/proposals/src/lib.rs`
  - [ ] Verify caller is a treasury member (via treasury client)
  - [ ] Verify proposal status is `Approved` (and not Executed)
  - [ ] Verify treasury has sufficient balance
  - [ ] Call `TokenClient::transfer` (or treasury/withdraw path consistent with repo)
  - [ ] Deduct balance from `DataKey::Balances`
  - [ ] Set proposal status to `Executed`
  - [ ] Emit `WithdrawEvent` and `ProposalExecutedEvent`
- [ ] Add/extend treasury interface(s) in proposals contract to match the needed calls
- [ ] Add unit tests covering acceptance criteria:
  - [ ] Pending proposal panics with "proposal not approved"
  - [ ] Already executed proposal panics
  - [ ] Balance correctly reduced after execution
  - [ ] Non-member caller panics
- [ ] Run contract tests (`cargo test -p proposals` and any other affected crates)
- [ ] Create new git branch `blackboxai/...`, commit changes, and push to GitHub

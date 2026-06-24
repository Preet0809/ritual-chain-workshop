## Starter for Ritual workshop on 23th June 2026

/hardhat -> Where we'll write the smart contract

/web -> Where the frontend lives.
# Privacy-Preserving AI Bounty Judge

## Lifecycle

1. Bounty owner creates a bounty with a reward and rubric.
2. Participants submit commitments during the submission phase.
3. After the deadline, participants reveal their answers and salts.
4. The contract verifies that the reveal matches the original commitment.
5. Revealed answers are sent for AI judging.
6. The bounty owner finalizes the winner and releases the reward.

## Test Plan

* Submit a valid commitment and reveal.
* Attempt reveal with incorrect salt.
* Attempt reveal after judging.
* Judge all valid revealed answers.
* Finalize the winner and verify reward transfer.

## Architecture Note

The system uses a commit-reveal workflow to keep answers hidden during the submission phase. Commitments are stored on-chain, while plaintext answers are revealed only after the deadline. AI judging is performed after all valid reveals are collected.

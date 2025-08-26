### Getting Started

1. *Navigate to the Simulation Folder*
   - Go to the experiment/simulation/ directory in your project workspace.

2. *Open the Simulation*
   - Locate the index.html file inside the simulation folder.
   - Open index.html in your preferred web browser (e.g., Chrome, Firefox).
   - You can do this by double-clicking the file or right-clicking and selecting "Open With" > your browser.

### Understanding the Interface

The simulation interface consists of three main areas:

1. *Control Panel (Left)*: Contains all buttons and controls
2. *Experiment Area (Center)*: Visual representation of nodes and communication
3. *Transaction Log (Right)*: Real-time log of all protocol activities

### How to Use the Program

#### Basic Transaction Simulation

1. *Start New Transaction*
   - Click the *"Start New Transaction"* button to begin the simulation
   - This initializes a new two-phase commit protocol instance
   - The "Next Step" button becomes enabled

2. *Step Through the Protocol*
   - Click *"Next Step"* repeatedly to advance through each phase:
     - *Phase 1 (Voting Phase)*: 
       - Coordinator sends PREPARE messages to all participants
       - Each participant votes YES and enters PREPARED state
     - *Phase 2 (Decision Phase)*: 
       - Coordinator decides COMMIT based on unanimous YES votes
       - Coordinator sends COMMIT messages to all participants
       - Participants acknowledge and complete the transaction

3. *Reset Simulation*
   - Click *"Reset Simulation"* to return to the initial state
   - All nodes return to idle state and logs are cleared

#### Failure Simulation (Advanced)

4. *Simulate Participant Failure (Phase 1)*
   - Click this button during Phase 1 to simulate a random participant failing
   - Observe how the coordinator handles timeouts and decides to abort
   - Watch the protocol's response to unreachable participants

5. *Simulate Coordinator Failure (Phase 1)*
   - Click this button during Phase 1 to simulate coordinator failure
   - Participants enter "in-doubt" state (holding locks)
   - Demonstrates the blocking nature of 2PC

6. *Simulate Participant Failure (Phase 2)*
   - Click this button during Phase 2 to simulate participant failure during commit
   - Shows how participants can recover and complete delayed commits

7. *Simulate Coordinator Failure (Phase 2)*
   - Click this button during Phase 2 to simulate the most critical failure scenario
   - Some participants may commit while others remain blocked
   - Demonstrates potential consistency issues

8. *Simulate Recovery*
   - Click this button to recover failed nodes
   - Shows how the protocol handles recovery using transaction logs
   - Resolves in-doubt and blocked participants

### Understanding Visual Elements

- *Blue Circle (Center)*: Coordinator node
- *Smaller Blue Circles*: Participant nodes (P1, P2, P3, P4)
- *Animated Lines*: Communication channels between nodes
- *Message Bubbles*: Protocol messages (PREPARE, YES/NO, COMMIT, ABORT)
- *Node Colors*:
  - Blue: Normal/Ready state
  - Green: Voted YES or Committed
  - Orange: Voted NO
  - Red: Failed node
  - Blinking: In-doubt state
  - Gray: Aborted

### Observing Protocol Behavior

1. *Transaction Log (Right Panel)*
   - Monitor real-time protocol activities
   - Observe message exchanges and state changes
   - Track failure scenarios and recovery procedures

2. *Phase Indicator (Top-Right of Center)*
   - Shows current protocol phase
   - Updates as simulation progresses

3. *Connection Lines*
   - Solid lines: Normal communication
   - Broken/dashed lines: Failed communication
   - Animated lines: Active message transmission



### Troubleshooting

- If the simulation does not load, ensure your browser supports HTML5 and JavaScript
- Check that all files in the simulation folder are present and not corrupted
- For best experience, use a modern browser (Chrome, Firefox, Safari, Edge)

# Finite-State-Machine-ST-CODESYS

This project presents the design of a finite state machine (FSM) for controlling a conveyor system
integrated with a proximity sensor and a robotic arm. The system consists of four main stages,
where transitions depend on sensor inputs and timer events.

## Stages Details:
Stage 0: Initial State
- The system remains idle.
- Transition Condition: When Start = 1, the system moves to Stage 1.
Stage 1: Conveyor Running
- Conveyor starts moving (Conveyor = 1).
- No specific condition required to stay in this stage.
- Transition Condition: Proximity Sensor detects a box (Proximity = 1) => Move to Stage 2.
Stage 2: Box Detected
- Conveyor stops moving (Conveyor = 0).
- A timer is activated once the box is detected.
- Transition Condition: When the Timer Elapses, move to Stage 3.
Stage 3: Robot Picking
- The robot checks if it is busy.
- If RobotBusy = 0, the robot picks the box.
- After the robot finishes, the system returns to Stage 0, ready for the next box.

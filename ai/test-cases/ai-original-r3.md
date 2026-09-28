# Original AI Output — Senko Standing Fan Test Cases

This file preserves the unchanged 15-case AI baseline generated for
`PROMPT-08`. All Actual Result values were `Not Executed` and all Verdict
values were `NOT EXECUTED` in the original batch.

## TC-01 — Start at speed 1

- Objective: Verify normal start at the lowest speed.
- Preconditions: Fan is assembled, upright on a dry level floor, oscillation off, and connected to a normal outlet.
- Input: Speed button 1.
- Steps: (1) Stand clear of the grille. (2) Press speed button 1. (3) Observe blade rotation, airflow, noise and base movement for 15 seconds.
- Expected Result: The fan starts promptly at low speed, produces steady airflow and has no scraping sound, excessive vibration or base movement.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-02 — Differentiate three speed levels

- Objective: Verify that the three speed buttons produce distinguishable airflow levels.
- Preconditions: Fan is upright, oscillation off, with a light paper strip positioned at a fixed safe distance in front of the grille.
- Input: Speed buttons 1, 2 and 3.
- Steps: (1) Run speed 1 for 10 seconds and observe the paper strip. (2) Repeat at speed 2. (3) Repeat at speed 3 without changing the strip position.
- Expected Result: Each button produces a stable operating level, and the observed airflow increases from level 1 to level 2 to level 3.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-03 — Direct start at speed 3

- Objective: Verify startup when the highest-speed button is selected directly from the stopped state.
- Preconditions: Fan is stopped, upright, oscillation off and connected to power.
- Input: Speed button 3.
- Steps: (1) Confirm the blades are stopped. (2) Press speed button 3 directly. (3) Observe startup and operation for 15 seconds.
- Expected Result: The fan starts promptly at the highest level and runs steadily without delayed startup, abnormal jerk, scraping or excessive vibration.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-04 — Stop using the OFF button

- Objective: Verify that the OFF button stops normal operation.
- Preconditions: Fan is running at speed 2 with oscillation off.
- Input: OFF button.
- Steps: (1) Press the OFF button. (2) Observe the blades until they stop. (3) Wait 10 seconds for unintended restart.
- Expected Result: Power to the motor is removed, the blades coast to a complete stop and the fan does not restart by itself.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-05 — Speed button interlock

- Objective: Verify that selecting a new speed replaces the previous selection.
- Preconditions: Fan is upright, oscillation off and initially stopped.
- Input: Button sequence 1, 3, 2.
- Steps: (1) Press speed 1 and observe for 5 seconds. (2) Press speed 3 and observe the buttons and airflow. (3) Press speed 2 and observe again.
- Expected Result: Only the most recently selected speed remains active, the earlier speed button releases, and the fan changes level without stopping unexpectedly.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-06 — Enable horizontal oscillation

- Objective: Verify that the oscillation control starts horizontal head movement.
- Preconditions: Fan is running at speed 1, positioned with clear space around the head.
- Input: Oscillation control ON.
- Steps: (1) Activate the oscillation control. (2) Observe one complete left-to-right-to-left cycle. (3) Listen for abnormal mechanical noise.
- Expected Result: The head sweeps smoothly through its normal horizontal range, reverses direction without sticking and produces no abnormal clicking or grinding.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-07 — Disable horizontal oscillation

- Objective: Verify that the oscillation control stops horizontal head movement.
- Preconditions: Fan is running at speed 1 and oscillating normally.
- Input: Oscillation control OFF.
- Steps: (1) Deactivate the oscillation control. (2) Observe the head for 15 seconds. (3) Confirm the fan continues producing airflow.
- Expected Result: Horizontal sweeping stops and the head remains facing one direction while blade rotation and airflow continue normally.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-08 — Change speed during oscillation

- Objective: Verify that speed selection works without interrupting active oscillation.
- Preconditions: Fan is oscillating normally at speed 1 with clear surrounding space.
- Input: Button sequence 1, 2, 3 while oscillating.
- Steps: (1) Observe oscillation at speed 1. (2) Press speed 2 and observe. (3) Press speed 3 and observe one further sweep.
- Expected Result: Airflow changes at each selection while oscillation continues smoothly without stopping, sticking or changing its normal sweep range.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-09 — Adjust and retain vertical tilt

- Objective: Verify that supported vertical tilt positions can be set and retained during operation.
- Preconditions: Fan is stopped and unplugged before the head is adjusted.
- Input: Lowest, center and highest supported tilt positions.
- Steps: (1) Unplug the fan. (2) Set each supported tilt position and check that it holds. (3) Return to the center position. (4) Reconnect power and run at speed 1 for 15 seconds.
- Expected Result: The head moves only within its designed tilt range, holds each selected position and does not drop or drift during operation.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-10 — Base stability at speed 3

- Objective: Verify stability at the highest speed with oscillation disabled.
- Preconditions: Fan is upright on a dry, hard and level floor; oscillation is off.
- Input: Speed button 3.
- Steps: (1) Mark the initial base position without attaching anything to the fan. (2) Run speed 3 for 30 seconds. (3) Observe the base and fan body from a safe distance.
- Expected Result: The base stays in its initial position and the fan does not walk, rock, tilt or approach an unstable condition.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-11 — Stability while oscillating at speed 3

- Objective: Verify stability under combined maximum airflow and oscillating movement.
- Preconditions: Fan is upright on a dry, hard and level floor with clear space around the head.
- Input: Speed 3 and oscillation ON.
- Steps: (1) Select speed 3. (2) Activate oscillation. (3) Observe one complete oscillation cycle and the base position.
- Expected Result: The fan completes the sweep without walking, rocking, tipping, cable pulling or excessive structural vibration.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-12 — Operating noise and vibration

- Objective: Check for abnormal sound or vibration across normal operating states.
- Preconditions: Fan is on a stable level floor with oscillation initially off.
- Input: Speed 1, speed 3, then speed 3 with oscillation.
- Steps: (1) Listen and observe at speed 1 for 15 seconds. (2) Repeat at speed 3. (3) Enable oscillation and observe one complete sweep.
- Expected Result: The fan has no scraping, grinding, repeated clicking, grille contact or excessive vibration in any tested state.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-13 — Reconnect power from OFF state

- Objective: Verify that reconnecting power does not cause unintended startup when OFF is selected.
- Preconditions: OFF button is selected; blades are fully stopped; tester's hands and plug area are dry.
- Input: Normal unplug, 10-second wait and reconnect.
- Steps: (1) Confirm OFF is selected. (2) Unplug by holding the plug, not the cord. (3) Wait 10 seconds. (4) Reconnect to the same normal outlet. (5) Observe for 10 seconds without pressing a speed button.
- Expected Result: The fan remains stopped after reconnection and shows no spark, burning smell or unexpected motor movement.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-14 — Continuous 30-minute operation

- Objective: Verify stable operation during a normal extended-use period.
- Preconditions: Fan is clean, unobstructed, upright and has clear ventilation around the motor housing.
- Input: Speed 2 with oscillation ON for 30 minutes.
- Steps: (1) Start speed 2 and enable oscillation. (2) Observe at the start, 15-minute point and 30-minute point. (3) Stop immediately if smoke, sparking or burning smell occurs.
- Expected Result: The fan operates continuously for 30 minutes without stopping, speed fluctuation, burning smell, smoke, sparking or new abnormal noise.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

## TC-15 — Repeat normal control cycle

- Objective: Verify consistent response across repeated normal button operations.
- Preconditions: Fan is upright, oscillation off and initially stopped.
- Input: Sequence OFF, 1, 2, 3, OFF repeated five times.
- Steps: (1) Press 1, 2, 3 and OFF with at least 3 seconds between presses. (2) Repeat the sequence five times. (3) Observe button release, motor response and abnormal noise during every cycle.
- Expected Result: Every cycle produces the selected operating state, each previous speed button releases, OFF stops the motor, and no button sticks or response is missed.
- Actual Result: Not Executed.
- Verdict: NOT EXECUTED.

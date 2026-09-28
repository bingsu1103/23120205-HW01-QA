# Physical Appliance Defects

Repository: https://github.com/bingsu1103/23120205-HW01-QA

Issues list: https://github.com/bingsu1103/23120205-HW01-QA/issues

| Defect ID | Related Test Case | GitHub Issue URL | Status |
|---|---|---|---|
| PDEF-01 | TC-12 | https://github.com/bingsu1103/23120205-HW01-QA/issues/1 | CREATED — VERIFIED |
| PDEF-02 | TC-05 | https://github.com/bingsu1103/23120205-HW01-QA/issues/2 | CREATED — VERIFIED |
| PDEF-03 | TC-06 | https://github.com/bingsu1103/23120205-HW01-QA/issues/3 | CREATED — VERIFIED |
| PDEF-04 | TC-09 | https://github.com/bingsu1103/23120205-HW01-QA/issues/4 | CREATED — VERIFIED |
| PDEF-05 | TC-11 | https://github.com/bingsu1103/23120205-HW01-QA/issues/5 | CREATED — VERIFIED |
| PDEF-06 | TC-07 | https://github.com/bingsu1103/23120205-HW01-QA/issues/6 | CREATED — VERIFIED |
| PDEF-07 | TC-15 | https://github.com/bingsu1103/23120205-HW01-QA/issues/7 | CREATED — VERIFIED |

The five submission videos document PASS cases (`TC-01`, `TC-02`, `TC-04`,
`TC-08` and `TC-10`). They are not evidence for the five defects below. The five
GitHub Issues and the Issues-list screenshot were verified on 28 September 2026.
The screenshot is stored at
`private-evidence/github/git-issue-evidence.jpg`; it shows the repository,
username `bingsu1103` and all seven issue titles, including the later TC-07 and
TC-15 findings.

## PDEF-01

**GitHub title:** `[PDEF-01][TC-12] Abnormal metal grille rattling at speed 3 — Lồng kim loại rung và kêu rè ở mức 3`

### Environment

- Device: Senko standing fan
- Model: B113
- Year: 2021
- Serial: Not found on the device
- Surface: Stable level floor

### Preconditions

The fan is assembled, upright, with the grille correctly installed and oscillation disabled.

### Steps to reproduce

1. Place the fan on a stable, level surface.
2. Select speed 3.
3. Observe the grille vibration and operating noise.

### Expected result

The fan produces normal airflow noise without continuous metallic rattling or heavy grille vibration.

### Actual result

The outer metal grille vibrates heavily against the plastic retaining ring and produces a continuous loud rattling noise ("rè rè").

### Severity

**Medium.** The fan remains operable, but the continuous vibration and noise degrade normal use and may indicate a loose grille connection.

## PDEF-02

**GitHub title:** `[PDEF-02][TC-05] Sluggish speed-button interlock release — Nút tốc độ nhả chậm khi chuyển nấc`

### Environment

- Device: Senko standing fan
- Model: B113
- Year: 2021
- Serial: Not found on the device

### Preconditions

The fan is upright and operating with speed button 1 engaged.

### Steps to reproduce

1. Press speed button 1.
2. Press speed button 2 while button 1 is active.
3. Observe the release movement of button 1.

### Expected result

Button 1 releases immediately when button 2 is engaged, leaving only the newly selected speed button active.

### Actual result

Button 1 remains partially depressed for approximately 1–2 seconds before returning to its released position.

### Severity

**Low-Medium.** Operation continues, but the delayed mechanical interlock can confuse the selected state and may worsen with repeated use.

## PDEF-03

**GitHub title:** `[PDEF-03][TC-06] Clicking and stutter at oscillation reversal — Tuốc năng khựng và kêu cạch khi đảo chiều`

### Environment

- Device: Senko standing fan
- Model: B113
- Year: 2021
- Serial: Not found on the device
- Speed: 1
- Oscillation: ON

### Preconditions

The fan is upright with clear space around the head and oscillates at speed 1.

### Steps to reproduce

1. Select speed 1.
2. Enable horizontal oscillation.
3. Observe at least one complete left-to-right-to-left sweep.

### Expected result

The head reverses direction smoothly at both boundaries without a sharp click, stutter or visible jerk.

### Actual result

The head stutters slightly and produces a sharp mechanical click at both the leftmost and rightmost reversal points.

### Severity

**Medium.** The defect is repeatedly observable and may indicate wear or misalignment in the oscillation mechanism.

## PDEF-04

**GitHub title:** `[PDEF-04][TC-09] Vertical tilt drifts downward during operation — Góc nghiêng tự trôi xuống khi quạt chạy`

### Environment

- Device: Senko standing fan
- Model: B113
- Year: 2021
- Serial: Not found on the device
- Speed: 3
- Initial tilt: Maximum upward position

### Preconditions

The head is adjusted while the fan is unplugged, then power is reconnected for the operating observation.

### Steps to reproduce

1. Unplug the fan.
2. Set the head to its maximum supported upward tilt position.
3. Reconnect power and select speed 3.
4. Observe the tilt position for 3 minutes.

### Expected result

The selected vertical tilt position remains unchanged throughout operation.

### Actual result

After approximately 3 minutes, motor vibration causes the head to move downward by one tilt position.

### Severity

**Medium.** The fan continues operating, but it cannot retain the airflow direction selected by the user.

## PDEF-05

**GitHub title:** `[PDEF-05][TC-11] Base shifts during maximum oscillation — Chân đế xê dịch khi mức 3 kết hợp đảo gió`

### Environment

- Device: Senko standing fan
- Model: B113
- Year: 2021
- Serial: Not found on the device
- Surface: Smooth, dry tile floor
- Speed: 3
- Oscillation: ON

### Preconditions

The fan is upright on a dry, level tile floor with its starting position visibly marked and the power cord free from tension.

### Steps to reproduce

1. Mark the initial base position without attaching anything to the fan.
2. Select speed 3 and enable oscillation.
3. Operate for 2 minutes while observing from a safe distance.
4. Measure the displacement from the starting mark.

### Expected result

The base remains stationary throughout operation.

### Actual result

The base moves approximately 1.5 cm from its marked starting position within 2 minutes.

### Severity

**High.** Movement of the base is a stability concern and can increase the risk of the fan approaching an unsafe position or placing tension on its power cord.

## PDEF-06

**GitHub title:** `[PDEF-06][TC-07] Abnormal jamming sound during oscillation obstruction — Âm thanh kẹt bất thường khi cản chuyển động đảo gió`

### Environment

- Device: Senko standing fan
- Model: B113
- Year: 2021
- Serial: Not found on the device
- Oscillation: ON

### Preconditions

The fan is oscillating with a controlled obstruction in its sweep path. The
test must follow the approved safety method and must not involve unprotected
hand contact with the powered fan head.

### Steps to reproduce

1. Enable horizontal oscillation using the approved guarded method.
2. Apply the controlled obstruction to the sweep path.
3. Observe the sound and movement while obstructed.
4. Remove the obstruction and observe whether normal oscillation resumes.

### Expected result

The device avoids hazardous force, overheating and permanent mechanical
damage, then returns to normal oscillation after the obstruction is removed.

### Actual result

An abnormal jammed mechanical sound occurs while the movement is obstructed.
Normal operation resumes after the obstruction is removed.

### Severity

**Pending triage.** The abnormal sound is repeatable evidence of mechanical
stress, but severity cannot be finalized until the student confirms whether
there was heat, visible damage, persistent noise or reduced oscillation after
the obstruction was removed.

## PDEF-07

**GitHub title:** `[PDEF-07][TC-15] Clicking, temporary stop and shifted sweep after counter-rotation — Kêu tạch tạch, dừng và lệch biên độ sau khi ép quay ngược`

### Environment

- Device: Senko standing fan
- Model: B113
- Year: 2021
- Serial: Not found on the device
- Oscillation: ON

### Preconditions

The fan is oscillating using the approved guarded, torque-limited test method.
Direct unprotected hand contact with the powered fan head is not permitted.

### Steps to reproduce

1. Enable horizontal oscillation.
2. Apply controlled counter-force opposite to the current sweep direction.
3. Observe sound and head movement while the force is applied.
4. Release the force and compare the resumed sweep with its initial range.

### Expected result

The mechanism avoids hazardous force and permanent damage, then resumes its
previous oscillation range without abnormal clicking after force removal.

### Actual result

The fan produces repeated clicking sounds and stops while counter-force is
applied. It resumes after release, but its oscillation sweep range shifts from
the previous position.

### Severity

**Medium.** The fan resumes operation, but the altered sweep range and repeated
clicking indicate mechanical stress or displacement in the oscillation drive.

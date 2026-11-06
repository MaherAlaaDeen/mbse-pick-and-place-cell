# 07 Decisions, assumptions and limits

## Decision log

| Decision | Reason |
|---|---|
| Fenced cell, not collaborative | Keeps the safety case within ISO 10218 and guarded-machine rules; collaborative operation adds force and speed limits outside this project |
| Source, verification method and risk stored in the requirement (ExtendedRequirement) | The profile route was not available in the tool; the built-in fields keep the information next to the text |
| No Status field | Not needed for a single-author model, and it adds upkeep |
| REQ-INT-002 changed from 200 ms to 300 ms (A) | D11a showed the 2.65 s cycle absorbs the latency, so the original limit was stricter than the system needs and had no basis |
| One "shall" per requirement | One pass or fail result per requirement |
| Separate control and safety chains | Independence is required by REQ-SAF-010 and follows ISO 13849-1 |
| Requirement diagrams with palette tools to create relations | The matrix cells could not be edited in the tool |
| Analyses limited to four | Each one checks a requirement with a number |

## Assumptions register

| Value | Status | How to confirm |
|---|---|---|
| Classification rate 98 % | Assumed | Vision supplier data |
| False-pass rate 0.5 % | Assumed | Vision validation test |
| Cycle-time share 95 % | Assumed | Production data |
| Availability 95 % | Assumed | Operating data |
| Communication cycle 10 ms | Assumed | Controller specification |
| Vision latency limit 300 ms | Assumed | Cycle budget (page 05) |
| Pad replacement 15 min | Assumed | Maintenance trial |
| Manual speed limit 250 mm/s | TBC | ISO 10218 clause |
| Door interlock response 0.02 s | TBC | Component datasheet |
| Light curtain response | TBC | Component datasheet |
| Approach speed K = 1600 mm/s | TBC | ISO 13855 |
| Detection capability 30 mm | Assumed | Light curtain datasheet |
| Installed distance 800 mm | Assumed | Cell layout |
| Payload limit ratio 0.5 | Assumed | Robot manufacturer guidance |
| Timing values for capture, classification, pick, move, place, settle | Assumed | Robot and vision trials |
| Safety controller reaction 0.03 s, robot stopping time 0.25 s | Assumed | Datasheets and a stopping test |

## Limitations

- The constants in the safety-distance formula are TBC, and only the light curtain is analysed.
- Standard editions are unchecked, except ISO 10218 (2025) and EU 2023/1230, and the Source properties hold no clause numbers.
- The payload check is a simplified ratio, not a joint-torque analysis.
- Timing and mass values are assumptions, not measurements from a real cell.
- The model has not been reviewed by a safety expert.

## Next steps

1. Read the relevant standard clauses and add clause numbers.
2. Replace the TBC values with values from the standards and datasheets.
3. Analyse the door interlock in the safety distance check.
4. Replace the payload ratio with a joint-torque model.
5. Add a simulation or control prototype and compare its timing to the model.

# Standards register

This page lists every standard and regulation referenced in the model, why it was chosen, and where it shows up. Standards are cited by number and edition only; no text from them is reproduced.

**Status of this register.** Each standard was chosen for its scope, which I know from its title and purpose. I have not yet read the clauses, so the `Source` property of each requirement names the standard but holds no clause number. Editions marked "check" have to be confirmed against the current edition before the model is used for a real design.

## Regulation and modelling language

| Reference | What it covers | Why it was chosen | Where it shows up | Edition |
|---|---|---|---|---|
| EU Machinery Regulation 2023/1230 | Legal safety requirements for machinery placed on the EU market; replaces Directive 2006/42/EC from January 2027 | A robot cell sold or operated in the EU has to meet it, and it is the legal reason the safety standards below matter | Safety requirements (SAF), scope in D01 | 2023/1230 |
| OMG SysML 1.x | Modelling language for systems | Standard language for MBSE; supported by Cameo Systems Modeler | All diagrams | 1.x as in Cameo |

## Safety of machinery and robots

| Standard | What it covers | Why it was chosen | Where it shows up | Edition |
|---|---|---|---|---|
| ISO 12100 | General principles for risk assessment and risk reduction | It is the base method for finding hazards; the three own requirements (no restart after power restoration, energy isolation for maintenance, no robot entry during bin exchange) came from applying its hazard thinking | REQ-SAF-011, 012, 013; D02 | Check |
| ISO 10218-1 | Safety requirements for the industrial robot itself | The cell uses an industrial robot arm, and this part sets what the robot must provide (stops, speed limits, modes) | SAF and FUN requirements; D08 operating modes | 2025 |
| ISO 10218-2 | Safety requirements for robot systems, cells and integration | The project is a cell, so integration requirements (guarding, layout, mode selection) apply here | SAF requirements; D04, D06 | 2025 |
| ISO 13849-1 | Safety-related parts of control systems; performance levels and categories | The safety chain has to be independent of the control chain and reach a defined performance level; this standard gives that vocabulary | REQ-SAF-010; D06, D06b | Check |
| IEC 62061 | Functional safety of safety-related control systems; SIL | Alternative route to ISO 13849-1 for the same safety functions; named so a reviewer sees both were considered | SAF requirements (Source) | Check |
| ISO 13850 | Emergency stop function | The cell has an E-Stop, and this standard defines how it must work | E-Stop in D04 and D06; D08 | Check |
| IEC 60204-1 | Electrical equipment of machines | Covers stop categories, power isolation and restart behaviour, which drive the energy-isolation and no-restart requirements | REQ-SAF-011, 012; D08 | Check |
| ISO 14119 | Interlocking devices associated with guards | The fence door has an interlock, and this standard sets how it must be chosen and protected against defeat | Door Interlock in D04, D06, D09 | Check |
| IEC 61496 | Electro-sensitive protective equipment (light curtains) | The bin-exchange opening is protected by a light curtain, and this is the product standard for it | Light curtain in D04, D06, D11b | Check |
| ISO 13855 | Positioning of safeguards based on approach speeds of body parts | It gives the safety-distance formula S = K x T + C used in D11b; constants K and C are TBC | REQ-SAF-007; D11b | Check |
| ISO 13857 | Safety distances against reaching hazard zones | Sets fence height and opening sizes, which the cell layout depends on | SAF requirements (Source) | Check |

## Performance, controls, security and environment

| Standard | What it covers | Why it was chosen | Where it shows up | Edition |
|---|---|---|---|---|
| ISO 9283 | Performance criteria and test methods for manipulating industrial robots | Gives measurable definitions for robot accuracy and repeatability, so performance requirements can be verified | PER requirements | Check |
| IEC 61131-3 | Programming languages for programmable controllers | The cell controller is a PLC, and this standard names the languages it is programmed in | CellController, PLC Controller in D04 | Check |
| IEC 62443 | Security for industrial automation and control systems | The cell connects to a plant network, so remote access and configuration need a security basis | REQ-CYB-001; D05 configuration interface | Check |
| IEC 61000-6-2 | EMC immunity for industrial environments | The cell works near drives and switching equipment and must keep working | ENV requirements | Check |
| IEC 61000-6-4 | EMC emission for industrial environments | The cell must not disturb other plant equipment | ENV requirements | Check |

## Next steps

1. Read the relevant clauses of each standard and add clause numbers to the `Source` property.
2. Confirm every "Check" edition against the current one.
3. Replace the TBC constants K and C in D11b with the values from ISO 13855.

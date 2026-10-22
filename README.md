# OT Security Risk Assessment – IEC 62443-3-2 (fictional machine)

> **Portfolio work sample.** The machine "WDL-8", its architecture and all risk values are invented for demonstration. This repository does not describe or assess any real product, customer or company.

## Goal

Show how a structured risk analysis from automotive security (TARA according to ISO/SAE 21434) transfers to industrial automation, using the zone-and-conduit process of **IEC 62443-3-2** on a connected special machine: a fictional multi-wire drawing line, seen from the machine builder's perspective.

## What the assessment contains

| Step | Content |
|---|---|
| ZCR 1 | System under consideration: PLC, drives, safety PLC, HMI, remote-access gateway, OPC UA interface to MES |
| ZCR 2 / 4 | Initial risk assessment against a tolerable risk of R ≤ 6 (likelihood × impact, 1–5 each) |
| ZCR 3 | Four zones (DMZ, HMI, machine control, safety) and six conduits, with target security levels (SL-T 2–3) |
| ZCR 5 | Detailed assessment of 10 threat scenarios, countermeasures mapped to the 7 foundational requirements, residual risk |
| ZCR 6 | 14 derived requirements mapped to IEC 62443-3-3 system requirements (SR) |
| Operation | SBOM-based vulnerability and patch management with VEX and patch windows aligned to production |
| ZCR 7 | Residual risk acceptance by the asset owner |

## Key results

- 9 of 10 threats reduced to tolerable risk; the remaining one (vulnerabilities in third-party components) is handled by an ongoing SBOM/CVE/VEX process and needs asset-owner acceptance.
- The safety system is kept in its own zone with no write path from the network, so security failures cannot disable safety functions.
- Remote service access is **on demand only**, approved at the machine via key switch, with MFA and session logging.

## Files

- `OT_Risk_Assessment_IEC62443-3-2_WDL-8.pdf`: the full assessment (4 pages, version 1.1)
- `OT_Risk_Assessment_IEC62443-3-2_WDL-8.docx`: editable Word version
- `zones.png`: zone and conduit diagram

## Related work

- [Vuln-handling-demo](https://github.com/Sreejapillarisetty11/Vuln-handling-demo): hands-on SBOM → CVE scan → triage → VEX workflow, plus a CRA & IEC 62443 gap analysis

## Limitations

Fictional system and qualitative ratings. A real assessment needs the operator's network data, an agreed risk matrix and component-level checks against IEC 62443-4-2.

---
Author: Sreeja Pillarisetty · October 2026

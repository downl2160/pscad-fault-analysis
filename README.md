# PSCAD Fault Analysis

Simulation of a single-phase line-to-ground fault scenario with overcurrent relay protection (IEEE 50) in PSCAD Free Edition v5. This project replicates a simple protection system and highlights both functionality and limitations faced while using PSCAD Free for educational/proof-of-concept purposes.

---

## ⚙️ Overview

This project models:

* A single-phase power system with a 230 V, 50 Hz AC source
* A line simulated using lumped R, L, and split capacitors (manual Pi-section)
* An overcurrent relay (type 50) with a pickup of 15 A and delay of 0.05 s
* A transistor used as a logic-controlled breaker (due to Free Edition limitations)
* A load (5.3 Ω) connected beyond the fault point
* A fixed line-to-ground fault, hard-connected without switching

---

## 📂 File Structure

```
pscad-fault-analysis/
├── README.md                  # This file
├── waveforms.csv              # Simulated or placeholder waveform data
├── project/
│   └── project_report.pdf     # Detailed simulation summary & limitations
```

---

## ⚡ Simulation Summary

* Fault is active from t = 0 s (uncontrollable in Free Edition)
* Relay detects overcurrent (>15 A)
* After a delay of 0.05 s, the relay sends a signal to the transistor
* Transistor opens the circuit, isolating the load

---

## 🔍 PSCAD Free Edition Limitations

This project was built under significant limitations of PSCAD Free v5:

| Feature                   | Status in Free Version |
| ------------------------- | ---------------------- |
| Graph plotting            | ❌ Not available        |
| Step/Logic blocks         | ❌ Not available        |
| Logic-controlled breakers | ❌ Not available        |
| Fault control timing      | ❌ Not possible         |
| Waveform export (CSV)     | ✅ Available            |
| Relay blocks (IEEE 50)    | ✅ Available            |

As a workaround:

* The fault is **always on** (connected directly to ground)
* A **Constant block** was temporarily used to simulate logic, but ultimately removed
* A **Transistor** was used in place of a logic-controlled breaker

Despite these constraints, core protection logic is successfully demonstrated.

---

## 📈 Waveforms

See `waveforms.csv` for exported data:

* `Ia_1`: Line current
* `Relay_output`: Relay trip status
* `Switch_status`: Breaker control status

These can be plotted in Python, Excel, or MATLAB.

---

## 📌 How to Run (Optional)

If re-using the simulation:

1. Open project in PSCAD Free Edition v5
2. Compile (Build)
3. Run (Play button)
4. Export data manually from Output Channels

---

## 📄 License

MIT License — for academic use.

---

## 📌 Author Notes

This simulation was completed under time constraints. 

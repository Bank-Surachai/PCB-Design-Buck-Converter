PCB Buck Converter:                               
This circuit implements a step-down (Buck) DC–DC converter using the LM2596S-ADJ, producing a regulated lower output voltage from a higher DC input source. The design follows the standard application recommended in the LM2596 datasheet, including input filtering, switching control, energy storage, feedback regulation, and output filtering.

⚡1. Input Stage (J1, J2, C1, C2)

J1 / J2: Power input connectors

C1 (100uF): Bulk electrolytic capacitor that stabilizes input voltage and reduces large ripple

C2 (100nF): High-frequency bypass capacitor that filters switching noise

Together, these capacitors ensure a clean and stable input for the regulator.

❤️ 2. LM2596S-ADJ Switching Regulator (U1)

The LM2596 operates as a buck converter via high-frequency switching.
Key pins in use:

VIN (Pin 1): Receives the stabilized input voltage

GND (Pin 3): System ground

OUT (Pin 2): Switch output driving the inductor

FB (Pin 4): Feedback pin for output voltage regulation

ON/OFF (Pin 5): Connected to input so the regulator is always enabled

The internal switch rapidly toggles on/off, feeding energy into the inductor.

🧲 3. Output Energy Storage (L1, D1, C3)

L1 (470µH): Stores energy during the switching cycle and smooths current to the load

D1 (1N5822): Schottky diode providing a low-loss current path during switch-off

C3 (220uF): Output capacitor that stabilizes output voltage and reduces ripple

🎛️ 4. Feedback & Output Voltage Setting (R1, R2, C4)

The LM2596-ADJ uses a voltage divider between output and GND to set the output voltage:

R1 (330Ω): Lower feedback resistor

R2 (103 = 10kΩ): Upper resistor

C4 (100nF): Filter capacitor reducing noise at the feedback pin

This ensures stable regulation and prevents oscillations.

🔌 5. Output Connectors (J3, J4)

Provide the final regulated DC voltage to the load

Connected after filtering elements for maximum stability

This is my circuit schematic:

<img width="1542" height="633" alt="Screenshot 2025-11-14 112037" src="https://github.com/user-attachments/assets/8b158561-fe50-4356-a6e2-1f3a774a9d0f" />

This is 3D of my PCB:
<img width="1264" height="829" alt="Screenshot 2025-11-14 111901" src="https://github.com/user-attachments/assets/60d3b0cb-72de-4634-a318-ce220fad6b6c" />

This is real PCB:
![Mypcb](https://github.com/user-attachments/assets/bea26613-01a2-4a98-82ed-826a8f677336)

CNC Programming & G-Code Writing  
BRI302 – Manufacturing Technology for Robotics
---

## Academic Training

Completed CNC machining module as part of:

- **Course:** BRI302 – Manufacturing Technology for Robotics  
- **Software Used:** FANUC CNC Simulator  
- **Machine Type:** CNC Milling  
- **Programming Standard:** ISO G-Code  

---

##  Technical Competencies

- Absolute & Incremental Positioning (G90 / G91)
- Linear Interpolation (G01)
- Circular Interpolation (G02 / G03)
- Tool Selection & Spindle Control (T, M03, M05)
- Feed Rate & Depth Control
- Workpiece Zero Referencing
- 2.5D Contour Machining
- Toolpath Simulation & Verification

---

## 🔍 Machining Strategy Understanding

- Step-down depth planning
- Feed rate optimization
- Coordinate referencing
- Material removal sequencing
- Program debugging & error correction

---

## 🖥 Simulation & Toolpath Verification

<p align="center">
  <img src="./images/cnc-simulation.jpg" width="600">
</p>

Simulated contour milling program in FANUC environment to validate:

- Toolpath accuracy  
- Depth consistency  
- Machining sequence  
- Collision avoidance  

---

##  Sample CNC Milling Programs
###  Contour Pocket Milling Example (2.5D Profile)

```gcode
%
O1001 (RECTANGULAR POCKET MILLING)
G21 (METRIC UNITS)
G17 (XY PLANE SELECTION)
G90 (ABSOLUTE PROGRAMMING)

T1 M06 (TOOL CHANGE - END MILL)
M03 S1200 (SPINDLE ON CLOCKWISE)
G00 X0 Y0 (RAPID TO START POSITION)
G00 Z5 (SAFE HEIGHT)

G01 Z-2 F100 (STEP DOWN)
G01 X50 Y0 F200
G01 X50 Y30
G01 X0 Y30
G01 X0 Y0

G00 Z5
G01 Z-4 F100 (SECOND PASS)
G01 X50 Y0 F200
G01 X50 Y30
G01 X0 Y30
G01 X0 Y0

G00 Z10
M05 (SPINDLE STOP)
M30 (END PROGRAM)

%
```

### Circular Interpolation Example

```gcode
%
O1002 (CIRCULAR POCKET)
G21
G17
G90

T1 M06
M03 S1000
G00 X25 Y25
G00 Z5

G01 Z-3 F100
G02 X25 Y25 I10 J0 F200

G00 Z10
M05
M30
%
```

### Multi-Step Contour Machining

```gcode
%
O1003 (STEP CONTOUR MACHINING)
G21
G17
G90
G40 G49 G80

T1 M06
M03 S1500
G54
G00 X10 Y10
G00 Z5

G01 Z-1 F120
G01 X80 Y10 F250
G01 X80 Y60
G01 X10 Y60
G01 X10 Y10

G00 Z5

G01 Z-2 F100
G01 X80 Y10 F200
G01 X80 Y60
G01 X10 Y60
G01 X10 Y10

G00 Z20
M05
M30
%
```




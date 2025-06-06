# Defend the Data Bridge

**Defend the Data Bridge** is a challenge focused on secure, synchronized data transmission in a simulated network environment. The objective is to guide a group of data packets across a multi-lane "data bridge" while avoiding vulnerabilities and ensuring a minimum number of packets successfully reach the other side within a limited number of turns.

## 🧩 Challenge Overview

You control a group of data packets, each starting at a specific location on a bridge composed of several parallel lanes. Each turn, a single global instruction is issued and applied simultaneously to all remaining packets. The system simulates a real-time control scenario where precision and strategic planning are critical.

## 🎯 Objectives

- Safely transmit a minimum required number of packets across the bridge.
- Avoid all known vulnerabilities in the network (represented as hazards on the grid).
- Complete the transmission in **50 turns or fewer**.
- Utilize only the allowed set of synchronized commands (`INC`, `DEC`, `WAIT`, `SHIFT`, `UP`, `DOWN`).

## 🚦 Movement Rules

- Packets move horizontally based on their current transmission rate.
- Vertical movement (lane changes) is subject to boundary constraints.
- Any packet passing through a vulnerability without using `SHIFT` is permanently lost.
- All commands apply to all packets simultaneously.

## 💥 Vulnerabilities

- Represented as obstacles on the grid.
- A packet is lost if it crosses a vulnerable cell without shifting.
- Vertical movements must also account for vulnerabilities in both source and destination lanes.

## ✅ Mission Success Criteria

- A scenario is successful if the minimum number of packets reaches the end of the bridge within 50 steps.
- Failure occurs if:
  - Not enough packets survive.
  - The 50-step limit is exceeded.

## 📥 Input Format

- Initial packet count, starting transmission rate, minimum required survivors, number of lanes.
- Starting coordinates of each packet.
- Grid layout for each lane, where:
  - `.` represents a safe position,
  - `0` represents a vulnerability.

## 📤 Output Format

- One command per line, representing the action for that turn.
- Commands must come from the predefined set.

## 🔧 Advanced Notes

- All scenarios are guaranteed to be solvable.
- For bonus credit, inputs/outputs may be extended to support structured formats (e.g., JSON or YAML).
- A `Dockerfile` may be included for easy containerized execution.

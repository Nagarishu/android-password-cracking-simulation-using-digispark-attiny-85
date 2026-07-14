# android-password-cracking-simulation-using-digispark-attiny-85
# Android Password Brute-Force Simulation via DigiSpark ATtiny85

A USB Human Interface Device (HID) attack simulation demonstrating automated
PIN/password brute-forcing against Android lock screens, built on the
DigiSpark ATtiny85 microcontroller.

## Overview

This project explores HID-based attack vectors by emulating a USB keyboard
that programmatically injects PIN sequences into an Android device's lock
screen. It was built to study physical-access attack surfaces and the
effectiveness of Android's lockout/delay countermeasures.

## Motivation

Physical HID attacks (BadUSB-class) remain an underexplored risk in most
threat models compared to network-based attacks. This project was built to
understand:
- How Android's failed-attempt lockout timers respond to automated input
- The practical feasibility (and limitations) of brute-forcing short PINs
- Defensive takeaways for device hardening (USB debugging, lockout policies)

## Hardware

- DigiSpark ATtiny85 (USB HID-capable microcontroller)
- Target: Android device (lock screen PIN entry)

## How It Works

1. DigiSpark enumerates as a standard USB HID keyboard
2. On connection, it cycles through a configurable PIN keyspace
3. Injects each attempt via simulated keystrokes + Enter
4. Incorporates timing delays to account for Android's progressive lockout

## Repository Contents

This repo contains the Arduino sketch (`.ino`) for the DigiSpark, written in
C++ using the DigiKeyboard library.

## Key Limitations & Findings

- Android's escalating lockout delays make full 4-digit brute-force
  impractical beyond a handful of attempts
- No touchscreen emulation — limited to devices/scenarios accepting
  keyboard-based PIN entry
- Built strictly for controlled, authorized testing on personal devices

## Disclaimer

This project is intended **strictly for educational and authorized
security-testing purposes** (e.g., testing your own devices, or with
explicit written authorization). Unauthorized use against devices you don't
own or lack permission to test is illegal. The author assumes no liability
for misuse.

## Author

Rishu — Cybersecurity graduate, SRM University

# FPGA Alarm Clock (SystemVerilog · DE10-Lite)

[![Watch Demo](https://img.shields.io/badge/Watch-Demo-blue)](https://media.oregonstate.edu/media/t/1_h6xfm340)

A modular alarm clock on an Intel/Altera FPGA board. Features a 50 MHz timebase, seven-segment display, user-set alarm, and a simple tone generator. Includes simulation (ModelSim) and hardware bring-up notes.

---

## Demo (≈5mins)
▶ **Video:** https://media.oregonstate.edu/media/t/1_h6xfm340

---

## What’s inside
- **Modular design:** time counters, display multiplexer, alarm set UI, match→latch, tone generator  
- **Simulation:** ModelSim/Questa testbenches + a `.do` script for quick runs  
- **Hardware:** pin/IO map for DE10-Lite, speaker output, seven-segment driver  
- **Docs:** PDF report with block diagrams, testing, and results

---

## I/O map (quick reference)
| Signal        | Dir | Width | Meaning / Notes                           |
|---------------|:---:|:-----:|-------------------------------------------|
| `clk_50`      | in  | 1     | 50 MHz board clock                        |
| `rst_n`       | in  | 1     | Active-low reset                          |
| `tick_1Hz`    | out | 1     | 1-cycle pulse each second                 |
| `sel_field`   | in  | 2     | 0=sec, 1=min, 2=hr                        |
| `inc_btn`     | in  | 1     | Increment selected field (debounced)      |
| `match_pulse` | out | 1     | Time == alarm (single-cycle)              |
| `alarm_en`    | out | 1     | Latched enable for tone                   |
| `seg[6:0]`    | out | 7     | Seven-segment segments                    |
| `an[3:0]`     | out | 4     | Digit select (multiplexing)               |
| `spk_out`     | out | 1     | Square-wave to speaker GPIO               | 

## Credits  
Built by Kevin Lui, Justin Chu, Eric Tran, Oregon State University  

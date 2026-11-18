# Visible Light Communication (Li-Fi) Data Link

> **Status:** Academic Project (In Progress)

A point-to-point optical wireless communication (**Li-Fi**) transceiver link built between two **ESP32** microcontrollers. Digital data frames are modulated onto a high-power 1W white LED beam and demodulated by a custom analog front-end receiver with real-time Packet Error Rate (**PER**) diagnostics displayed on an **OLED** screen.

---

## System Architecture

```text
  TRANSMITTER NODE                                                RECEIVER NODE
┌──────────────────┐   ┌────────────────┐   ┌──────────────┐     ┌────────────────┐   ┌─────────────────┐   ┌────────────────┐   ┌──────────────────┐
│  ESP32 TX MCU    │──►│ Logic MOSFET   │──►│  1W White    │ ~~► │ BPW34          │──►│ LM358 Transimp. │──►│ LM393 Voltage  │──►│  ESP32 RX MCU    │
│ (Frame Encoding) │   │ (LED Driver)   │   │  LED Emitter │     │ Photodiode     │   │ Amplifier (TIA) │   │ Comparator     │   │ (Decode + OLED)  │
└──────────────────┘   └────────────────┘   └──────────────┘     └────────────────┘   └─────────────────┘   └────────────────┘   └──────────────────┘

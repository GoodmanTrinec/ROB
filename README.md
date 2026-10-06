# ROB

Domácí modulární AI robot. Projekt začíná verzí **v0.1**.

> Status: návrh / pre-alpha  
> Verze: v0.1

## Cíl v0.1
- PC → Wi-Fi → Raspberry Pi
- Raspberry Pi → USB/UART → ESP32
- řízení motorů
- kamera, mikrofon, reproduktor
- emergency STOP
- bezpečnostní vrstva mezi AI a motory

## Architektura
```text
PC (AI / Ollama / Vision / STT)
  │ Wi-Fi
  ▼
Raspberry Pi 5 (API / kamera / audio / safety)
  │ USB/UART
  ▼
ESP32 (PWM / DIR / encoders / watchdog)
  │
  ▼
Motor driver → motors
```

## Stav
v0.1: návrh hardwarové a softwarové architektury.

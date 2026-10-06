# Architecture

## Design principle

The robot is split into three layers.

### 1. AI / planning layer
Runs on the main PC.

Responsibilities:
- LLM
- speech recognition
- vision
- task planning
- high-level decisions

### 2. Robot services layer
Runs on Raspberry Pi.

Responsibilities:
- network API
- camera
- audio
- sensors
- command validation
- safety limits
- communication with ESP32

### 3. Realtime motor layer
Runs on ESP32.

Responsibilities:
- PWM
- motor direction
- encoders
- watchdog
- hard stop behavior

## Safety boundary

The AI layer must never directly control PWM or motor voltage.

All motion commands pass through the Raspberry Pi safety layer and then through the ESP32 realtime controller.

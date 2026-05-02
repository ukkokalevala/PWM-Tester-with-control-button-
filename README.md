Project Overview
Interactive LED lighting controller with 6 programmable animation effects, controlled via a physical button on an ESP8266 microcontroller.
Hardware Requirements
•	ESP8266 board (NodeMCU, Wemos D1, etc.)
•	LED connected to pin D4 (with appropriate resistor)
•	Push button connected to pin D3 (using internal pull-up)
Key Features
Effects Library (6 modes)
1.	Smooth Breathing - Exponential sine wave for natural fade
2.	Fast Strobe - 50ms on/off pulses
3.	Color Fade - Triangular wave modulation (50-255 range)
4.	Candle Flicker - Random brightness with varying delays
5.	Heartbeat - Patterned double-pulse simulation
6.	Rainbow Wave - Sinusoidal smooth transition
Technical Specifications
•	PWM Frequency: 2 kHz (smoother than default 1 kHz)
•	PWM Resolution: 8-bit (0-255 range)
•	Animation Speed: 20ms intervals (~50 FPS)
•	Button Debounce: 300ms hardware debounce
Code Architecture
Key Functions
•	triwave8() - Triangular waveform generation
•	simpleWave() - Sine wave generator with configurable range
•	Breathing effect uses exponential sine: (exp(sin(brightness/50*π)) - 0.3679) * 108
State Management
•	Effect cycling via button press (0→1→2→3→4→5→0)
•	Non-blocking timing using millis() for smooth animations

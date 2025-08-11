XIAO ESP32S3 Yes/No Voice Inference (Edge Impulse)
Important: This project works only with the ESP32 board package version 2.0.16 in Arduino IDE. Please downgrade your ESP32 board version to 2.0.16 before compiling. Tested on Seeed XIAO ESP32S3. ✅



Overview
This project runs an Edge Impulse “Yes/No” keyword spotting model on the Seeed XIAO ESP32S3 with its onboard PDM microphone to control the onboard LED based on voice commands. It captures audio via I2S, performs on-device inference, and toggles the LED when confidence exceeds a threshold.

Hardware

1.Seeed XIAO ESP32S3 (Sense variant recommended with onboard PDM mic)

2.Onboard PDM microphone (DATA GPIO41, CLK GPIO42 on XIAO ESP32S3 Sense)

Software Requirements

1.Arduino IDE 2.x

2.ESP32 Boards package: 2.0.16 (required)

3.Edge Impulse Arduino library exported for your project (e.g., XIAO_esp32S3_YesNo_inferencing.zip)

Before You Start:-

Downgrade ESP32 core to 2.0.16:

Arduino IDE → Tools → Board → Boards Manager

Search “esp32” (by Espressif Systems)

Install version 2.0.16

Select your board/port:

Tools → Board → ESP32 → Seeed XIAO_ESP32S3

Tools → Port → your XIAO COM port



How to Install a .ZIP Library in Arduino IDE

Download the Edge Impulse Arduino library for your project as a .zip.

In Arduino IDE:

Sketch → Include Library → Add .ZIP Library…

Select your downloaded .zip file and open.

Wait for “Library added” notification.

Restart IDE if examples do not appear.

Note: Do not unzip the library before adding it. If you face issues, ensure the library contains at least a .h/.cpp and is not nested inside multiple folders.

Project Behavior:

Captures 16 kHz audio using I2S from the onboard PDM mic.

Runs the Edge Impulse model to classify “yes” / “no”.

Example logic:

If top class index is 0 (e.g., “no”) with confidence > 0.80 → LED OFF.

If top class index is 2 (e.g., “yes”) with confidence > 0.80 → LED ON.

You may need to adjust label indices based on your exported model (check Serial Monitor output).



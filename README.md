# 📱 Where Is My Phone Button

A standalone, Wi-Fi-enabled physical button that calls your phone when pressed. Built with an ESP32, a satisfying mechanical keyboard switch, and a custom 3D-printed enclosure featuring an engineered flexure spring for perfect tactile feedback. 

No more asking someone else to call your phone or shouting for a smart speaker—just press the button on your desk, and your phone rings.

## ✨ Features
* **Satisfying Tactile Feedback:** Uses a mechanical keyboard switch coupled with a custom 3D-printed stabilizer spring.
* **Standalone Operation:** Connects directly to Wi-Fi via an ESP32; no companion app or bridge required.
* **Reliable API Trigger:** Integrates with the Twilio Voice API to initiate an actual phone call to any verified number.
* **Custom Audio:** Configured to play a custom text-to-speech message (TwiML) when the call is answered.

## 🛠️ Hardware Requirements
* 1x ESP32 Development Board (e.g., NodeMCU or similar)
* 1x Mechanical Keyboard Switch (Cherry MX style or similar)
* 3D Printed Enclosure & Stabilizer Spring (STLs provided)
* Micro-USB or USB-C cable for power

*(Note: If you don't have a 3D printer, you can grab the fully printed hardware kit and switch directly from [GEFEN3D](#) - link your store here!)*

## 🖨️ 3D Printing & Assembly
The enclosure and custom serpentine flexure spring were designed to provide a crisp return force against the center axis. The design files can easily be modified in Fusion 360 or SolidWorks if you need to adjust the tolerances for your specific printer.
* **Material:** PLA or PETG (Carbon-fiber filled PLA-CF works excellently for a stiffer spring rate).
* **Settings:** Recommend 4+ perimeters/wall loops on the spring to ensure the flexure arms are printed as solid, continuous extruded lines rather than infill.

## 💻 Software Setup

### 1. Twilio Configuration
1. Create a free [Twilio](https://www.twilio.com/) account.
2. Get a Trial Phone Number.
3. In the Twilio Console, go to **Verified Caller IDs** and verify your personal phone number.
4. Create a **TwiML Bin** with the message you want to hear when you pick up:
   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <Response>
       <Say>Here is your phone! Look around you.</Say>
   </Response>

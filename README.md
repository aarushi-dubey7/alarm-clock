🕐 WiFi-Enabled Alarm Clock with ESP8266
A simple alarm clock using ESP8266, 16x2 LCD display, and button module. Features WiFi-synced time via NTP, weekday/weekend alarms, and time-based greetings.

📋 Quick Start
Required Libraries

LiquidCrystal (built-in)
ESP8266WiFi (built-in)
time.h (built-in)

Install via: Tools → Manage Libraries (if needed)
Components

ESP8266 NodeMCU
16x2 LCD Display (parallel)
Button Module (KY-040)
Breadboard & Jumper Wires


⚙️ Setup

Install ESP8266 Board:

File → Preferences
Add to URLs: https://arduino.esp8266.com/stable/package_esp8266com_index.json
Tools → Board Manager → Search "esp8266" → Install


Select Board Settings:

Board: NodeMCU 1.0 (ESP-12E Module)
Upload Speed: 115200


Update WiFi Credentials:
In the code, you'll find a comment to add in your wifi ssid and password. 

Upload Code:

Connect ESP8266 via USB
Click Upload
Open Serial Monitor (115200 baud) to verify




🔌 Wiring Table
ESP8266 PinLCD PinConnectionD0Pin 4 (RS)Register SelectD1Pin 6 (E)EnableD2Pin 11 (DB4)Data Bit 4D3Pin 12 (DB5)Data Bit 5D4Pin 13 (DB6)Data Bit 6D5Pin 14 (DB7)Data Bit 73.3VPin 2 (VDD)PowerGNDPin 1 (VSS)GroundGNDPin 3 (VO)ContrastGNDPin 5 (RW)Write Mode
Button Module:
Button PinESP8266 PinS (Signal)D7- (GND)GND+ (VCC)3.3V

🎮 Usage
Single Click: Shows current time + date with greeting
Double Click: Shows time remaining until alarm

🔧 Changes to Make
Change WiFi Network
const char* password = "YourPassword";
Change Timezone
Change Alarm Times
Change Greeting Times
Change Display Timeout
cpp#define DISPLAY_TIMEOUT 5000  // Time in milliseconds (5000 = 5 seconds)

⚠️ Important Notes

Use D7 for button, NOT D8 (D8 is a strapping pin)
WiFi credentials: Replace with your network info
Time zone: Match your location
All grounds: Connect to GND rail on breadboard
All 3.3V: Connect to 3.3V rail on breadboard


🐛 Troubleshooting
LCD blank? Check contrast (Pin 3), power (Pin 2), and data pins (D2-D5)
Button not working? Make sure you're using D7, not D8
Wrong time? Check WiFi is connected and timezone is correct
WiFi won't connect? Verify SSID and password are correct

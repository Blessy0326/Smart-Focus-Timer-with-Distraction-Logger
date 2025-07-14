demo video of project --> https://drive.google.com/file/d/1vA9LjFeBl2s5cyAijo6FcsSGtKFzlYaY/view?usp=drive_link


## 🧠 Smart Focus Timer – M5Stack (IoT Component)

This project runs on the **M5Stack Core (Basic)** and is programmed using **UIFlow (Blockly)**. It helps track focused work sessions and logs **distractions detected via PIR sensor**, storing them on an **SD card** and optionally uploading to **EzData cloud**.

---

### 🔧 Requirements

* M5Stack Core (Basic)
* M5 PIR Unit (Port A)
* RGB (NeoPixel) Unit (Port B)
* MicroSD card (formatted as FAT32)
* Wi-Fi connection (for time API and EzData)
* Access to [https://flow.m5stack.com](https://flow.m5stack.com) (UIFlow)

---

### 🚀 How to Run the M5Stack Code

1. **Insert your SD Card**

   * Use a **FAT32-formatted** microSD card (≤32 GB recommended).
   * Insert it into the M5Stack Core before powering on.

2. **Connect Units**

   * PIR Sensor → **Port A**
   * NeoPixel RGB Strip → **Port B**

3. **Open UIFlow (Blockly Editor)**

   * Go to [https://flow.m5stack.com](https://flow.m5stack.com)
   * Select your device: **Core → Core (Basic)**
   * Connect via WebUSB or set your device token via Wi-Fi

4. **Load Your Blockly Program**

   * Upload or drag your `.m5f` Blockly file (if committed to GitHub)
   * Ensure blocks include:

     * Button A = Start focus
     * Button B = Resume
     * Button C = Reset
     * Timer logic using countdown
     * PIR motion check → pause timer + log distraction
     * Log output to `focus_log.txt` on SD
     * Optional: Upload to EzData using topic token

5. **Configure Wi-Fi**

   * In Blockly: use the `Wi-Fi connect` block with your **SSID** and **password**
   * Required for fetching quotes and current time

6. **Run in Real Time**

   * Press Button A to start focus
   * Motion triggers pause and logs distraction
   * After timer ends, session data is saved to SD and optionally EzData

---

### 📦 Output Files

* `focus_log.txt`: Stored in SD card root directory
  Contains JSON-like entries for each session:

  ```json
  {"session_start_time": "2025-07-01T00:38:56", "distraction": 2}
  ```

---

### 🛠️ Optional: Modify Tokens & API URLs

* You can edit the Blockly blocks to:

  * Change EzData topic or token
  * Use a different time API
  * Customize motivational quote sources

---


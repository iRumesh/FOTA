# FOTA - Firmware Over-the-air updates using github repo

# Folder Structure

```plaintext
ESP/
├── cert.h                    # Github rootCA [Valid till 1/15/38, 5:30:00 PM GMT+5:30]
├── config.h                  # WiFi Credential, FW ver, Github FW json path config
├── ESP.ino                   # Main Sketch
├── ESP.bin                   # Updated compiled sketch
├── FW.json                   # FW version and bin file configs
└── README.md                 # Project documentation
```

## Prerequisites

- Ensure you have configured and correctly installed Arduino, Board, Libraries.

## Steps to Check

1. **Clone the Repository and Navigate to the directory**  
 
   ```bash
   git clone https://github.com/iRumesh/FOTA
   cd FOTA
   ```
2. **Change the WiFi Credentials, Github FW Json URL in config.h**  
   ```bash
    // WiFi credentials
    const char* ssid = "";
    const char* wifiPassword = "";

    #define URL_fw_JSON "https://raw.githubusercontent.com/iRumesh/FOTA/main/ESP/FW.json"
   ```
3. **Save the changes and upload the Firmware to the Board**  

4.  **Firmware update**  
    - Now change the firmware, compile the binary (.bin) and upload to the  github.
    - FW.json content should be modified based on the requirement
    
```json
     {
      "esp32": {
     "version": "1.1",
     "bin_url": "https://raw.githubusercontent.com/iRumesh/FOTA/main/ESP/ESP.ino.bin"
        }
     }
```

5.  **From ESP side now new firmware will be downloaded and flashed**  
    This can be verified by comparing the serial monitor FW version print:


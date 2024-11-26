## How to Turn Off the LED on Raspberry Pi Zero 2 W (Bookworm OS Edition)

If you want to turn off the activity LED on your Raspberry Pi Zero 2 W running Bookworm OS, follow these steps:

### Step 1: Edit the Configuration File

1. Open the terminal on your Raspberry Pi.
2. Enter the following command to edit the `/boot/firmware/config.txt` file:
   ```bash
   sudo nano /boot/firmware/config.txt
   ```

### Step 2: Add the Necessary Parameters

1. Scroll to the end of the file.
2. Add the following lines:
   ```bash
   dtparam=act_led_trigger=none
   dtparam=act_led_activelow=on
   ```

### Step 3: Save and Exit

1. Press `Ctrl + X` to exit the editor.
2. Press `Y` to confirm saving the changes.
3. Press `Enter` to write the changes to the file.

### Step 4: Reboot Your Raspberry Pi

1. Enter the following command to reboot your Raspberry Pi:
   ```bash
   sudo reboot
   ```

### Alternative Method: Temporary LED Turn Off

If you want to turn off the LED temporarily without editing the configuration file, you can use the following commands:

1. Open the terminal.
2. Run these commands:
   ```bash
   echo gpio | sudo tee /sys/class/leds/led0/trigger
   echo 0 | sudo tee /sys/class/leds/led0/brightness
   ```

### Troubleshooting

If the LED does not turn off, ensure there are no typos in the configuration file and that you have the necessary permissions. Also, make sure there are no conflicting parameters in the `/boot/firmware/config.txt` file.

---

Feel free to customize these instructions further if needed. Let me know if there's anything else you need help with!

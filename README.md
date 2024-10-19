# Auto Launch Python Voice Assistant at Startup of Raspberry Pi

A hands-on tutorial to configure Raspberry Pi so that it will automatically launch a Google Gemini-powered voice assistant (chatbot) built with Python at the startup of Raspberry Pi

Following the YouTube video below to learn more about this project:     
https://youtu.be/iagQxcXv-So

Please also check out my previous video on how to build the voice assistant,  
https://youtu.be/uV6hJQcuW4w

### Steps: 
1. Download the Python script.   
2. Add your Google Gemini API key at line 36 of the Python script. 
3. Login to Raspberry Pi with SSH.
4. Transfer the Python script with WinSCP to the project folder, for example,
   ```console 
   /home/pi/projects/va/
   ```
5. Create a cron job with this command, 
   ```console 
   sudo crontab -e
   ```

6. Add the following entry to the cron job file, 
   ```console 
   @reboot sleep 60 && /bin/bash -c "source /home/pi/.venv/bin/activate && /home/pi/.venv/bin/python /home/pi/projects/va/gva7_led.py >> /home/pi/cron_output.log 2>&1 &"
   ```

# Dialtronincs Gateway Configurations.

## what is dialtronics gateway?

A Dialtorics Gateway is likely a device or software that helps connect regular phone lines to internet-based phone systems (VoIP/SIP).

- Think of it like a bridge:
- It connects:
Old-style phone systems (landlines, analog phones) to modern internet phone systems (like SIP trunks or IP PBX) So you can make and receive calls over the internet using regular phone equipment.

![WhatsApp Image 2025-08-02 at 2 21 33 PM](https://github.com/user-attachments/assets/d6ae1f5c-98d0-4e80-8bcb-86cedc2a6402)

- This is the gateway image for your reference.
### On the front side, it has SIM slots numbered 0 to 31. There are also two indicator lights: one for power and another to show whether the device is running or not.

![WhatsApp Image 2025-08-02 at 2 21 34 PM](https://github.com/user-attachments/assets/14e20c84-a182-4748-afff-e62c25c02dc6)
### On the back side, it has antenna ports numbered 0 to 31 for SIM networks. Additionally, it includes ports labeled LAN, WAN, USB, and CONSOLE. The gateway can be reset using the reset button located inside the reset port

##### Lets start the configuration.

1. reset the gateway by using some pens by client the reset button like this
   <img width="3054" height="2512" alt="image" src="https://github.com/user-attachments/assets/3cba42b7-fe53-4002-aa18-a20c4492d290" />
It takes few seconds both LAN indiaction lights turns off for a cuople of seconds and turns on which means its reseted.

After that connect the lan cable to the laptop.
2. press win+R and type ncpa.cpl
<img width="363" height="210" alt="Capture" src="https://github.com/user-attachments/assets/252aa26e-1be8-4aa3-8256-d928e1ff001c" />

3. The below picture you can able to show ethenet double click on it the go to properties
<img width="578" height="282" alt="Dtel" src="https://github.com/user-attachments/assets/56ab7a03-d39c-4dfd-b498-7b18094040a4" />

4. After that this tab will be open.
<img width="275" height="350" alt="Screenshot 2025-08-02 152816" src="https://github.com/user-attachments/assets/17831c2d-2c72-45bc-8759-31b86301b292" />

- Double click **Internet protocol version4 (TCP/UDP)** and edit according to the below image.

<img width="298" height="338" alt="IPVfour" src="https://github.com/user-attachments/assets/c088dffd-39c3-4624-be2a-1a8043e349ba" />
click ok & ok button to save it.

5. Then use this **192.168.12.10** IP to open this page. username is admin and password is admin.
<img width="948" height="481" alt="dialtronicslogin" src="https://github.com/user-attachments/assets/8268dea6-0c5f-4c36-8d3f-8da339974dc7" />

after that you may see the dashboard page.
<img width="948" height="446" alt="dashboard" src="https://github.com/user-attachments/assets/fdd52a89-3239-4a44-a608-c4d8b8d8bf2f" />

6. Go to network settings and network configurations.
<img width="940" height="446" alt="network_configuration" src="https://github.com/user-attachments/assets/2694bb87-e79f-47bd-85c5-48e6fc43119c" />

configure the following one

-  Go to command promt on neighbour system and use ping command to find the free IP  and use the free IP here called 172.17.15.12 to configure LAN, In your case it may differ based on your network.
<img width="1911" height="887" alt="image" src="https://github.com/user-attachments/assets/05f6e0e0-e488-4e7a-8e9a-7eaa4e4a8f0c" />

and click save button to save.

- Then unplug the LAN cable from your computer and connect it to lan network.

7. connect lan cable and open the IP address on your browser that what you set on previously in that LAN configuration **my case 172.17.15.12**
<img width="1898" height="958" alt="image" src="https://github.com/user-attachments/assets/fb6df368-f752-44e5-b5c8-9eae0f843155" />

- login using admin admin.
8. Then go to call configuration and click sip/trunk configuration
  <img width="939" height="441" alt="call_confiuration" src="https://github.com/user-attachments/assets/f4fd6fbe-aba4-4375-9b42-f146544296cb" />

The page opened like this then click add new.
<img width="956" height="447" alt="stc" src="https://github.com/user-attachments/assets/5d4abf42-50ab-4382-8c49-e9a331fe9db3" />

 

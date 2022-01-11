# Home-Automation-with-Supla

![image](https://user-images.githubusercontent.com/79988029/148890174-67d13927-a5e8-4a9f-a563-173e729fbde0.png)

 

Google and Alexa Controlled Home Automation using Supla (no coding required)

Hello friends! Welcome back to the Home Automation Series. In the previous blogs we have learnt how to control appliances with the help of Alexa. For a change, in this blog we are going to learn how to control appliances with both Google assistant and Alexa using Supla Cloud services.
Without any delay let’s get started.
 
A Brief Introduction about Supla

SUPLA is simple, open and free of charge. It gives an opportunity to build elements based on RaspberryPI, Arduino or ESP8266 platforms and then join them either through LAN or Wi-Fi. Through SUPLA you can, among others, control the lighting, switch on and off household appliances and media, open and shut gates and doors, or control room temperature. 
Source:  https://www.supla.org/en/

Objective

The main objective of this project is to control any Electrical appliances with both Alexa and Google Assistant voice commands, Amazon Alexa app, Google Home app, Supla app and manual switches.
•	We can check the real time status of the electrical appliances from anywhere in the world from Amazon Alexa app, Google Home app and Supla app.
•	You can also control the appliances from the above-mentioned apps in our mobile phone when the internet connection is alive.
•	When the internet connection is not alive, then you can control the appliances with the switches.
•	There is no need to write any code to do this project. But we have to generate a firmware based on our requirements from the Sula website. We will learn how to do that in this blog.


Components required
Hardware
1.Nodemcu board:  
                                        We will upload our code into this development board. It is more compatible than any other development boards available. 
 ![image](https://user-images.githubusercontent.com/79988029/148890211-c661faf7-45fe-485b-883b-c11fb72acf09.png)

Buy it from here 
 https://www.hnhcart.com/products/node-mcu-cp-210x?_pos=1&_sid=16b795a75&_ss=r 
                                                                                  
If you want to make your project cheaper you can use ESP-12e board. You can check how to program it here
 https://youtu.be/UxIBCyP0V18

![image](https://user-images.githubusercontent.com/79988029/148890232-2b56066b-8a93-4171-bd30-8fcac4ea5536.png)

 
Buy it from here
 https://www.hnhcart.com/products/esp-12e-wifi-module?_pos=1&_sid=ec9ba047b&_ss=r
Don’t forgot to add 3.3v voltage regulator (AMS 1117 3.3v regulator is recommended)
Buy it from here
https://www.hnhcart.com/products/reg1117-ic?_pos=2&_sid=39426c2de&_ss=r

2. 4 channel relay board:
                                         It acts as a switch. It can be controlled with little dc voltage to control high voltage appliances. 
 ![image](https://user-images.githubusercontent.com/79988029/148890252-dfa66f90-dac0-48ca-80cb-122de9f5d6b7.png)

https://www.hnhcart.com/products/4-channel-5v-relay-module?_pos=11&_sid=959d29598&_ss=r

3. Jumper wires:
                                        As its name, it is used to connect pins of NodeMCU and relay board as well as switches.
 ![image](https://user-images.githubusercontent.com/79988029/148890267-c4d3436c-36ec-4569-b5be-ac34e2daa099.png)

4.Power source:
 ![image](https://user-images.githubusercontent.com/79988029/148890278-5b6b0f62-f16c-4d5a-83e3-9dfc1a6f01dd.png)

You can use even a mobile charger for power source.
Or you can buy it from here
https://www.hnhcart.com/collections/power-supply-and-regulators/products/5v-1-amp-power-supply-board-220v-ac-to-5v-dc

5. Switches, Sockets and 8-way Gang box:
                                        There is nothing to talk about it. These are familiar to everyone. These are available in every electrical shop.
     ![image](https://user-images.githubusercontent.com/79988029/148890295-2eef4fc1-7037-4cee-af30-f9bc45ab75d6.png)

6. Any Alexa device: 
                                      Alexa is a voice assistant developed by Amazon.
                Some Alexa devices are mentioned here. You can buy any of these for this project:
Note: Buying these devices are not necessary. Without these devices also, we can use voice assistance 
Alexa Echo Dot:
https://www.amazon.in/Echo-Dot-3rd-Gen/dp/B07PFFMP9P/ref=sr_1_1?dchild=1&keywords=echo+dot+3rd+generation&qid=1625132670&sr=8-1
https://www.amazon.in/All-new-Echo-Dot/dp/B084DWH53T/ref=sr_1_3?dchild=1&keywords=echo+dot+3rd+generation&qid=1625132670&sr=8-3


Alexa Echo Portable:
https://www.amazon.in/Echo-Input-Portable-Smart-Speaker/dp/B07YP9WYFN/ref=sr_1_1?crid=2A0CGLFLXY27G&dchild=1&keywords=echo+portable&qid=1625132718&sprefix=echo+po%2Caps%2C331&sr=8-1
7. Any Google Assistant device:
    
 Note: Buying these devices are not necessary. Without these devices also, we can use voice assistance 

Google home mini:
https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChcSEwjrvOeBzsHxAhVLfysKHWzKDpAYABAGGgJzZg&ae=2&ohost=www.google.com&cid=CAESQeD2zHi8-8Jhjgn1bHKPPBXKtJ2t6OWMbDYa44u_YJBOmhVBx-EQ-9c9sRMZHQAgDvUH-uXfbrAsHa536hwebV1w&sig=AOD64_3O_S0_ziV4DWCtKbPPAlfZJZGcNw&ctype=5&q=&ved=2ahUKEwjW09yBzsHxAhVI7XMBHTy7BdMQ9aACegQIARBO&adurl=

Software

1.	Espressif Flashing tools. You can download it from here.
https://www.espressif.com/sites/default/files/tools/flash_download_tool_v3.8.8_0.zip
2.	 We have to build a firmware in the form of BIN file. To do that search this link https://gui-generic-builder.supla.io/
Keep the settings as shown in figure and then scroll to bottom of the page and click generate. A BIN file will be downloaded. Keep it with you.
![image](https://user-images.githubusercontent.com/79988029/148891370-b3754190-4776-40ee-a157-9836b2562ffc.png)

![image](https://user-images.githubusercontent.com/79988029/148891403-fe28d73d-e5f6-42b0-81e1-98effcfb1e78.png)
               
                                                 
3.	Download the apps listed below

Supla App: SUPLA - Apps on Google Play
Alexa App: Amazon Alexa - Apps on Google Play
Google Home App: Google Home - Apps on Google Play

Process

Flashing BIN file to Esp8266 based modules

1.	Unzip the flashing tool which we have downloaded. And then run the flash download tool application.
          ![image](https://user-images.githubusercontent.com/79988029/148891420-0ef2afe4-e671-436f-9305-10cfbbe6d068.png)
           

2.	Keep the settings as shown in the figure and click ok.

           ![image](https://user-images.githubusercontent.com/79988029/148891436-21a68dc5-6aa8-4e9c-9d05-aad4ad529f28.png)
                               

3.	A window will be opened like this. Click on the three dots at the top right and select the BIN file that we have generated. Write the texts and keep the settings as shown in the figure.
      ![image](https://user-images.githubusercontent.com/79988029/148891454-5cc3e2a7-cf6e-4a02-ac28-4f8234dfa141.png)


4.	Connect the ESP8266 based module (let’s say NodeMCU) to your system. Select the correct COM port and baud rate to 115200 and write the address of the BIN file as 0x00000. 
5.	First click Erase. After the Erasing process is completed, click on Start.
6.	After Flashing the firmware, just click the reset button on NodeMCU.

Creating Supla Account

Supla account creation and its services are absolutely free. 
1.	Go through this link and create your account
                    https://cloud.supla.org/register
2.	After creating the account go through this link 
                    https://cloud.supla.org/home
3.	Sign-in with your account and note the data present in both the boxes Supla-dev and Supla-client.

Configuring the NodeMCU

1.	Open your Smart phone or Laptop and connect to the Access point whose name is displayed like this “SUPLA-ESP8266-************”.
2.	Open any one of your favourite browsers and search the IP address 192.168.4.1
3.	A page will be opened like this
            ![image](https://user-images.githubusercontent.com/79988029/148891474-805e1eb7-6e14-43dd-a3e5-a1fbbb0d6f86.png)
                    
4.	Enter the details asked in the figure.
5.	After entering the details click on Zapisz (means Save).
            ![image](https://user-images.githubusercontent.com/79988029/148891493-b87e7b36-2669-4a18-a6d8-6d5f56f6732e.png)
                    

6.	After saving click on Ustawienia urzadzenia (means Device Settings).
7.	A page will be opened like this. Click on BRAK and select SONOFF 4CH. After selecting click Zapisz.
         ![image](https://user-images.githubusercontent.com/79988029/148891509-1b838ed1-92b9-46f6-bde8-2f7c30816d66.png)
          ![image](https://user-images.githubusercontent.com/79988029/148891525-ba4b40d5-20ad-479e-b9e7-caeb77e64196.png)
    

8.	Click on PRZEKAZNIKI. Then a page will be opened like this. Keep the settings as shown in the figure (by default the settings are already selected). Then click Zapisz. Ater the settings are saved , click Powrot (means Back).                                                             
             ![image](https://user-images.githubusercontent.com/79988029/148891538-6c69a0ab-1c8f-418d-859f-b4e35fcc243f.png)
                                        

9.	Now, click on PRZYCISKI. Then a page will be opened like this. Keep the settings as shown in the figure. Then click Zapisz. Ater the settings are saved , click Powrot.

  ![image](https://user-images.githubusercontent.com/79988029/148891554-6209abae-e210-4aed-b32c-5381a4b3d4ec.png)
![image](https://user-images.githubusercontent.com/79988029/148891567-c68367a3-3485-4fee-a8c8-8e2085b68496.png)


10.	After the pages comes back, click Powrot again. Now, click on the reset button on NodeMCU. The device will connect to your Access point or Router. 
11.	Now, go through this link 
https://cloud.supla.org/login
and login with the account you created.

12.	After login, you will see a message at the top right corner like this. 
 ![image](https://user-images.githubusercontent.com/79988029/148891594-d5e4e1c4-03d2-43c5-bb3c-64c5a3de7e0d.png)

13.	Just click on it and then you will see a message like this. And you can also see the information of the NodeMCU device we created.
![image](https://user-images.githubusercontent.com/79988029/148891609-e2b4ba59-7509-4c90-8ced-3aeb4fcf10ab.png)
 

Setting the Apps

Supla App:

Open the Supla app and login with the account you created. You can see the devices list in the panel. You can control the devices from here.
          ![image](https://user-images.githubusercontent.com/79988029/148891632-7d4d9dca-ec4e-43c5-937a-2e2664c8a4d5.png)
                                                   
Alexa App:

Open the Alexa app and login with your amazon account. Now, click on more and then skills and games. In the search bar, search for Supla. Open it and enable the skill by signing in with your Supla account. The devices will automatically get connected to your Alexa app.
                               
      ![image](https://user-images.githubusercontent.com/79988029/148891651-ebf9ce74-e93f-47f9-9966-abf0fdcd1aea.png)
                                                  
![image](https://user-images.githubusercontent.com/79988029/148891669-7a60befb-cc25-4eb5-aed0-3657379db55b.png)
![image](https://user-images.githubusercontent.com/79988029/148891695-7e9b42bb-0d6a-41db-a1e0-6d4479406385.png)


Google Home App:

Open the Google Home App and sign in with your google account. Now tap on + symbol and then tap on + set up device again. Now tap on works with google and search for Supla. And sign in with your Supla account.
![image](https://user-images.githubusercontent.com/79988029/148891739-d479585d-0348-4c48-86e6-d0b8246e89be.png)
![image](https://user-images.githubusercontent.com/79988029/148891750-1a8d68b0-4fcb-40bf-b3d9-52ea4571c9e4.png)
![image](https://user-images.githubusercontent.com/79988029/148891764-5fd12c46-2630-4b09-bfe3-16618b7439c5.png)
![image](https://user-images.githubusercontent.com/79988029/148891787-f68657ad-836a-4438-ad87-43b8a2c2d420.png)

                        
	               

Circuit diagram

GPIO 12   – D6 of NodeMCU        -         IN 1 of Relay board
GPIO5      – D1 of NodeMCU        -         IN 2 of Relay board
GPIO4      – D2 of NodeMCU        -         IN 3 of Relay board
GPIO15    – D8 of NodeMCU        -         IN 4 of Relay board
GPIO0      – D3 of NodeMCU        -         Switch 1
GPIO1       - TX of NodeMCU        -         Switch 2
GPIO3       - RX of NodeMCU        -         Switch 3
GPIO14    – D5 of NodeMCU        -         Switch 4

 ![image](https://user-images.githubusercontent.com/79988029/148891812-aa690138-5835-4504-a44b-a99743edb93f.png)

Now all set. You can simply change the names of the appliances in both Alexa App and Google Home App. You can Turn on or off the devices by simply calling the appliance name and telling on or off. You can tell to both Google Assistant and Alexa also. You can also get the real time feedback, if we turn on or off the devices using the switches. Real time feedback and Voice assistant services work only when the internet connection is alive. If the Internet connection is not present you can control the appliances with the switches.



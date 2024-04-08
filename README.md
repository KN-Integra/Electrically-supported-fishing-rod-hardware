# Electrically-supported-fishing-rod


Electrically supported fishing rod is an open-source hardware solution that supports an idea of "the one-hand cappable fishing rod".
Hardware consists of two PCB designs called later as **upper** and **lower** due to their arrangement in the final enclosure.

Both of mentioned PCBs were designed in **Altium Designer**, based on free student's license.


## Upper PCB ##

The upper plate is mainly responsible for I/O operation including driving up to 2 brushed motors based on nRF52840 Dongle & Toshiba TB67H420FTG.

Main features of the upper board PCB:
* reverse polarity protection
* external Imax regulation via potentiometer
* build-in 3v3 LDO
* small switch changing the power supply method for the nrf (VCC/LDO)
* simple cinfiguration via R8-R13 jumpers



![image](https://github.com/eSqadron/Electrically-supported-fishing-rod/assets/75276739/dcd5063c-58aa-449c-bb61-3fb6512a2a4f)
![image](https://github.com/eSqadron/Electrically-supported-fishing-rod/assets/75276739/84956fde-1b0e-4025-b5b5-c3022e60c385)


---
**Nordic nRF52840 Dongle connection:**


![image](https://github.com/eSqadron/Electrically-supported-fishing-rod/assets/75276739/93ef9d11-6a9a-4f4f-82c7-f4159f647ee8)

**where:**


* **LO1, LO2, LO12, LO22**  error pins from Toshiba (overheating, current limit)
* **INA1, INA2, INB1/INA12, INB2/INA22, PWMA, PWMB/PWMA2** (pinouts responsible for motor driving, **please refere to Toshiba datasheet**)
* **SW DONGLE** input from the external switch
* **ADC VM** input voltage after divider supplied to nordic ADC pin
* **uC A, uC B** (signals from encoder)
* **HBMODE** setting 1/2 motors (**please refere to Toshiba datasheet**)

---


**Toshiba TB67H420FTG**

![image](https://github.com/KN-Integra/Electrically-supported-fishing-rod-hardware/assets/75276739/40a6e502-3676-4842-a689-786aa4305431)

Below, documentation with pinout naming can be found:

https://toshiba.semicon-storage.com/info/TB67H420FTG_datasheet_en_20201016.pdf?did=59110&prodName=TB67H420FTG

---

**Pinout connection:**


![image](https://github.com/eSqadron/Electrically-supported-fishing-rod/assets/75276739/21d33192-e7c5-43f7-8b9f-39559961ef73)


**where:** 

* **VM** is a supply connection with voltage equal to input voltage (12V adviced)
* **SW SIG** is external input signal from the switch
* **A OUT & B OUT** signals from encoder
* **OUT A+ OUT A-** 1 motor connection
* **NetPinout_5 & NetPinout_6** 2 motor connection if configured correctly

---

**R8-R13 jumpers configuration**


![image](https://github.com/KN-Integra/Electrically-supported-fishing-rod-hardware/assets/75276739/2f02bac3-dd09-4685-ba07-05d3f3929c38)

**R8 & BR9** soldered if you want to use **1 motor & 1 driver**

**R10 & BR11** soldered if you want to use **2 motors & 1 driver**

**R12 & BR13** soldered if you want to use **2 motors & 2 drivers**



## Bottom PCB ##

The bottom plate responsible for control of charging/discharging of 4S Li-ION 18650 battery pack with basic power consumption display on the LCD. Up to **10A** constant current. 

**Free pads visible in the top right corner of the picture are designed for ON/OFF switch and LCD reset.**

![image](https://github.com/eSqadron/Electrically-supported-fishing-rod/assets/75276739/f771859e-c4f4-448e-9e45-0ea538b86819)

---

![image](https://github.com/eSqadron/Electrically-supported-fishing-rod/assets/75276739/a6f4e09b-8165-492e-9409-770386c0a31a)


LCD harvested from uniwersal 10in1 meter **KWS-MX18L**.
Can be easly found on the internet.

BMS is a ready module that can be track by simply using **"ERGO BMS 4S"**.




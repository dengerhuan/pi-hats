## RTC HAT(ds1307)
## High Accuracy RTC HAT(ds3231)
## 4-Channel 16-Bit ADC HAT(ads1115)
### for Raspberry Pi
##
## Installation
1. Driver Installation

    Only applied for Raspbian Jessie/Stretch

    *RTC HAT(ds1307)*
    ```bash
        sudo ./install.sh -u rtc_ds1307
    ```
    *High Accuracy RTC HAT(ds3231)*
    ```bash
        sudo ./install.sh -u rtc_ds3231
    ```
    *4-Channel 16-Bit ADC HAT(ads1115)*
    ```bash
        sudo ./install.sh -u adc_ads1115
    ```
2. Power off Raspberry Pi
3. Insert the HAT to Raspberry Pi
4. Power up Raspberry Pi

#### List install status
```bash
    ./install.sh -l
```

#### Uninstallation
```bash
    sudo ./install.sh -u
```

##
## RTC Guide
### RTC HAT(ds1307) or High Accuracy RTC HAT(ds3231)
Read hardware clock and print result
```bash
    sudo hwclock -r
```
Set the system time from the hardware clock
```bash
    sudo hwclock -s
```
Set the hardware clock from the current system time
```bash
    sudo hwclock -w
```
More usage
```bash
    hwclock --help
```
##
## ADC Guide
### 4-Channel 16-Bit ADC HAT(ads1115)
![](https://github.com/Seeed-Studio/pi-hats/raw/master/images/ads1115-channels.png) 

channels 0-3 is differntial voltage, full scale range -2.048V - +2.048V 

channels 4-7 is absolute voltage of AIN0-AIN3, full scale range 0 - +2.048V

Read AIN0(channel 4) voltage(unit mV).
```bash
    cat /sys/devices/platform/soc/*04000.i2c/i2c-1/1-0048/in4_input
```

<div>
        <table border="0">
	  <tr align="center">
	    <th>INPUT</th>
	    <th>channel</th>
	    <th>/sys/.../XXX</th>
	  </tr>
	  <tr align="center">
	    <td>AIN0</td>
	    <td>4</td>
	    <td>in4_input</td>
	  </tr>
	  <tr align="center">
	    <td>AIN1</td>
	    <td>5</td>
	    <td>in5_input</td>
	  </tr>
	  <tr align="center">
	    <td>AIN2</td>
	    <td>6</td>
	    <td>in6_input</td>
	  </tr>
	  <tr align="center">
	    <td>AIN3</td>
	    <td>7</td>
	    <td>in7_input</td>
	  </tr>
	</table>
</div>
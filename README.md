# soem-w5500-rpi
Opensource realtime EtherCAT master for Raspberry pi 

**HARDWARE:**
+ Raspberry pi 1, zero or zero W
+ Wiznet W5500 Ethernet chip with SPI interface

**SOFTWARE:**
+ Raspbian or Raspbian lite OS (https://www.raspberrypi.org/downloads/)
+ Patched kernel with xenomai 2.6 (for xenomai 3, we have different build) 
+ Simple Open Source EtherCAT Master (SOEM) version 1.3.0 (https://openethercatsociety.github.io/)
+ SOEM is patched to support xenomai
+ Realtime compatible W5500 driver for SOEM on rpi 

**BUILD:**
* You MUST have a raspberri pi (any version) with xenomai 2 patched kernel
* User space xenomai library is installed at /user/xenomai
* For this realtime issue, you can build everything by yourself or install prebuilt packages here: https://www.raspberrypi.org/forums/viewtopic.php?f=71&t=74686
* From your raspberry pi box:

      git clone -b rpi01-xenomai-2 git://github.com/thanhtamh/soem-w5500-rpi.git
      cd soem-w5500-rpi
      chmod +x *.sh
      ./build.sh
        
**TEST:**
* Check information of all slaves on bus:

      cd test/slaveInfo/
      sudo ./slaveinfo wiz
	
* Check pdo mapping of all slaves on bus:

      cd test/slaveInfo/
      sudo ./slaveinfo wiz -map

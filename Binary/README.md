# Release Version

Recommend Version for the new project is 1.1.2.0.<BR>
AT+CIUPDATE<BR>
An OTA URL is http://wiki.wiznet.io/download/WizFi360/O11/WizFi360_SDK.img.<BR>

Recommend Version for existing project is 1.0.7.5.<BR>
AT+CIUPDATE<BR>
An OTA URL is http://wiki.wiznet.io/download/WizFi360/WizFi360_SDK.img.<BR>

## Released 1.1.2.0<BR>
 20230412<BR>

1. Fixed Station mode & AP mode password related bugs caused by memory storage defect

## Released 1.1.1.9<BR>
 20220905<BR>

1. Modified the length of 'AT+AZSET' input parameter register ID from 64 to 128

## Released 1.1.1.8<BR>
 20220628<BR>

1. Added +MQTTPUBSEND sending binary data

2. Added +MQTTQOS settings QoS configuration

3. Fixed response bugs when connecting Station to WizFi360 set with SoftAP

4. Modified Change topic while connecting to a broker

## Released 1.1.1.7<BR>
 20210504<BR>

1. Removed unnecessary debug outputs

2. Added more ciphersuite support

3. Patched SSL socket close function

4. Fixed double print in "AT+CIPCLOSE"

5. Added semaphore for UART to TCP, SSL, MQTT

6. Fixed "AT+MQTTSET?" bugs

## Released 1.1.1.2<BR>
 20210107<BR>

1. Fix bug related to link ID 0 closure when others socket are closed by external reasons (AT+CIPMUX=1)

2. Update AT+MQTTCON: <linkID> parameter added when AT+CIPMUX=1

## Released 1.1.1.1<BR>
 20201224<BR>

1. Fixed bugs related to SPI, CWDHCP_DEF command

## Released 1.1.1.0<BR>
 20201006<BR>

1. Fixed bugs related to data transmission AT commands

## Released 1.0.7.5<BR>
 20201006<BR>

1. Fixed bugs related to data transmission AT commands

## Released 1.1.0.9<BR>
 20200911<BR>

1. Fixed Wi-Fi connection can be made even if SSID is used as a special character

	Wi-Fi connection and auto connection using web server configuration.

2. Fixed AT command array size

## Released 1.0.7.4<BR>
 20200911<BR>

1. Fixed Wi-Fi connection can be made even if SSID is used as a special character

	Wi-Fi connection and auto connection using web server configuration.

## Released 1.1.0.8<BR>
 20200903<BR>

1. Added sub topic 2, max 5 sub topic

2. Added MQTTPUBDEX command

3. Added AWS MQTT topic 4 in AWS application initialization function

4. Fixed hostif task stack size(If SPI SSL connect, stack overflow occurs)

5. Fixed auto connection sequence when using AT command "AT+SAVETRANSLINK"

	UDP auto connection was defective.

6. Fixed "AT+CWSAP"

	Fixed the maximum number of stations are connected to SoftAP.

7. Fixed defects that do not set the maximum number of stations are connected to SoftAP

## Released 1.0.7.3<BR>
 20200903<BR>

1. Fixed AT+CWSTARTSMART

	When it started web server, Wi-Fi mode variable was still Station. And it had printed Staion IP on Command CIFSR.

2. Added error message of auto connect

	When it prepared auto connect, there was no message of the reason for failure.

3. Fixed auto connection & transparent mode sequence when using AT command "AT+SAVETRANSLINK"

	UDP auto connection & transparent mode was defective.

4. Fixed "AT+CWSAP"

	Fixed the maximum number of stations are connected to SoftAP.

## Released 1.1.0.7<BR>
 20200413<BR>
 For the new project<BR>

1.  Added AT+AWSCON<BR>

2.  Added AT+AWSPKSEND<BR>

3.  Added AT+CLICASEND<BR>

4.  Fixed AutoConnect<BR>
    When it connected to AP automatically, it didn't back up mode value of parameters, so the wrong value(0) was written to flash. After reset, its mode value of parameters was 0, and then it didn't try to connect to AP automatically.

## Released 1.1.0.6<BR>
 20200309<BR>
 For the new project<BR>

1.  Added AT+WIZ_NETCONFIG<BR>
    WebServer for setting SSID/PWD(Default 192.168.36.1).<BR>

2.  Modified AT+CWSTARTSMART<BR>
    AT+CWSTARTSMART=#1<BR>

    #1: 1<=Try cnt<=60 (Minutes)<BR>
    If failed to connect via Airkiss, the WizFi360 start WebServer(Default 192.168.36.1).<BR>

    Example:<BR>
    AT+CWSTARTSMART=3 : Try Airkiss 3 times<BR>

    AT+CWSTARTSMART : Unlimited try Airkiss<BR>

    The LED(PB_07) is blinking fast during running Oneshot via Airkiss.<BR>
    The LED(PB_07) is blinking slowly during running Oneshot via WebServer.<BR>
    It prints messages to UART1 like below.<BR>

    AT+CWSTARTSMART=2\r\n<BR>
    \r\n<BR>
    OK\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:Try:1/2\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:Try:2/2\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:WebCfgStart\r\n<BR>

3.  AT+CIUPDATE<BR>
    An OTA URL is changed to http://wizwiki.net/download/WizFi360/O11/WizFi360_SDK.img.<BR>

    If you want to update to Version 1.0.x.x, run AT+CIUPDATE="http://wizwiki.net/download/WizFi360/WizFi360_SDK.img"\r\n

## Released 1.0.7.2<BR>
 20200309<BR>
 For existing project<BR>

1.  Added AT+WIZ_NETCONFIG<BR>
    WebServer for setting SSID/PWD(Default 192.168.36.1).<BR>

2.  Modified AT+CWSTARTSMART<BR>
    AT+CWSTARTSMART=#1,#2<BR>
    #1: 1 : ESP-TOUCH<BR>
    #1: 2 : Airkiss<BR>
    #1: 3 : ESP-TOUCH and Airkiss<BR>

    #2: 1<=Try cnt<=60 (Minutes)<BR>
    If failed to connect via ESP-TOUCH/Airkiss, the WizFi360 start WebServer(Default 192.168.36.1).<BR>

    Example:<BR>
    AT+CWSTARTSMART=2,3 : Try Airkiss 3 times<BR>

    AT+CWSTARTSMART : Unlimited try AT+CWSTARTSMART=3<BR>

    The LED(PB_07) is blinking fast during running Oneshot via ESP-TOUCH/Airkiss.<BR>
    The LED(PB_07) is blinking slowly during running Oneshot via WebServer.<BR>
    It prints messages to UART1 like below.<BR>

    AT+CWSTARTSMART=2\r\n<BR>
    \r\n<BR>
    OK\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:Try:1/2\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:Try:2/2\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:WebCfgStart\r\n<BR>

3.  AT+CIUPDATE<BR>
    An OTA URL is http://wizwiki.net/download/WizFi360/WizFi360_SDK.img.<BR>
    If you want to update to Version 1.1.x.x, run AT+CIUPDATE="http://wizwiki.net/download/WizFi360/O11/WizFi360_SDK.img"\r\n

## Released 1.1.0.5<BR>
 20200207<BR>

 When the pin PB13 is low level in booting, the WizFi360 runs to SPI mode.<BR>
 Then you cannot use UART to run AT Command and to receive.<BR><BR>

1.  AT+CIUPDATE<BR>
    An OTA URL is http://wizwiki.net/download/WizFi360/WizFi360_SDK.img.<BR>
    If you want to update to Version 1.1.x.x, run AT+CIUPDATE="http://wizwiki.net/download/WizFi360/O11/WizFi360_SDK.img"\r\n

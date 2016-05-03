---
author: joshbax-msft
title: WLAN Association Tests - WPA2\_PSK\_TTLS\_TKIP\_AES - Reliability
description: WLAN Association Tests - WPA2\_PSK\_TTLS\_TKIP\_AES - Reliability
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 212c8124-21e1-421a-902b-766839fa2286
---

# WLAN Association Tests - WPA2\_PSK\_TTLS\_TKIP\_AES - Reliability


This test suite validates the WLAN associations.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Network.WLAN.Base.MeetScanAndConnReq Device.Network.WLAN.CSBBase.MeetScanAndConnReq Device.Network.WLAN.CSBNLO.SupportNetworkListOffload Device.Network.WLAN.NLO.SupportNetworkListOffload</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows RT (ARM-based) Windows 8 (x64) Windows 8 (x86) Windows RT 8.1 Windows 8.1 x64 Windows 8.1 x86</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~20 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification Reliability</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [Wireless LAN (802.11) Testing Prerequisites](wireless-lan--80211--testing-prerequisites.md).

This test suite performs the following actions:

-   Sets up two routers (Router 0 and Router 1) as follows:

    -   Router 0 – 2.4Ghz : WPA2PSK/AES/G/Channel 1

    -   Router 0 – 5Ghz : WPA2PSK /TKIP/N/Channel 40

    -   Router 1 – 2.4Ghz : WPA2Enterprise (TTLS-EAPMSCHAPV2)/TKIP/G/Channel 11

    -   Router 1 – 5Ghz : WPA2Enterprise (TTLS-EAPMSCHAPV2)/TKIP/N/Channel 36

-   Disables Router 0 2.4Ghz and 5Ghz beacon.

-   Turns on all radios.

-   Creates a TCP server on the access point (AP) controller server.

-   Creates a profile for 2.4 GHz on router 0 with ConnectionMode configured as manual.

-   Stops the Remote Authentication Dial In User Service (RADIUS) server if it is running. Creates a RADIUS server on the AP controller for router 0 at 2.4 GHz.

-   WlanConnect using the profile.

-   Waits for WlanConnect to complete by using WLAN notifications.

-   Registers for NLM events.

-   After the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   Use the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 0 at 2.4 GHz.

-   Establishes a connection to the TCP Server on the AP controller server.

-   Creates a profile for 5 GHz on router 1 with ConnectionMode configured as Auto.

-   Stops the RADIUS server if it is running. Creates a RADIUS server on the AP controller for router 0 at 5 GHz.

-   Polls for WLAN notifications.

-   Turns off the 2.4 GHz radio on router 0 and the 5 GHz radio on router 1.

-   After a WLAN connected notification is received and the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   Use the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 1 at 5 GHz

-   Establishes a connection to the TCP Server on AP controller server.

-   Creates a profile for 5 GHz on router 0 with ConnectionMode configured as Auto.

-   Stops the RADIUS server if it is running. Creates a RADIUS server on the AP controller for router 1 at 5 GHz.

-   Polls for WLAN notifications.

-   Turns off the 5 GHz radios on router 0 and router 1.

-   After a WLAN connected notification is received and the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   Use the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 0 at 5 GHz.

-   Establishes a connection to the TCP Server on AP controller server.

-   Creates a profile for 2.4 GHz on router 1 with ConnectionMode configured as Auto.

-   Stops the RADIUS server if it is running. Creates a RADIUS server on the AP controller for router 1 at 2.4 GHz.

-   Polls for WLAN notifications.

-   Turns off the 5 GHz radio on router 0 and the 2.4 GHz radio on router 1.

-   After a WLAN connected notification is received and the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   Use the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 0 at 5 GHz.

If the device supports S3 or S4 sleep states, the following tests are performed. They are repeated for each supported sleep state.

-   Set up two routers (Router 0 and Router 1).

-   Turns on all radios.

-   Creates a profile for 2.4 GHz on router 0 with ConnectionMode configured as manual.

-   Stops the RADIUS server if it is running. Creates a RADIUS server on the AP controller for router 0 at 2.4 GHz.

-   WlanConnect using the profile.

-   Waits for WlanConnect to complete by using WLAN notifications.

-   Registers for NLM events.

-   After the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   Use the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 0 at 2.4 GHz.

-   Establishes a connection to the TCP Server on AP controller server.

-   Creates a profile for 5 GHz on router 1 with ConnectionMode configured as Auto.

-   Stops the RADIUS server if it is running. Creates a RADIUS server on the AP controller for router 0 at 5 GHz.

-   Polls for WLAN notifications.

-   Turns off the 2.4 GHz radio on router 0.

-   Puts the device in either S3 or S4 sleep state for 30 seconds.

-   Turns on the 5 GHz radio on router 1.

-   After a WLAN connected notification is received and the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   UseValidate by using the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 1 at 5 GHz.

-   Establishes a connection to the TCP Server on AP controller server.

-   Creates a profile for 5 GHz on router 0 with ConnectionMode configured as Auto.

-   Stops the RADIUS server if it is running. Creates a RADIUS server on the AP controller for router 1 at 5 GHz.

-   Polls for WLAN notifications.

-   Turns off the 5 GHz radios on router 1.

-   Puts the device in either S3 or S4 sleep state for 30 seconds.

-   Turns on the 5 GHz radios on router 0

-   After a WLAN connected notification is received and the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   Use the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 0 at 5 GHz.

-   Establishes a connection to the TCP Server on AP controller server.

-   Creates a profile for 2.4 GHz on router 1 with ConnectionMode configured as Auto.

-   Stops the RADIUS server if it is running. Creates a RADIUS server on the AP controller for router 1 at 2.4 GHz.

-   Polls for WLAN notifications.

-   Turns off the 5 GHz radio on router 0.

-   Puts the device in either S3 or S4 sleep state for 30 seconds.

-   Turns on the 5 GHz radios on router 0.

-   After a WLAN connected notification is received and the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   Use the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 0 at 5 GHz.

-   Turns on all radios.

-   Delete all profiles that were Createsd.

The following tests are performed for both the 2.4 GHz and 5 GHz frequency on router 0 and router 1:

-   Delete all profiles that were Createsd.

-   Disconnect any existing connections on the test adapter.

-   Establishes a connection to the TCP Server on AP controller server.

-   Stops the RADIUS server if it is running. Creates a RADIUS server on the AP controller for the router at the specified bandwidth.

-   Creates a profile for the router at the specific bandwidth with connectionMode configured as Auto

-   Registers for NLM events.

-   After a WLAN connected notification is received and the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   Use the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 0 at 5 GHz.

-   Establishes a connection to the TCP Server on AP controller server.

-   Puts the device in the specified sleep state for 30 seconds.

-   Registers for NLM events.

-   After a WLAN connected notification is received and the NLM notifies that LAN connectivity is available on the test adapter interface, polls the TCP server on the AP controller server to confirm that full network connectivity is available.

-   Use the WLAN API GetConnectionAttributes to confirm that the association is correct and the connection is to router 0 at 5 GHz.

-   Puts the device in the specified sleep state for 30 seconds.

## Troubleshooting


For troubleshooting information, see [Troubleshooting Wireless LAN (802.11) Tests](troubleshooting-wireless-lan--80211--tests.md).

## More information


### Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>TestDeviceSupports5ghz</strong></p></td>
<td><p>Determine if the router supports 5 GHz.</p>
<p>Default value: true</p></td>
</tr>
<tr class="even">
<td><p><strong>AP1Password</strong></p></td>
<td><p>The root password for the first AP.</p>
<p>Default value: password</p></td>
</tr>
<tr class="odd">
<td><p><strong>AP1IPAddress</strong></p></td>
<td><p>The IP address of the first AP.</p>
<p>Default value: 192.168.2.2</p></td>
</tr>
<tr class="even">
<td><p><strong>AP2Password</strong></p></td>
<td><p>The root password for the first AP.</p>
<p>Default value: password</p></td>
</tr>
<tr class="odd">
<td><p><strong>AP2IPAddress</strong></p></td>
<td><p>The IP address of the first AP.</p>
<p>Default value: 192.168.2.3</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableTracing</strong></p></td>
<td><p>Default value: No</p></td>
</tr>
</tbody>
</table>

 

## Related topics


[Wireless LAN (802.11) Tests](wireless-lan--80211--tests.md)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_hck\p_hck%5D:%20WLAN%20Association%20Tests%20-%20WPA2_PSK_TTLS_TKIP_AES%20-%20Reliability%20%20RELEASE:%20%284/27/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





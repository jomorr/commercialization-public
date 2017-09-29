---
title: Microsoft-Windows-Wlansvc
description: Microsoft-Windows-Wlansvc
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 59efff83-392d-4777-b8db-2f70000d2d47
ms.mktglfcycl: deploy
ms.sitesec: msdn
ms.author: alhopper
ms.date: 05/02/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-oem
---

# Microsoft-Windows-Wlansvc


The Microsoft-Windows-Wlansvc component implements:

-   System capabilities for Wi-Fi adapters, which are new for Windows 10. These system capabilities are added at image time to ensure that the information is at its most accurate. The capabilities allow the OS to have a better understanding of the underlying hardware that it's running on. Telemetry data is generated by the system to provide data that can be used to diagnose both software and hardware issues.

    OEMs or ODMs can configure the system capabilities for Wi-Fi adapters to accurately provide the information during image creation time. These system capabilities are different from device capabilities, which the IHV that developed the WLAN driver, provides. System capabilities are only locked down after the OEM or ODM has assembled a complete system and an understanding of the WLAN radio is available. For example, an OEM can configure a 2X2 WLAN device as a 1X1 device so the OEM must relay this configuration information to the OS using the system capabilities.

    If OEMs or ODMs don't use these system capabilities or no additional input is registered by the OS, the OS will not generate any default values to store in the registry.

    The settings you can use to enable system capabilities for Wi-Fi adapters are: `CoexistenceSupport`, `NumAntennaConnected`, `SimultaneousMultiChannelSupported`, `WLANFunctionLevelDeviceResetSupported`, and `WLANPlatformLevelDeviceResetSupported`.

    The following example shows how you can configure these settings:

    ```
    <component name="Microsoft-Windows-Wlansvc" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
         <NumAntennaConnected>2</NumAntennaConnected>            
         <CoexistenceSupport>1</CoexistenceSupport>
         <SimultaneousMultiChannelSupport>2</ SimultaneousMultiChannelSupport>
         <WLANFunctionLevelDeviceResetSupported>1</WLANFunctionLevelDeviceResetSupported>
         <WLANPlatformLevelDeviceResetSupported>0</WLANPlatformLevelDeviceResetSupported>
    </component>
    ```

-   The `RadioLocation` setting, which specifies the location of the radio feature when a wireless local area network (LAN) connection is used.

## Child elements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[CoexistenceSupport](microsoft-windows-wlansvc-coexistencesupport.md)</p></td>
<td><p>Specifies the type of co-existence that's supported on the device:</p>
<ul>
<li><strong>Both</strong> - Both Wi-Fi and Bluetooth work at the same performance level during co-existence.</li>
<li><strong>Wi-Fi reduced</strong> - On a 2X2 system, Wi-Fi performance is reduced to 1X1 level.</li>
<li><strong>Bluetooth centered</strong> - When co-existing, Bluetooth has priority and restricts Wi-Fi performance.</li>
<li><strong>One</strong> - Either Wi-Fi or Bluetooth will stop working.</li>
</ul></td>
</tr>
<tr class="even">
<td><p>[NumAntennaConnected](microsoft-windows-wlansvc-numantennaeconnected.md)</p></td>
<td><p>Specifies the number of antennas that are connected to the WLAN radio.</p></td>
</tr>
<tr class="odd">
<td><p>[RadioLocation](microsoft-windows-wlansvc-radiolocation.md)</p></td>
<td><p><code>RadioLocation</code> provides instructions to users for enabling the wireless local area network (WLAN) hardware. These instructions are displayed when a wireless connectivity problem is detected, for example, when a wireless adapter is turned off.</p></td>
</tr>
<tr class="even">
<td><p>[SimultaneousMultiChannelSupported](microsoft-windows-wlansvc-simultaneousmultichannelsupported.md)</p></td>
<td><p>Specifies the maximum number of channels that the Wi-Fi device can simultaneously operate on. For example, you can use this to specify support for Station mode and Wi-Fi Direct GO on separate channels simultaneously.</p></td>
</tr>
<tr class="odd">
<td><p>[WLANFunctionLevelDeviceResetSupported](microsoft-windows-wlansvc-wlanfunctionalleveldevicereset.md)</p></td>
<td><p>Specifies whether the device supports functional level device reset (FLDR). The FLDR feature in the OS checks this system capability exclusively to determine if it can run.</p></td>
</tr>
<tr class="even">
<td><p>[WLANPlatformLevelDeviceResetSupported](microsoft-windows-wlansvc-wlanplatformleveldevicereset.md)</p></td>
<td><p>Specifies whether the device supports platform level device reset (PLDR). The PLDR feature in the OS checks this system capability exclusively to determine if it can run.</p></td>
</tr>
</tbody>
</table>

 

## Applies To


To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://msdn.microsoft.com/library/windows/hardware/dn915078).

## Related topics


[Components](components-b-unattend.md)

 

 







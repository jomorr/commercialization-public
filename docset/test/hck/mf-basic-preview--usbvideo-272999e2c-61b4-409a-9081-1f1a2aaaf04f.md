---
author: joshbax-msft
title: MF Basic Preview USBVideo 2
description: MF Basic Preview USBVideo 2
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 81328a23-d15a-4c86-85ca-8719dfa4c956
---

# MF Basic Preview USBVideo 2


This test is functionally equivalent to [MF Basic Preview base 2](mf-basic-preview--base-2cffa93f1-7362-449f-9893-3a00d179687b.md), which validates that the webcam works with Microsoft® Media Foundation (MF). This test runs if the device that you’re testing uses a driver that is not included with Windows. This test includes the same test cases as MF Basic Preview Test (Base).

For more information, see [MF Basic Preview base 2](mf-basic-preview--base-2cffa93f1-7362-449f-9893-3a00d179687b.md).

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Streaming.Webcam.NonMSDriver.VideoInfoHeader2</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows 8 (x64) Windows 8 (x86) Windows 8.1 x64 Windows 8.1 x86</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~420 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification Functional</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [Webcam Testing Prerequisites](webcam-testing-prerequisites.md).

## Troubleshooting


For troubleshooting information, see [Troubleshooting Device.Streaming Testing](troubleshooting-devicestreaming-testing.md).

## More information


### Parameters

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
<td><p>WDKDeviceID</p></td>
<td><p>Specifies the Plug and Play (PnP) ID of the device to be tested.</p>
<p>Example: \\?\root#media#0001#{65e8773d-8f56-11d0-a3b9-00a0c9223196}\global</p></td>
</tr>
</tbody>
</table>

 

### Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Command option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Te.exe WLKWebcamLogoTest.dll /p:DS=Table:captureEngineTests_taef.xml#CaptureEngine/select:@Data:TestCategory='Preview' /p:”DEVICE=[WDKDeviceID]”</strong></p></td>
<td><p>Runs the test.</p></td>
</tr>
</tbody>
</table>

 

### File list

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>File</th>
<th>Location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CaptureEngineTests_taef.xml</p></td>
<td><p><em>&lt;testbinroot&gt;</em>\nttest\MULTIMEDIATEST\CDSPTEST\CaptureWLK\</p></td>
</tr>
<tr class="even">
<td><p>WLKWebcamLogoTest.dll</p></td>
<td><p><em>&lt;testbinroot&gt;</em>\nttest\MULTIMEDIATEST\CDSPTEST\</p></td>
</tr>
<tr class="odd">
<td><p>Te.exe</p></td>
<td><p><em>&lt;testbinroot&gt;</em>\Testing\Runtimes\TAEF\x86\</p></td>
</tr>
</tbody>
</table>

 

 

 






---
author: joshbax-msft
title: NDISTest 6.5 - WlanWakeTests
description: NDISTest 6.5 - WlanWakeTests
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4ccc866f-cb50-4549-959d-ff6e2cf0e1b9
---

# NDISTest 6.5 - WlanWakeTests


This automated test suite verifies the different wake states.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Network.WLAN.Base.MeetScanAndConnReq Device.Network.WLAN.CSBBase.MeetScanAndConnReq Device.Network.WLAN.CSBWoWLAN.MustSupportWakeOnWLAN Device.Network.WLAN.WoWLAN.ImplementWakeOnWLAN</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows RT (ARM-based) Windows 8 (x64) Windows 8 (x86) Windows RT 8.1 Windows 8.1 x64 Windows 8.1 x86</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~8 minutes</p></td>
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


Before you run the test, complete the test setup as described in the test requirements: [Wireless LAN (802.11) Testing Prerequisites](wireless-lan--80211--testing-prerequisites.md).

The following suites are available:

-   PM\_LinkChange.cpp

-   PM\_Requirements.cpp

-   PM\_WoWlanFourWayHS.cpp

-   PM\_WoWlanGTKTestAp.cpp

The PM\_LinkChange.cpp suite consists of the following:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><ul>
<li><p>Connect to the access point.</p></li>
<li><p>Put the device into a low power state.</p></li>
<li><p>Turn off the access point.</p></li>
<li><p>Verify the device wakes and indicates NdisWakeReasonWlanAPAssociationLost.</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

The PM\_Requirements.cpp suite consists of the following:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VerifyBssidNotInScanList</p></td>
<td><ul>
<li><p>Verify power management support for the adapter being tested.</p></li>
<li><p>Verify Wake on LAN support (bitmap and magic packet) for the adapter being tested.</p></li>
<li><p>Verify Protocol Offload Support for the adapter being tested.</p></li>
<li><p>Verify Wake on LAN pattern capacity for the adapter being tested.</p></li>
<li><p>Verify No-Pause-On-Suspend for the adapter being tested.</p></li>
<li><p>Verify Wake-On-Media-Connect for the adapter being tested.</p></li>
<li><p>Verify Wake-On-Media-Disconnect for the adapter being tested.</p></li>
<li><p>Verify wake packet indication support for the adapter being tested.</p></li>
<li><p>Verify USB Selective Suspend for the adapter being tested.</p></li>
<li><p>Verify whether MiniportCheckForHang is allowed for the adapter being tested.</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

The PM\_WoWlanFourWayHS.cpp suite consists of the following:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><ul>
<li><p>Connect the DUT to an access point.</p></li>
<li><p>Set NDIS_WLAN_WAKE_ON_4WAY_HANDSHAKE_REQUEST_ENABLED on the DUT.</p></li>
<li><p>Put the DUT to sleep.</p></li>
<li><p>Start the 4 way HS from the access point.</p></li>
<li><p>Validate the DUT wakes up and indicates NdisWakeReasonWlan4WayHandshakeRequest.</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

The PM\_WoWlanGTKTestAp.cpp suite consists of the following:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VerifyBssidNotInScanList</p></td>
<td><ul>
<li><p>Connect the DUT to an access point.</p></li>
<li><p>Set NDIS_WLAN_WAKE_ON_GTK_HANDSHAKE_ERROR_ENABLED on the DUT.</p></li>
<li><p>Put the DUT to sleep.</p></li>
<li><p>Send a GTK message that is not valid.</p></li>
<li><p>Verify wake and indication.</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## Troubleshooting


For troubleshooting information, see [Troubleshooting Wireless LAN (802.11) Tests](troubleshooting-wireless-lan--80211--tests.md).

 

 






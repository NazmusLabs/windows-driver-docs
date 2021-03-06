---
title: OID_DOT11_WFD_CONNECT_TO_GROUP_REQUEST
author: windows-driver-content
description: When set, the OID_DOT11_WFD_CONNECT_TO_GROUP_REQUEST object identifier (OID) requests that the miniport driver perform a connection operation to join a Wi-Fi Direct (WFD) group.
ms.assetid: 67B02FD9-1CB2-424D-989C-11A307070B93
ms.author: windowsdriverdev
ms.date: 08/08/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
keywords: 
 -OID_DOT11_WFD_CONNECT_TO_GROUP_REQUEST Network Drivers Starting with Windows Vista
---

#  OID\_DOT11\_WFD\_CONNECT\_TO\_GROUP\_REQUEST


**Important**  The [Native 802.11 Wireless LAN](https://msdn.microsoft.com/library/windows/hardware/ff560690) interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see [WLAN Universal Windows driver model](https://msdn.microsoft.com/library/windows/hardware/dn897672).

 

When set, the OID\_DOT11\_WFD\_CONNECT\_TO\_GROUP\_REQUEST object identifier (OID) requests that the miniport driver perform a connection operation to join a Wi-Fi Direct (WFD) group. The operation for this OID is identical to that of an [OID\_DOT11\_CONNECT\_REQUEST](oid-dot11-connect-request.md) request for an Extensible Station (ExtSTA) port. For more information about the connection operation, see [Connection Operations](https://msdn.microsoft.com/library/windows/hardware/ff545185).

No data is associated with this OID.

If the connection operation completes successfully, the miniport driver must transition to the WFD client operational (OP) state. The miniport driver must remain in the WFD client OP state until either a method request of [OID\_DOT11\_RESET\_REQUEST](oid-dot11-reset-request.md) or set request of [OID\_DOT11\_WFD\_DISCONNECT\_FROM\_GROUP\_REQUEST](oid-dot11-wfd-disconnect-from-group-request.md) is made. For more information about this state, see [Extensible Station Operating States](https://msdn.microsoft.com/library/windows/hardware/ff549883).

When OID\_DOT11\_WFD\_CONNECT\_TO\_GROUP\_REQUEST is set, the miniport driver must fail the request by returning **NDIS\_STATUS\_POWER\_STATE\_INVALID** from its [*MiniportOidRequest*](https://msdn.microsoft.com/library/windows/hardware/ff559416) function if any of the following are true:

-   All of the PHYs specified through the ExtSTA *msDot11DesiredPhyList* MIB object are turned off through sets of [OID\_DOT11\_NIC\_POWER\_STATE](oid-dot11-nic-power-state.md). For more information about this MIB object, see [OID\_DOT11\_DESIRED\_PHY\_LIST](oid-dot11-desired-phy-list.md).

-   All of the PHYs specified through the ExtSTA *msDot11DesiredPhyList* MIB object are turned off through a hardware switch setting or proprietary software setting.

-   Additional criteria apply for the connection request to fail, as described in [General Connection Operation Guidelines](https://msdn.microsoft.com/library/windows/hardware/ff552458).

When OID\_DOT11\_WFD\_CONNECT\_TO\_GROUP\_REQUEST is set, the miniport driver can do one of the following:

-   Wait for the connection operation to complete before completing the set request.

-   Initiate the connection operation and complete the set request. In this situation, the miniport driver must return **NDIS\_STATUS\_PENDING** from its [*MiniportOidRequest*](https://msdn.microsoft.com/library/windows/hardware/ff559416) function after initiating the connection operation. After the reset operation has finished, the miniport driver completes the set request by calling [**NdisMRequestComplete**](https://msdn.microsoft.com/library/windows/hardware/ff563622).

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version</p></td>
<td><p>Versions: Supported in Windows 8.</p></td>
</tr>
<tr class="even">
<td><p>Header</p></td>
<td>Windot11.h (include Windot11.h)</td>
</tr>
</tbody>
</table>

## See also


[OID\_DOT11\_CONNECT\_REQUEST](oid-dot11-connect-request.md)

[OID\_DOT11\_RESET\_REQUEST](oid-dot11-reset-request.md)

[OID\_DOT11\_WFD\_DISCONNECT\_FROM\_GROUP\_REQUEST](oid-dot11-wfd-disconnect-from-group-request.md)

 

 





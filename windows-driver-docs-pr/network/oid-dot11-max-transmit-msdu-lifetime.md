---
title: OID_DOT11_MAX_TRANSMIT_MSDU_LIFETIME
author: windows-driver-content
description: OID_DOT11_MAX_TRANSMIT_MSDU_LIFETIME
ms.assetid: fb129074-6078-48b6-8043-e6296ec831d4
ms.author: windowsdriverdev
ms.date: 08/08/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
keywords: 
 -OID_DOT11_MAX_TRANSMIT_MSDU_LIFETIME Network Drivers Starting with Windows Vista
---

# OID\_DOT11\_MAX\_TRANSMIT\_MSDU\_LIFETIME


**Important**  The [Native 802.11 Wireless LAN](https://msdn.microsoft.com/library/windows/hardware/ff560690) interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see [WLAN Universal Windows driver model](https://msdn.microsoft.com/library/windows/hardware/dn897672).

 

When queried, the OID\_DOT11\_MAX\_TRANSMIT\_MSDU\_LIFETIME object identifier (OID) requests that the miniport driver return the value of the IEEE 802.11 **dot11MaxTransmitMSDULifetime** MIB object.

The **dot11MaxTransmitMSDULifetime** MIB object specifies the maximum time that the 802.11 station can spend transmitting all management protocol data unit (MPDU) fragments for a management service data unit (MSDU) packet.

The data type for OID\_DOT11\_MAX\_TRANSMIT\_MSDU\_LIFETIME is a ULONG value that specifies the maximum transmit lifetime in 802.11 time units (TU). One TU is 1024 microseconds. The value of the **dot11MaxTransmitMSDULifetime** MIB object must be from 1 through 4294967295.

If the maximum transmit lifetime expires before the transmission of the MSDU packet has completed, the miniport driver must do the following:

-   Discard the MSDU packet.

-   If the miniport driver is operating in Extensible Station (ExtSTA) mode, increment the **ullMaxTXLifetimeExceededCount** member of the DOT11\_STATISTICS structure. For more information about this structure, see [OID\_DOT11\_STATISTICS](oid-dot11-statistics.md).

**Note**  A Native 802.11 miniport driver that is designed to run on the Windows Vista or Windows Server 2008 operating systems must always reset this 802.11 MIB OID to its default value. This is the case regardless of the value of the **bSetDefaultMIB** member of the DOT11\_RESET\_REQUEST structure. This requirement applies to a miniport driver that, in a call to the **NdisMSetMiniportAttributes** function, sets **MiniportAttributes**-&gt; **Native\_802\_11\_Attributes** -&gt; **Header** -&gt; **Revision** to NDIS\_MINIPORT\_ADAPTER\_802\_11\_ATTRIBUTES\_REVISION\_1.

 

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
<td><p>Available in Windows Vista and later versions of the Windows operating systems.</p></td>
</tr>
<tr class="even">
<td><p>Header</p></td>
<td>Windot11.h (include Ndis.h)</td>
</tr>
</tbody>
</table>

## See also


[Native 802.11 MIB OIDs](https://msdn.microsoft.com/library/windows/hardware/ff560645)

[Native 802.11 Wireless LAN OIDs](https://msdn.microsoft.com/library/windows/hardware/ff560691)

 

 





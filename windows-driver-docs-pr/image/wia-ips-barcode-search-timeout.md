---
title: WIA\_IPS\_BARCODE\_SEARCH\_TIMEOUT
description: The WIA\_IPS\_BARCODE\_SEARCH\_TIMEOUT property describes the maximum time to search for barcodes on a document page.
ms.assetid: 3EE6C492-722E-439A-8BB5-03496DAC78D2
keywords: ["WIA_IPS_BARCODE_SEARCH_TIMEOUT Imaging Devices"]
topic_type:
- apiref
api_name:
- WIA_IPS_BARCODE_SEARCH_TIMEOUT
api_location:
- Wiadef.h
api_type:
- HeaderDef
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# WIA\_IPS\_BARCODE\_SEARCH\_TIMEOUT


The **WIA\_IPS\_BARCODE\_SEARCH\_TIMEOUT** property describes the maximum time to search for barcodes on a document page.

## <span id="ddk_wia_ipa_depth_si"></span><span id="DDK_WIA_IPA_DEPTH_SI"></span>


Property Type: VT\_I4

Valid Values: WIA\_PROP\_RANGE

Access Rights: Read/Write

Remarks
-------

The time unit is not specified (it can be milliseconds or tenths of a second, for example) but the application can choose values in the minimum – maximum range reported by the WIA minidriver.

This property is required for all Barcode Reader items. The property can be implemented to support a range that contain one single value (meaning that the application cannot change this timeout).

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Header</p></td>
<td>Wiadef.h (include Wiadef.h)</td>
</tr>
</tbody>
</table>

 

 






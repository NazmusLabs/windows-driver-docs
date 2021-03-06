---
title: Rectangle Area Fill Commands
author: windows-driver-content
description: Rectangle Area Fill Commands
ms.assetid: b9401126-4173-4187-960a-dc5ce69d3522
keywords:
- rectangular area fill commands WDK Unidrv
- filling rectangular areas WDK Unidrv
ms.author: windowsdriverdev
ms.date: 04/20/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# Rectangle Area Fill Commands


## <a href="" id="ddk-rectangle-area-fill-commands-gg"></a>


The following table lists the rectangle area fill commands. All commands are specified using [command entry format](command-entry-format.md).

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Command</th>
<th>Description</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CmdRectBlackFill</p></td>
<td><p>Command to black fill a rectangle.</p></td>
<td><p>Optional. If not specified, Unidrv attempts black fill by specifying the CmdRectGrayFill command with a gray percentage of *MaxGrayFill.</p></td>
</tr>
<tr class="even">
<td><p>CmdRectGrayFill</p></td>
<td><p>Command to gray fill a rectangle. (Does not erase the background.)</p></td>
<td><p>Optional. If not specified, Unidrv assumes no gray fill capability. Command string typically includes the GrayPercentage variable.</p></td>
</tr>
<tr class="odd">
<td><p>CmdRectWhiteFill</p></td>
<td><p>Command to white fill a rectangle. (Erases the background.)</p></td>
<td><p>Optional. If not specified, Unidrv assumes no erasing white fill. In that case, Unidrv returns failure if an application requests white fill, because gray fill cannot erase the background.</p></td>
</tr>
<tr class="even">
<td><p>CmdSetRectHeight</p></td>
<td><p>Command to set the rectangle height.</p></td>
<td><p>Optional. Must be specified if CmdSetRectWidth is specified.</p></td>
</tr>
<tr class="odd">
<td><p>CmdSetRectSize</p></td>
<td><p>Command to set the rectangle width and height.</p>
<p>Not supported for Windows 2000 or later.</p></td>
<td><p>Optional. Used for printers that set the width and height in one command.</p></td>
</tr>
<tr class="even">
<td><p>CmdSetRectWidth</p></td>
<td><p>Command to set the rectangle width.</p></td>
<td><p>Optional. Must be specified if CmdSetRectHeight is specified.</p></td>
</tr>
</tbody>
</table>

 

For examples, see the [sample GPD files](sample-gpd-files.md).

 

 





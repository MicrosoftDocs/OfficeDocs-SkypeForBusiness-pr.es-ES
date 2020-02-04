---
title: 'Lync Server 2013: configuración de intervalos de puertos de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80e835bfcf12495c75612ecee93d87cf3c421651
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Configuración de la configuración de intervalo de puertos de medios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

La configuración de intervalo de puertos de medios puede influir significativamente en el rendimiento del cliente y debe configurarse. Puede configurar estas opciones con el shell de administración de Lync Server.

### <a name="media-port-range-settings"></a>Configuración de intervalo de puertos de medios

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración</th>
<th>Descripción</th>
<th>Cmdlet del shell de administración de Lync Server</th>
<th>Parámetros del cmdlet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Especifica si el cliente debe usar los intervalos de puertos enviados por el servidor para multimedia y para la señalización. Se usa junto con los subvalores MinMediaPort y MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Especifica el número de puerto de inicio que se va a usar para los medios. Se combina con MaxMediaPort para especificar el rango de puertos. El intervalo mínimo recomendado es 40 puertos.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (representa el número de puerto de inicio para usar en los medios del cliente)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Especifica el número de puerto más alto que se debe usar para los medios. Se combina con MinMediaPort para especificar el rango de puertos. El intervalo mínimo recomendado es 40 puertos.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (indica el número total de puertos disponibles para los medios de cliente; el valor predeterminado es 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>Para configurar las opciones de intervalo de puertos de medios

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente cmdlet:
    
        Get-CsConferencingConfiguration
    
    Este cmdlet devuelve la configuración de la Conferencia.

3.  Ejecute el siguiente cmdlet con los parámetros y valores que desea cambiar (para obtener información detallada sobre los parámetros para este cmdlet, consulte la documentación del shell de administración de Lync Server):
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > Puede crear más conjuntos de parámetros de configuración de conferencias para sitios específicos. Use el cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> con una identidad de sitio. Al crear nuevas opciones de configuración de conferencias para sitios, la configuración del sitio tiene prioridad sobre la configuración global. Para obtener más información, consulte la documentación del shell de administración de Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


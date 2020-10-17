---
title: 'Lync Server 2013: configuración de intervalos de puertos de medios'
description: 'Lync Server 2013: configuración del intervalo de puertos de medios.'
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
ms.openlocfilehash: 1a7670284c593197068c366f43bbb3faaaad8f63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570746"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Configuración de intervalos de puertos de medios en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

La configuración del intervalo de puertos de medios puede afectar significativamente al rendimiento del cliente y debe configurarse. Puede configurar estas opciones mediante el shell de administración de Lync Server.

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
<th>Cmdlet de Shell de administración de Lync Server</th>
<th>Parámetros del cmdlet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Especifica si el cliente debe usar los intervalos de puertos enviados por el servidor para medios y señalización. Se usa junto con los subvalores MinMediaPort y MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>Los parámetros clientmediaportrangeenabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Especifica el número de Puerto inicial que se va a usar para los medios. Se combina con MaxMediaPort para especificar el intervalo de puertos. El intervalo mínimo recomendado es de 40 puertos.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (representa el número inicial de puerto que debe usarse para los medios de cliente)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Especifica el número de puerto más alto que se va a usar para los medios. Se combina con MinMediaPort para especificar el intervalo de puertos. El intervalo mínimo recomendado es de 40 puertos.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (indica el número total de puertos disponibles para los medios de cliente; el valor predeterminado es 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>Para configurar las opciones de intervalo de puertos de medios

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente cmdlet:
    
        Get-CsConferencingConfiguration
    
    Este cmdlet devuelve las opciones de configuración de conferencia.

3.  Ejecute el siguiente cmdlet con los parámetros y valores que desee cambiar (para obtener información detallada sobre los parámetros de este cmdlet, consulte la documentación del shell de administración de Lync Server):
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > Puede crear conjuntos adicionales de opciones de configuración de conferencia para sitios específicos. Use el cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> con una identidad de sitio. Al crear nuevas opciones de configuración de conferencia para los sitios, la configuración del sitio tiene prioridad sobre la configuración global. Para obtener más información, vea la documentación referente a Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Crear o modificar una colección de opciones de configuración del servidor perimetral A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faff058e2d4e2ef3a874ad5fcece3ad1422605c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de opciones de configuración del servidor perimetral A/V en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V constituye un modo de que los usuarios internos (aquellos que han iniciado sesión en la red de la organización) puedan compartir audio y vídeo con los usuarios externos (aquellos que no han iniciado sesión en la red de la organización). El servicio perimetral A/V se administra principalmente a mediante la configuración de servidor perimetral A/V, que se puede definir en el ámbito de sitio o en el ámbito de servicio (esto es, se puede configurar para un solo servidor perimetral A/V).

Al instalar Lync Server, se crea una colección global de opciones de configuración perimetral A/V. Además, puede usar Windows PowerShell y el cmdlet New-CsAVEdgeConfiguration para crear una nueva configuración en el ámbito de sitio o en el ámbito de servicio (es decir, para un servidor perimetral A/V individual). Si crea nuevos valores, tenga en cuenta que:

  - Los valores configurados en el ámbito del servicio (es decir, en un servidor individual) tienen prioridad sobre todo.

  - 
Las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones configuradas en el ámbito global. Pero las opciones del ámbito de servicio tienen prioridad sobre las opciones del ámbito de sitio.

  - Se usarán los valores del ámbito global solo si no hay valores del servicio configurados en el servidor individual y si no hay ninguna valores del sitio para el sitio donde se encuentra el servidor.

Los valores pueden modificarse después con el cmdlet Set-CsAVEdgeConfiguration. Para obtener más información, consulte los temas de ayuda para los cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) y [set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Para crear una nueva configuración perimetral a/V en el ámbito de sitio

  - El comando siguiente crea una nueva colección de valores de configuración del servicio perimetral A/V para el sitio Redmond.
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Para crear una configuración de servidor perimetral a/V personalizada en el ámbito de sitio

  - Ya que no se incluyeron parámetros adicionales, estos nuevos valores usarán los valores predeterminados para el servicio perimetral A/V. Como alternativa, puede agregar parámetros adicionales y valores de parámetros para crear una colección personalizada. Por ejemplo, este comando establece la propiedad MaxTokenLifetime en 4 horas (04 horas : 00 minutos : 00 segundos):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Para crear una configuración de servidor perimetral a/V personalizada en el ámbito de servicio

  - Este comando crea una colección similar aplicada al servidor perimetral A/V atl-edge-001.litwareinc.com:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Para modificar la configuración de servidor perimetral A/V existente

  - En este ejemplo, se usa el cmdlet de Set-CsAVEdgeConfiguration para cambiar la vigencia máxima del token en el sitio Redmond a 12 horas:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Vea también


[Devolver información de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Eliminar una colección existente de opciones de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


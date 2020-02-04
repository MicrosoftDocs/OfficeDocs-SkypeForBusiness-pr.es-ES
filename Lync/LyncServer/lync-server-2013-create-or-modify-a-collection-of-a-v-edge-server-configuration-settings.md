---
title: Crear o modificar una colección de parámetros de configuración del servidor perimetral A/V
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
ms.openlocfilehash: 5c4b45b34b5c52d0eb138fbc16c37e5aaee7262b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de valores de configuración del servidor perimetral A/V en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V proporciona a los usuarios internos (los usuarios que han iniciado sesión en la red de la organización) una forma de compartir audio y vídeo con usuarios externos (usuarios que no han iniciado sesión en la red de su organización). El servicio perimetral A/V se administra principalmente usando la configuración de borde de A/V, la configuración que se puede configurar en el ámbito del sitio o en el ámbito del servicio (es decir, se puede configurar para un servidor perimetral de A/V individual).

Al instalar Lync Server, se crea una colección global de las opciones de configuración del borde A/V. Además, puede usar Windows PowerShell y el cmdlet New-CsAVEdgeConfiguration para crear una nueva configuración en el ámbito del sitio o en el ámbito del servicio (es decir, para un servidor perimetral A/V individual). Si crea una nueva configuración, tenga en cuenta lo siguiente:

  - La configuración establecida en el ámbito del servicio (es decir, en un servidor individual) tiene prioridad sobre todo.

  - La configuración establecida en el ámbito del sitio tiene prioridad sobre la configuración establecida en el ámbito global. Sin embargo, la configuración del ámbito del servicio también reemplaza la configuración del ámbito del sitio.

  - La configuración del ámbito global se usará solo si no hay ninguna configuración de servicio establecida en el servidor individual y no hay configuración de sitio para el sitio en el que se encuentra el servidor.

Después, cualquiera de la configuración se puede modificar mediante el cmdlet Set-CsAVEdgeConfiguration. Para obtener más información, consulte los temas de ayuda de los cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) y [set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Para crear una configuración de borde a/V nueva en el ámbito del sitio

  - El siguiente comando crea una nueva colección de valores de configuración de borde A/V para el sitio de Redmond:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Para crear una configuración de borde personalizada a/V en el ámbito del sitio

  - Dado que no se incluyeron parámetros adicionales, esta nueva configuración usará los valores predeterminados para el servicio de borde A/V. También puede agregar parámetros adicionales y valores de parámetro para crear una colección personalizada. Por ejemplo, este comando establece la propiedad MaxTokenLifetime en 4 horas (04 horas: 00 minutos: 00 segundos):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Para crear una configuración de borde personalizada a/V en el ámbito de servicio

  - Este comando crea una colección similar que se aplica al servidor perimetral A/V atl-edge-001.litwareinc.com:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Para modificar la configuración de borde a/V existente

  - En este ejemplo, el cmdlet Set-CsAVEdgeConfiguration se usa para cambiar la vigencia máxima del token para el sitio de Redmond a 12 horas:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Vea también


[Devolver información de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Eliminar una colección existente de valores de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Nuevo: CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


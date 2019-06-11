---
title: Eliminar una colección existente de parámetros de configuración del servidor perimetral A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af42c338cb7032231ce562ac2227ff4089729ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Eliminar una colección existente de valores de configuración del servidor perimetral A/V en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V proporciona a los usuarios internos (los usuarios que han iniciado sesión en la red de la organización) una forma de compartir audio y vídeo con usuarios externos (usuarios que no han iniciado sesión en la red de su organización). El servicio perimetral A/V se administra principalmente usando la configuración de borde de A/V, la configuración que se puede configurar en el ámbito del sitio o en el ámbito del servicio (es decir, se puede configurar para un servidor perimetral de A/V individual).

Al instalar Lync Server, se crea una colección global de las opciones de configuración del borde A/V. No se puede eliminar esta colección global. Sin embargo, puede usar Windows PowerShell y el cmdlet Remove-CsAVEdgeConfiguration para "restablecer" la colección global; eso simplemente significa que todos los valores de propiedad de la colección global se restablecerán a su valor predeterminado. Por ejemplo, si ha establecido la propiedad MaxTokenLifetime en 16 horas, esa propiedad se restablecerá a su valor predeterminado de 8 horas.

Sin embargo, las colecciones de configuración personalizadas que haya creado en el ámbito del sitio o en el ámbito del servicio se pueden eliminar con el cmdlet Remove-CsAVEdgeConfiguration. Si elimina la configuración del sitio, los servidores perimetrales A/V de ese sitio serán administrados por la configuración global. Si elimina la configuración de ámbito de servicio, ese servidor se administrará por la configuración del sitio, si existe, o por la configuración global, si no hay ninguna configuración de sitio disponible.

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Para restablecer la colección global

  - El siguiente comando restablece la colección global de valores de configuración de borde A/V:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Para quitar una colección del ámbito de sitio

  - Este comando quita la configuración del borde A/V que se aplica al sitio de Redmond:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Para quitar una colección del ámbito de servicio

  - Este comando quita la configuración aplicada al servidor perimetral A/V atl-edge-001.litwareinc.com:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Vea también


[Devolver información de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Crear o modificar una colección de valores de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


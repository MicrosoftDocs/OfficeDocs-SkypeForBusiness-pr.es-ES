---
title: Eliminar una colección existente de opciones de configuración del servidor perimetral A/V
description: Eliminar una colección existente de opciones de configuración del servidor perimetral A/V.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7fe444e8bcb7e7e8e2633e59c23aeb2e80e9b98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553626"
---
# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Eliminar una colección existente de opciones de configuración del servidor perimetral A/V en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V constituye un modo de que los usuarios internos (aquellos que han iniciado sesión en la red de la organización) puedan compartir audio y vídeo con los usuarios externos (aquellos que no han iniciado sesión en la red de la organización). El servicio perimetral A/V se administra principalmente a mediante la configuración de servidor perimetral A/V, que se puede definir en el ámbito de sitio o en el ámbito de servicio (esto es, se puede configurar para un solo servidor perimetral A/V).

Al instalar Lync Server, se crea una colección global de opciones de configuración perimetral A/V. Esta colección global no se puede eliminar. Sin embargo, puede usar Windows PowerShell y el cmdlet Remove-CsAVEdgeConfiguration para "restablecer" la colección global; Esto simplemente significa que todos los valores de propiedad de la colección global se restablecerán a su valor predeterminado. Por ejemplo, si ha establecido la propiedad MaxTokenLifetime para 16 horas, esa propiedad se restablecerá a su valor predeterminado de 8 horas.

En cambio, las colecciones de opciones de configuración personalizadas que haya creado (ya sea en el ámbito de sitio o de servicio) se pueden eliminar con el cmdlet Remove-CsAVEdgeConfiguration. Si elimina la configuración de sitio, los servidores perimetrales A/V de dicho sitio pasarán a administrarse mediante la configuración global y, si elimina la configuración de servicio, el servidor se administrará por medio de su configuración de sitio (si la hay) o por la configuración global (en caso de que no haya configuración de sitio disponible).

Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Para restablecer la colección global

  - Con el siguiente comando se restablece la colección global de la configuración de servidor perimetral A/V:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Para quitar una colección del ámbito de sitio

  - Con este comando se quita la configuración de servidor perimetral A/V que se ha usado en el sitio de Redmond:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Para quitar una colección del ámbito de servicio

  - Con este comando se quita la configuración utilizada en el servidor perimetral A/V atl-edge-001.litwareinc.com:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Consulte también


[Devolver información de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Crear o modificar una colección de opciones de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


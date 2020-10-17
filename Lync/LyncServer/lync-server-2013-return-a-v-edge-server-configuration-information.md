---
title: 'Lync Server 2013: obtener información de configuración del servidor perimetral A/V'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73a6460b6045d5f1f2e35afcf91af0ebdd9e2b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511387"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Devolver información de configuración del servidor perimetral A/V en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V constituye un modo de que los usuarios internos (aquellos que han iniciado sesión en la red de la organización) puedan compartir audio y vídeo con los usuarios externos (aquellos que no han iniciado sesión en la red de la organización). El servicio perimetral A/V se administra principalmente a mediante la configuración de servidor perimetral A/V, que se puede definir en el ámbito de sitio o en el ámbito de servicio (esto es, se puede configurar para un solo servidor perimetral A/V).

Para devolver información acerca de las opciones de configuración perimetral A/V que se usan en la organización, debe usar Windows PowerShell y el cmdlet Get-CsAVEdgeConfiguration. Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

La información devuelta desde el cmdlet Get-CsAVEdgeConfiguration tendrá un aspecto similar a este:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>Para devolver información de todas las opciones de configuración del servidor perimetral A/V

  - El siguiente comando devuelve información sobre todas las opciones de configuración del servidor perimetral A/V que actualmente usa la organización:
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>Para devolver información sobre las opciones de configuración del servidor perimetral A/V en el ámbito del sitio

  - Para devolver información sobre una colección específica de opciones de configuración del servidor perimetral A/V, especifique la identidad de esa colección al ejecutar el cmdlet Get-CsAVEdgeConfiguration. Por ejemplo, este comando devuelve información solo para las opciones aplicadas al sitio Redmond:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>Para devolver información sobre las opciones de configuración del servidor perimetral A/V con ámbito de servicio

  - Este comando devuelve información solo para las opciones aplicadas a un servidor perimetral A/V específico:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Consulte también


[Crear o modificar una colección de opciones de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Eliminar una colección existente de opciones de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: devolver información de configuración del servidor perimetral A/V'
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
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Devolver información de configuración del servidor perimetral A/V en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V proporciona a los usuarios internos (los usuarios que han iniciado sesión en la red de la organización) una forma de compartir audio y vídeo con usuarios externos (usuarios que no han iniciado sesión en la red de su organización). El servicio perimetral A/V se administra principalmente usando la configuración de borde de A/V, la configuración que se puede configurar en el ámbito del sitio o en el ámbito del servicio (es decir, se puede configurar para un servidor perimetral de A/V individual).

Para obtener información sobre las opciones de configuración del borde A/V en uso en su organización, debe usar Windows PowerShell y el cmdlet Get-CsAVEdgeConfiguration. Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

La información devuelta desde el cmdlet Get-CsAVEdgeConfiguration será similar a la siguiente:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>Para obtener información sobre todas las opciones de configuración del borde A/V

  - El siguiente comando devuelve información acerca de todas las opciones de configuración de borde A/V que se usan actualmente en su organización:
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>Para devolver información para la configuración del borde a/V del ámbito de un sitio

  - Para obtener información sobre una colección específica de valores de configuración de borde A/V, especifique la identidad de esa colección al ejecutar el cmdlet Get-CsAVEdgeConfiguration. Por ejemplo, este comando devuelve información solo de la configuración que se aplica al sitio de Redmond:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>Para devolver información para las opciones de configuración del borde a/V del ámbito de servicio

  - Y este comando solo devuelve información para la configuración que ha aplicado el servidor perimetral A/V específico:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar una colección de valores de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Eliminar una colección existente de valores de configuración del servidor perimetral A/V en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


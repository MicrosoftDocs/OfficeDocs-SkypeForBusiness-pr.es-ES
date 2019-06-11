---
title: 'Lync Server 2013: habilitar QoS para dispositivos que no se basan en Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Habilitar QoS en Lync Server 2013 para dispositivos que no se basan en Windows

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Al instalar Microsoft Lync Server 2013, no se habilitará la calidad de servicio (QoS) en los dispositivos usados en su organización que usen un sistema operativo que no sea Windows. Para comprobarlo, ejecute el siguiente comando desde el shell de administración de Lync Server 2013:

    Get-CsMediaConfiguration

Suponiendo que no haya realizado cambios en la configuración de los elementos multimedia, debe obtener información similar a la siguiente:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Si la propiedad EnableQoS se establece en false (como en la salida anterior), significa que la calidad de servicio no está habilitada para los equipos y dispositivos que usan un sistema operativo que no sea Windows. QoS está habilitado de forma predeterminada para los dispositivos de Lync Phone Edition; sin embargo, es posible deshabilitar la calidad de servicio para Lync Phone Edition.

Para habilitar la calidad de servicio en el ámbito global, ejecute el siguiente comando desde el shell de administración de Lync Server:

    Set-CsMediaConfiguration -EnableQoS $True

El comando anterior habilita QoS en el ámbito global; sin embargo, es importante tener en cuenta que la configuración de los medios también se puede aplicar al ámbito del sitio. Si necesita habilitar la calidad de servicio para un sitio, debe incluir la identidad de las opciones de configuración al llamar a set-CsMediaConfiguration. Por ejemplo, este comando habilita QoS para el sitio de Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> ¿Necesita habilitar QoS en el ámbito del sitio? Eso depende. La configuración asignada al ámbito del sitio tiene prioridad sobre la configuración asignada al ámbito global. Supongamos que tiene QoS habilitado en el ámbito global, pero está deshabilitado en el ámbito del sitio (para el sitio de Redmond). En ese caso, la calidad de servicio se deshabilitará para el sitio de Redmond; Esto se debe a que la configuración del sitio tiene prioridad. Para habilitar QoS para el sitio de Redmond, tendrá que hacerlo usando las opciones de configuración de medios que se aplican a ese sitio.



</div>

Si desea habilitar simultáneamente QoS para todos los valores de configuración multimedia (independientemente del ámbito), ejecute este comando desde el shell de administración de Lync Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows si establece el valor de la propiedad EnableQoS en false. Por ejemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Esto le ofrece la posibilidad de implementar QoS en algunas partes de su red (por ejemplo, en el sitio de Redmond) mientras deja la calidad de servicio deshabilitada en otras partes de la red.

QoS solo se puede habilitar y deshabilitar mediante Windows PowerShell estas opciones no están disponibles en el panel de control de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>


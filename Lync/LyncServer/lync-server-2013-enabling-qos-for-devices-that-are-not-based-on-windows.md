---
title: 'Lync Server 2013: habilitación de QoS para dispositivos que no están basados en Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad830b2cf15e3f34c443feaa5ea21e19279804cb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Habilitación de QoS en Lync Server 2013 para dispositivos que no están basados en Windows

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Al instalar Microsoft Lync Server 2013, la calidad de servicio (QoS) no se habilitará para los dispositivos que se usen en su organización que usen un sistema operativo distinto de Windows. Puede comprobarlo ejecutando el siguiente comando desde el shell de administración de Lync Server 2013:

    Get-CsMediaConfiguration

Suponiendo que no ha realizado cambios en su valores de configuración multimedia debería obtener información similar a la siguiente:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Si la propiedad EnableQoS está establecida en false (como en la salida anterior), significa que la calidad de servicio no está habilitada para equipos y dispositivos que usan un sistema operativo distinto de Windows. La QoS está habilitada de forma predeterminada para los dispositivos Lync Phone Edition; sin embargo, es posible deshabilitar la calidad de servicio para Lync Phone Edition.

Para habilitar la calidad de servicio en el ámbito global, ejecute el siguiente comando desde el shell de administración de Lync Server:

    Set-CsMediaConfiguration -EnableQoS $True

El comando anterior habilita QoS en el ámbito global; sin embargo, es importante tener en cuenta que los valores de configuración multimedia también se pueden aplicar al ámbito de sitio. Si tiene que habilitar la calidad de servicio para un sitio, debe incluir la identidad de los valores de configuración al llamar a Set-CsMediaConfiguration. Por ejemplo, este comando habilita QoS para el sitio de Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> ¿Tiene que habilitar QoS en el ámbito de sitio? Depende. La configuración asignada al ámbito de sitio tiene prioridad sobre la configuración asignada al ámbito global. Supongamos que tiene la QoS habilitada en el ámbito global pero deshabilitada en el ámbito de sitio (para el sitio de Redmond.) En ese caso, la calidad de servicio se deshabilitará para el sitio de Redmond; eso se debe a que la configuración de sitio tiene prioridad. Para habilitar QoS para el sitio de Redmond tendrá que hacerlo mediante los valores de configuración multimedia aplicados a dicho sitio.



</div>

Si desea habilitar simultáneamente QoS para todos los valores de configuración de medios (independientemente del ámbito), ejecute este comando desde el shell de administración de Lync Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows si establece el valor de la propiedad EnableQoS en false. Por ejemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Esto le ofrece la capacidad de implementar QoS en algunas partes de su red (por ejemplo, en el sitio de Redmond) a la vez que se deja la calidad de servicio deshabilitada en otras partes de la red.

QoS solo se puede habilitar y deshabilitar mediante Windows PowerShell estas opciones no están disponibles en el panel de control de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>


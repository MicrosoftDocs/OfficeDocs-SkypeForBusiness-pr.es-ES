---
title: Habilitación de la QoS para dispositivos que no están basados en Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Obtenga información sobre cómo habilitar QoS para los dispositivos usados en su organización que usan un sistema operativo distinto de Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814180"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Habilitar QoS en Skype Empresarial Server para dispositivos que no están basados en Windows


Al instalar Skype Empresarial Server, la calidad de servicio (QoS) no se habilitará para los dispositivos usados en su organización que usen un sistema operativo distinto de Windows. Para comprobarlo, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server:

    Get-CsMediaConfiguration

Suponiendo que no haya realizado ningún cambio en las opciones de configuración multimedia, debería obtener información similar a la siguiente:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Si la propiedad EnableQoS se establece en False (como en la salida anterior), significa que la calidad de servicio no está habilitada para equipos y dispositivos que usan un sistema operativo distinto de Windows.

Para habilitar la calidad de servicio en el ámbito global, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server:

    Set-CsMediaConfiguration -EnableQoS $True

El comando anterior habilita QoS en el ámbito global; sin embargo, es importante tener en cuenta que los valores de configuración multimedia también se pueden aplicar al ámbito de sitio. Si necesita habilitar calidad de servicio para un sitio, debe incluir la identidad de las opciones de configuración al llamar a Set-CsMediaConfiguration. Por ejemplo, este comando habilita QoS para el sitio de Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> ¿Tiene que habilitar QoS en el ámbito de sitio? Depende. La configuración asignada al ámbito de sitio tiene prioridad sobre la configuración asignada al ámbito global. Supongamos que tiene QoS habilitada en el ámbito global, pero deshabilitada en el ámbito de sitio (para el sitio Redmond). En ese caso, la calidad de servicio se deshabilitaría para el sitio redmond; esto se debe a que la configuración del sitio tiene prioridad. Para habilitar QoS para el sitio redmond, tendría que hacerlo con las opciones de configuración de medios aplicadas a ese sitio.


Si desea habilitar QoS simultáneamente para todas las opciones de configuración de medios (independientemente del ámbito), ejecute este comando desde el Shell de administración de LSkype para Business Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows estableciendo el valor de la propiedad EnableQoS en False. Por ejemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Esto le ofrece la capacidad de implementar QoS en algunas partes de su red (por ejemplo, en el sitio de Redmond) a la vez que se deja la calidad de servicio deshabilitada en otras partes de la red.

QoS solo se puede habilitar y deshabilitar mediante Windows PowerShell. Estas opciones no están disponibles en el Panel de control de Skype Empresarial Server.

> [!NOTE]
> Los clientes de Skype Empresarial para iOS versión 6.17 y posteriores ahora admiten QoS.  Esta funcionalidad qoS solo se aplica a los clientes de Skype Empresarial y a los dispositivos de teléfono IP que se registran directamente en un servidor interno de skype empresarial o de grupo de Lync en redes administradas. QoS no es aplicable para el tráfico enrutado a través de Internet.




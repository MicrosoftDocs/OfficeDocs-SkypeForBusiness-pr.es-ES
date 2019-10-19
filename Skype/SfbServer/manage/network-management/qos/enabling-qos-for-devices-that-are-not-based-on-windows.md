---
title: Habilitación de la QoS para dispositivos que no están basados en Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información sobre cómo habilitar QoS para los dispositivos usados en su organización que usan un sistema operativo que no sea Windows.
ms.openlocfilehash: 956fff0e7fc69b1950e35261c02f9f44977510ce
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "37341946"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Habilitar QoS en Skype empresarial Server para dispositivos que no se basan en Windows


Al instalar Skype empresarial Server, la calidad de servicio (QoS) no se habilitará para los dispositivos usados en su organización que usen un sistema operativo que no sea Windows. Para comprobarlo, ejecute el siguiente comando desde el shell de ServerManagement de Skype empresarial:

    Get-CsMediaConfiguration

Suponiendo que no ha realizado ningún cambio en la configuración de los medios, debe obtener información similar a la siguiente:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Si la propiedad EnableQoS se establece en false (como en la salida anterior), significa que la calidad de servicio no está habilitada para los equipos y dispositivos que usan un sistema operativo que no sea Windows.

Para habilitar la calidad de servicio en el ámbito global, ejecute el siguiente comando desde el shell de administración de Skype empresarial Server:

    Set-CsMediaConfiguration -EnableQoS $True

El comando anterior habilita QoS en el ámbito global; sin embargo, es importante tener en cuenta que la configuración de los medios también se puede aplicar al ámbito del sitio. Si necesita habilitar la calidad de servicio para un sitio, debe incluir la identidad de las opciones de configuración al llamar a set-CsMediaConfiguration. Por ejemplo, este comando habilita QoS para el sitio de Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> ¿Necesita habilitar QoS en el ámbito del sitio? Eso depende. La configuración asignada al ámbito del sitio tiene prioridad sobre la configuración asignada al ámbito global. Supongamos que tiene QoS habilitado en el ámbito global, pero está deshabilitado en el ámbito del sitio (para el sitio de Redmond). En ese caso, la calidad de servicio sería deshabilitada para el sitio de Redmond; Esto se debe a que la configuración del sitio tiene prioridad. Para habilitar QoS para el sitio de Redmond, tendría que hacerlo usando la configuración de medios aplicada a ese sitio.


Si desea habilitar simultáneamente QoS para todos los valores de configuración multimedia (independientemente del ámbito), ejecute este comando desde el shell de administración de LSkype para empresas:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows si establece el valor de la propiedad EnableQoS en false. Por ejemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Esto le ofrece la posibilidad de implementar QoS en algunas partes de su red (por ejemplo, en el sitio de Redmond) mientras deja la calidad de servicio deshabilitada en otras partes de la red.

QoS solo se puede habilitar y deshabilitar mediante Windows PowerShell. Estas opciones no están disponibles en el panel de control de Skype empresarial Server.

> [!NOTE]
> Los clientes de Skype empresarial para iOS versión 6,17 y posteriores ahora son compatibles con QoS.  Esta capacidad de QoS solo se aplica a los clientes de Skype empresarial y a los dispositivos de telefonía IP que están registrados directamente en un servidor interno de Skype empresarial o de grupos de Lync en redes administradas. QoS no es aplicable para tráfico enrutado a través de Internet.




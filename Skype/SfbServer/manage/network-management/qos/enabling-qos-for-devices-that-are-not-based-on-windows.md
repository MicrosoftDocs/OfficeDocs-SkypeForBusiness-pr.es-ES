---
title: Habilitación de la QoS para dispositivos que no están basados en Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información sobre cómo habilitar QoS para dispositivos que se usan en la organización que usan un sistema operativo distinto de Windows.
ms.openlocfilehash: b1f3dae2d2b499b334995d7754282c56872ce111
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887123"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Habilitar QoS en Skype para Business Server para los dispositivos que no están basados en Windows


Al instalar Skype para Business Server, la calidad de servicio (QoS) no se habilitará para todos los dispositivos usados en la organización que usan un sistema operativo distinto de Windows. Puede comprobarlo ejecutando el siguiente comando desde dentro de la Skype para profesionales ServerManagement Shell:

    Get-CsMediaConfiguration

Suponiendo que no ha realizado ningún cambio en las opciones de configuración de medios, debería obtener información similar a la siguiente:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Si la propiedad EnableQoS está establecida en False (como se muestra en el resultado anterior) que significa que la calidad de servicio no está habilitado para los equipos y dispositivos que usan un sistema operativo distinto de Windows.

Para habilitar la calidad de servicio en el ámbito global, ejecute el siguiente comando desde dentro de la Skype para Shell de administración de servidor empresarial:

    Set-CsMediaConfiguration -EnableQoS $True

El comando anterior permite QoS en el ámbito global; Sin embargo, es importante tener en cuenta que también se pueden aplicar opciones de configuración de medios al ámbito del sitio. Si necesita habilitar la calidad de servicio para un sitio, debe incluir la identidad de las opciones de configuración cuando se llama a Set-CsMediaConfiguration. Por ejemplo, este comando habilita QoS para el sitio de Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> ¿Necesita habilitar QoS en el ámbito del sitio? Eso depende. La configuración asignada al ámbito del sitio tiene prioridad sobre la configuración asignada al ámbito global. Suponga que tiene QoS habilitado en el ámbito global pero está deshabilitado en el ámbito del sitio (para el sitio de Redmond). En ese caso, se desactivará la calidad de servicio para el sitio de Redmond; eso es porque la configuración del sitio tiene prioridad. Para habilitar QoS para el sitio de Redmond, tendría hacerlo usando las opciones de configuración de medios aplicado a ese sitio.


Si desea habilitar de manera simultánea QoS para todas las opciones de configuración de medios (independientemente del ámbito), ejecute este comando desde dentro de la LSkype de consola de administración de servidor empresarial:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows estableciendo el valor de la propiedad EnableQoS en False. Por ejemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Esto le ofrece la posibilidad de implementar QoS en algunas partes de la red (por ejemplo, en el sitio de Redmond) dejando deshabilitados en otras partes de la red de calidad de servicio.

QoS sólo puede habilitar y deshabilitar mediante Windows PowerShell. Estas opciones no están disponibles en el Skype para el Panel de Control de servidor empresarial.



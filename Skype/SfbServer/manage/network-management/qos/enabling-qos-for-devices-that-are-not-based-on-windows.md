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
description: Obtenga información sobre cómo habilitar QoS para dispositivos usados en su organización que usan un sistema operativo distinto de Windows.
ms.openlocfilehash: 81350ae252252a85bd3f88a000d6cd78d85408e43ca56335517de7b50bb6fd49
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590934"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Habilitar QoS en Skype Empresarial Server dispositivos que no se basan en Windows


Al instalar Skype Empresarial Server, la calidad del servicio (QoS) no se habilitará para los dispositivos usados en la organización que usen un sistema operativo que no sea Windows. Para comprobar esto, ejecute el siguiente comando desde el Shell Skype Empresarial ServerManagement:

**Get-CsMediaConfiguration**

Suponiendo que no haya realizado ningún cambio en las opciones de configuración de medios, debe obtener información similar a la siguiente:

Identity : Global<br/>
EnableQoS : False<br/>
EncryptionLevel : RequireEncryption<br/>
EnableSiren : False<br/>
MaxVideoRateAllowed : VGA600K<br/>
EnableG722StereoCodec : True<br/>
EnableH264Codec : True<br/>
EnableAdaptiveBandwidthEstimation : True<br/>

Si la propiedad EnableQoS se establece en False (como en el resultado anterior), significa que la calidad del servicio no está habilitada para equipos y dispositivos que usan un sistema operativo distinto de Windows.

Para habilitar la calidad del servicio en el ámbito global, ejecute el siguiente comando desde el Shell Skype Empresarial Server administración:

**Set-CsMediaConfiguration -EnableQoS $True**

El comando anterior habilita QoS en el ámbito global; sin embargo, es importante tener en cuenta que los valores de configuración multimedia también se pueden aplicar al ámbito de sitio. Si necesita habilitar la calidad del servicio para un sitio, debe incluir la identidad de las opciones de configuración al llamar a Set-CsMediaConfiguration. Por ejemplo, este comando habilita QoS para el sitio de Redmond:

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True**


> [!NOTE]
> ¿Tiene que habilitar QoS en el ámbito de sitio? Depende. La configuración asignada al ámbito de sitio tiene prioridad sobre la configuración asignada al ámbito global. Supongamos que la QoS está habilitada en el ámbito global pero deshabilitada en el ámbito del sitio (para el sitio Redmond). En ese caso, la calidad del servicio se deshabilitaría para el sitio redmond; esto se debe a que la configuración del sitio tiene prioridad. Para habilitar QoS para el sitio redmond, tendría que hacerlo con las opciones de configuración de medios aplicadas a ese sitio.


Si desea habilitar QoS simultáneamente para todas las opciones de configuración multimedia (independientemente del ámbito), ejecute este comando desde el Shell de administración de LSkype para Business Server:

**Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True**

Puede deshabilitar QoS para dispositivos que usan un sistema operativo distinto de Windows estableciendo el valor de la propiedad EnableQoS en False. Por ejemplo:

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False**

Esto le ofrece la capacidad de implementar QoS en algunas partes de su red (por ejemplo, en el sitio de Redmond) a la vez que se deja la calidad de servicio deshabilitada en otras partes de la red.

QoS solo se puede habilitar y deshabilitar mediante Windows PowerShell. Estas opciones no están disponibles en el Panel Skype Empresarial Server control.

> [!NOTE]
> Skype Empresarial clientes para iOS versión 6.17 y versiones posteriores ahora admiten QoS.  Esta funcionalidad de QoS solo se aplica Skype Empresarial clientes y dispositivos de teléfono IP que se registran directamente en un servidor de grupo de servidores Skype Empresarial o Lync en redes administradas. QoS no es aplicable para el tráfico enrutado a través de Internet.

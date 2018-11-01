---
title: Habilitación de la QoS para dispositivos que no están basados en Windows
TOCTitle: Habilitación de la QoS para dispositivos que no están basados en Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48274730
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitación de la QoS para dispositivos que no están basados en Windows

 

_**Última modificación del tema:** 2012-11-01_

Cuando instala Microsoft Lync Server 2013, la calidad de servicio (QoS) no estará habilitada para ningún dispositivo usado en su organización que use un sistema operativo distinto de Windows. Puede comprobarlo ejecutando el siguiente comando desde dentro del Shell de administración de Lync Server 2013:

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

Si la propiedad de EnableQoS se establece en False (como en el resultado anterior) eso significa que la Calidad de servicio no está habilitada para equipos y dispositivos que usan un sistema operativo distinto de Windows. QoS está habilitada de manera predeterminada para dispositivos de Lync Phone Edition; sin embargo, es posible deshabilitar la calidad de servicio para Lync Phone Edition.

Para habilitar la calidad del servicio en el ámbito global, ejecute el siguiente comando desde dentro del Shell de administración de Lync Server:

    Set-CsMediaConfiguration -EnableQoS $True

El comando anterior habilita QoS en el ámbito global; sin embargo, es importante tener en cuenta que los valores de configuración multimedia también se pueden aplicar al ámbito de sitio. Si tiene que habilitar la calidad de servicio para un sitio, debe incluir la identidad de los valores de configuración al llamar a Set-CsMediaConfiguration. Por ejemplo, este comando habilita QoS para el sitio de Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True


> [!NOTE]
> ¿Tiene que habilitar QoS en el ámbito de sitio? Depende. La configuración asignada al ámbito de sitio tiene prioridad sobre la configuración asignada al ámbito global. Supongamos que tiene la QoS habilitada en el ámbito global pero deshabilitada en el ámbito de sitio (para el sitio de Redmond.) En ese caso, la calidad de servicio se deshabilitará para el sitio de Redmond; eso se debe a que la configuración de sitio tiene prioridad. Para habilitar QoS para el sitio de Redmond tendrá que hacerlo mediante los valores de configuración multimedia aplicados a dicho sitio.



Si desea habilitar de manera simultánea QoS para todos los valores de configuración multimedia (independientemente del ámbito), ejecute este comando desde dentro del Shell de administración de Lync Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Puede deshabilitar QoS para dispositivos que usen un sistema operativo distinto de Windows estableciendo el valor de la propiedad de EnableQoS en False. Por ejemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Esto le ofrece la capacidad de implementar QoS en algunas partes de su red (por ejemplo, en el sitio de Redmond) a la vez que se deja la calidad de servicio deshabilitada en otras partes de la red.

QoS solo se puede habilitar y deshabilitar mediante Shell de administración de Lync Server. Estas opciones no están disponibles en el Panel de control de Lync Server.


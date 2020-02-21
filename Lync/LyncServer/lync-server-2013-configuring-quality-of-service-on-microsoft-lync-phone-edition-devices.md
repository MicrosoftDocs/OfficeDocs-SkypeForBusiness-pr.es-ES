---
title: Configuración de la calidad de servicio en dispositivos Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e154df7c71b32e9f5f1c1440707511bc91c3117
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Configuración de la calidad de servicio en dispositivos Microsoft Lync Phone Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Aunque la calidad de servicio (QoS) no está habilitada de forma predeterminada para dispositivos como iPhone, la QoS está habilitada de forma predeterminada para los dispositivos que ejecutan Lync Phone Edition. (Estos dispositivos se denominan comúnmente teléfonos de comunicaciones unificadas o UC). Para comprobarlo, ejecute el siguiente comando de Windows PowerShell en el shell de administración de Lync Server:

    Get-CsUCPhoneConfiguration

Si no ha hecho ningún cambio en la configuración de su teléfono UC, obtendrá como respuesta una información que presentará el siguiente aspecto:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Para fines de Calidad del servicio, solo es de interés una de estas propiedades: VoiceDiffServTag. VoiceDiffServTag representa el valor DSCP asignado al tráfico de voz que emana de un dispositivo de Lync Phone Edition.

<div>


> [!NOTE]
> El parámetro Voice8021p ya no se admite en Lync Server 2013. El parámetro sigue siendo válido para la compatibilidad con versiones anteriores de Microsoft Lync Server 2010; sin embargo, no tiene efecto en los dispositivos que se usan con Lync Server 2013.



</div>

En la mayoría de las redes, la marcación de paquetes de Lync Phone Edition con un VoiceDiffServTag de 40 no debería causar ningún problema. Ahora bien, 40 no es el valor que suele utilizarse para tráfico de audio, que casi siempre se marca con el código 46 de DSCP. Con el fin de mantener la coherencia en toda la red, es posible que le interese cambiar la propiedad VoiceDiffServTag de sus teléfonos UC a 46.

Para ello, puede usar Windows PowerShell o el panel de control de Lync Server. Para modificar el valor VoiceDiffServTag mediante Windows PowerShell, ejecute el siguiente comando desde el shell de administración de Lync Server:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

El comando anterior modifica la recopilación global de opciones de configuración de teléfono UC. Ahora bien, tenga en cuenta que la configuración de teléfono UC también puede asignarse al ámbito del sitio. Para modificar la configuración de teléfono UC en el ámbito del sitio, deberá especificar la identidad del sitio. Por ejemplo:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

También puede utilizar el siguiente comando para modificar simultáneamente todos sus parámetros de configuración de teléfono UC:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Si prefiere realizar este cambio mediante el panel de control de Lync Server, inicie el panel de control y, a continuación, realice el siguiente procedimiento:

1.  Haga clic en **Clientes** y, a continuación, en **Configuración de dispositivo**.

2.  En la pestaña **Configuración de dispositivo**, haga doble clic en la colección de parámetros de configuración que desee modificar (por ejemplo, **Global**).

3.  En el cuadro de diálogo **Editar configuración de dispositivo**, establezca en el cuadro **Calidad de voz del servicio (QoS)** el valor **46** y luego haga clic en **Confirmar**.

Si tiene varias recopilaciones de opciones de configuración de teléfono UC, deberá repetir este proceso para cada una de ellas. El panel de control de Lync Server no le permitirá modificar simultáneamente varias colecciones de configuración.

Si en su organización tiene dispositivos que no se basan en el sistema operativo Windows (por ejemplo, iPhones), dichos dispositivos no se verán afectados por los cambios en la opción de configuración VoiceDiffServTag. Si desea modificar los valores de DSCP de dichos dispositivos, deberá consultar con el manual de administración de cada tipo de dispositivo.

</div>

<span> </span>

</div>

</div>

</div>


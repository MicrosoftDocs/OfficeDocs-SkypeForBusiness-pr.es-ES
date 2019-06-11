---
title: Configuración de la calidad de servicio en dispositivos Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Configuración de la calidad de servicio en los dispositivos Microsoft Lync Phone Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Aunque la calidad de servicio (QoS) no está habilitada de forma predeterminada en dispositivos como iPhone, QoS está habilitado de forma predeterminada para los dispositivos que ejecutan Lync Phone Edition. (Estos dispositivos se conocen comúnmente como comunicaciones unificadas o comunicaciones unificadas). Para comprobarlo, ejecute el siguiente comando de Windows PowerShell desde el shell de administración de Lync Server:

    Get-CsUCPhoneConfiguration

Si no ha realizado ningún cambio en la configuración de su teléfono de comunicaciones unificadas, recibirá la siguiente información:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Para fines de calidad de servicio, solo una de estas propiedades es de interés: VoiceDiffServTag. El VoiceDiffServTag representa el valor de DSCP asignado al tráfico de voz que emana de un dispositivo de Lync Phone Edition.

<div>


> [!NOTE]
> El parámetro Voice8021p ya no es compatible con Lync Server 2013. El parámetro sigue siendo válido para la compatibilidad con Microsoft Lync Server 2010; sin embargo, no tiene ningún efecto en los dispositivos que se usan con Lync Server 2013.



</div>

En la mayoría de las redes, marcar paquetes de Lync Phone Edition con un VoiceDiffServTag de 40 no debería causar problemas. Pero, 40 no es el valor usado normalmente para el tráfico de audio; en su lugar, el tráfico de audio se marca casi siempre con el código 46 de DSCP. Para mantener la coherencia en toda la red, es posible que desee cambiar la propiedad VoiceDiffServTag de sus teléfonos de comunicaciones unificadas a 46.

Para ello, puede usar Windows PowerShell o el panel de control de Lync Server. Para modificar el valor de VoiceDiffServTag mediante Windows PowerShell, ejecute el siguiente comando desde el shell de administración de Lync Server:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

El comando anterior modifica la colección global de las opciones de configuración del teléfono UC. Sin embargo, ten en cuenta que la configuración del teléfono UC también se puede asignar al ámbito del sitio. Para modificar las opciones de configuración del teléfono UC en el ámbito del sitio, debe especificar la identidad del sitio. Por ejemplo:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

También puede usar el siguiente comando para modificar de forma simultánea todas las opciones de configuración del teléfono UC:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Si prefiere realizar este cambio mediante el panel de control de Lync Server, inicie el panel de control y, a continuación, realice el siguiente procedimiento:

1.  Haga clic en **clientes** y, después, en **configuración de dispositivo**.

2.  En la pestaña **configuración de dispositivo** , haga doble clic en la colección de configuraciones que desea modificar (por ejemplo, **global**).

3.  En el cuadro de diálogo **Editar configuración del dispositivo** , establezca el valor de la casilla **calidad de servicio (QoS) de voz** en **46** y, a continuación, haga clic en **confirmar**.

Si tienes varias colecciones, deberás repetir este proceso para cada colección de opciones de teléfono de comunicaciones unificadas. El panel de control de Lync Server no le permitirá modificar varias colecciones de configuración al mismo tiempo.

Si tiene dispositivos que no se basan en el sistema operativo Windows (como iPhones) de su organización, estos dispositivos no se verán afectados por el cambio de la configuración de VoiceDiffServTag. Si desea cambiar los valores de DSCP en esos dispositivos, tendrá que consultar el manual de administración de cada uno de los tipos de dispositivos.

</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: 2033e3a59684e2d551448e37cccb9be2d027313f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="cf9b8-102">Configuración de la calidad de servicio en dispositivos Microsoft Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf9b8-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf9b8-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cf9b8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cf9b8-104">Aunque la calidad de servicio (QoS) no está habilitada de forma predeterminada para dispositivos como iPhone, la QoS está habilitada de forma predeterminada para los dispositivos que ejecutan Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="cf9b8-105">(Estos dispositivos se denominan comúnmente teléfonos de comunicaciones unificadas o UC). Para comprobarlo, ejecute el siguiente comando de Windows PowerShell en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="cf9b8-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="cf9b8-106">Si no ha hecho ningún cambio en la configuración de su teléfono UC, obtendrá como respuesta una información que presentará el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="cf9b8-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="cf9b8-107">Para fines de Calidad del servicio, solo es de interés una de estas propiedades: VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="cf9b8-108">VoiceDiffServTag representa el valor DSCP asignado al tráfico de voz que emana de un dispositivo de Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cf9b8-109">El parámetro Voice8021p ya no se admite en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="cf9b8-110">El parámetro sigue siendo válido para la compatibilidad con versiones anteriores de Microsoft Lync Server 2010; sin embargo, no tiene efecto en los dispositivos que se usan con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="cf9b8-111">En la mayoría de las redes, la marcación de paquetes de Lync Phone Edition con un VoiceDiffServTag de 40 no debería causar ningún problema.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="cf9b8-112">Ahora bien, 40 no es el valor que suele utilizarse para tráfico de audio, que casi siempre se marca con el código 46 de DSCP.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="cf9b8-113">Con el fin de mantener la coherencia en toda la red, es posible que le interese cambiar la propiedad VoiceDiffServTag de sus teléfonos UC a 46.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="cf9b8-114">Para ello, puede usar Windows PowerShell o el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="cf9b8-115">Para modificar el valor VoiceDiffServTag mediante Windows PowerShell, ejecute el siguiente comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="cf9b8-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="cf9b8-p106">El comando anterior modifica la recopilación global de opciones de configuración de teléfono UC. Ahora bien, tenga en cuenta que la configuración de teléfono UC también puede asignarse al ámbito del sitio. Para modificar la configuración de teléfono UC en el ámbito del sitio, deberá especificar la identidad del sitio. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf9b8-p106">The preceding command modifies the global collection of UC phone configuration settings. Note, however, that UC phone settings can also be assigned to the site scope. To modify UC phone configuration settings at the site scope, you must specify the site Identity. For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="cf9b8-120">También puede utilizar el siguiente comando para modificar simultáneamente todos sus parámetros de configuración de teléfono UC:</span><span class="sxs-lookup"><span data-stu-id="cf9b8-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="cf9b8-121">Si prefiere realizar este cambio mediante el panel de control de Lync Server, inicie el panel de control y, a continuación, realice el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="cf9b8-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="cf9b8-122">Haga clic en **Clientes** y, a continuación, en **Configuración de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="cf9b8-123">En la pestaña **Configuración de dispositivo**, haga doble clic en la colección de parámetros de configuración que desee modificar (por ejemplo, **Global**).</span><span class="sxs-lookup"><span data-stu-id="cf9b8-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="cf9b8-124">En el cuadro de diálogo **Editar configuración de dispositivo**, establezca en el cuadro **Calidad de voz del servicio (QoS)** el valor **46** y luego haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="cf9b8-125">Si tiene varias recopilaciones de opciones de configuración de teléfono UC, deberá repetir este proceso para cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="cf9b8-126">El panel de control de Lync Server no le permitirá modificar simultáneamente varias colecciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="cf9b8-p108">Si en su organización tiene dispositivos que no se basan en el sistema operativo Windows (por ejemplo, iPhones), dichos dispositivos no se verán afectados por los cambios en la opción de configuración VoiceDiffServTag. Si desea modificar los valores de DSCP de dichos dispositivos, deberá consultar con el manual de administración de cada tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cf9b8-p108">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting. If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


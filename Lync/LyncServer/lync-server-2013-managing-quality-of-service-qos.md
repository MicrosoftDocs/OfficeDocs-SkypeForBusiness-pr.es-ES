---
title: 'Lync Server 2013: administración de calidad de servicio (QoS)'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce88471361c63fde3ebf8a3ea716a140567e722e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="7f668-102">Administración de calidad de servicio (QoS) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f668-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f668-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="7f668-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="7f668-104">Calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia de usuario final óptima para las comunicaciones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="7f668-104">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications.</span></span> <span data-ttu-id="7f668-105">La mayoría de las veces se usa en redes en las que el ancho de banda es limitado: con un gran número de paquetes de red que compiten por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio proporciona una forma para que los administradores asignen prioridades mayores a los paquetes datos de audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="7f668-105">QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data.</span></span> <span data-ttu-id="7f668-106">Al dar a estos paquetes una prioridad más alta, es probable que las comunicaciones de audio y vídeo se completen más rápido y con menos interrupciones, que sesiones de red en las que se incluyen tareas como las transferencias de archivos, la navegación por Internet o las copias de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7f668-106">By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups.</span></span> <span data-ttu-id="7f668-107">Esto se debe a que los paquetes de red que se usan para las transferencias de archivos o las copias de seguridad de la base de datos tienen una prioridad de "mejor esfuerzo".</span><span class="sxs-lookup"><span data-stu-id="7f668-107">That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f668-108">Como regla general, la calidad de servicio solo se aplica a las sesiones de comunicación de la red interna.</span><span class="sxs-lookup"><span data-stu-id="7f668-108">As a general rule, Quality of Service applies only to communication sessions on your internal network.</span></span> <span data-ttu-id="7f668-109">Al implementar QoS, puede configurar los servidores y los enrutadores para que admitan la marcación de paquetes; sin embargo, estos dispositivos se configuran para admitir la marcación de paquetes de una manera determinada.</span><span class="sxs-lookup"><span data-stu-id="7f668-109">When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner.</span></span> <span data-ttu-id="7f668-110">No puede dar por sentado que la calidad de servicio será compatible en Internet o en otras redes.</span><span class="sxs-lookup"><span data-stu-id="7f668-110">You cannot assume that Quality of Service will be supported on the Internet or on other networks.</span></span> <span data-ttu-id="7f668-111">Incluso si la calidad es compatible con otras redes, no hay garantía de que QoS se configure de la misma manera en la que se configuró el servicio en la red.</span><span class="sxs-lookup"><span data-stu-id="7f668-111">Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="7f668-112">Microsoft Lync Server 2013 no requiere calidad de servicio; Si actualmente no usa QoS, no es necesario que instale el servicio antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f668-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="7f668-113">Si experimenta una cantidad considerable de paquetes perdidos en su red, la forma recomendada para aliviar este problema es agregar ancho de banda adicional.</span><span class="sxs-lookup"><span data-stu-id="7f668-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="7f668-114">Si no es posible agregar más ancho de banda, es posible que desee implementar la calidad de servicio en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7f668-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="7f668-115">Lync Server 2013 ofrece compatibilidad total con la calidad de servicio: eso significa que las organizaciones que ya usan QoS pueden integrar fácilmente Lync Server en su infraestructura de red existente.</span><span class="sxs-lookup"><span data-stu-id="7f668-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="7f668-116">Para ello, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="7f668-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="7f668-117">[Habilitar QoS en Lync Server 2013 para dispositivos que no se basan en Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span><span class="sxs-lookup"><span data-stu-id="7f668-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="7f668-118">De forma predeterminada, la QoS está deshabilitada en los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="7f668-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="7f668-119">Aunque puede usar Lync Server para habilitar y deshabilitar la calidad de servicio para los dispositivos, normalmente no puede usar el producto para modificar los códigos de DSCP usados por estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7f668-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="7f668-120">[Configurar intervalos de puertos en Lync Server 2013 para sus servidores de conferencias, aplicaciones y mediación](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="7f668-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="7f668-121">Es preciso reservar un conjunto único de puertos para distintos tipos de paquetes, como paquetes de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="7f668-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="7f668-122">Con Lync Server 2013 no se habilita ni deshabilita la calidad de servicio, por ejemplo, estableciendo un valor de propiedad en verdadero o falso.</span><span class="sxs-lookup"><span data-stu-id="7f668-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="7f668-123">En su lugar, se habilita la calidad de servicio mediante la configuración de intervalos de puerto y la creación y aplicación de la Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="7f668-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="7f668-124">Si más tarde decide no usar QoS, puede "Deshabilitar" la calidad de servicio simplemente quitando los objetos de directiva de grupo apropiados.</span><span class="sxs-lookup"><span data-stu-id="7f668-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="7f668-125">[Configurar intervalos de puertos para los servidores perimetrales en Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="7f668-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="7f668-126">Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores.</span><span class="sxs-lookup"><span data-stu-id="7f668-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="7f668-127">[Configurar intervalos de puertos para los clientes de Microsoft Lync en Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="7f668-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="7f668-128">Estos intervalos de puertos se aplican solo a los equipos cliente y normalmente no son los mismos que los intervalos de puertos configurados en los servidores.</span><span class="sxs-lookup"><span data-stu-id="7f668-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="7f668-129">[Configurar una directiva de calidad de servicio en Lync Server 2013 para sus servidores de conferencias, aplicaciones y mediación](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="7f668-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="7f668-130">Estas directivas determinan los códigos DSCP que se aplican a tipos de paquetes diferentes.</span><span class="sxs-lookup"><span data-stu-id="7f668-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="7f668-131">[Configurar una directiva de calidad de servicio para los servidores perimetrales a/V en Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="7f668-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="7f668-132">Esto solo se debe hacer para el lado interno de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="7f668-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="7f668-133">Esto se debe a que la calidad de servicio está diseñada para su uso en su red interna y no en Internet.</span><span class="sxs-lookup"><span data-stu-id="7f668-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="7f668-134">[Configurar directivas de calidad de servicio en Lync Server 2013 para clientes que funcionen en Windows 7 o Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span><span class="sxs-lookup"><span data-stu-id="7f668-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="7f668-135">Tenga en cuenta que Microsoft Lync Server 2013 no es compatible con QoS para otros sistemas operativos de Windows, como Windows Vista o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="7f668-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="7f668-136">[Configuración de la calidad de servicio en los dispositivos Microsoft Lync Phone Edition en Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span><span class="sxs-lookup"><span data-stu-id="7f668-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="7f668-137">De forma predeterminada, QoS está habilitado para los dispositivos de Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="7f668-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="7f668-138">Sin embargo, es posible que desee cambiar el valor predeterminado de DSCP para garantizar que todos los paquetes de audio de su organización usen el mismo código DSCP.</span><span class="sxs-lookup"><span data-stu-id="7f668-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f668-139">Si está usando Microsoft Windows Server 2012 o Windows Server 2012 R2, es posible que esté interesado en el nuevo conjunto de cmdlets de Windows PowerShell disponibles para administrar la calidad de servicio en esa plataforma.</span><span class="sxs-lookup"><span data-stu-id="7f668-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="7f668-140">Para obtener más información, consulte cmdlets de calidad de servicio de red en [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)Windows PowerShell en.</span><span class="sxs-lookup"><span data-stu-id="7f668-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


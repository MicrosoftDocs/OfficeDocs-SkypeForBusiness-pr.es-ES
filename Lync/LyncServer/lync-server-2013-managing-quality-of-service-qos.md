---
title: 'Lync Server 2013: administración de la calidad de servicio (QoS)'
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
ms.openlocfilehash: b9b6661bb9e34db11099bc0f1a7526ba23792198
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="81d89-102">Administración de la calidad de servicio (QoS) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81d89-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81d89-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="81d89-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="81d89-p101">La calidad de servicio (QoS) es una tecnología de red que usan algunas organizaciones para ofrecer una experiencia de usuario final óptima para las comunicaciones de audio y vídeo. QoS se usa principalmente en redes donde el ancho de banda es limitado. Como hay una gran cantidad de paquetes de red compitiendo por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio permite a los administradores asignar prioridades más altas a los paquetes que contienen datos de audio o vídeo. Al asignar una prioridad más alta a estos paquetes, las comunicaciones de audio y vídeo probablemente se completen con mayor rapidez y con menos interrupciones que las sesiones de red que incluyen transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que se asigna una prioridad de "mejor esfuerzo" a los paquetes de red usados para las transferencias de archivos o las copias de seguridad de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="81d89-p101">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications. QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data. By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81d89-p102">Como regla general, la calidad de servicio se aplica solamente a las sesiones de comunicación de la red interna. Al implementar QoS, debe configurar los servidores y enrutadores para que admitan el marcado de paquetes, pero de una manera especial. No puede dar por sentado que la calidad de servicio se admitirá en Internet o en otras redes. Incluso si la calidad de servicio se admite en otras redes, no existe ninguna garantía de que QoS se configurará de la misma manera que configuró el servicio en la red.</span><span class="sxs-lookup"><span data-stu-id="81d89-p102">As a general rule, Quality of Service applies only to communication sessions on your internal network. When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner. You cannot assume that Quality of Service will be supported on the Internet or on other networks. Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="81d89-112">Microsoft Lync Server 2013 no requiere calidad de servicio; Si actualmente no usa QoS, no es necesario que instale el servicio antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81d89-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="81d89-113">Si experimenta una cantidad considerable de pérdida de paquetes en la red, la forma recomendada para paliar este problema es agregar ancho de banda adicional.</span><span class="sxs-lookup"><span data-stu-id="81d89-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="81d89-114">Si no es posible agregar más ancho de banda, puede que desee implementar la calidad de servicio en su lugar.</span><span class="sxs-lookup"><span data-stu-id="81d89-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="81d89-115">Lync Server 2013 ofrece total compatibilidad con la calidad de servicio: Esto significa que las organizaciones que ya usan QoS pueden integrar fácilmente Lync Server en su infraestructura de red existente.</span><span class="sxs-lookup"><span data-stu-id="81d89-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="81d89-116">Para ello, es necesario realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="81d89-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="81d89-117">[Habilitación de QoS en Lync Server 2013 para dispositivos que no están basados en Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span><span class="sxs-lookup"><span data-stu-id="81d89-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="81d89-118">De manera predeterminada, QoS se deshabilita para los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="81d89-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="81d89-119">Aunque puede usar Lync Server para habilitar y deshabilitar la calidad de servicio para dispositivos, normalmente no puede usar el producto para modificar los códigos de DSCP usados por estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="81d89-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="81d89-120">[Configuración de intervalos de puertos en Lync Server 2013 para los servidores de conferencia, aplicación y mediación](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="81d89-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="81d89-121">Debe reservar un conjunto único de puertos para diferentes tipos de paquetes, como paquetes de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="81d89-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="81d89-122">Con Lync Server 2013 no puede habilitar o deshabilitar la calidad de servicio por, por ejemplo, estableciendo un valor de propiedad en true o en false.</span><span class="sxs-lookup"><span data-stu-id="81d89-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="81d89-123">En su lugar, la calidad de servicio se habilita al configurar intervalos de puertos, y al crear y aplicar luego una directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="81d89-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="81d89-124">Si más adelante decide no usar QoS, para "deshabilitar" la calidad de servicio, simplemente puede quitar los objetos de directiva de grupo adecuados.</span><span class="sxs-lookup"><span data-stu-id="81d89-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="81d89-125">[Configuración de intervalos de puertos para los servidores perimetrales en Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="81d89-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="81d89-126">Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores.</span><span class="sxs-lookup"><span data-stu-id="81d89-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="81d89-127">[Configuración de intervalos de puertos para los clientes de Microsoft Lync en Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="81d89-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="81d89-128">Estos intervalos de puertos solo se aplican a equipos cliente y, por lo general, no son los mismos que los intervalos de puertos configurados en los servidores.</span><span class="sxs-lookup"><span data-stu-id="81d89-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="81d89-129">[Configurar una directiva de calidad de servicio en Lync Server 2013 para los servidores de conferencia, aplicación y mediación](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="81d89-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="81d89-130">Estas directivas determinan los códigos DSCP que se aplican a diferentes tipos de paquetes.</span><span class="sxs-lookup"><span data-stu-id="81d89-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="81d89-131">[Configurar una directiva de calidad de servicio para los servidores perimetrales a/V en Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="81d89-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="81d89-132">Esto solo debe realizarse para el lado interno de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="81d89-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="81d89-133">Esto se debe a que la calidad de servicio está diseñada para usarse en la red interna y no en Internet.</span><span class="sxs-lookup"><span data-stu-id="81d89-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="81d89-134">[Configurar directivas de calidad de servicio en Lync Server 2013 para clientes que ejecutan Windows 7 o Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span><span class="sxs-lookup"><span data-stu-id="81d89-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="81d89-135">Tenga en cuenta que Microsoft Lync Server 2013 no es compatible con QoS para otros sistemas operativos Windows, como Windows Vista o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="81d89-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="81d89-136">[Configuración de la calidad de servicio en dispositivos Microsoft Lync Phone Edition en Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span><span class="sxs-lookup"><span data-stu-id="81d89-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="81d89-137">De forma predeterminada, la QoS está habilitada para los dispositivos de Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="81d89-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="81d89-138">Sin embargo, recomendamos cambiar el valor predeterminado de DSCP a fin de garantizar que todos los paquetes de audio de la organización usen el mismo código DSCP.</span><span class="sxs-lookup"><span data-stu-id="81d89-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81d89-139">Si usa Microsoft Windows Server 2012 o Windows Server 2012 R2, es posible que le interese el nuevo conjunto de cmdlets de Windows PowerShell disponibles para administrar la calidad de servicio en esa plataforma.</span><span class="sxs-lookup"><span data-stu-id="81d89-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="81d89-140">Para obtener más información, consulte red de cmdlets de calidad de servicio en [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)Windows PowerShell en.</span><span class="sxs-lookup"><span data-stu-id="81d89-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: definición de los requisitos de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f560df21555bf15c1a51c055861898860ff8dc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516337"
---
# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="794fb-102">Definición de los requisitos de movilidad para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794fb-102">Defining your mobility requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="794fb-103">_**Última modificación del tema:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="794fb-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="794fb-104">Durante la fase de planeación de la característica de movilidad de Lync Server 2013, cuando se usan clientes móviles de Lync 2010 Mobile y Lync 2013, se toman decisiones que determinan los pasos de implementación.</span><span class="sxs-lookup"><span data-stu-id="794fb-104">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="794fb-105">Estas son las decisiones que debe tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="794fb-105">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="794fb-106">**¿Quiere usar la detección automática para clientes móviles de Lync?**</span><span class="sxs-lookup"><span data-stu-id="794fb-106">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="794fb-107">Si desea admitir la detección automática, debe crear nuevos registros internos y externos del sistema de nombres de dominio (DNS), agregar nombres alternativos del sujeto a certificados en los servidores front-end, directores y proxy inverso, y modificar las reglas de publicación existentes en el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="794fb-107">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="794fb-108">Para obtener más información, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="794fb-108">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="794fb-109">Con la detección automática, los usuarios pueden ubicar automáticamente los servicios Web de Lync Server 2013 desde cualquier lugar dentro o fuera de la red corporativa, sin especificar las direcciones URL en la configuración del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="794fb-109">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="794fb-110">Si usa la configuración manual en lugar de la detección automática, los usuarios móviles deben especificar manualmente las siguientes direcciones URL en sus dispositivos móviles:</span><span class="sxs-lookup"><span data-stu-id="794fb-110">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="794fb-111">https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.SVC/root para acceso externo</span><span class="sxs-lookup"><span data-stu-id="794fb-111">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="794fb-112">https:// \<IntPoolFQDN\> /AutoDiscover/autodiscoverservice. SVC/root para acceso interno</span><span class="sxs-lookup"><span data-stu-id="794fb-112">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="794fb-p102">Se recomienda encarecidamente usar la detección automática. El uso principal de los parámetros manuales es para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="794fb-p102">We strongly recommend using automatic discovery. The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="794fb-115">**Si decide admitir la detección automática, ¿está dispuesto a actualizar certificados en el proxy inverso con nombres alternativos de sujeto para cada dominio SIP?**</span><span class="sxs-lookup"><span data-stu-id="794fb-115">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="794fb-116">Si tiene muchos dominios SIP, actualizar certificados públicos en el proxy inverso puede resultar muy caro.</span><span class="sxs-lookup"><span data-stu-id="794fb-116">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="794fb-117">Si este es el caso, puede optar por implementar la detección automática para que la solicitud del servicio Detección automática inicial use HTTP en el puerto 80, en lugar de usar HTTPS en el puerto 443.</span><span class="sxs-lookup"><span data-stu-id="794fb-117">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="794fb-118">Sin embargo, no se trata del método recomendado.</span><span class="sxs-lookup"><span data-stu-id="794fb-118">However, this is not the recommended approach.</span></span> <span data-ttu-id="794fb-119">Si decide elegir esta alternativa, no necesita actualizar los certificados en el proxy inverso, pero debe crear una regla de publicación web para HTTP en el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="794fb-119">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="794fb-120">Para obtener más información, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="794fb-120">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="794fb-121">**¿Desea admitir clientes móviles de Lync internos y externos a la red corporativa, o admitir solamente clientes internos de la red corporativa?**</span><span class="sxs-lookup"><span data-stu-id="794fb-121">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="794fb-p104">Si desea admitir clientes móviles internos y externos a la red corporativa, los dispositivos móviles pueden tener acceso a características de movilidad desde cualquier ubicación. La configuración predeterminada es admitir clientes internos y externos a la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="794fb-p104">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location. The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="794fb-124">Aunque la configuración predeterminada permite que el tráfico del cliente móvil circule a través del sitio externo, puede restringir el tráfico del cliente móvil a la red corporativa interna.</span><span class="sxs-lookup"><span data-stu-id="794fb-124">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="794fb-125">Al restringir el tráfico a la red corporativa interna, los usuarios pueden usar aplicaciones móviles de Lync en sus dispositivos móviles solo cuando están dentro de la red.</span><span class="sxs-lookup"><span data-stu-id="794fb-125">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="794fb-126">Para las implementaciones que admiten movilidad con MCX Mobility Service y Lync 2010 Mobile, ejecute el cmdlet **set-CsMcxConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="794fb-126">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="794fb-127">Para establecer la movilidad solo para uso interno, debe usar un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="794fb-127">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="794fb-128">No es necesario realizar ninguna configuración adicional para UCWA.</span><span class="sxs-lookup"><span data-stu-id="794fb-128">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="794fb-129">UCWA no tiene una configuración de solo interno equivalente.</span><span class="sxs-lookup"><span data-stu-id="794fb-129">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="794fb-130">Si usa un servidor front-end de Lync Server 2013 &nbsp; o grupos de servidores front-end y <STRONG>no tiene</STRONG> servidores front-end de Lync Server 2010 &nbsp; o grupos de servidores front-end, no hay <STRONG>ningún requisito para la persistencia basada en cookies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="794fb-130">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="794fb-131">Si necesita conservar los servidores front-end de Lync Server 2010 o los grupos de servidores &nbsp; front-end, se siguen aplicando las mismas reglas que en Lync Server 2010 para la persistencia basada en cookies.</span><span class="sxs-lookup"><span data-stu-id="794fb-131">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="794fb-132">**¿Desea admitir las notificaciones de inserción para dispositivos Apple iOS y Windows Phone?**</span><span class="sxs-lookup"><span data-stu-id="794fb-132">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="794fb-133">Si admite notificaciones de inserción, los dispositivos Apple iOS y Windows Phone admitidos reciben una notificación de eventos que ocurren cuando la aplicación móvil está inactiva.</span><span class="sxs-lookup"><span data-stu-id="794fb-133">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="794fb-134">Debe configurar el servidor perimetral para que tenga una relación de Federación con el servicio de notificación de inserción de Lync Server basado en la nube, que se encuentra en el centro de servicios de Lync Online, y ejecutar un cmdlet para habilitar las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="794fb-134">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="794fb-135">Si desea admitir las notificaciones de inserción a través de la red de Wi-Fi, además de admitir las notificaciones de inserción a través de redes de datos o 3G de proveedores de dispositivos móviles, debe abrir el puerto 5223 de salida en la red Wi-Fi de su empresa.</span><span class="sxs-lookup"><span data-stu-id="794fb-135">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="794fb-136">La admisión de notificaciones de inserción a través de la red Wi-Fi es compatible con dispositivos móviles que usan solo Wi-Fi y dispositivos móviles que tienen una recepción interior débil.</span><span class="sxs-lookup"><span data-stu-id="794fb-136">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="794fb-137">La apertura del puerto TCP 5223 solo es necesaria cuando se admiten dispositivos Apple que ejecutan el cliente móvil de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="794fb-137">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="794fb-138">Si no admite las notificaciones de inserción, los usuarios de dispositivos móviles Apple y Windows Phone no obtendrán información sobre eventos, como invitaciones a mensajes instantáneos o mensajes perdidos, que se producen cuando la aplicación móvil está inactiva.</span><span class="sxs-lookup"><span data-stu-id="794fb-138">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="794fb-139">Los clientes móviles de Lync 2013 en dispositivos Apple no necesitan una notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="794fb-139">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="794fb-140">Los clientes móviles de Lync 2013 en Windows Phone usan la notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="794fb-140">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="794fb-141">La planeación de las notificaciones de inserción y el centro de notificaciones de inserción siguen siendo los mismos para Lync Mobile en Windows Phone y los dispositivos Apple que no pueden ejecutar el cliente móvil de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="794fb-141">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="794fb-142">**¿Desea que todos los usuarios tengan acceso a las características de movilidad o desea poder especificar qué usuarios tienen acceso a estas características?**</span><span class="sxs-lookup"><span data-stu-id="794fb-142">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="794fb-143">En la tabla se describen las características disponibles para los usuarios en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="794fb-143">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="794fb-144">Los valores predeterminados permiten la llamada a través del trabajo, permiten la voz sobre IP (VoIP) y habilitan la movilidad.</span><span class="sxs-lookup"><span data-stu-id="794fb-144">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="794fb-145">Este es el conjunto completo de opciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="794fb-145">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="794fb-146">Nombre/ámbito de la característica/parámetro (los nombres de parámetro de Directiva pueden no ser los mismos)</span><span class="sxs-lookup"><span data-stu-id="794fb-146">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="794fb-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="794fb-147">Description</span></span></th>
    <th><span data-ttu-id="794fb-148">Agregado</span><span class="sxs-lookup"><span data-stu-id="794fb-148">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="794fb-149">Habilitar la movilidad</span><span class="sxs-lookup"><span data-stu-id="794fb-149">Enable Mobility</span></span></p>
    <p><span data-ttu-id="794fb-150">Nombre del parámetro: <code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="794fb-150">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="794fb-151">Ámbito: global, sitio o usuario</span><span class="sxs-lookup"><span data-stu-id="794fb-151">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="794fb-152">Configuración administrativa para controlar a los usuarios de un ámbito determinado que tienen Lync Mobile instalado, si la Directiva se establece en false, el usuario no podrá iniciar sesión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="794fb-152">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="794fb-153">El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="794fb-153">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="794fb-154">Actualización acumulativa de Lync Server 2010:2011 de noviembre</span><span class="sxs-lookup"><span data-stu-id="794fb-154">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="794fb-155">Habilitar voz externa</span><span class="sxs-lookup"><span data-stu-id="794fb-155">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="794fb-156">Nombre del parámetro: <code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="794fb-156">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="794fb-157">Ámbito: global, sitio o usuario</span><span class="sxs-lookup"><span data-stu-id="794fb-157">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="794fb-158">Controla la capacidad de un usuario de usar llamadas vía trabajo, una característica que permite a los usuarios realizar y recibir llamadas mediante su número de trabajo en lugar de su número de teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="794fb-158">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="794fb-159">Si se establece en false, el usuario no podrá realizar o recibir llamadas a través de su número de trabajo desde su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="794fb-159">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="794fb-160">El valor predeterminado es true.</span><span class="sxs-lookup"><span data-stu-id="794fb-160">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="794fb-161">Actualización acumulativa de Lync Server 2010:2011 de noviembre</span><span class="sxs-lookup"><span data-stu-id="794fb-161">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="794fb-162">Habilitar audio y vídeo IP</span><span class="sxs-lookup"><span data-stu-id="794fb-162">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="794fb-163">Nombre del parámetro: <code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="794fb-163">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="794fb-164">Ámbito: global, sitio o usuario</span><span class="sxs-lookup"><span data-stu-id="794fb-164">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="794fb-165">Controla si un usuario puede usar VoIP para realizar o recibir llamadas de voz o vídeo en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="794fb-165">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="794fb-166">Si se establece en false, el usuario no podrá realizar o recibir llamadas de VoIP o vídeo en su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="794fb-166">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="794fb-167">El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="794fb-167">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="794fb-168">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794fb-168">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="794fb-169">Requerir Wi-Fi para audio IP</span><span class="sxs-lookup"><span data-stu-id="794fb-169">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="794fb-170">Nombre del parámetro: <code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="794fb-170">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="794fb-171">Ámbito: global, sitio o usuario</span><span class="sxs-lookup"><span data-stu-id="794fb-171">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="794fb-172">Esta configuración define si el cliente tendrá que realizar y recibir llamadas a través de VoIP en WiFi en lugar de hacerlo en la red de datos de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="794fb-172">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="794fb-173">Si se establece en true, el usuario solo puede realizar y recibir llamadas de VoIP cuando esté conectado a una red WiFi.</span><span class="sxs-lookup"><span data-stu-id="794fb-173">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="794fb-174">El valor predeterminado es false.</span><span class="sxs-lookup"><span data-stu-id="794fb-174">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="794fb-175">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794fb-175">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="794fb-176">Requerir Wi-Fi para vídeo IP</span><span class="sxs-lookup"><span data-stu-id="794fb-176">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="794fb-177">Nombre del parámetro: <code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="794fb-177">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="794fb-178">Ámbito: global, sitio o usuario</span><span class="sxs-lookup"><span data-stu-id="794fb-178">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="794fb-179">Esta configuración define si el cliente tendrá que realizar y recibir llamadas de vídeo en Wi-Fi en lugar de en la red de datos de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="794fb-179">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="794fb-180">Si se establece en true, el usuario solo puede realizar y recibir llamadas de vídeo cuando esté conectado a un Wi-Fi red.</span><span class="sxs-lookup"><span data-stu-id="794fb-180">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="794fb-181">El valor predeterminado es false.</span><span class="sxs-lookup"><span data-stu-id="794fb-181">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="794fb-182">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794fb-182">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="794fb-183">Para obtener una descripción de la configuración de la Directiva que puede configurar y cómo administrar las directivas, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) y [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="794fb-183">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="794fb-184">**¿Desea que los usuarios no habilitados a Telefonía IP empresarial puedan usar Click to Join para unirse a conferencias?**</span><span class="sxs-lookup"><span data-stu-id="794fb-184">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="794fb-185">Para que los usuarios puedan tener acceso a las características de movilidad y Vía trabajo, deben estar habilitados para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="794fb-185">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="794fb-186">Sin embargo, los usuarios que no están habilitados para telefonía IP empresarial pueden unirse a conferencias haciendo clic en el vínculo de su dispositivo móvil, si tienen asignada una directiva de voz adecuada.</span><span class="sxs-lookup"><span data-stu-id="794fb-186">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="794fb-187">Puede asignar una directiva de voz específica a estos usuarios o asegurarse de que existe una directiva global o una directiva de nivel de sitio que se aplica a ellos.</span><span class="sxs-lookup"><span data-stu-id="794fb-187">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="794fb-188">La Directiva de voz que asigne debe tener registros y rutas de uso de la red telefónica conmutada (RTC) que definen las áreas a las que los usuarios pueden llamar para unirse a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="794fb-188">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="794fb-189">Para obtener información detallada sobre cómo configurar la Directiva de voz, los registros de uso de RTC y las rutas, vea [configurar directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="794fb-189">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="794fb-190">Los usuarios móviles que quieren usar hacer clic para unirse requieren una directiva de voz, junto con los registros de uso de RTC y las rutas de voz relacionados, porque al hacer clic en el vínculo del dispositivo móvil se produce una llamada saliente desde Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="794fb-190">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="794fb-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="794fb-191">See Also</span></span>


[<span data-ttu-id="794fb-192">Requisitos técnicos para la movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794fb-192">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="794fb-193">Configurar directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="794fb-193">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


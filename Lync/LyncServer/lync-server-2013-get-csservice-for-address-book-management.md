---
title: 'Lync Server 2013: Get-CsService para la administración de la libreta de direcciones'
description: 'Lync Server 2013: Get-CsService para la administración de la libreta de direcciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e46173429988d87022c13fab33e3778279dd0e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554656"
---
# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="c044c-103">Get-CsService para la administración de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c044c-103">Get-CsService for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c044c-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c044c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c044c-p101">Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Get-CsService de manera local: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c044c-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="c044c-107">Get-CsService es útil para recuperar y mostrar la configuración actual de los servicios web definidos de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="c044c-107">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="c044c-108">Al definir el nombre de dominio completo (FQDN) del grupo y el parámetro WebServer, el cmdlet devuelve los servicios basados en web que ofrece el servidor, incluido el controlador de libreta de direcciones y los URI de expansión de la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="c044c-108">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="c044c-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c044c-109">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="c044c-110">Este cmdlet devuelve lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c044c-110">This cmdlet returns the following:</span></span>

<span data-ttu-id="c044c-111">Identidad: WebServer:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="c044c-111">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="c044c-112">Almacén de elementos: almacén de:DC01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="c044c-112">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="c044c-113">UserServer: UserServer:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="c044c-113">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="c044c-114">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="c044c-114">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="c044c-115">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="c044c-115">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="c044c-116">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="c044c-116">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="c044c-117">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="c044c-117">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="c044c-118">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="c044c-118">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="c044c-119">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="c044c-119">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="c044c-120">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="c044c-120">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="c044c-121">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="c044c-121">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="c044c-122">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="c044c-122">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="c044c-123">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="c044c-123">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="c044c-124">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="c044c-124">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="c044c-125">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="c044c-125">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="c044c-126">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-126">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="c044c-127">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="c044c-127">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="c044c-128">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="c044c-128">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="c044c-129">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-129">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="c044c-130">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-130">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="c044c-131">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-131">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="c044c-132">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-132">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="c044c-133">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="c044c-133">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="c044c-134">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="c044c-134">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="c044c-135">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-135">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="c044c-136">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="c044c-136">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="c044c-137">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="c044c-137">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="c044c-138">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="c044c-138">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="c044c-139">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="c044c-139">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="c044c-140">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-140">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="c044c-141">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-141">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="c044c-142">MeetExternalUri : https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="c044c-142">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="c044c-143">DialinExternalUri : https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="c044c-143">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="c044c-144">CscpInternalUri : https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="c044c-144">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="c044c-145">ReachExternalUri : https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="c044c-145">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="c044c-146">ReachInternalUri : https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="c044c-146">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="c044c-147">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-147">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="c044c-148">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="c044c-148">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="c044c-149">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c044c-149">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="c044c-150">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c044c-150">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="c044c-151">DependentServiceList: {registrar:pool01. contoso. net, ConferencingServer:pool01. contoso. net}</span><span class="sxs-lookup"><span data-stu-id="c044c-151">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="c044c-152">ServiceId: 1-webservices-1</span><span class="sxs-lookup"><span data-stu-id="c044c-152">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="c044c-153">SiteId: sitio: Redmond</span><span class="sxs-lookup"><span data-stu-id="c044c-153">SiteId : Site:Redmond</span></span>

<span data-ttu-id="c044c-154">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c044c-154">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="c044c-155">Versión: 5</span><span class="sxs-lookup"><span data-stu-id="c044c-155">Version : 5</span></span>

<span data-ttu-id="c044c-156">Rol: servidor de WebServer</span><span class="sxs-lookup"><span data-stu-id="c044c-156">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c044c-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c044c-157">See Also</span></span>


[<span data-ttu-id="c044c-158">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="c044c-158">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


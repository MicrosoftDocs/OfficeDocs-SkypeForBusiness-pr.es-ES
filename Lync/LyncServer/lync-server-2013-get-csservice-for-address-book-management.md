---
title: 'Lync Server 2013: get-CsService para la administración de libretas de direcciones'
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
ms.openlocfilehash: 656c1aa545a1f10e49c5ff60b51c20386854d146
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="4a2cc-102">Get-CsService para la administración de libretas de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a2cc-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a2cc-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4a2cc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4a2cc-104">¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Get-CsService de forma local: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="4a2cc-105">Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4a2cc-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="4a2cc-106">Get-CsService es útil para recuperar y mostrar la configuración actual de los servicios web definidos de su infraestructura.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="4a2cc-107">Al definir el nombre de dominio completo (FQDN) de la agrupación y el parámetro webserver, el cmdlet devuelve los servicios basados en web ofrecidos por su servidor, incluidos los URI de expansión de la lista de distribución y el controlador de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="4a2cc-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4a2cc-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="4a2cc-109">Este cmdlet devuelve lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a2cc-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="4a2cc-110">Identidad: WebServer:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="4a2cc-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="4a2cc-111">Almacén de almacén::DC01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="4a2cc-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="4a2cc-112">UserServer: UserServer:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="4a2cc-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="4a2cc-113">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="4a2cc-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="4a2cc-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="4a2cc-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="4a2cc-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="4a2cc-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="4a2cc-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="4a2cc-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="4a2cc-117">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="4a2cc-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="4a2cc-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="4a2cc-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="4a2cc-119">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="4a2cc-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="4a2cc-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="4a2cc-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="4a2cc-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="4a2cc-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="4a2cc-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="4a2cc-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="4a2cc-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="4a2cc-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="4a2cc-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="4a2cc-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="4a2cc-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="4a2cc-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="4a2cc-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="4a2cc-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="4a2cc-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="4a2cc-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="4a2cc-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="4a2cc-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="4a2cc-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="4a2cc-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="4a2cc-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="4a2cc-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="4a2cc-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="4a2cc-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="4a2cc-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="4a2cc-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="4a2cc-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="4a2cc-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="4a2cc-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="4a2cc-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="4a2cc-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="4a2cc-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="4a2cc-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="4a2cc-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="4a2cc-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="4a2cc-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="4a2cc-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="4a2cc-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="4a2cc-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="4a2cc-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="4a2cc-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="4a2cc-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="4a2cc-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="4a2cc-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="4a2cc-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="4a2cc-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2cc-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="4a2cc-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4a2cc-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="4a2cc-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4a2cc-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="4a2cc-150">DependentServiceList: {registrar:pool01. contoso. net, ConferencingServer:pool01. contoso. net}</span><span class="sxs-lookup"><span data-stu-id="4a2cc-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="4a2cc-151">ServiceId: 1-webservices-1</span><span class="sxs-lookup"><span data-stu-id="4a2cc-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="4a2cc-152">SiteId: sitio: Redmond</span><span class="sxs-lookup"><span data-stu-id="4a2cc-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="4a2cc-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4a2cc-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="4a2cc-154">Versión: 5</span><span class="sxs-lookup"><span data-stu-id="4a2cc-154">Version : 5</span></span>

<span data-ttu-id="4a2cc-155">Rol: servidor WebServer</span><span class="sxs-lookup"><span data-stu-id="4a2cc-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4a2cc-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a2cc-156">See Also</span></span>


[<span data-ttu-id="4a2cc-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="4a2cc-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: get-CsService para la administración de la libreta de direcciones'
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
ms.openlocfilehash: c39520a54ae664a1eddf241cbf1d8d27fe858510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a>Get-CsService para la administración de la libreta de direcciones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Get-CsService de manera local: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

Get-CsService es útil para recuperar y mostrar la configuración actual de los servicios web definidos de la infraestructura. Al definir el nombre de dominio completo (FQDN) del grupo y el parámetro WebServer, el cmdlet devuelve los servicios basados en web que ofrece el servidor, incluido el controlador de libreta de direcciones y los URI de expansión de la lista de distribución.

Por ejemplo:

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

Este cmdlet devuelve lo siguiente:

Identidad: WebServer:pool01. contoso. net

Almacén de elementos: almacén de:DC01. contoso. net

UserServer: UserServer:pool01. contoso. net

PrimaryHttpPort: 80

PrimaryHttpsPort: 443

ExternalHttpPort: 8080

ExternalHttpsPort: 4443

PublishedPrimaryHttpPort: 80

PublishedPrimaryHttpsPort: 443

PublishedExternalHttpPort: 80

PublishedExternalHttpsPort: 443

ReachPrimaryPsomServerPort: 8060

ReachExternalPsomServerPort: 8061

AppSharingPortStart: 49152

AppSharingPortCount: 16383

LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc

ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler

ABHandlerExternalUri :https://csweb.contoso.com/abs/handler

DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc

DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc

CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CollabContentInternalUri :https://internalweb.contoso.net/CollabContent

CollabContentExternalUri :https://csweb.contoso.com/CollabContent

CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri :https://csweb.contoso.com/Meet

DialinExternalUri :https://csweb.contoso.com/Dialin

CscpInternalUri :https://internalweb.contoso.net/Cscp

ReachExternalUri :https://csweb.contoso.com/Reach

ReachInternalUri :https://internalweb.contoso.net/Reach

WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn: csweb.contoso.com

InternalFqdn: internalweb.contoso.net

DependentServiceList: {registrar:pool01. contoso. net, ConferencingServer:pool01. contoso. net}

ServiceId: 1-webservices-1

SiteId: sitio: Redmond

PoolFqdn: pool01.contoso.net

Versión: 5

Rol: servidor de WebServer

<div>

## <a name="see-also"></a>Vea también


[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


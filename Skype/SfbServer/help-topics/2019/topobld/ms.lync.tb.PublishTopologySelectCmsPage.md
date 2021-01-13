---
title: Publicar página CMS de selección de topología
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: La topología que ha configurado se publica con topology Builder. Se le pedirá que seleccione en una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central. Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado.
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822190"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="2df22-105">Publicar página CMS de selección de topología</span><span class="sxs-lookup"><span data-stu-id="2df22-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="2df22-106">La topología que ha configurado se publica con topology Builder.</span><span class="sxs-lookup"><span data-stu-id="2df22-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="2df22-107">Se le pedirá que seleccione en una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="2df22-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="2df22-108">Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="2df22-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="2df22-109">Acerca del servidor de administración central</span><span class="sxs-lookup"><span data-stu-id="2df22-109">About the Central Management Server</span></span>
<span data-ttu-id="2df22-110">El servidor de administración central es un único sistema maestro/réplica múltiple, donde el servidor front-end que contiene el servidor de administración central contiene la copia de lectura y escritura de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2df22-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="2df22-111">Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y la implementación.</span><span class="sxs-lookup"><span data-stu-id="2df22-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="2df22-112">La base de datos local recibe actualizaciones de réplicas mediante el agente de replicador de réplicas de Lync Server que se ejecuta como servicio en todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="2df22-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="2df22-113">El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que se incluye en los archivos xds.mdf y xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="2df22-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="2df22-114">Un punto de control de servicio (SCP) de los Servicios de dominio de Active Directory hace referencia a la ubicación de la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="2df22-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="2df22-115">Todas las herramientas que usan el servidor de administración central para administrar y configurar Lync Server usan el SCP para ubicar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="2df22-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2df22-116">Ver también</span><span class="sxs-lookup"><span data-stu-id="2df22-116">See also</span></span>

[<span data-ttu-id="2df22-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="2df22-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)

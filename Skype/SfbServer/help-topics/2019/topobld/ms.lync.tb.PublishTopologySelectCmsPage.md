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
description: Publique la topología que haya configurado mediante el Generador de topologías. Se le pedirá que seleccione de una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central. Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado.
ms.openlocfilehash: fe3e7ed8c0a58b0547ede0eb02f0ea476bce94bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096886"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="094b3-105">Publicar página CMS de selección de topología</span><span class="sxs-lookup"><span data-stu-id="094b3-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="094b3-106">Publique la topología que haya configurado mediante el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="094b3-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="094b3-107">Se le pedirá que seleccione de una lista qué servidor front-end o grupo de servidores front-end asumirá el rol de mantener el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="094b3-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="094b3-108">Solo un servidor front-end o grupo de servidores front-end puede mantener este rol en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="094b3-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="094b3-109">Acerca del servidor de administración central</span><span class="sxs-lookup"><span data-stu-id="094b3-109">About the Central Management Server</span></span>
<span data-ttu-id="094b3-110">El servidor de administración central es un único sistema de réplica principal o múltiple, donde el servidor front-end que contiene el servidor de administración central contiene la copia de lectura y escritura de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="094b3-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="094b3-111">Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén de administración central en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y la implementación.</span><span class="sxs-lookup"><span data-stu-id="094b3-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="094b3-112">La base de datos local recibe actualizaciones de réplicas a través del agente replicador de réplicas de Lync Server que se ejecuta como servicio en todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="094b3-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="094b3-113">El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está hecho de los archivos xds.mdf y xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="094b3-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="094b3-114">Se hace referencia a la ubicación de la base de datos maestra mediante un punto de control de servicio (SCP) en Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="094b3-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="094b3-115">Todas las herramientas que usan el servidor de administración central para administrar y configurar Lync Server usan scp para buscar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="094b3-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="094b3-116">Ver también</span><span class="sxs-lookup"><span data-stu-id="094b3-116">See also</span></span>

[<span data-ttu-id="094b3-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="094b3-117">Move-CsManagementServer</span></span>](/powershell/module/skype/move-csmanagementserver?view=skype-ps)
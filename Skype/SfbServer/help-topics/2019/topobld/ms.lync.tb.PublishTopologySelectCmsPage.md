---
title: Publicar página CMS de selección de topología
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Publicar la topología que se ha configurado mediante el generador de topología. Le pedirá que seleccione en la lista que el grupo de servidores Front-End o de servidor Front-End asumirá la función de mantener el almacén de Administración Central. Un solo grupo de servidores Front-End o de servidor Front-End puede contener esta función en cualquier momento dado.
ms.openlocfilehash: 0c80fa30721fe47fc3bc4725ca4f50f8a75f7009
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201696"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="1d2d9-105">Publicar página CMS de selección de topología</span><span class="sxs-lookup"><span data-stu-id="1d2d9-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="1d2d9-106">Publicar la topología que se ha configurado mediante el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="1d2d9-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="1d2d9-107">Le pedirá que seleccione en la lista que el grupo de servidores Front-End o de servidor Front-End asumirá la función de mantener el almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="1d2d9-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="1d2d9-108">Un solo grupo de servidores Front-End o de servidor Front-End puede contener esta función en cualquier momento dado.</span><span class="sxs-lookup"><span data-stu-id="1d2d9-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="1d2d9-109">Acerca del servidor de Administración Central</span><span class="sxs-lookup"><span data-stu-id="1d2d9-109">About the Central Management Server</span></span>
<span data-ttu-id="1d2d9-110">El servidor de Administración Central es un sistema de única réplica maestro o varios, donde se mantiene la copia de lectura y escritura de la base de datos por el servidor Front-End que contiene el servidor de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="1d2d9-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="1d2d9-111">Cada equipo en la topología, incluido el servidor Front-End que contiene el servidor de Administración Central, tiene una copia de solo lectura de los datos del almacén de Administración Central en la base de datos de SQL (denominado RTCLOCAL de forma predeterminada) instalado en el equipo durante el programa de instalación y despliegue.</span><span class="sxs-lookup"><span data-stu-id="1d2d9-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="1d2d9-112">La base de datos local recibe actualizaciones de réplica mediante el agente de Replicador de Lync Server réplica que se ejecuta como un servicio en todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="1d2d9-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="1d2d9-113">El nombre de la base de datos real en el servidor de Administración Central y la réplica local es XDS, que se compone de los archivos xds.mdf y xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="1d2d9-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="1d2d9-114">Un punto de control de servicio (SCP) en servicios de dominio de Active Directory al que hace referencia la ubicación de la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="1d2d9-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="1d2d9-115">Todas las herramientas que use el servidor de Administración Central para administrar y configurar Lync Server usa la SCP para encontrar el almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="1d2d9-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1d2d9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d2d9-116">See also</span></span>

[<span data-ttu-id="1d2d9-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="1d2d9-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)

---
title: Publicar página CMS de selección de topología
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Publique la topología que ha configurado con el generador de topología. Se le pedirá que seleccione de una lista en la que el servidor front-end o el grupo de servidores front-end asumirán la función de mantener el almacén de administración central. Solo un servidor front-end o un grupo de servidores front-end pueden mantener este rol en un momento dado.
ms.openlocfilehash: 9cecdc170934f7359597484e56299e2fe76499b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701675"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="b60f6-105">Publicar página CMS de selección de topología</span><span class="sxs-lookup"><span data-stu-id="b60f6-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="b60f6-106">Publique la topología que ha configurado con el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="b60f6-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="b60f6-107">Se le pedirá que seleccione de una lista en la que el servidor front-end o el grupo de servidores front-end asumirán la función de mantener el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="b60f6-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="b60f6-108">Solo un servidor front-end o un grupo de servidores front-end pueden mantener este rol en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="b60f6-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="b60f6-109">Acerca del servidor de administración central</span><span class="sxs-lookup"><span data-stu-id="b60f6-109">About the Central Management Server</span></span>
<span data-ttu-id="b60f6-110">El servidor de administración central es un único sistema de réplica principal/múltiple, donde la copia de lectura y escritura de la base de datos es retenida por el servidor front-end que contiene el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="b60f6-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="b60f6-111">Cada equipo de la topología, incluido el servidor front-end que contiene el servidor de administración central, tiene una copia de solo lectura de los datos del almacén central de administración en la base de datos de SQL Server (denominada RTCLOCAL de forma predeterminada) instalada en el equipo durante la instalación y implementación.</span><span class="sxs-lookup"><span data-stu-id="b60f6-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="b60f6-112">La base de datos local recibe actualizaciones de réplica por medio del agente replicador de réplicas de Lync Server que se ejecuta como un servicio en todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="b60f6-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="b60f6-113">El nombre de la base de datos real en el servidor de administración central y la réplica local es XDS, que está compuesto de los archivos XDS. MDF y XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="b60f6-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="b60f6-114">Un punto de control de servicio (SCP) hace referencia a la ubicación de la base de datos maestra en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b60f6-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="b60f6-115">Todas las herramientas que usan el servidor de administración central para administrar y configurar Lync Server usan el SCP para localizar el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="b60f6-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b60f6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b60f6-116">See also</span></span>

[<span data-ttu-id="b60f6-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="b60f6-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)

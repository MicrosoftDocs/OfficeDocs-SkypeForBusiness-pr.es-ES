---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Proceso para comprobar la coexistencia de un grupo piloto con grupo heredado.
ms.openlocfilehash: dd2edd2e6ecef26b22ba9bf5c093c631866110ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280656"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="6f57c-103">Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado</span><span class="sxs-lookup"><span data-stu-id="6f57c-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="6f57c-104">**En este artículo**</span><span class="sxs-lookup"><span data-stu-id="6f57c-104">**In this article**</span></span>
  
[<span data-ttu-id="6f57c-105">Comprobar que los servicios de Skype empresarial Server 2019 se han iniciado</span><span class="sxs-lookup"><span data-stu-id="6f57c-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="6f57c-106">Abrir el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="6f57c-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="6f57c-107">No intente abrir la topología en el generador de topología heredado</span><span class="sxs-lookup"><span data-stu-id="6f57c-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="6f57c-108">Después de implementar el grupo piloto, debe comprobar la coexistencia de las dos agrupaciones mediante las herramientas administrativas para ver la información del grupo.</span><span class="sxs-lookup"><span data-stu-id="6f57c-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="6f57c-109">Para los grupos de 2019 y los grupos heredados de Skype empresarial Server, debe usar las herramientas del panel de control y del generador de topologías de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6f57c-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="6f57c-110">Comprobar que los servicios de Skype empresarial Server 2019 se han iniciado</span><span class="sxs-lookup"><span data-stu-id="6f57c-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="6f57c-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="6f57c-111"></span></span>

1. <span data-ttu-id="6f57c-112">Desde el servidor front-end de Skype empresarial Server 2019, navegue hasta el applet Tools\Services administrativo.</span><span class="sxs-lookup"><span data-stu-id="6f57c-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="6f57c-113">Compruebe que se están ejecutando los siguientes servicios en el servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="6f57c-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="6f57c-114">Agente del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="6f57c-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="6f57c-115">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6f57c-115">Application Sharing</span></span>
    - <span data-ttu-id="6f57c-116">Servicio de prueba de audio</span><span class="sxs-lookup"><span data-stu-id="6f57c-116">Audio Test Service</span></span>
    - <span data-ttu-id="6f57c-117">Audioconferencias y videoconferencias</span><span class="sxs-lookup"><span data-stu-id="6f57c-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="6f57c-118">Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="6f57c-118">Call Park</span></span>
    - <span data-ttu-id="6f57c-119">Anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="6f57c-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="6f57c-120">Operador de conferencias</span><span class="sxs-lookup"><span data-stu-id="6f57c-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="6f57c-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="6f57c-121">Front-End</span></span>
    - <span data-ttu-id="6f57c-122">Conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="6f57c-122">IM Conferencing</span></span>
    - <span data-ttu-id="6f57c-123">Servidores</span><span class="sxs-lookup"><span data-stu-id="6f57c-123">Mediation</span></span>
    - <span data-ttu-id="6f57c-124">Agente duplicador de réplicas</span><span class="sxs-lookup"><span data-stu-id="6f57c-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="6f57c-125">Grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6f57c-125">Response Group</span></span>
    - <span data-ttu-id="6f57c-126">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="6f57c-126">Web Conferencing</span></span>
    - <span data-ttu-id="6f57c-127">Puerta de enlace de traducción de XMPP</span><span class="sxs-lookup"><span data-stu-id="6f57c-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="6f57c-128">Abrir el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="6f57c-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="6f57c-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="6f57c-129"></span></span>

<span data-ttu-id="6f57c-130">Desde el servidor front-end de su implementación de Skype empresarial Server 2019, abra el panel de control de Skype empresarial Server 2019 y seleccione el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="6f57c-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="6f57c-131">Repita el procedimiento para abrir el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="6f57c-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6f57c-132">En Skype empresarial Server 2019, debe actualizar Silverlight a la versión 5 antes de usar el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6f57c-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="6f57c-133">Ahora, esta topología incluye roles de servidor heredados de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6f57c-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="6f57c-134">No intente abrir la topología en el generador de topología heredado</span><span class="sxs-lookup"><span data-stu-id="6f57c-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="6f57c-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="6f57c-135"></span></span>

<span data-ttu-id="6f57c-136">Si intenta abrir la topología con el generador de topología heredado, encontrará el error siguiente.</span><span class="sxs-lookup"><span data-stu-id="6f57c-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="6f57c-137">La topología solo se puede ver con el generador de topología de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6f57c-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="6f57c-138">El generador de topología de Skype empresarial Server 2019 debe usarse para crear grupos de servidores para Skype empresarial Server 2019 y la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="6f57c-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  


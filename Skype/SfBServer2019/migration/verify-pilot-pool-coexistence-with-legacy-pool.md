---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Proceso para comprobar la coexistencia del grupo piloto con el grupo heredado.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751662"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="e13b3-103">Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="e13b3-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="e13b3-104">**En este artículo**</span><span class="sxs-lookup"><span data-stu-id="e13b3-104">**In this article**</span></span>
  
[<span data-ttu-id="e13b3-105">Comprobar que se han iniciado los servicios de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="e13b3-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="e13b3-106">Abrir el Panel de control de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="e13b3-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="e13b3-107">No intente abrir la topología en el Generador de topologías heredado</span><span class="sxs-lookup"><span data-stu-id="e13b3-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="e13b3-108">Después de implementar el grupo piloto, verifique la coexistencia de los dos grupos de servidores con las herramientas administrativas para ver la información del grupo.</span><span class="sxs-lookup"><span data-stu-id="e13b3-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="e13b3-109">Para los grupos de Skype Empresarial Server 2019 y los grupos heredados, debe usar las herramientas del Panel de control de Skype Empresarial Server 2019 y del Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="e13b3-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="e13b3-110">Comprobar que se han iniciado los servicios de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="e13b3-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="e13b3-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e13b3-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="e13b3-112">Desde el servidor front-end de Skype Empresarial Server 2019, vaya al applet Herramientas administrativas\Servicios.</span><span class="sxs-lookup"><span data-stu-id="e13b3-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="e13b3-113">Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="e13b3-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="e13b3-114">Agente de servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="e13b3-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="e13b3-115">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e13b3-115">Application Sharing</span></span>
    - <span data-ttu-id="e13b3-116">Servicio de prueba de audio</span><span class="sxs-lookup"><span data-stu-id="e13b3-116">Audio Test Service</span></span>
    - <span data-ttu-id="e13b3-117">Conferencias de audio/vídeo</span><span class="sxs-lookup"><span data-stu-id="e13b3-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="e13b3-118">Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="e13b3-118">Call Park</span></span>
    - <span data-ttu-id="e13b3-119">Anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="e13b3-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="e13b3-120">Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="e13b3-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="e13b3-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="e13b3-121">Front-End</span></span>
    - <span data-ttu-id="e13b3-122">Conferencia de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="e13b3-122">IM Conferencing</span></span>
    - <span data-ttu-id="e13b3-123">Mediación</span><span class="sxs-lookup"><span data-stu-id="e13b3-123">Mediation</span></span>
    - <span data-ttu-id="e13b3-124">Replica Replicator Agent</span><span class="sxs-lookup"><span data-stu-id="e13b3-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="e13b3-125">Grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="e13b3-125">Response Group</span></span>
    - <span data-ttu-id="e13b3-126">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="e13b3-126">Web Conferencing</span></span>
    - <span data-ttu-id="e13b3-127">Puerta de enlace de traducción XMPP</span><span class="sxs-lookup"><span data-stu-id="e13b3-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="e13b3-128">Abrir el Panel de control de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="e13b3-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="e13b3-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="e13b3-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="e13b3-130">En el servidor front-end de su implementación de Skype Empresarial Server 2019, abra el Panel de control de Skype Empresarial Server 2019 y seleccione el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="e13b3-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="e13b3-131">Repita el procedimiento para abrir el grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e13b3-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e13b3-132">En Skype Empresarial Server 2019, debe actualizar Silverlight a la versión 5 de Silverlight antes de usar el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e13b3-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="e13b3-133">Esta topología ahora incluye roles de servidor heredados y de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e13b3-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="e13b3-134">No intente abrir la topología en el Generador de topologías heredado</span><span class="sxs-lookup"><span data-stu-id="e13b3-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="e13b3-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="e13b3-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="e13b3-136">La topología solo se puede ver con el Generador de topologías de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e13b3-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="e13b3-137">El Generador de topologías de Skype Empresarial Server 2019 debe usarse para crear grupos tanto para Skype Empresarial Server 2019 como para la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="e13b3-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  


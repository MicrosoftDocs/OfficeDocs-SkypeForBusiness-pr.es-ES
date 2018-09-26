---
title: Comprobar la coexistencia de grupo piloto con grupo heredado
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Proceso para comprobar la coexistencia del grupo piloto con grupo heredado.
ms.openlocfilehash: 717726acd3654abb2296d622afc5a4d45009430e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028694"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="ca7c3-103">Comprobar la coexistencia de grupo piloto con grupo heredado</span><span class="sxs-lookup"><span data-stu-id="ca7c3-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="ca7c3-104">**En este artículo**</span><span class="sxs-lookup"><span data-stu-id="ca7c3-104">**In this article**</span></span>
  
[<span data-ttu-id="ca7c3-105">Compruebe que se han iniciado Skype para servicios de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="ca7c3-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="ca7c3-106">Abra el Skype para el Panel de Control de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="ca7c3-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="ca7c3-107">No intente abrir la topología en el generador de topología heredada</span><span class="sxs-lookup"><span data-stu-id="ca7c3-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="ca7c3-108">Después de implementar el grupo piloto, debe comprobar la coexistencia de los dos grupos de servidores mediante las herramientas administrativas para ver la información de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="ca7c3-109">Para Skype para grupos de negocio Server 2019 y grupos de servidores heredados, debe usar el Skype para herramientas de Panel de Control de Business Server 2019 y generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="ca7c3-110">Compruebe que se han iniciado Skype para servicios de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="ca7c3-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="ca7c3-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="ca7c3-111"></span></span>

1. <span data-ttu-id="ca7c3-112">Desde Skype para profesionales de 2019 Front-End Server, navegue hasta el applet herramientas Administrativas\servicios.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="ca7c3-113">Compruebe que los siguientes servicios se están ejecutando en el servidor Front-End:</span><span class="sxs-lookup"><span data-stu-id="ca7c3-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="ca7c3-114">Agente del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="ca7c3-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="ca7c3-115">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ca7c3-115">Application Sharing</span></span>
    - <span data-ttu-id="ca7c3-116">Servicio de prueba de audio</span><span class="sxs-lookup"><span data-stu-id="ca7c3-116">Audio Test Service</span></span>
    - <span data-ttu-id="ca7c3-117">Conferencia de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="ca7c3-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="ca7c3-118">Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="ca7c3-118">Call Park</span></span>
    - <span data-ttu-id="ca7c3-119">Anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="ca7c3-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="ca7c3-120">Operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="ca7c3-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="ca7c3-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="ca7c3-121">Front-End</span></span>
    - <span data-ttu-id="ca7c3-122">Conferencia de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="ca7c3-122">IM Conferencing</span></span>
    - <span data-ttu-id="ca7c3-123">Servidores</span><span class="sxs-lookup"><span data-stu-id="ca7c3-123">Mediation</span></span>
    - <span data-ttu-id="ca7c3-124">Agente de réplica del replicador de usuarios</span><span class="sxs-lookup"><span data-stu-id="ca7c3-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="ca7c3-125">Grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="ca7c3-125">Response Group</span></span>
    - <span data-ttu-id="ca7c3-126">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="ca7c3-126">Web Conferencing</span></span>
    - <span data-ttu-id="ca7c3-127">Traducción de puerta de enlace XMPP</span><span class="sxs-lookup"><span data-stu-id="ca7c3-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="ca7c3-128">Abra el Skype para el Panel de Control de Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="ca7c3-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="ca7c3-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="ca7c3-129"></span></span>

<span data-ttu-id="ca7c3-130">Desde el servidor Front-End en su Skype para la implementación empresarial Server 2019, abra el Skype para el Panel de Control de Business Server 2019 y seleccione el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="ca7c3-131">Repita el procedimiento para abrir el Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ca7c3-132">En Skype para Business Server 2019, debe actualizar Silverlight a Silverlight, versión 5 antes de usar el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="ca7c3-133">Esta topología incluye ahora heredado y Skype para funciones de servidor de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="ca7c3-134">No intente abrir la topología en el generador de topología heredada</span><span class="sxs-lookup"><span data-stu-id="ca7c3-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="ca7c3-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="ca7c3-135"></span></span>

<span data-ttu-id="ca7c3-136">Si se intenta abrir la topología con el generador de topología heredada, encontrará el error que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="ca7c3-137">Sólo se puede ver la topología con Skype para Business Server 2019 Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="ca7c3-138">Debe usarse el Skype para Business Server 2019 Topology Builder para crear grupos de servidores de Skype para Business Server 2019 y la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  


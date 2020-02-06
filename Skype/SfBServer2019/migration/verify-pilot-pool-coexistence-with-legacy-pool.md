---
title: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Proceso para comprobar la coexistencia de un grupo piloto con grupo heredado.
ms.openlocfilehash: 386ea4a7857fcdef7d45e5d8029ff4bf31293819
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812678"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="7ffff-103">Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado</span><span class="sxs-lookup"><span data-stu-id="7ffff-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="7ffff-104">**En este artículo**</span><span class="sxs-lookup"><span data-stu-id="7ffff-104">**In this article**</span></span>
  
[<span data-ttu-id="7ffff-105">Comprobar que los servicios de Skype empresarial Server 2019 se han iniciado</span><span class="sxs-lookup"><span data-stu-id="7ffff-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="7ffff-106">Abrir el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="7ffff-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="7ffff-107">No intente abrir la topología en el generador de topología heredado</span><span class="sxs-lookup"><span data-stu-id="7ffff-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="7ffff-108">Después de implementar el grupo piloto, debe comprobar la coexistencia de las dos agrupaciones mediante las herramientas administrativas para ver la información del grupo.</span><span class="sxs-lookup"><span data-stu-id="7ffff-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="7ffff-109">Para los grupos de 2019 y los grupos heredados de Skype empresarial Server, debe usar las herramientas del panel de control y del generador de topologías de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ffff-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="7ffff-110">Comprobar que los servicios de Skype empresarial Server 2019 se han iniciado</span><span class="sxs-lookup"><span data-stu-id="7ffff-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="7ffff-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="7ffff-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="7ffff-112">Desde el servidor front-end de Skype empresarial Server 2019, navegue hasta el applet Tools\Services administrativo.</span><span class="sxs-lookup"><span data-stu-id="7ffff-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="7ffff-113">Compruebe que se están ejecutando los siguientes servicios en el servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="7ffff-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="7ffff-114">Agente del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="7ffff-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="7ffff-115">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7ffff-115">Application Sharing</span></span>
    - <span data-ttu-id="7ffff-116">Servicio de prueba de audio</span><span class="sxs-lookup"><span data-stu-id="7ffff-116">Audio Test Service</span></span>
    - <span data-ttu-id="7ffff-117">Audioconferencias y videoconferencias</span><span class="sxs-lookup"><span data-stu-id="7ffff-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="7ffff-118">Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="7ffff-118">Call Park</span></span>
    - <span data-ttu-id="7ffff-119">Anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="7ffff-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="7ffff-120">Operador de conferencias</span><span class="sxs-lookup"><span data-stu-id="7ffff-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="7ffff-121">Front-end</span><span class="sxs-lookup"><span data-stu-id="7ffff-121">Front-End</span></span>
    - <span data-ttu-id="7ffff-122">Conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="7ffff-122">IM Conferencing</span></span>
    - <span data-ttu-id="7ffff-123">Servidores</span><span class="sxs-lookup"><span data-stu-id="7ffff-123">Mediation</span></span>
    - <span data-ttu-id="7ffff-124">Agente duplicador de réplicas</span><span class="sxs-lookup"><span data-stu-id="7ffff-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="7ffff-125">Grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="7ffff-125">Response Group</span></span>
    - <span data-ttu-id="7ffff-126">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="7ffff-126">Web Conferencing</span></span>
    - <span data-ttu-id="7ffff-127">Puerta de enlace de traducción de XMPP</span><span class="sxs-lookup"><span data-stu-id="7ffff-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="7ffff-128">Abrir el panel de control de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="7ffff-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="7ffff-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="7ffff-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="7ffff-130">Desde el servidor front-end de su implementación de Skype empresarial Server 2019, abra el panel de control de Skype empresarial Server 2019 y seleccione el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="7ffff-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="7ffff-131">Repita el procedimiento para abrir el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="7ffff-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7ffff-132">En Skype empresarial Server 2019, debe actualizar Silverlight a la versión 5 antes de usar el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7ffff-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="7ffff-133">Ahora, esta topología incluye roles de servidor heredados de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ffff-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="7ffff-134">No intente abrir la topología en el generador de topología heredado</span><span class="sxs-lookup"><span data-stu-id="7ffff-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="7ffff-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="7ffff-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="7ffff-136">La topología solo se puede ver con el generador de topología de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ffff-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="7ffff-137">El generador de topología de Skype empresarial Server 2019 debe usarse para crear grupos de servidores para Skype empresarial Server 2019 y la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="7ffff-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  


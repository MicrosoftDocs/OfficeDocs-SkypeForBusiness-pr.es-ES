---
title: Definir los requisitos para las llamadas de emergencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Resume los pasos necesarios para habilitar E9-1-1 en Skype empresarial Server Enterprise Voice, en función de si tiene un proveedor de servicios E9-1-1 o una puerta de enlace de ELIN de SIP.
ms.openlocfilehash: 9e6ccd4b93416d49993dbc24ee0592d130e25de8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276974"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="f33c8-103">Definir los requisitos para las llamadas de emergencia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="f33c8-104">Resume los pasos necesarios para habilitar E9-1-1 en Skype empresarial Server Enterprise Voice, en función de si tiene un proveedor de servicios E9-1-1 o una puerta de enlace de ELIN de SIP.</span><span class="sxs-lookup"><span data-stu-id="f33c8-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="f33c8-105">Antes de comenzar una implementación de Skype empresarial Server E9-1-1, primero debe poder responder a las preguntas detalladas en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="f33c8-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="f33c8-106">La planeación que necesite dependerá del tipo de solución E9-1-1 que haya decidido implementar, ya sea un proveedor de servicios E9-1-1 por medio de un tronco SIP o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="f33c8-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="f33c8-107">En la tabla siguiente se identifican las secciones de este libro de planeación que necesitará revisar para cada una de esas soluciones.</span><span class="sxs-lookup"><span data-stu-id="f33c8-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="f33c8-108">**Pasos de planeación por tipo de E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="f33c8-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="f33c8-109">**Proveedor de servicios troncales SIP**</span><span class="sxs-lookup"><span data-stu-id="f33c8-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="f33c8-110">**Puerta de enlace ELIN**</span><span class="sxs-lookup"><span data-stu-id="f33c8-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f33c8-111">Definir el ámbito de la implementación de E9-1-1 en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="f33c8-112">Definir el ámbito de la implementación de E9-1-1 en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="f33c8-113">Definir los elementos de red que se usan para determinar la ubicación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="f33c8-114">Definir los elementos de red que se usan para determinar la ubicación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="f33c8-115">Habilitar usuarios para E9-1-1 en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="f33c8-116">Habilitar usuarios para E9-1-1 en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="f33c8-117">Administrar las ubicaciones de los proveedores de servicios de tronco de SIP en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="f33c8-118">Administrar las ubicaciones de las puertas de enlace de ELIN en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="f33c8-119">Definir la experiencia de usuario para la adquisición manual de una ubicación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="f33c8-120">Definir la experiencia de usuario para la adquisición manual de una ubicación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="f33c8-121">Diseñar el tronco del SIP para E9-1-1 en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="f33c8-122">Incluir el escritorio de seguridad en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="f33c8-123">Incluir el escritorio de seguridad en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="f33c8-124">Planificar directivas de ubicación para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="f33c8-125">Elegir un proveedor de servicios E9-1-1 en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="f33c8-126">Asignar ámbito de directiva de ubicación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="f33c8-127">Planificar directivas de ubicación para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="f33c8-128">Asignar ámbito de directiva de ubicación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f33c8-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   


---
title: Definir los requisitos para las llamadas de emergencia de Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Se resumen los pasos necesarios para habilitar E9-1-1 en Skype para Business Server Enterprise Voice, dependiendo de si tiene un proveedor de servicios de E9-1-1 de tronco SIP o puerta de enlace ELIN.
ms.openlocfilehash: 6e61a21f77f9ed099e48b10c06e7afd0bde434df
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979106"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="f273d-103">Definir los requisitos para las llamadas de emergencia de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="f273d-104">Se resumen los pasos necesarios para habilitar E9-1-1 en Skype para Business Server Enterprise Voice, dependiendo de si tiene un proveedor de servicios de E9-1-1 de tronco SIP o puerta de enlace ELIN.</span><span class="sxs-lookup"><span data-stu-id="f273d-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="f273d-105">Antes de comenzar una Skype para la implementación de servidor empresarial E9-1-1, primero debe ser capaz de responder a las preguntas en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="f273d-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="f273d-106">La planeación que necesite dependerá del tipo de solución E9-1-1 que haya decidido implementar, ya sea un proveedor de servicios E9-1-1 por medio de un tronco SIP o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="f273d-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="f273d-107">En la siguiente tabla identifica las secciones de este libro de planeación que debe revisar para cada una de esas soluciones.</span><span class="sxs-lookup"><span data-stu-id="f273d-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="f273d-108">**Pasos de planeación por tipo de E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="f273d-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="f273d-109">**Proveedor de servicios troncales SIP**</span><span class="sxs-lookup"><span data-stu-id="f273d-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="f273d-110">**Puerta de enlace ELIN**</span><span class="sxs-lookup"><span data-stu-id="f273d-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f273d-111">Definir el ámbito de la implementación de E9-1-1 de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="f273d-112">Definir el ámbito de la implementación de E9-1-1 de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="f273d-113">Definir los elementos de red que se utiliza para determinar la ubicación de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="f273d-114">Definir los elementos de red que se utiliza para determinar la ubicación de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="f273d-115">Habilitar a usuarios para E9-1-1 en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="f273d-116">Habilitar a usuarios para E9-1-1 en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="f273d-117">Administración de ubicaciones para proveedores de servicios de tronco SIP en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="f273d-118">Administración de ubicaciones para puertas de enlace ELIN en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="f273d-119">Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="f273d-120">Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="f273d-121">Diseñar el tronco SIP para E9-1-1 en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="f273d-122">Incluir el departamento de seguridad en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="f273d-123">Incluir el departamento de seguridad en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="f273d-124">Planeación de las directivas de ubicación de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="f273d-125">Elija un proveedor de servicios E9-1-1 para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="f273d-126">Asignar el ámbito de directiva de ubicación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="f273d-127">Planeación de las directivas de ubicación de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="f273d-128">Asignar el ámbito de directiva de ubicación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f273d-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   


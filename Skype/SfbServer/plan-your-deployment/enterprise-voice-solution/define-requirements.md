---
title: Definir los requisitos para llamadas de emergencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Resume los pasos necesarios para habilitar E9-1-1 en Skype Empresarial Server Telefonía IP empresarial, en función de si tiene un proveedor de servicios E9-1-1 de tronco SIP o una puerta de enlace ELIN.
ms.openlocfilehash: 8efd38657a80bee1ecd979e8730feacfb980053e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825820"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="9502b-103">Definir los requisitos para llamadas de emergencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="9502b-104">Resume los pasos necesarios para habilitar E9-1-1 en Skype Empresarial Server Telefonía IP empresarial, en función de si tiene un proveedor de servicios E9-1-1 de tronco SIP o una puerta de enlace ELIN.</span><span class="sxs-lookup"><span data-stu-id="9502b-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="9502b-105">Antes de comenzar una implementación de Skype Empresarial Server E9-1-1, primero debería poder responder a las preguntas detalladas en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="9502b-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="9502b-106">La planeación que necesite dependerá del tipo de solución E9-1-1 que haya decidido implementar, ya sea un proveedor de servicios E9-1-1 mediante troncales SIP o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="9502b-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="9502b-107">En la tabla siguiente se identifican las secciones de este libro de planeación que deberá revisar para cada una de esas soluciones.</span><span class="sxs-lookup"><span data-stu-id="9502b-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="9502b-108">**Pasos de planeación por tipo de E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="9502b-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="9502b-109">**Proveedor de servicios troncales SIP**</span><span class="sxs-lookup"><span data-stu-id="9502b-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="9502b-110">**Puerta de enlace ELIN**</span><span class="sxs-lookup"><span data-stu-id="9502b-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9502b-111">Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="9502b-112">Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="9502b-113">Definir los elementos de red usados para determinar la ubicación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="9502b-114">Definir los elementos de red usados para determinar la ubicación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="9502b-115">Habilitar usuarios para E9-1-1 en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="9502b-116">Habilitar usuarios para E9-1-1 en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="9502b-117">Administrar ubicaciones para proveedores de servicios troncales SIP en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="9502b-118">Administrar ubicaciones para puertas de enlace ELIN en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="9502b-119">Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="9502b-120">Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="9502b-121">Diseñar el tronco SIP para E9-1-1 en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="9502b-122">Incluir el servicio de seguridad en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="9502b-123">Incluir el servicio de seguridad en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="9502b-124">Planear directivas de ubicación para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="9502b-125">Elegir un proveedor de servicios E9-1-1 para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="9502b-126">Asignar ámbito de directiva de ubicación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="9502b-127">Planear directivas de ubicación para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="9502b-128">Asignar ámbito de directiva de ubicación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9502b-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   


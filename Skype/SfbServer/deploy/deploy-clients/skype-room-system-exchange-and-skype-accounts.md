---
title: Aprovisionamiento de cuentas de Exchange y Skype del sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: Lea estos temas para obtener información sobre cómo aprovisionar cuentas de Exchange y Skype para el sistema de salas de Skype.
ms.openlocfilehash: be43e732a97dc81fdd2e3a6bdb355afaff4db37d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220920"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="3e15f-103">Aprovisionamiento de cuentas de Exchange y Skype del sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="3e15f-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="3e15f-104">Lea estos temas para obtener información sobre cómo aprovisionar cuentas de Exchange y Skype para el sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="3e15f-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="3e15f-105">Salas de Microsoft Teams es un producto diferente con diferentes dependencias y procedimientos de implementación.</span><span class="sxs-lookup"><span data-stu-id="3e15f-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="3e15f-106">Para obtener información sobre las salas de Microsoft Teams, vea la [información general sobre la implementación](room-systems-v2.md)de salas de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e15f-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3e15f-107">El aprovisionamiento de la cuenta del sistema de salas de Skype depende del tipo de topología que tenga su organización.</span><span class="sxs-lookup"><span data-stu-id="3e15f-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="3e15f-108">Para obtener más información acerca de las topologías de Active Directory, consulte [Environmental Requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e15f-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="3e15f-109">Aprovisionamiento de &amp; las cuentas de Skype empresarial para el sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="3e15f-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="3e15f-110">En los siguientes temas se describe cómo aprovisionar y administrar las cuentas de Exchange y Skype empresarial del sistema de salas de Skype para:</span><span class="sxs-lookup"><span data-stu-id="3e15f-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="3e15f-111">Implementaciones locales de un solo bosque</span><span class="sxs-lookup"><span data-stu-id="3e15f-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="3e15f-112">Implementaciones locales de bosques múltiples</span><span class="sxs-lookup"><span data-stu-id="3e15f-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="3e15f-113">Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="3e15f-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="3e15f-114">Implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="3e15f-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="3e15f-115">Sistema de salas de Skype y socios federados de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="3e15f-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="3e15f-116">Administrar cuentas de sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="3e15f-116">Manage Skype Room System accounts</span></span>
    


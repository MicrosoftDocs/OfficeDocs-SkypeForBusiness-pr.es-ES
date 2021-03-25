---
title: Aprovisionamiento de cuentas de Skype Room System Exchange y Skype
ms.author: v-cichur
author: cichur
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
description: Lea estos temas para obtener información sobre cómo aprovisionar cuentas de Exchange y Skype para El sistema de salón de Skype.
ms.openlocfilehash: 0e8c73bc83a62465dc711b4a6f2725f1d9c576f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113066"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="b0c69-103">Aprovisionamiento de cuentas de Skype Room System Exchange y Skype</span><span class="sxs-lookup"><span data-stu-id="b0c69-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="b0c69-104">Lea estos temas para obtener información sobre cómo aprovisionar cuentas de Exchange y Skype para El sistema de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="b0c69-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="b0c69-105">Microsoft Teams Rooms es un producto diferente con diferentes dependencias y procedimientos de implementación.</span><span class="sxs-lookup"><span data-stu-id="b0c69-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="b0c69-106">Para obtener información sobre salas de Microsoft Teams, vea la introducción a la implementación de Salas [de](/MicrosoftTeams/rooms/rooms-deploy)Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="b0c69-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](/MicrosoftTeams/rooms/rooms-deploy).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0c69-107">El aprovisionamiento de cuentas del sistema de salón de Skype depende del tipo de topología que tenga su organización.</span><span class="sxs-lookup"><span data-stu-id="b0c69-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="b0c69-108">Para obtener más información acerca de las topologías de Active Directory, vea [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0c69-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="b0c69-109">Aprovisionamiento de cuentas de Skype Room System Exchange &amp; Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b0c69-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="b0c69-110">En los temas siguientes se describe cómo aprovisionar y administrar cuentas de Skype Room System Exchange y Skype Empresarial para:</span><span class="sxs-lookup"><span data-stu-id="b0c69-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="b0c69-111">Implementaciones locales de un solo bosque</span><span class="sxs-lookup"><span data-stu-id="b0c69-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="b0c69-112">Implementaciones locales de múltiples bosques</span><span class="sxs-lookup"><span data-stu-id="b0c69-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="b0c69-113">Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="b0c69-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="b0c69-114">Implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="b0c69-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="b0c69-115">Sistema de sala de Skype y socios federados de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b0c69-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="b0c69-116">Administrar cuentas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="b0c69-116">Manage Skype Room System accounts</span></span>

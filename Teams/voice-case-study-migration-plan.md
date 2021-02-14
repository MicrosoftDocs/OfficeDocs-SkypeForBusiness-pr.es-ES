---
title: Caso práctico de Teams voice Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Caso práctico de voz de Teams para una corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786089"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="45949-103">Caso práctico Contoso: Plan de actualización de Teams</span><span class="sxs-lookup"><span data-stu-id="45949-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="45949-104">En la decisión de migrar de Skype Empresarial a Teams, Contoso quería proporcionar una experiencia de transición sencilla para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="45949-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="45949-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span><span class="sxs-lookup"><span data-stu-id="45949-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="45949-106">Esto permitía a los usuarios de Teams y Skype Empresarial local compartir la presencia y comunicarse.</span><span class="sxs-lookup"><span data-stu-id="45949-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="45949-107">Cuando los usuarios entraban en el programa piloto de Sistema telefónico, solo se movían al modo Teams.</span><span class="sxs-lookup"><span data-stu-id="45949-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="45949-108">Para comprender conceptos fundamentales sobre la actualización, los métodos y los modos, Contoso lea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="45949-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="45949-109">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45949-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="45949-110">Actualización de Skype Empresarial a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45949-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="45949-111">Guía de migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="45949-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="45949-112">Contoso también ha participado en la sesión Ignite 2019 diseñando la ruta de [Skype Empresarial a Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="45949-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="45949-113">Contoso ha aprendido acerca de:</span><span class="sxs-lookup"><span data-stu-id="45949-113">Contoso learned about:</span></span>

- <span data-ttu-id="45949-114">Conceptos fundamentales como la interoperabilidad, la federación y el comportamiento de actualización</span><span class="sxs-lookup"><span data-stu-id="45949-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="45949-115">Modos de coexistencia y administración basados en TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="45949-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="45949-116">Experiencia del usuario final para:</span><span class="sxs-lookup"><span data-stu-id="45949-116">End user experience for:</span></span> 

  - <span data-ttu-id="45949-117">Chat y llamadas</span><span class="sxs-lookup"><span data-stu-id="45949-117">Chat and Calling</span></span> 

  - <span data-ttu-id="45949-118">Programación de reuniones</span><span class="sxs-lookup"><span data-stu-id="45949-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="45949-119">Disponibilidad de la funcionalidad de colaboración en clientes de Teams</span><span class="sxs-lookup"><span data-stu-id="45949-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="45949-120">Para planear y configurar la conectividad híbrida, el primer paso para mover su [](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) entorno local a la nube, Contoso lea la conectividad híbrida de [Plan](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) y Configurar conectividad híbrida para comprender cómo:</span><span class="sxs-lookup"><span data-stu-id="45949-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="45949-121">Configure su servicio de entorno local para federar con Office 365.</span><span class="sxs-lookup"><span data-stu-id="45949-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="45949-122">Configurar su entorno local para confiar en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365</span><span class="sxs-lookup"><span data-stu-id="45949-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="45949-123">Habilite el espacio de direcciones SIP compartido en su espacio empresarial de Office 365.</span><span class="sxs-lookup"><span data-stu-id="45949-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="45949-124">Use el modo Islas durante el piloto técnico.</span><span class="sxs-lookup"><span data-stu-id="45949-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="45949-125">Cambie a los usuarios al modo TeamsOnly una vez que el usuario esté habilitado para Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="45949-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="45949-126">TeamsOnly mode is required for Calling Plan and Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="45949-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 

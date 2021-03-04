---
title: Caso práctico de Contoso de voz de Teams
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
ms.openlocfilehash: 93f6d0877537a740dc867b44c3c4deb9bebb8441
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421295"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="24fa7-103">Caso práctico de Contoso: Plan de actualización de Teams</span><span class="sxs-lookup"><span data-stu-id="24fa7-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="24fa7-104">En la decisión de migrar de Skype Empresarial a Teams, Contoso quería proporcionar una experiencia de transición fácil para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="24fa7-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="24fa7-105">En lugar de cambiar todos a Teams al mismo tiempo, decidieron configurar la conectividad híbrida y usar el método de capacidades superpuestas para mover usuarios a Teams.</span><span class="sxs-lookup"><span data-stu-id="24fa7-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="24fa7-106">Esto permitía a los usuarios de Teams y Skype Empresarial local compartir presencia y comunicarse.</span><span class="sxs-lookup"><span data-stu-id="24fa7-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="24fa7-107">Cuando los usuarios entraron en el piloto de Sistema telefónico, se movieron al modo Solo para equipos.</span><span class="sxs-lookup"><span data-stu-id="24fa7-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="24fa7-108">Para comprender conceptos fundamentales sobre la actualización, los métodos y los modos, Contoso leyó los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="24fa7-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="24fa7-109">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24fa7-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="24fa7-110">Estrategias de actualización para administradores de TI</span><span class="sxs-lookup"><span data-stu-id="24fa7-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- [<span data-ttu-id="24fa7-111">Guía de migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="24fa7-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="24fa7-112">Contoso también asistió a la sesión Ignite 2019 Diseñando su ruta de [Skype Empresarial a Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="24fa7-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="24fa7-113">Contoso ha aprendido acerca de:</span><span class="sxs-lookup"><span data-stu-id="24fa7-113">Contoso learned about:</span></span>

- <span data-ttu-id="24fa7-114">Conceptos fundamentales como interoperabilidad, federación y comportamiento de actualización</span><span class="sxs-lookup"><span data-stu-id="24fa7-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="24fa7-115">Modos de coexistencia y administración basados en TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="24fa7-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="24fa7-116">Experiencia de usuario final para:</span><span class="sxs-lookup"><span data-stu-id="24fa7-116">End user experience for:</span></span> 

  - <span data-ttu-id="24fa7-117">Chat y llamadas</span><span class="sxs-lookup"><span data-stu-id="24fa7-117">Chat and Calling</span></span> 

  - <span data-ttu-id="24fa7-118">Programación de reuniones</span><span class="sxs-lookup"><span data-stu-id="24fa7-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="24fa7-119">Disponibilidad de la funcionalidad de colaboración en clientes de Teams</span><span class="sxs-lookup"><span data-stu-id="24fa7-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="24fa7-120">Para planear y configurar la conectividad híbrida, el primer paso para [](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) mover su entorno local a la nube, Contoso leyó Planear conectividad híbrida y [Configurar](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) conectividad híbrida para comprender cómo:</span><span class="sxs-lookup"><span data-stu-id="24fa7-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="24fa7-121">Configure su servicio de entorno local para federar con Office 365.</span><span class="sxs-lookup"><span data-stu-id="24fa7-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="24fa7-122">Configurar su entorno local para confiar en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365</span><span class="sxs-lookup"><span data-stu-id="24fa7-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="24fa7-123">Habilitar el espacio de direcciones SIP compartido en su espacio empresarial de Office 365.</span><span class="sxs-lookup"><span data-stu-id="24fa7-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="24fa7-124">Use el modo Islas durante el piloto técnico.</span><span class="sxs-lookup"><span data-stu-id="24fa7-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="24fa7-125">Cambiar usuarios al modo TeamsOnly una vez que el usuario esté habilitado para Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="24fa7-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="24fa7-126">TeamsOnly mode is required for Calling Plan and Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="24fa7-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 

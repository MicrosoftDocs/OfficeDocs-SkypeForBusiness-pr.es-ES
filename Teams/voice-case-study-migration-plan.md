---
title: Caso práctico de voz de Contoso
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
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786089"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="8235a-103">Caso práctico de Contoso: Plan de actualización de Teams</span><span class="sxs-lookup"><span data-stu-id="8235a-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="8235a-104">En la decisión de migrar de Skype empresarial a Teams, contoso quería proporcionar una experiencia de transición sencilla para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="8235a-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="8235a-105">En lugar de cambiar a todos los equipos al mismo tiempo, decidieron configurar la conectividad híbrida y usar el método de funciones superpuestas para mover usuarios a teams.</span><span class="sxs-lookup"><span data-stu-id="8235a-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="8235a-106">Esto permitía a los usuarios de Teams y de Skype empresarial locales compartir presencia y comunicarte.</span><span class="sxs-lookup"><span data-stu-id="8235a-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="8235a-107">A medida que los usuarios escribieron el piloto para el sistema telefónico, se movieron al modo solo para equipos.</span><span class="sxs-lookup"><span data-stu-id="8235a-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="8235a-108">Para comprender los conceptos fundamentales sobre la actualización, los métodos y los modos, contoso Lee los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8235a-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="8235a-109">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8235a-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="8235a-110">Actualización de Skype Empresarial a Teams</span><span class="sxs-lookup"><span data-stu-id="8235a-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="8235a-111">Guía de migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="8235a-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="8235a-112">Contoso también asistió a la sesión de encendido 2019, en la [que se diseña la ruta de Skype empresarial a teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="8235a-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="8235a-113">Contoso aprendió acerca de:</span><span class="sxs-lookup"><span data-stu-id="8235a-113">Contoso learned about:</span></span>

- <span data-ttu-id="8235a-114">Conceptos fundamentales como la interoperabilidad, la Federación y el comportamiento de actualización</span><span class="sxs-lookup"><span data-stu-id="8235a-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="8235a-115">Modos de coexistencia y administración basada en TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="8235a-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="8235a-116">Experiencia de usuario final para:</span><span class="sxs-lookup"><span data-stu-id="8235a-116">End user experience for:</span></span> 

  - <span data-ttu-id="8235a-117">Conversaciones y llamadas</span><span class="sxs-lookup"><span data-stu-id="8235a-117">Chat and Calling</span></span> 

  - <span data-ttu-id="8235a-118">Programación de reuniones</span><span class="sxs-lookup"><span data-stu-id="8235a-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="8235a-119">Disponibilidad de las funciones de colaboración en los clientes de Teams</span><span class="sxs-lookup"><span data-stu-id="8235a-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="8235a-120">Para planear y configurar la conectividad híbrida, el primer paso para mover su entorno local a la nube, el [plan](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) de lectura de [contoso y la conectividad híbrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) para comprender cómo:</span><span class="sxs-lookup"><span data-stu-id="8235a-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="8235a-121">Configure su servicio de entorno local para federarse con Office 365.</span><span class="sxs-lookup"><span data-stu-id="8235a-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="8235a-122">Configurar su entorno local para confiar en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365</span><span class="sxs-lookup"><span data-stu-id="8235a-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="8235a-123">Habilite el espacio de direcciones SIP compartido en su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8235a-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="8235a-124">Use el modo islas durante el programa piloto.</span><span class="sxs-lookup"><span data-stu-id="8235a-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="8235a-125">Cambiar usuarios al modo TeamsOnly una vez que el usuario esté habilitado para el sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="8235a-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="8235a-126">El modo TeamsOnly es necesario para llamar a plan y enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="8235a-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 

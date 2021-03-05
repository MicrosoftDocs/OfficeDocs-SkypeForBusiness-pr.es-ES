---
title: Consideraciones del modo Teams solo
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: El administrador puede obtener información sobre cómo prepararse para una actualización al modo solo de Microsoft Teams en el Centro de administración de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a38967ffb80f59fab88006b5aad2e6ecb76395c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461000"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="40e20-103">Consideraciones del modo Teams solo</span><span class="sxs-lookup"><span data-stu-id="40e20-103">Teams Only mode considerations</span></span>

<span data-ttu-id="40e20-104">Los administradores de microsoft 365 u organizaciones de Office 365 pueden actualizar a los usuarios individuales o a todo el espacio empresarial al modo solo de Teams.</span><span class="sxs-lookup"><span data-stu-id="40e20-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

<span data-ttu-id="40e20-105">Actualizar al modo Solo teams ofrece a los usuarios todas las ventajas de Microsoft Teams, el hub para el trabajo en equipo en Microsoft 365 u Office 365, a través de una sola experiencia de cliente.</span><span class="sxs-lookup"><span data-stu-id="40e20-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="40e20-106">Los usuarios del modo Solo teams recibirán todas las llamadas y chats en Teams, independientemente de si el remitente usa Skype Empresarial o Teams, y se beneficiarán del soporte de interoperabilidad y federación.</span><span class="sxs-lookup"><span data-stu-id="40e20-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="40e20-107">Aunque miles de clientes se han actualizado correctamente a Microsoft Teams, hay consideraciones que pueden influir en la escala de tiempo de actualización de su organización y en la experiencia del usuario en el camino.</span><span class="sxs-lookup"><span data-stu-id="40e20-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="40e20-108">Para conseguir la mejor experiencia de usuario posible, confirme que Teams cumple los requisitos de colaboración y comunicación, asegúrese de que su red está lista para dar soporte a Teams e implemente su plan de preparación de usuarios antes de actualizar a los usuarios a Teams.</span><span class="sxs-lookup"><span data-stu-id="40e20-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="40e20-109">Si acaba de iniciar la planificación de la actualización, asegúrese de revisar nuestra Guía de introducción a la actualización [de Microsoft Teams.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="40e20-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="40e20-110">**Consideraciones de coexistencia:** las organizaciones que ya usan Skype Empresarial Online o Skype Empresarial Server pueden introducir Teams en su entorno a un ritmo que satisfaga sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="40e20-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="40e20-111">Las organizaciones pueden agregar Teams de forma incremental a un conjunto de usuarios deseado según sea necesario, y los usuarios que usan Teams pueden comunicarse con los usuarios que usan Skype Empresarial y viceversa.</span><span class="sxs-lookup"><span data-stu-id="40e20-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="40e20-112">Para administrar esta experiencia, los administradores usan modos de coexistencia, que definen la experiencia del cliente del usuario final, el comportamiento de enrutamiento de las llamadas y chats entrantes, y si las nuevas reuniones están programadas en Teams o Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="40e20-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="40e20-113">Los usuarios pueden federar con usuarios de otras organizaciones si el usuario se actualiza a **Teams Only**; sin embargo, se proporciona la mejor experiencia cuando ambos usuarios usan Teams.</span><span class="sxs-lookup"><span data-stu-id="40e20-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="40e20-114">Los usuarios que se actualicen a Teams Only aún pueden unirse a reuniones de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="40e20-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="40e20-115">Para obtener información más detallada sobre la coexistencia, consulte Comprender la coexistencia e interoperabilidad de Microsoft Teams y [Skype Empresarial.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="40e20-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="40e20-116">Para obtener más información sobre Teams y Skype (consumidor), vea [Teams e Interoperabilidad de Skype.](teams-skype-interop.md)</span><span class="sxs-lookup"><span data-stu-id="40e20-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="40e20-117">**Consideraciones específicas del** usuario: algunos escenarios de usuario siguen evolucionando y los administradores pueden decidir posponer temporalmente la actualización de determinados usuarios al actualizar otros usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="40e20-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="40e20-118">En particular, seguimos trabajando en escenarios de direccionamiento para los usuarios cuyo dispositivo principal está basado en VDI.</span><span class="sxs-lookup"><span data-stu-id="40e20-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="40e20-119">Para los anuncios del sitio, supervise la [hoja de ruta de Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="40e20-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="40e20-120">Antes de pasar al modo solo de Teams, debe reemplazar o actualizar dispositivos que no son compatibles con Teams.</span><span class="sxs-lookup"><span data-stu-id="40e20-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="40e20-121">**Recuerde:** El paso a Teams es más que una migración técnica.</span><span class="sxs-lookup"><span data-stu-id="40e20-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="40e20-122">Una actualización correcta evalúa la preparación técnica y la preparación del usuario final.</span><span class="sxs-lookup"><span data-stu-id="40e20-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="40e20-123">Revise nuestras instrucciones de actualización de Skype Empresarial [a](upgrade-framework.md) Teams para obtener más información sobre cómo planear la implementación de la actualización a Teams.</span><span class="sxs-lookup"><span data-stu-id="40e20-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  

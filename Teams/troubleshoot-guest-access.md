---
title: Solución de problemas con el acceso de invitado en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Obtenga ayuda para solucionar problemas y solucionar problemas con el acceso de invitados en Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0468d0d3d1cc7a8d1c17699e28c1449e1f7800c8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948688"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="cc610-103">Solución de problemas con el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc610-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>

- <span data-ttu-id="cc610-104">Para ver si conocemos el problema, consulte Soporte [técnico Teams en su organización.](/MicrosoftTeams/troubleshoot/teams-welcome)</span><span class="sxs-lookup"><span data-stu-id="cc610-104">To see whether we know about your problem, check out [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>
- <span data-ttu-id="cc610-105">Para comprobar si hay problemas de soporte técnico actuales relacionados con el acceso de invitados en Teams, vaya a [Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="cc610-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="cc610-106">Los invitados son personas de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="cc610-106">Guests are people outside your organization.</span></span> <span data-ttu-id="cc610-107">Si alguien se encuentra en su organización (incluidos los empleados, los contratistas in situ o los agentes in situ), no se pueden agregar como invitados.</span><span class="sxs-lookup"><span data-stu-id="cc610-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="cc610-108">Esto mismo se aplica a las filiales.</span><span class="sxs-lookup"><span data-stu-id="cc610-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="cc610-109">Obtenga más información sobre las próximas características de acceso de invitados nuevas o actualizadas en la [Hoja de ruta de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="cc610-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="cc610-110">Díganos lo que quiere en [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="cc610-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="cc610-111">Si los invitados ven errores de licencia</span><span class="sxs-lookup"><span data-stu-id="cc610-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="cc610-112">El acceso de invitado en Teams usa Azure Active Directory (Azure AD) negocio a negocio (B2B) y el modelo de licencia.</span><span class="sxs-lookup"><span data-stu-id="cc610-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="cc610-113">El acceso de invitados está incluido en todas las suscripciones de Microsoft 365 Empresa Estándar, Office 365 Enterprise y Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="cc610-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="cc610-114">No se necesita ninguna otra licencia de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc610-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="cc610-115">Teams estar habilitado en el espacio empresarial de un invitado para que los invitados puedan iniciar sesión y usar Teams como invitado en otro espacio empresarial (recurso).</span><span class="sxs-lookup"><span data-stu-id="cc610-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="cc610-116">Si ve errores de licencia, asegúrese de leer el modelo de facturación de identidades externas de [Azure AD](/azure/active-directory/external-identities/external-identities-pricing) para determinar los requisitos de licencias para satisfacer sus necesidades de acceso de invitado en su organización.</span><span class="sxs-lookup"><span data-stu-id="cc610-116">If you're seeing licensing errors, make sure to read the [Billing model for Azure AD External Identities](/azure/active-directory/external-identities/external-identities-pricing) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>

- <span data-ttu-id="cc610-117">Las licencias de invitado se cuentan contra la organización que invita.</span><span class="sxs-lookup"><span data-stu-id="cc610-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="cc610-118">Considere esto al calcular el número de licencias que necesita.</span><span class="sxs-lookup"><span data-stu-id="cc610-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="cc610-119">Las licencias se cuentan en su organización tanto si los invitados invitados proceden de otra organización Microsoft 365 como si usan sus direcciones de correo electrónico personales.</span><span class="sxs-lookup"><span data-stu-id="cc610-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="cc610-120">Soporte técnico para los tipos de usuario B2B</span><span class="sxs-lookup"><span data-stu-id="cc610-120">Support for B2B User types</span></span>

<span data-ttu-id="cc610-121">Actualmente, Teams solo admiten los tipos de estado 1 y estado 2 de usuarios invitados [definido por Azure B2B](/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="cc610-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc610-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cc610-122">Related topics</span></span>

[<span data-ttu-id="cc610-123">Acceso de invitado a Teams</span><span class="sxs-lookup"><span data-stu-id="cc610-123">Guest access in Teams</span></span>](guest-access.md)

[<span data-ttu-id="cc610-124">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="cc610-124">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
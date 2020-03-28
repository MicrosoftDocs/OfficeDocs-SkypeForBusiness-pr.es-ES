---
title: Solución de problemas con el acceso de invitado en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837640"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="5eb88-103">Solución de problemas con el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5eb88-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="5eb88-104">Es posible que tenga que esperar hasta 24 horas para que sus cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="5eb88-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="5eb88-105">Para comprobar si hay problemas de soporte técnico actuales relacionados con el acceso de invitados en Teams, vaya a [Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="5eb88-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="5eb88-106">Para comprobar si conocemos su problema, consulte [Problemas conocidos de Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5eb88-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="5eb88-107">Los invitados son usuarios de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="5eb88-107">Guests are users outside your organization.</span></span> <span data-ttu-id="5eb88-108">Si alguien se encuentra en su organización (incluidos los empleados, los contratistas in situ o los agentes in situ), no se pueden agregar como invitados.</span><span class="sxs-lookup"><span data-stu-id="5eb88-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="5eb88-109">Esto mismo se aplica a las filiales.</span><span class="sxs-lookup"><span data-stu-id="5eb88-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="5eb88-110">Obtenga más información sobre las próximas características de acceso de invitados nuevas o actualizadas en la [Hoja de ruta de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="5eb88-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="5eb88-111">Díganos lo que quiere en [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="5eb88-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="5eb88-112">Si los invitados ven errores de licencia</span><span class="sxs-lookup"><span data-stu-id="5eb88-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="5eb88-113">El acceso de invitado en Teams usa Azure Active Directory (Azure AD) negocio a negocio (B2B) y el modelo de licencia.</span><span class="sxs-lookup"><span data-stu-id="5eb88-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="5eb88-114">El acceso de invitado se incluye con todas las suscripciones de Office 365 Empresa Premium, Office 365 Enterprise y Office 365 Educación.</span><span class="sxs-lookup"><span data-stu-id="5eb88-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="5eb88-115">No se necesita ninguna otra licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5eb88-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="5eb88-116">Si ve errores de licencia, asegúrese de leer la información [instrucciones de licencias B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar los requisitos de licencia para satisfacer las necesidades de acceso de invitado en su organización.</span><span class="sxs-lookup"><span data-stu-id="5eb88-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="5eb88-117">Las licencias de invitado se cuentan contra la organización que invita.</span><span class="sxs-lookup"><span data-stu-id="5eb88-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="5eb88-118">Considere esto al calcular el número de licencias que necesita.</span><span class="sxs-lookup"><span data-stu-id="5eb88-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="5eb88-119">Las licencias se cuentan en contra de su organización, independientemente de si los invitados provienen de otro espacio empresarial de Office 365 o si están utilizando sus direcciones de correo electrónico personales.</span><span class="sxs-lookup"><span data-stu-id="5eb88-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="5eb88-120">Soporte técnico para los tipos de usuario B2B</span><span class="sxs-lookup"><span data-stu-id="5eb88-120">Support for B2B User types</span></span>
<span data-ttu-id="5eb88-121">Actualmente, Teams solo admiten los tipos de estado 1 y estado 2 de usuarios invitados [definido por Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="5eb88-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5eb88-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5eb88-122">Related topics</span></span>

[<span data-ttu-id="5eb88-123">Acceso de invitado a Teams</span><span class="sxs-lookup"><span data-stu-id="5eb88-123">Guest access in Teams</span></span>](guest-access.md)



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
ms.openlocfilehash: 35598c38ad80e7d1ed75c7aedce021d0d03d2765
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326717"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="ddb7b-103">Solución de problemas con el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ddb7b-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

- <span data-ttu-id="ddb7b-104">Para saber si conocemos su problema, consulte los [equipos de soporte técnico de su organización](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ddb7b-104">To see whether we know about your problem, check out [Support Teams in your organization](Known-issues.md).</span></span>
- <span data-ttu-id="ddb7b-105">Para comprobar si hay problemas de soporte técnico actuales relacionados con el acceso de invitados en Teams, vaya a [Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="ddb7b-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="ddb7b-106">Los invitados son usuarios de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-106">Guests are users outside your organization.</span></span> <span data-ttu-id="ddb7b-107">Si alguien se encuentra en su organización (incluidos los empleados, los contratistas in situ o los agentes in situ), no se pueden agregar como invitados.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="ddb7b-108">Esto mismo se aplica a las filiales.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="ddb7b-109">Obtenga más información sobre las próximas características de acceso de invitados nuevas o actualizadas en la [Hoja de ruta de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="ddb7b-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="ddb7b-110">Díganos lo que quiere en [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="ddb7b-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="ddb7b-111">Si los invitados ven errores de licencia</span><span class="sxs-lookup"><span data-stu-id="ddb7b-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="ddb7b-112">El acceso de invitado en Teams usa Azure Active Directory (Azure AD) negocio a negocio (B2B) y el modelo de licencia.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="ddb7b-113">El acceso de invitados está incluido en todas las suscripciones de Microsoft 365 Empresa Estándar, Office 365 Enterprise y Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="ddb7b-114">No se necesita ninguna otra licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-114">No additional Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="ddb7b-115">Los equipos deben estar habilitados en el inquilino principal de un invitado para que los invitados puedan iniciar sesión y usar Teams como invitado en otro inquilino (recurso).</span><span class="sxs-lookup"><span data-stu-id="ddb7b-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="ddb7b-116">Si ve errores de licencias, asegúrese de leer las instrucciones de licencias [B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar los requisitos de licencia para satisfacer sus necesidades de acceso de invitados en su organización.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-116">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="ddb7b-117">Las licencias de invitado se cuentan contra la organización que invita.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="ddb7b-118">Considere esto al calcular el número de licencias que necesita.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="ddb7b-119">Las licencias se cuentan en relación con su organización si los invitados invitados provienen de otra organización de Office 365 o si usan sus direcciones de correo electrónico personales.</span><span class="sxs-lookup"><span data-stu-id="ddb7b-119">Licenses are counted against your organization whether the invited guests come from another Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="ddb7b-120">Soporte técnico para los tipos de usuario B2B</span><span class="sxs-lookup"><span data-stu-id="ddb7b-120">Support for B2B User types</span></span>
<span data-ttu-id="ddb7b-121">Actualmente, Teams solo admiten los tipos de estado 1 y estado 2 de usuarios invitados [definido por Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="ddb7b-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ddb7b-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ddb7b-122">Related topics</span></span>

[<span data-ttu-id="ddb7b-123">Acceso de invitado a Teams</span><span class="sxs-lookup"><span data-stu-id="ddb7b-123">Guest access in Teams</span></span>](guest-access.md)



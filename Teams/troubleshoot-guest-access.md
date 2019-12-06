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
description: Obtenga ayuda y solucione problemas con el acceso de invitado en Microsoft Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e0a3530b7a1f9029d9f671d0a02ef58cbb7907bf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871736"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="07212-103">Solución de problemas con el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07212-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="07212-104">Es posible que tenga que esperar hasta 24 horas para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="07212-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="07212-105">Para comprobar si hay problemas de soporte técnico actuales con el acceso de invitado en Teams, vaya a [solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="07212-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="07212-106">Para ver si conocemos su problema, consulte [problemas conocidos de Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="07212-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="07212-107">Los invitados son usuarios externos a su organización.</span><span class="sxs-lookup"><span data-stu-id="07212-107">Guests are users outside your organization.</span></span> <span data-ttu-id="07212-108">Si alguien se encuentra dentro de su organización (incluidos los empleados, los contratistas en el sitio o los agentes en el sitio), no se pueden agregar como invitados.</span><span class="sxs-lookup"><span data-stu-id="07212-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="07212-109">Lo mismo se aplica a tus afiliados.</span><span class="sxs-lookup"><span data-stu-id="07212-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="07212-110">Descubra futuras características nuevas o actualizadas de acceso de invitado en la [Guía básica de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="07212-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="07212-111">Díganos lo que quiere en [UserVoice de Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="07212-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="07212-112">Si los invitados experimentan errores de licencia</span><span class="sxs-lookup"><span data-stu-id="07212-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="07212-113">El acceso de invitados en Teams usa Azure Active Directory (Azure AD) empresarial para empresas (B2B) y su modelo de licencias.</span><span class="sxs-lookup"><span data-stu-id="07212-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="07212-114">El acceso de invitado se incluye con todas las suscripciones de Office 365 Empresa Premium, Office 365 Enterprise y Office 365 Educación.</span><span class="sxs-lookup"><span data-stu-id="07212-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="07212-115">No se necesita ninguna otra licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="07212-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="07212-116">Si ve errores de licencias, asegúrese de leer las instrucciones de licencias [B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar los requisitos de licencia para satisfacer sus necesidades de acceso de invitados en su organización.</span><span class="sxs-lookup"><span data-stu-id="07212-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="07212-117">Las licencias de invitados se cuentan en relación con la organización que invita.</span><span class="sxs-lookup"><span data-stu-id="07212-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="07212-118">Considere esto cuando calcule el número de licencias que necesita.</span><span class="sxs-lookup"><span data-stu-id="07212-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="07212-119">Las licencias se cuentan en relación con su organización si los invitados invitados provienen de otro inquilino de Office 365 o si usan sus direcciones de correo electrónico personales.</span><span class="sxs-lookup"><span data-stu-id="07212-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="07212-120">Compatibilidad con tipos de usuario B2B</span><span class="sxs-lookup"><span data-stu-id="07212-120">Support for B2B User types</span></span>
<span data-ttu-id="07212-121">Actualmente, los equipos solo tienen compatibilidad con los tipos de estado 1 y estado 2 de los usuarios invitados [definidos por Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="07212-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="07212-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="07212-122">Related topics</span></span>

[<span data-ttu-id="07212-123">Acceso de invitado a Teams</span><span class="sxs-lookup"><span data-stu-id="07212-123">Guest access in Teams</span></span>](guest-access.md)



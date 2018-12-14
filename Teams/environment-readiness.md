---
title: Comprobación de la preparación del entorno para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Sepa lo que debe buscar cuando compruebe si el entorno está preparado para Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 057493f42a4bbfa012fb57c2394c372dfc25c9fc
ms.sourcegitcommit: a3181bc3707b09c1e3f87c343b38259fdc6dabd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2018
ms.locfileid: "27264831"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a><span data-ttu-id="5d9ca-103">Comprobación de la preparación del entorno para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d9ca-103">Check your environment’s readiness for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="5d9ca-104">La transición a la nube será diferente para cada organización y su estado actual podría influir en el futuro funcionamiento de Teams.</span><span class="sxs-lookup"><span data-stu-id="5d9ca-104">The transition to the cloud will vary by each organization, and current state may have an impact on how Teams will function.</span></span>

<span data-ttu-id="5d9ca-105">Se recomienda encarecidamente [implementar la sincronización de datos de School](https://docs.microsoft.com/schooldatasync/) instituciones educativas antes de implementar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d9ca-105">Educational institutions are strongly encouraged to [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span> <span data-ttu-id="5d9ca-106">Sincronización de datos de escuela utiliza datos de lista de participantes de su escuela SIS para crear automáticamente las clases y los grupos para Microsoft Teams y otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5d9ca-106">School Data Sync uses your school’s SIS roster data to automatically create classes and groups for Microsoft Teams and other applications.</span></span>

<span data-ttu-id="5d9ca-107">Para obtener la mejor experiencia en los equipos, su organización debe haber implementado Exchange Online y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5d9ca-107">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="5d9ca-108">También debe asegurarse de que está listo para los equipos de su entorno actual.</span><span class="sxs-lookup"><span data-stu-id="5d9ca-108">You must also ensure that your current environment is ready for Teams.</span></span>  <span data-ttu-id="5d9ca-109">Hacer referencia a estos vínculos para obtener ayuda:</span><span class="sxs-lookup"><span data-stu-id="5d9ca-109">Refer to these links for help:</span></span>

-   <span data-ttu-id="5d9ca-110">Si su organización no ha implementado ninguna carga de trabajo de Office 365, vea [Introducción a Office 365 para empresas](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="5d9ca-110">If your organization has not deployed any Office 365 workloads, see [Getting Started with Office 365 for business.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span></span>

-   <span data-ttu-id="5d9ca-111">Si su organización no ha agregado ni configurado un dominio verificado para Office 365, vea el tema sobre la [comprobación del dominio de Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="5d9ca-111">If your organization has not added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

-   <span data-ttu-id="5d9ca-112">Si su organización no ha sincronizado identidades en Azure Active Directory, vea [Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="5d9ca-112">If your organization has not synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

-   <span data-ttu-id="5d9ca-113">Si su organización no tiene Exchange Online, vea [Interacción entre Exchange y Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="5d9ca-113">If your organization does not have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

-   <span data-ttu-id="5d9ca-114">Si su organización no tiene SharePoint Online, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="5d9ca-114">If your organization does not have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="5d9ca-115">Si la organización es una institución de enseñanza y usar un sistema de información de estudiantes (SIS), que [implementar la sincronización de datos de escuela](https://docs.microsoft.com/schooldatasync/) antes de implementar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d9ca-115">If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="5d9ca-116">Si su organización tiene un Skype local existente para la implementación de Business Server (o Lync Server), debe configurar Azure Connect de AD para sincronizar el directorio local con Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d9ca-116">If your organization has an existing on-premises Skype for Business Server (or Lync Server) deployment, you must configure Azure AD Connect to synchronize your on-premises directory with Office 365.</span></span>  <span data-ttu-id="5d9ca-117">Para obtener más información, vea [Configurar Azure AD conectar para equipos y Skype para la empresa](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="5d9ca-117">For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span></span>
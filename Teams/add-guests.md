---
title: Agregar un invitado a un equipo
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: Los administradores pueden obtener más información sobre cómo agregar nuevos usuarios invitados a una organización en clientes de escritorio y web de Microsoft Teams y en el portal de colaboración de Azure Active Directory B2B.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60538383021028d043cb47197dd41ee89f8a4d37
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139369"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="deaeb-103">Agregar un invitado a un equipo</span><span class="sxs-lookup"><span data-stu-id="deaeb-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="deaeb-104">Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams.</span><span class="sxs-lookup"><span data-stu-id="deaeb-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="deaeb-105">Como administrador, puede agregar un usuario invitado nuevo a la organización de dos formas:</span><span class="sxs-lookup"><span data-stu-id="deaeb-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="deaeb-106">Los administradores globales o de Teams y los propietarios de equipo agregan un invitado a un equipo en los clientes de Teams o en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="deaeb-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="deaeb-107">Para obtener más información, consulte [Agregar invitados a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="deaeb-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="deaeb-108">Si aún no configuró el acceso de invitado, siga los pasos de la [Lista de comprobación de acceso de invitado](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="deaeb-108">If you haven't set up guest access yet, go through the steps in the [Guest access checklist](guest-access-checklist.md).</span></span>

> [!NOTE] 
> <span data-ttu-id="deaeb-109">Esto no sirve cuando se activa que **los administradores y usuarios del rol Invitador de usuarios invitados puedan invitar**.</span><span class="sxs-lookup"><span data-stu-id="deaeb-109">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="deaeb-110">La razón es que el rol de Invitador de usuarios invitados no es compatible con Teams.</span><span class="sxs-lookup"><span data-stu-id="deaeb-110">This is because the guest inviter role isn't supported in Teams.</span></span>

- <span data-ttu-id="deaeb-111">Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="deaeb-111">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="deaeb-112">La colaboración B2B de Azure AD permite a un administrador global invitar y autorizar a un conjunto de usuarios externos mediante la carga de un archivo de valores separados por comas (CSV) de no más de 2 000 líneas en el portal de colaboración B2B.</span><span class="sxs-lookup"><span data-stu-id="deaeb-112">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="deaeb-113">Para obtener más información, consulte [Colaboración de B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="deaeb-113">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="deaeb-114">Con la colaboración B2B de Azure AD, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B.</span><span class="sxs-lookup"><span data-stu-id="deaeb-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="deaeb-115">Estas directivas se pueden exigir en el nivel de inquilino, aplicación o usuario individual, del mismo modo que pueden habilitarse para empleados a tiempo completo y miembros de la organización.</span><span class="sxs-lookup"><span data-stu-id="deaeb-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="deaeb-116">Estas directivas se aplican en la organización de recursos.</span><span class="sxs-lookup"><span data-stu-id="deaeb-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="deaeb-117">Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="deaeb-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="deaeb-118">No es posible bloquear a usuarios invitados particulares.</span><span class="sxs-lookup"><span data-stu-id="deaeb-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="deaeb-119">Los usuarios invitados que ya haya agregado a través de B2B de Azure AD, los Grupos de Office 365 o SharePoint Online tienen todo listo.</span><span class="sxs-lookup"><span data-stu-id="deaeb-119">Guest users you have already added via Azure AD B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="deaeb-120">El administrador de Office 365 o el propietario de un equipo podrá agregar a esos invitados a sus respectivos equipos.</span><span class="sxs-lookup"><span data-stu-id="deaeb-120">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="deaeb-121">Si un equipo ya está con un grupo de Office 365 y se agrega un invitado al grupo, el invitado tendrá acceso al equipo.</span><span class="sxs-lookup"><span data-stu-id="deaeb-121">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="deaeb-122">Cuando se agrega un invitado a través del grupo de Office 365, el invitado no recibe ninguna invitación por correo electrónico, por lo que algún miembro del equipo tendrá que notificárselo.</span><span class="sxs-lookup"><span data-stu-id="deaeb-122">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="deaeb-123">Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="deaeb-123">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="deaeb-124">Se puede llevar un registro de qué invitados se han agregado en Azure AD o en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="deaeb-124">You can track guest additions in Azure AD or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="deaeb-125">Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo).</span><span class="sxs-lookup"><span data-stu-id="deaeb-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="deaeb-126">Si desea más detalles, vea [Auditoría y generación de informes para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) y [Buscar en el registro de auditoría del Centro de seguridad&amp; y cumplimiento de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="deaeb-126">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="deaeb-127">Más información</span><span class="sxs-lookup"><span data-stu-id="deaeb-127">More information</span></span>

[<span data-ttu-id="deaeb-128">Autorizar el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="deaeb-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="deaeb-129">Activar o desactivar el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="deaeb-129">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="deaeb-130">Usar PowerShell para controlar el acceso de invitados a un equipo</span><span class="sxs-lookup"><span data-stu-id="deaeb-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)

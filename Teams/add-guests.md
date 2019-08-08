---
title: Agregar un invitado a un equipo
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: Conozca las herramientas que un administrador tiene a su disposición para agregar usuarios invitados nuevos a una organización, incluidos los clientes web y de escritorio de Microsoft Teams y el portal de colaboración B2B de Azure Active Directory.
appliesto:
- Microsoft Teams
ms.openlocfilehash: acf62fe23a5b22f2cbe07e94e073037e1f95b041
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236324"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="9e564-103">Agregar un invitado a un equipo</span><span class="sxs-lookup"><span data-stu-id="9e564-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="9e564-104">Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams.</span><span class="sxs-lookup"><span data-stu-id="9e564-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="9e564-105">Como administrador, puede agregar un usuario invitado nuevo a la organización de dos formas:</span><span class="sxs-lookup"><span data-stu-id="9e564-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span>
- <span data-ttu-id="9e564-106">Los administradores globales que sean propietarios de un equipo y los propietarios de un equipo pueden agregar un invitado a un equipo mediante los clientes web o de escritorio de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9e564-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="9e564-107">Para obtener más detalles, consulte [Agregar invitados a un equipo](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="9e564-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>

> [!NOTE] 
> <span data-ttu-id="9e564-108">Esto no es aplicable cuando se activa que **los administradores y usuarios del rol Invitador de usuarios invitados puedan invitar**.</span><span class="sxs-lookup"><span data-stu-id="9e564-108">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="9e564-109">La razón es que el rol de Invitador de usuarios invitados no es compatible con Teams.</span><span class="sxs-lookup"><span data-stu-id="9e564-109">This is because the guest invitor role isn't supported in Teams.</span></span>

- <span data-ttu-id="9e564-110">Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9e564-110">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="9e564-111">La colaboración B2B de Azure AD permite a un administrador global invitar y autorizar a un conjunto de usuarios externos mediante la carga de un archivo de valores separados por comas (CSV) de no más de 2 000 líneas en el portal de colaboración B2B.</span><span class="sxs-lookup"><span data-stu-id="9e564-111">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="9e564-112">Para obtener más información, consulte [Colaboración de B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="9e564-112">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="9e564-113">Con la colaboración B2B de Azure AD, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B.</span><span class="sxs-lookup"><span data-stu-id="9e564-113">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="9e564-114">Estas directivas se pueden exigir en el nivel de inquilino, aplicación o usuario individual, del mismo modo que pueden habilitarse para empleados a tiempo completo y miembros de la organización.</span><span class="sxs-lookup"><span data-stu-id="9e564-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="9e564-115">Estas directivas se aplican en la organización de recursos.</span><span class="sxs-lookup"><span data-stu-id="9e564-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="9e564-116">Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="9e564-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="9e564-117">No es posible bloquear a usuarios invitados particulares.</span><span class="sxs-lookup"><span data-stu-id="9e564-117">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="9e564-118">Los usuarios invitados que ya haya agregado a través de B2B de Azure AD, los Grupos de Office 365 o SharePoint Online tienen todo listo.</span><span class="sxs-lookup"><span data-stu-id="9e564-118">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="9e564-119">El administrador de Office 365 o el propietario de un equipo podrá agregar a esos invitados a sus respectivos equipos.</span><span class="sxs-lookup"><span data-stu-id="9e564-119">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="9e564-120">Si un equipo ya está con un grupo de Office 365 y se agrega un invitado al grupo, el invitado tendrá acceso al equipo.</span><span class="sxs-lookup"><span data-stu-id="9e564-120">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="9e564-121">Cuando se agrega un invitado a través del grupo de Office 365, el invitado no recibe ninguna invitación por correo electrónico, por lo que algún miembro del equipo tendrá que notificárselo.</span><span class="sxs-lookup"><span data-stu-id="9e564-121">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="9e564-122">Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="9e564-122">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="9e564-123">Se puede llevar un registro de qué invitados se han agregado en Azure AD o en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e564-123">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="9e564-124">Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo).</span><span class="sxs-lookup"><span data-stu-id="9e564-124">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="9e564-125">Si desea más detalles, vea [Auditoría y generación de informes para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) y [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="9e564-125">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="9e564-126">Diferencias entre el acceso de invitados y el acceso externo (federación)</span><span class="sxs-lookup"><span data-stu-id="9e564-126">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="9e564-127">Más información</span><span class="sxs-lookup"><span data-stu-id="9e564-127">More information</span></span>

[<span data-ttu-id="9e564-128">Autorizar el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e564-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="9e564-129">Activar o desactivar el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e564-129">Turn on or off guest access to Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="9e564-130">Usar PowerShell para controlar el acceso de invitados a un equipo</span><span class="sxs-lookup"><span data-stu-id="9e564-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)

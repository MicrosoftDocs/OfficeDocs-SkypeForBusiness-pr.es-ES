---
title: Agregar un invitado a un equipo
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: sbhatta
description: Conozca las herramientas que un administrador tiene a su disposición para agregar usuarios invitados nuevos a una organización, incluidos los clientes web y de escritorio de Microsoft Teams y el portal de colaboración B2B de Azure Active Directory.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0671774d01ce8b2dfeea78fff36dde117931ff00
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674468"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="7c5a6-103">Agregar un invitado a un equipo</span><span class="sxs-lookup"><span data-stu-id="7c5a6-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="7c5a6-104">Cualquier usuario con una cuenta de correo electrónico empresariales o de clientes, como Outlook, Gmail u otras personas, puede participar como invitado en los equipos.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>


<span data-ttu-id="7c5a6-105">Como administrador, puede agregar un usuario invitado nuevo a la organización de dos formas:</span><span class="sxs-lookup"><span data-stu-id="7c5a6-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="7c5a6-106">Los administradores globales que sean propietarios de un equipo y los propietarios de un equipo pueden agregar un invitado a un equipo mediante los clientes web o de escritorio de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span>
- <span data-ttu-id="7c5a6-107">Agregue invitados a la organización a través de la colaboración B2B de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-107">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="7c5a6-108">La colaboración B2B de Azure Active Directory permite a un administrador global invitar y autorizar a un conjunto de usuarios externos mediante la carga de un archivo de valores separados por comas (CSV) de no más de 2000 líneas en el portal de colaboración B2B.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-108">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="7c5a6-109">Para obtener más información, consulte [Colaboración de B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="7c5a6-109">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>



<span data-ttu-id="7c5a6-110">Con la colaboración B2B de Azure Active Directory, las organizaciones pueden exigir que se cumplan las directivas de acceso condicional y autenticación multifactor (MFA) para los usuarios de B2B.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-110">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="7c5a6-111">Estas directivas se pueden aplicar al nivel de inquilino, aplicación o usuario individual, del mismo modo que se aplican para empleados a tiempo completo y miembros de la organización.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-111">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="7c5a6-112">Estas directivas se aplican en la organización de recursos.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-112">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="7c5a6-113">Para obtener más información, vea [Acceso condicional para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="7c5a6-113">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="7c5a6-114">No es posible bloquear a usuarios invitados particulares.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-114">Individual guest users can't be blocked.</span></span>



<span data-ttu-id="7c5a6-115">Los usuarios invitados que ya se ha agregado a través de Azure Active Directory B2B, grupos de Office 365 o SharePoint Online están listos para ir.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-115">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="7c5a6-116">El administrador de Office 365 o el propietario de un equipo podrá agregar a esos invitados a sus respectivos equipos.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-116">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="7c5a6-117">Si un equipo ya está con un grupo de Office 365 y se agrega un invitado al grupo, el invitado tendrá acceso al equipo.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-117">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="7c5a6-118">Cuando se agrega un invitado a través del grupo de Office 365, el invitado no recibe ninguna invitación por correo electrónico, por lo que algún miembro del equipo tendrá que notificárselo.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-118">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="7c5a6-119">Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="7c5a6-119">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>



<span data-ttu-id="7c5a6-120">Se puede llevar un registro de qué invitados se han agregado en Azure Active Directory o en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-120">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="7c5a6-121">Cuando se agrega un invitado en Microsoft Teams, esta actividad se audita y se registra como actividad de administración del grupo de Azure AD "Added member to group" (Se ha agregado un miembro al grupo).</span><span class="sxs-lookup"><span data-stu-id="7c5a6-121">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="7c5a6-122">Si desea más detalles, vea [Auditoría y generación de informes para usuarios de colaboración B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) y [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="7c5a6-122">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="more-information"></a><span data-ttu-id="7c5a6-123">Más información</span><span class="sxs-lookup"><span data-stu-id="7c5a6-123">More information</span></span>

<span data-ttu-id="7c5a6-124">[Autorizar el acceso de invitado en Microsoft Teams](teams-dependencies.md)
[Activar o desactivar el acceso como invitado en los equipos de Microsoft](set-up-guests.md)
[Use PowerShell para controlar el acceso de invitado a un equipo](guest-access-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="7c5a6-124">[Authorize guest access in Microsoft Teams](teams-dependencies.md)
[Turn on or off guest access in Microsoft Teams](set-up-guests.md)
[Use PowerShell to control guest access to a team](guest-access-powershell.md)</span></span>
---
title: Acceso de invitado en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Con el acceso de invitado en Microsoft Teams, los equipos de su organización pueden colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: df6f40fb439d4bef106671a8a21e211fb52fa50f
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637289"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="864d9-103">Acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="864d9-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="864d9-104">El acceso de invitado le permite agregar usuarios individuales de fuera de la organización a los equipos y canales de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="864d9-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="864d9-105">Para comparar el acceso externo (federación) con el acceso de invitado (y decidir cuál de ellos debe usar), lea [Comunicarse con usuarios de otras organizaciones en Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="864d9-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="864d9-106">Si está listo para activar el acceso de invitado en su organización, comience por la [Lista de comprobación de acceso de invitado](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="864d9-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="864d9-107">Introducción al acceso de invitados</span><span class="sxs-lookup"><span data-stu-id="864d9-107">Guest access overview</span></span>

<span data-ttu-id="864d9-108">Con el acceso de invitado, los equipos de su organización pueden colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales existentes en Teams.</span><span class="sxs-lookup"><span data-stu-id="864d9-108">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="864d9-109">Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook o Gmail) puede participar como invitado en Teams con acceso total a los chats, las reuniones y los archivos del equipo.</span><span class="sxs-lookup"><span data-stu-id="864d9-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="864d9-110">Como administrador de Teams, puede controlar qué características pueden (y no pueden) usar los invitados en Teams. Para más información, consulte [Administrar el acceso de invitados](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="864d9-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="864d9-111">El acceso de invitado es una configuración de Teams a nivel de toda la organización y se encuentra desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="864d9-111">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="864d9-112">El acceso de invitado está sujeto a los límites de servicio de Azure AD y de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="864d9-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="864d9-113">Los usuarios invitados siguen la configuración a nivel de organización en Teams para el modo de Actualización en coexistencia.</span><span class="sxs-lookup"><span data-stu-id="864d9-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="864d9-114">Esto no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="864d9-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="864d9-115">Licencias para acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="864d9-115">Licensing for guest access</span></span>

<span data-ttu-id="864d9-116">El acceso de invitados está incluido en todas las suscripciones de Microsoft 365 Empresa Estándar, Office 365 Enterprise y Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="864d9-116">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="864d9-117">No se necesita ninguna otra licencia de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="864d9-117">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="864d9-118">Teams no limita el número de invitados que se pueden agregar.</span><span class="sxs-lookup"><span data-stu-id="864d9-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="864d9-119">Sin embargo, el número total de invitados que se pueden agregar a su espacio empresarial depende de su licencia de Azure AD. Generalmente, son 5 invitados por usuario con licencia.</span><span class="sxs-lookup"><span data-stu-id="864d9-119">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="864d9-120">Para obtener más información, vea [Licencia de colaboración de Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="864d9-120">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="864d9-121">Los usuarios de su organización que solo tengan planes de suscripción de Microsoft 365 u Office 365 independientes, como Exchange Online Plan 2, no pueden participar como invitados en su organización porque Teams considera que estos usuarios pertenecen a la misma organización.</span><span class="sxs-lookup"><span data-stu-id="864d9-121">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="864d9-122">Para que estos usuarios puedan utilizar Teams, se les debe asignar una suscripción a Microsoft 365 Empresa Estándar, Office 365 Enterprise o Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="864d9-122">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="864d9-123">¿Quién es un invitado?</span><span class="sxs-lookup"><span data-stu-id="864d9-123">Who is a guest?</span></span>

<span data-ttu-id="864d9-124">Un invitado es un usuario que no es empleado, estudiante ni es un miembro de su organización.</span><span class="sxs-lookup"><span data-stu-id="864d9-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="864d9-125">Tampoco tiene una cuenta profesional o educativa con su organización.</span><span class="sxs-lookup"><span data-stu-id="864d9-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="864d9-126">Por ejemplo, los invitados pueden incluir socios, proveedores o consultores.</span><span class="sxs-lookup"><span data-stu-id="864d9-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="864d9-127">Cualquier persona que no forma parte de su organización puede agregarse como invitado en Teams.</span><span class="sxs-lookup"><span data-stu-id="864d9-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="864d9-128">Esto significa que cualquier usuario con una cuenta de empresa (es decir, una cuenta de Azure Active Directory) o una cuenta de correo electrónico de consumidor (con Outlook.com, Gmail.com u otros) puede participar como invitado en Teams con acceso completo a las experiencias de canales y equipos.</span><span class="sxs-lookup"><span data-stu-id="864d9-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="864d9-129">Para más información sobre qué pueden y no pueden hacer los invitados, lea [Autorización del acceso de invitado en Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="864d9-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="864d9-130">También puede consultar la tabla de [Comparación de funciones entre miembros del equipo e invitados](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="864d9-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="864d9-131">Por último, todos los invitados de Teams están protegidos con el mismo cumplimiento normativo y de auditorías que el resto de Microsoft 365 u Office 365. Además, los invitados se pueden administrar de forma segura dentro de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="864d9-131">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="864d9-132">¿Por qué usar el acceso de invitado?</span><span class="sxs-lookup"><span data-stu-id="864d9-132">Why use guest access?</span></span>

<span data-ttu-id="864d9-133">Con el acceso de invitado, las organizaciones que utilizan Microsoft Teams pueden proporcionar acceso a sus socios para que accedan a equipos, documentos en canales, recursos, chats y aplicaciones, sin perder por ello el control total de sus datos corporativos.</span><span class="sxs-lookup"><span data-stu-id="864d9-133">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="864d9-134">Todos los invitados de Teams están protegidos con el mismo cumplimiento normativo y de auditorías que el resto de Microsoft 365 u Office 365. Además, los invitados se pueden administrar de forma segura dentro de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="864d9-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="864d9-135">Comprender las limitaciones para los invitados</span><span class="sxs-lookup"><span data-stu-id="864d9-135">Understand the limitations for guests</span></span>

<span data-ttu-id="864d9-136">La experiencia de invitado tiene limitaciones deliberadamente establecidas.</span><span class="sxs-lookup"><span data-stu-id="864d9-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="864d9-137">Asegúrese de comprender la experiencia de invitado para no intentar solucionar algo que no sea realmente un problema.</span><span class="sxs-lookup"><span data-stu-id="864d9-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="864d9-138">Por ejemplo, aquí tiene una lista de algunas de las funciones que no están disponibles para un invitado en Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="864d9-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="864d9-139">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="864d9-139">OneDrive for Business</span></span>
- <span data-ttu-id="864d9-140">Búsqueda de personas fuera de Teams</span><span class="sxs-lookup"><span data-stu-id="864d9-140">People search outside of Teams</span></span>
- <span data-ttu-id="864d9-141">Calendario, Reuniones programadas o Detalles de la reunión</span><span class="sxs-lookup"><span data-stu-id="864d9-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="864d9-142">RTC</span><span class="sxs-lookup"><span data-stu-id="864d9-142">PSTN</span></span>
- <span data-ttu-id="864d9-143">Organigrama</span><span class="sxs-lookup"><span data-stu-id="864d9-143">Organization chart</span></span>
- <span data-ttu-id="864d9-144">Crear o revisar un equipo</span><span class="sxs-lookup"><span data-stu-id="864d9-144">Create or revise a team</span></span>
- <span data-ttu-id="864d9-145">Explorar en un equipo</span><span class="sxs-lookup"><span data-stu-id="864d9-145">Browse for a team</span></span>
- <span data-ttu-id="864d9-146">Cargar archivos en un chat entre personas</span><span class="sxs-lookup"><span data-stu-id="864d9-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="864d9-147">Actualmente, Teams solo admiten los tipos de estado 1 y estado 2 de usuarios invitados [definido por Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="864d9-147">Currently, Teams supports only State 1 and State 2 types of guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="864d9-148">Para obtener una lista completa de qué puede y no puede hacer un invitado en Teams, vea la tabla de [comparación entre las funciones de los miembros del equipo y los invitados](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="864d9-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="864d9-149">Para obtener más información sobre el acceso de invitados en el nivel de Microsoft 365 y Office 365, lea [Agregar invitados a Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="864d9-149">To learn more about guest access at the Microsoft 365 and Office 365 levels, read [Adding guests to Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>


## <a name="more-information"></a><span data-ttu-id="864d9-150">Más información</span><span class="sxs-lookup"><span data-stu-id="864d9-150">More information</span></span>

[<span data-ttu-id="864d9-151">Contactar al soporte técnico para productos empresariales: ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="864d9-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[<span data-ttu-id="864d9-152">Acceso de invitados a Microsoft 365 Groups</span><span class="sxs-lookup"><span data-stu-id="864d9-152">Guest access in Microsoft 365 Groups</span></span>](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  

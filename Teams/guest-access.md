---
title: Acceso de invitado en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Con el acceso de invitado en Microsoft Teams, los equipos de su organización pueden colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales.
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81bfde91cb73ed6741138be390533d56dc2e60e3
ms.sourcegitcommit: 3678dbbc8c36010fbf12c57b52281ef4fca9f065
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34695952"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="19237-103">Acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19237-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="19237-104">Introducción al acceso de invitados</span><span class="sxs-lookup"><span data-stu-id="19237-104">Guest access overview</span></span>

<span data-ttu-id="19237-105">El acceso de invitados es una de las características más solicitadas por los clientes.</span><span class="sxs-lookup"><span data-stu-id="19237-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="19237-106">Esto es lo que puede hacer para seguir nuestro progreso en el acceso de invitados y compartir con nosotros sus opiniones:</span><span class="sxs-lookup"><span data-stu-id="19237-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="19237-107">Si tiene problemas con el acceso de invitado, consulte [Problemas conocidos de Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="19237-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="19237-108">Obtenga más información sobre las próximas características nuevas o actualizadas en el [mapa de ruta de Microsoft Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="19237-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="19237-109">Háganos llegar sus ideas sobre cualquier aspecto en [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="19237-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="19237-110">Comparta su experiencia en la sección Comentarios que encontrará más abajo.</span><span class="sxs-lookup"><span data-stu-id="19237-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="19237-111">El acceso de invitados permite que los equipos de su organización puedan colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales en uno o más espacios empresariales.</span><span class="sxs-lookup"><span data-stu-id="19237-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="19237-112">Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook o Gmail) puede participar como invitado en Teams con acceso total a los chats, las reuniones y los archivos del equipo.</span><span class="sxs-lookup"><span data-stu-id="19237-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="19237-113">El acceso de invitado se incluye con todas las suscripciones de Office 365 Empresa Premium, Office 365 Enterprise y Office 365 Educación, sin necesidad de licencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="19237-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="19237-114">Puede tener un máximo de 5 invitados por licencia de usuario en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="19237-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="19237-115">Para obtener más información sobre las licencias, consulte [Guía de concesión de licencias de colaboración B2B de Azure Active Directory](https://docs.microsoft.com/es-ES/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="19237-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="19237-116">El acceso de invitado es una configuración a nivel de espacio empresarial de Microsoft Teams y se encuentra desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="19237-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="19237-117">El acceso de invitado está sujeto a los límites de servicio de Azure AD y de Office 365.</span><span class="sxs-lookup"><span data-stu-id="19237-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="19237-118">Los usuarios de su organización que solo tengan planes de suscripción de Office 365 independientes, como Exchange Online Plan 2, no pueden participar como invitados en su organización porque Teams considera que estos usuarios pertenecen a la misma organización.</span><span class="sxs-lookup"><span data-stu-id="19237-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="19237-119">Para que estos usuarios utilicen Teams, se les debe asignar una suscripción de Office 365 Empresa Premium, Office 365 Enterprise u Office 365 Educación.</span><span class="sxs-lookup"><span data-stu-id="19237-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="19237-120">¿Quién es un invitado?</span><span class="sxs-lookup"><span data-stu-id="19237-120">Who is a guest?</span></span>

<span data-ttu-id="19237-121">Un invitado es un usuario que no es empleado, estudiante ni es un miembro de su organización.</span><span class="sxs-lookup"><span data-stu-id="19237-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="19237-122">Tampoco tiene una cuenta profesional o educativa con su organización.</span><span class="sxs-lookup"><span data-stu-id="19237-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="19237-123">Por ejemplo, los invitados pueden incluir socios, proveedores o consultores.</span><span class="sxs-lookup"><span data-stu-id="19237-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="19237-124">Cualquier persona que no forma parte de su organización puede agregarse como invitado en Teams.</span><span class="sxs-lookup"><span data-stu-id="19237-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="19237-125">Esto significa que cualquier usuario con una cuenta de empresa (es decir, una cuenta de Azure Active Directory) o una cuenta de correo electrónico de consumidor (con Outlook.com, Gmail.com u otros) puede participar como invitado en Teams con acceso completo a las experiencias de canales y equipos.</span><span class="sxs-lookup"><span data-stu-id="19237-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="19237-126">(Puede leer sobre las restricciones de invitados en [Autorizar el acceso de invitados en Microsoft Teams](teams-dependencies.md)). Todos los invitados de Teams están protegidos con el mismo cumplimiento de normativas y auditorías que el resto de Office 365, y se pueden administrar de forma segura dentro de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19237-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="19237-127">¿Por qué usar el acceso de invitado?</span><span class="sxs-lookup"><span data-stu-id="19237-127">Why use guest access?</span></span>
      
<span data-ttu-id="19237-128">Con el acceso de invitado, las organizaciones que utilizan Microsoft Teams pueden proporcionar acceso externo a sus socios para que accedan a equipos, documentos en canales, recursos, chats y aplicaciones, sin perder por ello el control total de sus datos corporativos.</span><span class="sxs-lookup"><span data-stu-id="19237-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="19237-129">Todos los invitados de Teams están protegidos con el mismo cumplimiento de normativas y auditorías que el resto de Office 365, y se pueden administrar de forma segura dentro de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19237-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="19237-130">Teams se basa en Grupos de Office 365 y proporciona a los grupos de Office 365 una nueva manera de acceder a sus activos compartidos.</span><span class="sxs-lookup"><span data-stu-id="19237-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="19237-131">Microsoft Teams es la mejor solución para los miembros de grupos y equipos que chatean constantemente.</span><span class="sxs-lookup"><span data-stu-id="19237-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="19237-132">Grupos de Office 365 es un servicio que proporciona suscripciones entre aplicaciones para un conjunto de activos de grupo compartidos, como un sitio de SharePoint o un panel de Power BI. De esta manera, los equipos pueden colaborar de forma efectiva y segura.</span><span class="sxs-lookup"><span data-stu-id="19237-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="19237-133">¿En qué se diferencia el acceso de invitado del acceso externo (federación)?</span><span class="sxs-lookup"><span data-stu-id="19237-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="19237-134">Más información</span><span class="sxs-lookup"><span data-stu-id="19237-134">More information</span></span>
    
[<span data-ttu-id="19237-135">Contactar con soporte técnico para productos empresariales: ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="19237-135">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
<span data-ttu-id="19237-136">
  [Acceso de invitado en Grupos de Office 365](https://support.office.com/es-ES/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span><span class="sxs-lookup"><span data-stu-id="19237-136">[Guest access in Office 365 Groups](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span></span> 
  
|  |  |
|---------|---------|
|<span data-ttu-id="19237-137">Introducción al acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="19237-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="19237-138">Información especializada sobre el acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="19237-138">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="19237-139">Agregar invitados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19237-139">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    


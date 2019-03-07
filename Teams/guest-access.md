---
title: Acceso de invitado a Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/25/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Con el acceso de invitado en Microsoft Teams, los equipos de su organización pueden colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59cd4e06d3a5a98298d67fcfbb785efb371fe0f0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458831"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="f02e0-103">Acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f02e0-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="f02e0-104">Información general sobre el acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="f02e0-104">Guest access overview</span></span>

<span data-ttu-id="f02e0-105">Acceso como invitado es una de las características de los clientes han pedido el máximo.</span><span class="sxs-lookup"><span data-stu-id="f02e0-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="f02e0-106">Aquí es cómo puede mantener el ritmo con nuestro progreso en acceso de invitado y Cuéntenos su opinión:</span><span class="sxs-lookup"><span data-stu-id="f02e0-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="f02e0-107">Si tiene problemas con el acceso de invitado, consulte [Problemas conocidos de Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f02e0-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="f02e0-108">Obtenga más información sobre las próximas características nuevas o actualizadas en el [mapa de ruta de Microsoft Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="f02e0-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="f02e0-109">Háganos llegar sus ideas sobre cualquier aspecto en [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="f02e0-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="f02e0-110">Comparta su experiencia en la sección Comentarios que encontrará más abajo.</span><span class="sxs-lookup"><span data-stu-id="f02e0-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="f02e0-111">Acceso de invitado permite a los equipos de la organización para colaborar con personas fuera de su organización mediante la concesión de acceso a los equipos existentes y canales en uno o varios de los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="f02e0-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="f02e0-112">Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams con acceso total a los chats, las reuniones y los archivos del equipo.</span><span class="sxs-lookup"><span data-stu-id="f02e0-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="f02e0-113">Acceso de invitado se incluye con las suscripciones de todos los Business Premium de Office 365, Office 365 Enterprise y Office 365 educación con ningún requisito adicional de la licencia.</span><span class="sxs-lookup"><span data-stu-id="f02e0-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="f02e0-114">Puede tener hasta 5 invitados por licencia de usuario en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="f02e0-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="f02e0-115">Para obtener más información acerca de las licencias, vea la [orientación de licencias de colaboración de Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="f02e0-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="f02e0-116">El acceso de invitado es una configuración a nivel de inquilino de Microsoft Teams y se encuentra desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f02e0-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="f02e0-117">Acceso de invitado está sujeto a Azure AD y límites del servicio Office 365.</span><span class="sxs-lookup"><span data-stu-id="f02e0-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="f02e0-118">Los usuarios de la organización que tienen sólo, planes de suscripción de Office 365 independiente como Exchange Online Plan 2, no pueden ser invitados como invitados a la organización debido a que estos usuarios pertenecen a la misma organización considera que los equipos.</span><span class="sxs-lookup"><span data-stu-id="f02e0-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="f02e0-119">Para que estos usuarios usar los equipos, se debe asignar una suscripción a Office 365 Business Premium, Office 365 Enterprise u Office 365 educación.</span><span class="sxs-lookup"><span data-stu-id="f02e0-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="f02e0-120">¿Quién es un invitado?</span><span class="sxs-lookup"><span data-stu-id="f02e0-120">Who is a guest?</span></span>

<span data-ttu-id="f02e0-121">Un invitado es un usuario que no es empleado, estudiante ni es un miembro de su organización.</span><span class="sxs-lookup"><span data-stu-id="f02e0-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="f02e0-122">Tampoco tiene una cuenta profesional o educativa con su organización.</span><span class="sxs-lookup"><span data-stu-id="f02e0-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="f02e0-123">Por ejemplo, los invitados pueden incluir socios, proveedores o consultores.</span><span class="sxs-lookup"><span data-stu-id="f02e0-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="f02e0-124">Cualquier persona que no forma parte de la organización puede agregarse como invitado en los equipos.</span><span class="sxs-lookup"><span data-stu-id="f02e0-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="f02e0-125">Esto significa que cualquier persona con una cuenta de empresa (es decir, una cuenta de Azure Active Directory) o la cuenta de correo electrónico del consumidor (con Outlook.com, Gmail.com u otras) puede participar como invitado en los equipos, con acceso completo a los equipos y las experiencias de canal.</span><span class="sxs-lookup"><span data-stu-id="f02e0-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="f02e0-126">(Puede leer acerca de las restricciones de invitado en [autorizar el acceso de invitado en los equipos de Microsoft](teams-dependencies.md)). Todos los invitados en los equipos están cubiertos por la misma cumplimiento y la auditoría protección como el resto de Office 365 y se pueden administrar de forma segura dentro de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f02e0-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="f02e0-127">¿Por qué usar acceso como invitado?</span><span class="sxs-lookup"><span data-stu-id="f02e0-127">Why use guest access?</span></span>
      
<span data-ttu-id="f02e0-128">Con acceso como invitado, las organizaciones que usan los equipos pueden proporcionar acceso externo a los equipos, documentos de canales, recursos, chats y aplicaciones de sus socios, que se mantiene un control completo sobre sus propios datos corporativos.</span><span class="sxs-lookup"><span data-stu-id="f02e0-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="f02e0-129">Todos los invitados en los equipos están cubiertos por la misma cumplimiento y la auditoría protección como el resto de Office 365 y los invitados pueden administrarse de forma segura dentro de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f02e0-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="f02e0-130">Los equipos se basa en los grupos de Office 365 y proporciona una nueva forma de obtener acceso a activos compartidos para un grupo de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f02e0-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="f02e0-131">Microsoft Teams es la mejor solución para los miembros de grupos y equipos que chatean constantemente.</span><span class="sxs-lookup"><span data-stu-id="f02e0-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="f02e0-132">Grupos de Office 365 es un servicio que proporciona suscripciones entre aplicaciones para un conjunto de activos de grupo compartidos, como un sitio de SharePoint o un panel de Power BI. De esta manera, los equipos pueden colaborar de forma efectiva y segura.</span><span class="sxs-lookup"><span data-stu-id="f02e0-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="f02e0-133">¿Cómo se compara el acceso como invitado para acceso externo (federación)?</span><span class="sxs-lookup"><span data-stu-id="f02e0-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="f02e0-134">Más información</span><span class="sxs-lookup"><span data-stu-id="f02e0-134">More information</span></span>
    
[<span data-ttu-id="f02e0-135">Recursos de soporte técnico para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f02e0-135">Support resources for Microsoft Teams</span></span>](support-resources.md)  
[<span data-ttu-id="f02e0-136">Acceso como invitado en grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="f02e0-136">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|<span data-ttu-id="f02e0-137">Introducción al acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="f02e0-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="f02e0-138">Sumérjase en acceso de invitado</span><span class="sxs-lookup"><span data-stu-id="f02e0-138">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="f02e0-139">Adición de invitados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f02e0-139">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    


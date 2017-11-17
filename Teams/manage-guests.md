---
title: Administrar el acceso de invitado a Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: 
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: beb9e46248569d46e1deb6d9210fde4ba329faaf
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2017
---
<a name="manage-guest-access-to-microsoft-teams"></a><span data-ttu-id="5c991-102">Administrar el acceso de invitado a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5c991-102">Manage guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="5c991-103">El acceso de invitado se incluye con todas las suscripciones de Office 365 Empresa Premium, Office 365 Enterprise y Office 365 Educación.</span><span class="sxs-lookup"><span data-stu-id="5c991-103">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="5c991-104">No se necesita ninguna otra licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c991-104">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="5c991-105">El acceso de invitado de Teams es una configuración a nivel de inquilino y se encuentra desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5c991-105">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="5c991-106">Los administradores de TI pueden agregar invitados en el nivel de inquilino, configurar y administrar permisos y directivas de usuarios invitados, determinar qué usuarios pueden invitar y extraer informes sobre la actividad de los usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="5c991-106">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="5c991-107">Estos controles están disponibles a través del Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c991-107">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="5c991-108">Las actividades y el contenido de los usuarios invitados están protegidos con el mismo cumplimiento de normativas y auditorías que el resto de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c991-108">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="5c991-109">La configuración de inquilino para el acceso de invitado de Teams solo impide que el invitado inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="5c991-109">The Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="5c991-110">Los propietarios del equipo podrán invitar a nuevos invitados y agregar a los usuarios invitados que ya estén en el directorio a sus respectivos equipos.</span><span class="sxs-lookup"><span data-stu-id="5c991-110">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="5c991-111">Como recordatorio, Microsoft Teams siempre permite que las configuraciones externas de Azure Active Directory permitan o bloqueen la adición del usuario invitado al inquilino.</span><span class="sxs-lookup"><span data-stu-id="5c991-111">As a reminder, Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="5c991-112">Además, puede usar el portal de Azure Active Directory para administrar invitados y su acceso a los recursos de Office 365 y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5c991-112">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="5c991-113">El acceso de invitado de Microsoft Teams puede aprovechar las funcionalidades de colaboración negocio a negocio (B2B) de Azure Active Directory como la infraestructura subyacente donde almacenar la información relacionada con los principios de seguridad (como las propiedades de identidad, las suscripciones y la configuración de autenticación multifactor).</span><span class="sxs-lookup"><span data-stu-id="5c991-113">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="5c991-114">Para obtener más información sobre la colaboración B2B de Azure Active Directory, consulte [¿Qué es la colaboración B2B de Azure AD?](https://go.microsoft.com/fwlink/p/?linkid=853011) y [Preguntas más frecuentes acerca de la colaboración B2B de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853020).</span><span class="sxs-lookup"><span data-stu-id="5c991-114">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  
---
title: Administrar las características de Microsoft Teams en su organización de Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Obtenga información sobre cómo activar o desactivar las aplicaciones de Microsoft Teams en su organización de Office 365, incluidas las fichas, conectores, bots o cualquier combinación de los tres.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0be88d173186e762c2297178237004b6e583bde8
ms.sourcegitcommit: 39516662ee3eefe2fb86735c5bae97b3fb32b7ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "23834938"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="eb397-103">Administrar las características de Microsoft Teams en su organización de Office 365</span><span class="sxs-lookup"><span data-stu-id="eb397-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="eb397-104">Todas las opciones de los equipos pronto se van a migrar a la nueva Microsoft Teams & Skype para el centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="eb397-104">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="eb397-105">La única característica de los equipos que se administra en el centro de administración de Office 365 es las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="eb397-105">The only Teams feature that is managed in the Office 365 admin center is apps.</span></span> 

<span data-ttu-id="eb397-106">A menos que se indique lo contrario, el valor predeterminado para una opción es Activado.</span><span class="sxs-lookup"><span data-stu-id="eb397-106">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="eb397-107">Para ajustar la configuración de la administración en Microsoft Teams, vaya al Centro de administración de Office 365, abra **Configuración** > **Servicios y complementos**, y seleccione **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="eb397-107">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="eb397-108">Si ha iniciado sesión como administrador de Office 365, puede acceder con este vínculo:</span><span class="sxs-lookup"><span data-stu-id="eb397-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="eb397-109">Configuración a nivel de inquilino de Office 365</span><span class="sxs-lookup"><span data-stu-id="eb397-109">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="eb397-110">En **configuración de todo el inquilino**, puede activar o desactivar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="eb397-110">In **Tenant-wide settings**, you can turn on or turn off apps.</span></span>

<span data-ttu-id="eb397-111">Para editar **la configuración a nivel de inquilino** para Microsoft Teams, vaya al Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="eb397-111">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="eb397-112">Después, elija **Configuración** > **Servicios y complementos** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="eb397-112">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

## <a name="apps"></a><span data-ttu-id="eb397-113">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="eb397-113">Apps</span></span>

<span data-ttu-id="eb397-114">Las aplicaciones son fichas, conectores, bots o cualquier combinación de estos tres elementos que proporciona un servicio de terceros.</span><span class="sxs-lookup"><span data-stu-id="eb397-114">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="eb397-115">Hay directivas de administración de Microsoft Teams que se pueden configurar en el Centro de administración de Office 365 para controlar qué aplicaciones externas de terceros están permitidas.</span><span class="sxs-lookup"><span data-stu-id="eb397-115">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="eb397-116">Estas directivas le permiten especificar qué aplicaciones están permitidos y no permitidos, nuevo comportamiento de la aplicación externa, y si se permite la carga de lado aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="eb397-116">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="eb397-117">La sección **Aplicaciones** le permite establecer la siguiente configuración para su organización:</span><span class="sxs-lookup"><span data-stu-id="eb397-117">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Captura de pantalla de la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="eb397-119">**Permitir aplicaciones externas en Microsoft Teams:** si este conmutador está activado, los usuarios pueden agregar las fichas y los bots que estén disponibles al inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="eb397-119">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Captura de pantalla del control para permitir aplicaciones externas en la sección Aplicaciones.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="eb397-121">**Habilitar nuevas aplicaciones externas de manera predeterminada**: si este conmutador está activado, los usuarios pueden activar nuevas aplicaciones en cuanto estas se agregan al catálogo de aplicaciones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eb397-121">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="eb397-122">Desactive este conmutador si quiere controlar las aplicaciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="eb397-122">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="eb397-123">Si lo desactiva, deberá recordar revisar periódicamente las nuevas incorporaciones para que su organización no se pierda las nuevas aplicaciones de interés.</span><span class="sxs-lookup"><span data-stu-id="eb397-123">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="eb397-124">**Permitir la instalación de prueba de aplicaciones externas:** si este conmutador está activado, los usuarios pueden instalar y habilitar bots y fichas personalizados.</span><span class="sxs-lookup"><span data-stu-id="eb397-124">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="eb397-125">Para obtener más información, consulte [Configurar la administración para aplicaciones en Microsoft Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="eb397-125">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 


---
title: Configurar la administración para aplicaciones en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: Aprenda a permitir y habilitar aplicaciones en Microsoft Teams, incluida la carga lateral de aplicaciones externas.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.apppolicies.adminsettings
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad61e412bbbe0a880a279179f40124895d6e38a5
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568411"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="a602a-103">Configurar la administración para aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a602a-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a602a-104">Aplicaciones son las fichas, conectores, bots o cualquier combinación de estos tres, proporcionada por y los equipos (aplicaciones de cookies, también conocido como aplicaciones de forma predeterminada) o por un tercero (también conocido como aplicaciones externas).</span><span class="sxs-lookup"><span data-stu-id="a602a-104">Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, and also known as default apps) or by a third-party (also known as external apps).</span></span> <span data-ttu-id="a602a-105">En el centro de administración de Microsoft 365, puede habilitar y deshabilitar aplicaciones predeterminadas y configurar las opciones para controlar las aplicaciones externas.</span><span class="sxs-lookup"><span data-stu-id="a602a-105">In the Microsoft 365 admin center, you can enable and disable default apps and configure settings to control external apps.</span></span> <span data-ttu-id="a602a-106">Esta configuración permite especificar qué aplicaciones externas permitidas y no permitidos, nuevo comportamiento de la aplicación externa, y si se permite la carga de lado aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a602a-106">These settings let you specify which external apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

 <span data-ttu-id="a602a-107">Para administrar la configuración de administración de aplicaciones en los equipos, vaya al centro de administración de Microsoft 365 y elija **configuración** > **complementos & de servicios** > **Equipos de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a602a-107">To manage admin settings for apps in Teams, go to the Microsoft 365 admin center and choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="a602a-108">Si ha iniciado sesión como administrador de Office 365, puede acceder con este vínculo:</span><span class="sxs-lookup"><span data-stu-id="a602a-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="a602a-109">Si desea más información sobre la configuración de administrador para las aplicaciones, consulte el siguiente vídeo:</span><span class="sxs-lookup"><span data-stu-id="a602a-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="a602a-110">Administrar la experiencia de aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a602a-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="a602a-111">Permitir aplicaciones externas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a602a-111">Allow external apps in Teams</span></span>

<span data-ttu-id="a602a-112">De manera predeterminada, la opción **Permitir aplicaciones externas en Microsoft Teams** está activada con todas las aplicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="a602a-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span> <span data-ttu-id="a602a-113">Si desactiva esta opción, se deshabilitan todas las aplicaciones de otros fabricantes externas.</span><span class="sxs-lookup"><span data-stu-id="a602a-113">If you turn off this setting, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="a602a-114">Habilitar nuevas aplicaciones externas de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="a602a-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="a602a-115">:trophy: Procedimiento recomendado: Administrar las aplicaciones externas de forma individual</span><span class="sxs-lookup"><span data-stu-id="a602a-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="a602a-116">Para activar algunas aplicaciones (y desactivar otras), desactive **Permitir la instalación de prueba de aplicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="a602a-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="a602a-117">A continuación, desactive las aplicaciones que no quiera que usen los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a602a-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="a602a-118">Opcional: Desactive **Habilitar nuevas aplicaciones externas de manera predeterminada** (si desea controlar las nuevas aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="a602a-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="a602a-119">Aplicaciones predeterminadas, como los creados por Microsoft, no se ven afectadas por la configuración de **Habilitar las nuevas aplicaciones externas de forma predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="a602a-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="a602a-120">Nuevas aplicaciones están habilitadas de forma predeterminada cuando publicadas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a602a-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="a602a-121">Cuando esta opción está activada, los usuarios pueden activar las nuevas aplicaciones tan pronto como el que se agregan al catálogo de aplicaciones de los equipos.</span><span class="sxs-lookup"><span data-stu-id="a602a-121">When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="a602a-122">Para abrir el catálogo de aplicaciones de Microsoft Teams, haga clic en **Tienda** en la parte inferior de Microsoft Teams y después en **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a602a-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="a602a-123">Si desea controlar qué aplicaciones están disponibles, desactivar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="a602a-123">If you want to control which apps are available, turn off this setting.</span></span> <span data-ttu-id="a602a-124">Si lo desactiva, deberá recordar revisar periódicamente las nuevas incorporaciones para que su organización no se pierda las nuevas aplicaciones de interés.</span><span class="sxs-lookup"><span data-stu-id="a602a-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="a602a-125">La instalación de prueba es la forma en que se agrega una aplicación a Microsoft Teams mediante la carga de un archivo zip directamente a un equipo.</span><span class="sxs-lookup"><span data-stu-id="a602a-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="a602a-126">La instalación de prueba le permite probar una aplicación en fase de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a602a-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="a602a-127">También le permite crear una aplicación solo para el uso interno y compartirla con su equipo sin enviarla al catálogo de aplicaciones de Microsoft Teams en la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="a602a-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="a602a-128">La instalación de prueba de aplicaciones en Microsoft Teams la pueden realizar únicamente los propietarios del equipo o los miembros con los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="a602a-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

<span data-ttu-id="a602a-129">![Captura de pantalla de la sección de aplicaciones externas expandida.] (media/teams-tenant-wide-settings-external-apps.png "Captura de pantalla de la sección aplicaciones externas expandida que muestra aplicaciones externas")</span><span class="sxs-lookup"><span data-stu-id="a602a-129">![Screen shot of the expanded External Apps section.](media/teams-tenant-wide-settings-external-apps.png "Screen shot of the expanded External Apps section showing external apps")</span></span>

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="a602a-130">Crear y cargar paquetes de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a602a-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="a602a-131">Para obtener más información acerca de las aplicaciones, vea [desarrollar aplicaciones para los equipos](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="a602a-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 




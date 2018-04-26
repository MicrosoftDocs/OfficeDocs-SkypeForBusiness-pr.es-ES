---
title: Configurar la administración para aplicaciones en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Aprenda a permitir y habilitar aplicaciones en Microsoft Teams, incluida la carga lateral de aplicaciones externas.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50490b08986f1a8f312aa79d5492b1ed8a97ecc8
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="b4c17-103">Configurar la administración para aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4c17-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="b4c17-p101">Las aplicaciones están fichas, conectores, robots o cualquier combinación de estos tres, proporcionada por un servicio de terceros. Hay directivas de administración de equipos que pueden configurarse en el centro de administración de Office 365 para controlar qué aplicaciones de otros fabricantes externos están permitidas. Estas directivas le permiten especificar qué aplicaciones son permitidos y no permitidos, nuevo comportamiento de la aplicación externa, y si se permite la carga lateral apps.</span><span class="sxs-lookup"><span data-stu-id="b4c17-p101">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="b4c17-107">Para ajustar la configuración de la administración de aplicaciones en Microsoft Teams, vaya al Centro de administración de Office 365, abra **Configuración** > **Servicios y complementos**, y seleccione **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="b4c17-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="b4c17-108">Si ha iniciado sesión como administrador de Office 365, puede acceder con este vínculo:</span><span class="sxs-lookup"><span data-stu-id="b4c17-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="b4c17-109">Si desea más información sobre la configuración de administrador para las aplicaciones, consulte el siguiente vídeo:</span><span class="sxs-lookup"><span data-stu-id="b4c17-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="b4c17-110">Administrar la experiencia de aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4c17-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="b4c17-111">Permitir aplicaciones externas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4c17-111">Allow external apps in Teams</span></span>

<span data-ttu-id="b4c17-112">De manera predeterminada, la opción **Permitir aplicaciones externas en Microsoft Teams** está activada con todas las aplicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="b4c17-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="b4c17-113">Si desactiva este conmutador, se desactivarán todas las aplicaciones externas de terceros.</span><span class="sxs-lookup"><span data-stu-id="b4c17-113">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="b4c17-114">Habilitar nuevas aplicaciones externas de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="b4c17-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="b4c17-115">:trophy: Procedimiento recomendado: Administrar las aplicaciones externas de forma individual</span><span class="sxs-lookup"><span data-stu-id="b4c17-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="b4c17-116">Para activar algunas aplicaciones (y desactivar otras), desactive **Permitir la instalación de prueba de aplicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="b4c17-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="b4c17-117">A continuación, desactive las aplicaciones que no quiera que usen los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b4c17-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="b4c17-118">Opcional: Desactive **Habilitar nuevas aplicaciones externas de manera predeterminada** (si desea controlar las nuevas aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="b4c17-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="b4c17-119">Aplicaciones de forma predeterminada, como las generadas por Microsoft, no se ven afectadas por la opción de **habilitar nuevas aplicaciones externas de forma predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="b4c17-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span>

<span data-ttu-id="b4c17-120">Cuando este conmutador está activado, los usuarios pueden activar nuevas aplicaciones en cuanto estas se agregan al catálogo de aplicaciones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b4c17-120">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="b4c17-121">Para abrir el catálogo de aplicaciones de Microsoft Teams, haga clic en **Tienda** en la parte inferior de Microsoft Teams y después en **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="b4c17-121">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="b4c17-122">Si desea controlar qué aplicaciones están disponibles, desactive este conmutador.</span><span class="sxs-lookup"><span data-stu-id="b4c17-122">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="b4c17-123">Si lo desactiva, deberá recordar revisar periódicamente las nuevas incorporaciones para que su organización no se pierda las nuevas aplicaciones de interés.</span><span class="sxs-lookup"><span data-stu-id="b4c17-123">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="b4c17-124">La instalación de prueba es la forma en que se agrega una aplicación a Microsoft Teams mediante la carga de un archivo zip directamente a un equipo.</span><span class="sxs-lookup"><span data-stu-id="b4c17-124">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="b4c17-125">La instalación de prueba le permite probar una aplicación en fase de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b4c17-125">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="b4c17-126">También le permite crear una aplicación solo para el uso interno y compartirla con su equipo sin enviarla al catálogo de aplicaciones de Microsoft Teams en la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="b4c17-126">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="b4c17-127">La instalación de prueba de aplicaciones en Microsoft Teams la pueden realizar únicamente los propietarios del equipo o los miembros con los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="b4c17-127">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![Captura de pantalla de la sección de aplicaciones ampliada en configuración del arrendatario.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="b4c17-129">Crear y cargar paquetes de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b4c17-129">Creating and uploading app packages</span></span> 

<span data-ttu-id="b4c17-130">Para obtener más información acerca de aplicaciones, vea [desarrollar aplicaciones para equipos](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="b4c17-130">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 




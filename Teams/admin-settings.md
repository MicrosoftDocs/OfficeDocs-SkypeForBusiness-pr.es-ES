---
title: "Configurar la administración para aplicaciones en Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Aprenda a permitir y habilitar aplicaciones en Microsoft Teams, incluida la carga lateral de aplicaciones externas.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4cdca98cca13ffb49575b808a5cfa82f784d1752
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="79656-103">Configurar la administración para aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79656-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="79656-p101">Las aplicaciones son fichas, conectores, bots o cualquier combinación de estos tres elementos que proporciona un servicio de terceros. Hay directivas de administración de Microsoft Teams que se pueden configurar en el Centro de administración de Office 365 para controlar qué aplicaciones externas de terceros están permitidas. Estas directivas permiten especificar qué aplicaciones están permitidas y cuáles no, el comportamiento de las aplicaciones nuevas externas y si se permite la instalación de prueba de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="79656-p101">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="79656-107">Para ajustar la configuración de la administración de aplicaciones en Microsoft Teams, vaya al Centro de administración de Office 365, abra **Configuración** > **Servicios y complementos**, y seleccione **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="79656-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="79656-108">Si ha iniciado sesión como administrador de Office 365, puede acceder con este vínculo:</span><span class="sxs-lookup"><span data-stu-id="79656-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="79656-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="79656-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="79656-110">Permitir aplicaciones externas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79656-110">Allow external apps in Microsoft Teams</span></span>

<span data-ttu-id="79656-111">De manera predeterminada, la opción **Permitir aplicaciones externas en Microsoft Teams** está activada con todas las aplicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="79656-111">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="79656-112">Si desactiva este conmutador, se desactivarán todas las aplicaciones externas de terceros.</span><span class="sxs-lookup"><span data-stu-id="79656-112">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="79656-113">Habilitar nuevas aplicaciones externas de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="79656-113">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="79656-114">:trophy: Procedimiento recomendado: Administrar las aplicaciones externas de forma individual</span><span class="sxs-lookup"><span data-stu-id="79656-114">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="79656-115">Para activar algunas aplicaciones (y desactivar otras), desactive **Permitir la instalación de prueba de aplicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="79656-115">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="79656-116">A continuación, desactive las aplicaciones que no quiera que usen los usuarios.</span><span class="sxs-lookup"><span data-stu-id="79656-116">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="79656-117">Opcional: Desactive **Habilitar nuevas aplicaciones externas de manera predeterminada** (si desea controlar las nuevas aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="79656-117">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

<span data-ttu-id="79656-118">Cuando este conmutador está activado, los usuarios pueden activar nuevas aplicaciones en cuanto estas se agregan al catálogo de aplicaciones de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79656-118">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="79656-119">Para abrir el catálogo de aplicaciones de Microsoft Teams, haga clic en **Tienda** en la parte inferior de Microsoft Teams y después en **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="79656-119">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="79656-120">Si desea controlar qué aplicaciones están disponibles, desactive este conmutador.</span><span class="sxs-lookup"><span data-stu-id="79656-120">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="79656-121">Si lo desactiva, deberá recordar revisar periódicamente las nuevas incorporaciones para que su organización no se pierda las nuevas aplicaciones de interés.</span><span class="sxs-lookup"><span data-stu-id="79656-121">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="79656-122">La instalación de prueba es la forma en que se agrega una aplicación a Microsoft Teams mediante la carga de un archivo zip directamente a un equipo.</span><span class="sxs-lookup"><span data-stu-id="79656-122">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="79656-123">La instalación de prueba le permite probar una aplicación en fase de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="79656-123">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="79656-124">También le permite crear una aplicación solo para el uso interno y compartirla con su equipo sin enviarla al catálogo de aplicaciones de Microsoft Teams en la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="79656-124">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="79656-125">La instalación de prueba de aplicaciones en Microsoft Teams la pueden realizar únicamente los propietarios del equipo o los miembros con los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="79656-125">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![Captura de pantalla de la sección Aplicaciones de la configuración de Microsoft Teams.](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png) 

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="79656-127">Crear y cargar paquetes de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="79656-127">Creating and uploading app packages</span></span> 

<span data-ttu-id="79656-128">Para obtener más información sobre las aplicaciones, consulte [Desarrollar aplicaciones para Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="79656-128">To learn more about apps, read [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 




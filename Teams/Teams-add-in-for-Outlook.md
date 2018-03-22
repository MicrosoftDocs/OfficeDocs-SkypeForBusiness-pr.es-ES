---
title: Usar el complemento para reunión de Microsoft Teams en Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Microsoft Teams instala un complemento en Outlook que permite a los usuarios programar reuniones de Microsoft Teams desde Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 811c27a48a0e9bbccfbea7ac12e54ef0697b3f2b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="e60c0-103">Usar el complemento para reunión de Microsoft Teams en Outlook</span><span class="sxs-lookup"><span data-stu-id="e60c0-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="e60c0-104">El complemento para reunión de Microsoft Teams se instala automáticamente para los usuarios que tienen instalado Microsoft Teams y Office 2013 o 2016 en su equipo Windows.</span><span class="sxs-lookup"><span data-stu-id="e60c0-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="e60c0-105">Los usuarios verán el complemento para reunión de Microsoft Teams en la cinta del Calendario de Outlook.</span><span class="sxs-lookup"><span data-stu-id="e60c0-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Captura de pantalla del complemento de Microsoft Teams en la cinta de Outlook.](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="e60c0-107">Si los usuarios no pueden ver el complemento de Microsoft Teams, pídales que cierren Outlook y Microsoft Teams, y que luego reinicien en primer lugar el cliente de Microsoft Teams y luego el de Outlook, específicamente en ese orden.</span><span class="sxs-lookup"><span data-stu-id="e60c0-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="e60c0-108">El complemento para reunión de Microsoft Teams para Outlook no está disponible actualmente para usuarios de Mac.</span><span class="sxs-lookup"><span data-stu-id="e60c0-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="e60c0-109">Requisitos de autenticación</span><span class="sxs-lookup"><span data-stu-id="e60c0-109">Authentication requirements</span></span>

<span data-ttu-id="e60c0-110">El complemento para reunión de Microsoft Teams requiere que los usuarios inicien sesión en Microsoft Teams usando la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="e60c0-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="e60c0-111">Aunque los usuarios no usen este método para iniciar sesión, podrán usar el cliente de Microsoft Teams, pero no podrán programar reuniones en línea de Microsoft Teams usando el complemento de Outlook.</span><span class="sxs-lookup"><span data-stu-id="e60c0-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="e60c0-112">Puede solucionar este inconveniente de una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="e60c0-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="e60c0-113">Si la autenticación moderna no está configurada en su organización, configúrela.</span><span class="sxs-lookup"><span data-stu-id="e60c0-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="e60c0-114">Si la autenticación moderna está configurada, pero el usuario opta por no utilizarla en el cuadro de diálogo, pídale que vuelva a iniciar sesión usando la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="e60c0-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="e60c0-115">Para obtener más información sobre cómo configurar la autenticación, consulte [Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e60c0-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="e60c0-116">Habilitar las reuniones privadas</span><span class="sxs-lookup"><span data-stu-id="e60c0-116">Enable private meetings</span></span>

<span data-ttu-id="e60c0-117">Para que se implemente el complemento, debe estar habilitado Permitir la programación de reuniones privadas en el [Centro de administración de Office 365](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="e60c0-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Captura de pantalla de la configuración en la sección Llamadas y reuniones del Centro de administración de Office 365.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="e60c0-119">El cliente de Microsoft Teams determina si los usuarios necesitan la versión de 32 o de 64 bits e instala el complemento correcto.</span><span class="sxs-lookup"><span data-stu-id="e60c0-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="e60c0-120">Es posible que los usuarios deban reiniciar Outlook después de una instalación o una actualización de Microsoft Teams para obtener el complemento más reciente.</span><span class="sxs-lookup"><span data-stu-id="e60c0-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="e60c0-121">Otras consideraciones</span><span class="sxs-lookup"><span data-stu-id="e60c0-121">Other considerations</span></span>

<span data-ttu-id="e60c0-122">El complemento para reunión de Microsoft Teams sigue en proceso de desarrollo para ampliar sus funcionalidades, por lo que le recomendamos que tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e60c0-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="e60c0-123">Algunas características de reunión en línea, como la grabación, los sondeos y el uso de pizarras todavía no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="e60c0-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="e60c0-124">Las opciones de reunión no están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="e60c0-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="e60c0-125">En estos momentos, solo es posible invitar a personas de su compañía, dado que los usuarios externos todavía no pueden unirse a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="e60c0-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="e60c0-126">Este complemento es para reuniones programadas con participantes específicos, no para reuniones en un canal.</span><span class="sxs-lookup"><span data-stu-id="e60c0-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="e60c0-127">Las reuniones de canal se deben programar desde Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e60c0-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="e60c0-128">Actualmente, el complemento para reunión de Microsoft Teams en Outlook solo está disponible para usuarios de Windows, pero próximamente será compatible con Mac.</span><span class="sxs-lookup"><span data-stu-id="e60c0-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="e60c0-129">El complemento no funciona si hay un proxy de autenticación en la ruta de red entre el equipo del usuario y los servicios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e60c0-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>

<span data-ttu-id="e60c0-130">Para obtener instrucciones generales sobre cómo desactivar complementos, consulte [Ver, administrar e instalar los complementos de los programas de Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="e60c0-130">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="e60c0-131">Obtenga más información sobre [reuniones y llamadas en Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="e60c0-131">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>


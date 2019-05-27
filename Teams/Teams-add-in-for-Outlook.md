---
title: Usar el complemento para reunión de Microsoft Teams en Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams instala un complemento en Outlook que permite a los usuarios programar reuniones de Microsoft Teams desde Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb6ba92185d797e3925ad56c8747fd504f40dccd
ms.sourcegitcommit: d010c615ee530deb34d79a1a62815ef0a52a2086
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2019
ms.locfileid: "34404230"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="8489c-103">Usar el complemento para reunión de Microsoft Teams en Outlook</span><span class="sxs-lookup"><span data-stu-id="8489c-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8489c-104">El complemento para reunión de Microsoft Teams se instala automáticamente para los usuarios que tienen instalado Microsoft Teams y Office 2013 o 2016 en su equipo Windows.</span><span class="sxs-lookup"><span data-stu-id="8489c-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="8489c-105">Los usuarios verán el complemento para reunión de Microsoft Teams en la cinta del Calendario de Outlook.</span><span class="sxs-lookup"><span data-stu-id="8489c-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Captura de pantalla del complemento de Microsoft Teams en la cinta de Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> <span data-ttu-id="8489c-107">Los usuarios de Windows 7 deben instalar la [Actualización Universal C Runtime en Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) para que el complemento Reunión de Teams funcione.</span><span class="sxs-lookup"><span data-stu-id="8489c-107">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>

<span data-ttu-id="8489c-108">Si los usuarios no pueden ver el complemento de Microsoft Teams, pídales que cierren Outlook y Microsoft Teams, y que luego reinicien en primer lugar el cliente de Microsoft Teams y luego el de Outlook, específicamente en ese orden.</span><span class="sxs-lookup"><span data-stu-id="8489c-108">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="8489c-109">El botón reunión de equipos de Outlook para Mac aparecerá en la cinta de opciones de Outlook para Mac si Outlook está ejecutando la compilación 16,20 y posteriores de producción.</span><span class="sxs-lookup"><span data-stu-id="8489c-109">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running Production Build 16.20 and later.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="8489c-110">Requisitos de autenticación</span><span class="sxs-lookup"><span data-stu-id="8489c-110">Authentication requirements</span></span>

<span data-ttu-id="8489c-111">El complemento para reunión de Microsoft Teams requiere que los usuarios inicien sesión en Microsoft Teams usando la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="8489c-111">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="8489c-112">Aunque los usuarios no usen este método para iniciar sesión, podrán usar el cliente de Microsoft Teams, pero no podrán programar reuniones en línea de Microsoft Teams usando el complemento de Outlook.</span><span class="sxs-lookup"><span data-stu-id="8489c-112">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="8489c-113">Puede solucionar este inconveniente de una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="8489c-113">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="8489c-114">Si la autenticación moderna no está configurada en su organización, configúrela.</span><span class="sxs-lookup"><span data-stu-id="8489c-114">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="8489c-115">Si la autenticación moderna está configurada, pero el usuario opta por no utilizarla en el cuadro de diálogo, pídale que vuelva a iniciar sesión usando la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="8489c-115">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="8489c-116">Para obtener más información sobre cómo configurar la autenticación, consulte [Modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="8489c-116">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="8489c-117">Habilitar las reuniones privadas</span><span class="sxs-lookup"><span data-stu-id="8489c-117">Enable private meetings</span></span>

<span data-ttu-id="8489c-118">Para que se implemente el complemento, debe estar habilitado Permitir la programación de reuniones privadas en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8489c-118">Allow scheduling for private meetings must be enabled in the Microsoft Teams admin center for the plug-in to get deployed.</span></span> <span data-ttu-id="8489c-119">En el centro de administración, vaya a **Reuniones** > **Directivas de reunión** y, en la sección **General**, habilite **Permitir la programación de reuniones privadas**).</span><span class="sxs-lookup"><span data-stu-id="8489c-119">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Captura de pantalla de la configuración en el centro de administración de Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="8489c-121">El cliente de Microsoft Teams determina si los usuarios necesitan la versión de 32 o de 64 bits e instala el complemento correcto.</span><span class="sxs-lookup"><span data-stu-id="8489c-121">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="8489c-122">Es posible que los usuarios deban reiniciar Outlook después de una instalación o una actualización de Microsoft Teams para obtener el complemento más reciente.</span><span class="sxs-lookup"><span data-stu-id="8489c-122">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="8489c-123">Otras consideraciones</span><span class="sxs-lookup"><span data-stu-id="8489c-123">Other considerations</span></span>

<span data-ttu-id="8489c-124">El complemento para reunión de Microsoft Teams sigue en proceso de desarrollo para ampliar sus funcionalidades, por lo que le recomendamos que tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8489c-124">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="8489c-125">Las opciones de reunión no están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="8489c-125">Meeting options are currently not available.</span></span>
- <span data-ttu-id="8489c-126">En estos momentos, solo es posible invitar a personas de su compañía, dado que los usuarios externos todavía no pueden unirse a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="8489c-126">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="8489c-127">Este complemento es para reuniones programadas con participantes específicos, no para reuniones en un canal.</span><span class="sxs-lookup"><span data-stu-id="8489c-127">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="8489c-128">Las reuniones de canal se deben programar desde Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8489c-128">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="8489c-129">Actualmente, el complemento para reunión de Microsoft Teams en Outlook solo está disponible para usuarios de Windows, pero próximamente será compatible con Mac.</span><span class="sxs-lookup"><span data-stu-id="8489c-129">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="8489c-130">El complemento no funciona si hay un proxy de autenticación en la ruta de red entre el equipo del usuario y los servicios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8489c-130">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="8489c-131">El complemento se está implementando paulatinamente y puede que aún no esté disponible para su organización.</span><span class="sxs-lookup"><span data-stu-id="8489c-131">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8489c-132">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="8489c-132">Troubleshooting</span></span>

<span data-ttu-id="8489c-133">Si no consigue instalar el complemento Reunión de Teams para Outlook, pruebe estos pasos para solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="8489c-133">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="8489c-134">Asegúrese de que se han aplicado todas las actualizaciones disponibles para el cliente de escritorio de Outlook</span><span class="sxs-lookup"><span data-stu-id="8489c-134">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="8489c-135">Reinicie el cliente de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="8489c-135">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="8489c-136">Cierre la sesión y vuelva a iniciarla en el cliente de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="8489c-136">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="8489c-137">Reinicie el cliente de escritorio de Outlook.</span><span class="sxs-lookup"><span data-stu-id="8489c-137">Restart the Outlook desktop client.</span></span> <span data-ttu-id="8489c-138">(Asegúrese de que Outlook no se está ejecutando en modo de administrador).</span><span class="sxs-lookup"><span data-stu-id="8489c-138">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="8489c-139">Asegúrese de que el nombre de la cuenta de usuario activa no contiene espacios.</span><span class="sxs-lookup"><span data-stu-id="8489c-139">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="8489c-140">(Este es un problema conocido y se corregirá en una actualización futura).</span><span class="sxs-lookup"><span data-stu-id="8489c-140">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="8489c-141">Asegúrese de que el inicio de sesión único (SSO) está habilitado.</span><span class="sxs-lookup"><span data-stu-id="8489c-141">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="8489c-142">Para obtener instrucciones generales sobre cómo desactivar complementos, consulte [Ver, administrar e instalar los complementos de los programas de Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="8489c-142">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="8489c-143">Obtenga más información sobre [reuniones y llamadas en Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="8489c-143">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]


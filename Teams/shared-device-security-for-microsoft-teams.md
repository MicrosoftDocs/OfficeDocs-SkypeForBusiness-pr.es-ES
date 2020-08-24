---
title: Guía de seguridad para Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Instrucciones para usar Microsoft Teams de forma segura desde un equipo compartido en el lugar de trabajo.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: a723a7300febde4eaa5045b9b1318a3e0cafe779
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860840"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="843a6-103">Usar Microsoft Teams de forma segura en equipos compartidos</span><span class="sxs-lookup"><span data-stu-id="843a6-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="843a6-104">Siempre que sea posible, *se recomienda* a las empresas emplear un enfoque de Confianza cero con los dispositivos cliente que hacen uso de las funciones de administración de dispositivos, las comprobaciones de estado del dispositivo y la aplicación de directivas, el cifrado a nivel de dispositivo y otras características de seguridad.</span><span class="sxs-lookup"><span data-stu-id="843a6-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Imagen de Confianza cero que muestra en círculos azules los principios básicos de la Confianza cero: la comprobación explícita, los privilegios mínimos y la suposición de vulneraciones.":::

<span data-ttu-id="843a6-106">Los administradores pueden crear condiciones muy seguras si *insisten* en la comprobación, en los privilegios mínimos y en la suposición de que se va a intentar comprometer la seguridad; estos principios llevan a tomar medidas que reducen el riesgo para los usuarios y los datos.</span><span class="sxs-lookup"><span data-stu-id="843a6-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="843a6-107">Para un examen más profundo de los principios de Confianza cero, puede ver [estos vídeos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span><span class="sxs-lookup"><span data-stu-id="843a6-107">For a deeper examination of Zero Trust principles, see [these videos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="843a6-108">Consejos para usar Microsoft Teams de forma segura desde un equipo compartido.</span><span class="sxs-lookup"><span data-stu-id="843a6-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="843a6-109">Si bien puede que esto no sea posible o práctico en todos los escenarios, sigue siendo importante que los administradores de seguridad sigan lo mejor que puedan las instrucciones para el uso de Teams en un equipo compartido o en un dispositivo no administrado.</span><span class="sxs-lookup"><span data-stu-id="843a6-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="843a6-110">Deben elaborarse planes para ceñirse a las directrices tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="843a6-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="843a6-111">Haga uso de las funciones de seguridad de la plataforma del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="843a6-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="843a6-112">Asegúrese de que el sistema operativo se haya configurado para instalar actualizaciones automáticas desde el proveedor del sistema operativo (lo que, en el caso de Microsoft Systems, se puede realizar mediante [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span><span class="sxs-lookup"><span data-stu-id="843a6-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    2. <span data-ttu-id="843a6-113">Asegúrese de que todas las funciones de cifrado de dispositivo, como [**BitLocker**](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption), estén habilitadas y de que la clave utilizada para acceder al dispositivo esté protegida.</span><span class="sxs-lookup"><span data-stu-id="843a6-113">Ensure that any device encryption capabilities such as [**bitlocker**](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) are enabled, and the key used to access the device is secured.</span></span>
    1. <span data-ttu-id="843a6-114">Utilice funciones antivirus como las ofrecidas por [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) en sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="843a6-114">Use anti-virus capabilities such as those offered by [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="843a6-115">Se recomienda encarecidamente el uso de [cuentas de usuario independientes](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) para cada usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="843a6-115">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="843a6-116">*No* conceda ni utilice privilegios de administrador para las funciones no administrativas (como navegar por la web, ejecutar Teams, etc.).</span><span class="sxs-lookup"><span data-stu-id="843a6-116">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

2. <span data-ttu-id="843a6-117">Aproveche las funciones de seguridad del explorador.</span><span class="sxs-lookup"><span data-stu-id="843a6-117">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="843a6-118">Utilice sesiones de exploración privada para minimizar los datos y el historial que se conservan en el disco.</span><span class="sxs-lookup"><span data-stu-id="843a6-118">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="843a6-119">Por ejemplo, use [la exploración de InPrivate en Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [la exploración en modo incógnito de Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en) o las funcionalidades que ofrezca su explorador para navegar de forma privada.</span><span class="sxs-lookup"><span data-stu-id="843a6-119">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="843a6-120">Se recomienda cambiar el comportamiento del sistema para activar la exploración privada *de forma predeterminada*.</span><span class="sxs-lookup"><span data-stu-id="843a6-120">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

3. <span data-ttu-id="843a6-121">Utilice el explorador para desplazarse a la [aplicación web de Teams](https://teams.microsoft.com) (también conocido como cliente *web*) y utilícela, en lugar de usar el cliente descargable de Teams.</span><span class="sxs-lookup"><span data-stu-id="843a6-121">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

4. <span data-ttu-id="843a6-122">Cuando termine de usar el sistema compartido, debe:</span><span class="sxs-lookup"><span data-stu-id="843a6-122">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="843a6-123">[Cerrar la sesión de Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span><span class="sxs-lookup"><span data-stu-id="843a6-123">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="843a6-124">Cerrar todas las pestañas y ventanas del explorador.</span><span class="sxs-lookup"><span data-stu-id="843a6-124">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="843a6-125">Cerrar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="843a6-125">Sign out of the device.</span></span>

<span data-ttu-id="843a6-126">Los elementos anteriores no constituyen una lista completa de las prácticas recomendadas o de los controles de seguridad que cubren todos los casos. Por tanto, puede que existan acciones adicionales que se puedan llevar a cabo en su entorno (por ejemplo, puede que los administradores de seguridad decidan usar Vínculos seguros y Datos adjuntos seguros para Teams si tiene [ATP de Office 365 Plan 1 o 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span><span class="sxs-lookup"><span data-stu-id="843a6-126">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="843a6-127">Sin embargo, estos pasos son un punto de partida para crear instrucciones de uso de Teams en dispositivos compartidos.</span><span class="sxs-lookup"><span data-stu-id="843a6-127">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="843a6-128">Más información</span><span class="sxs-lookup"><span data-stu-id="843a6-128">More Information</span></span>

[<span data-ttu-id="843a6-129">BitLocker en Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="843a6-129">Bitlocker in Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="843a6-130">BitLocker para Windows 10 en Intune</span><span class="sxs-lookup"><span data-stu-id="843a6-130">Bitlocker for Windows 10 in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="843a6-131">Seguridad de punto de conexión en Intune</span><span class="sxs-lookup"><span data-stu-id="843a6-131">Endpoint security in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

<span data-ttu-id="843a6-132">[Habilitar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Antivirus de Microsoft defender en la Seguridad de Windows y [ejecutar exámenes](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span><span class="sxs-lookup"><span data-stu-id="843a6-132">[Enable](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="843a6-133">Artículo del Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="843a6-133">Microsoft Defender security center article</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="843a6-134">Cliente web de Teams o aplicación web de Teams</span><span class="sxs-lookup"><span data-stu-id="843a6-134">Teams web client/teams web app</span></span>](../get-clients.md#web-client)

[<span data-ttu-id="843a6-135">Seguridad y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="843a6-135">Security and Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-security-guide)

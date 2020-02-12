---
title: Iniciar sesión en Microsoft Teams con la autenticación moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Cómo iniciar sesión en Microsoft Teams mediante la autenticación moderna.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bb74338a3e46bb4e3a65fcbf2a69d56558dad61
ms.sourcegitcommit: f859843003b34feab18a3d2df34fdbb9858e7148
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41889443"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="dd04e-103">Iniciar sesión en Microsoft Teams con la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="dd04e-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="dd04e-104">Microsoft Teams usa la autenticación moderna para mantener la experiencia de inicio de sesión sencilla y segura.</span><span class="sxs-lookup"><span data-stu-id="dd04e-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="dd04e-105">Para ver cómo inician sesión en Teams los usuarios, consulte [Iniciar sesión en Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="dd04e-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="dd04e-106">Cómo funciona la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="dd04e-106">How modern authentication works</span></span>

<span data-ttu-id="dd04e-107">La autenticación moderna es un proceso que permite que Teams sepa que los usuarios ya escribieron sus credenciales (como el correo electrónico y la contraseña del trabajo) en otro lugar, por lo que no es necesario volver a escribirlos para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd04e-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="dd04e-108">La experiencia variará según un par de factores, como si los usuarios están trabajando en Windows o en un equipo Mac.</span><span class="sxs-lookup"><span data-stu-id="dd04e-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="dd04e-109">También puede variar en función de si la organización tiene habilitada la autenticación de un solo factor o la autenticación multifactor (por lo general, la autenticación multifactor requiere comprobar las credenciales a través de un teléfono, proporcionar un código único, escribir un PIN o presentar una huella digital).</span><span class="sxs-lookup"><span data-stu-id="dd04e-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="dd04e-110">Este es un resumen de cada escenario de autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="dd04e-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="dd04e-111">Usuarios de Windows</span><span class="sxs-lookup"><span data-stu-id="dd04e-111">Windows users</span></span> 

- <span data-ttu-id="dd04e-112">Si los usuarios ya han iniciado sesión en otras aplicaciones de Office a través de su cuenta de Office 365 Enterprise, cuando inicien Teams, se les dirigirá directamente a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd04e-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="dd04e-113">No es necesario que introduzcan sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="dd04e-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="dd04e-114">Si los usuarios no han iniciado sesión en su cuenta de Office 365 Enterprise en ningún otro lugar, cuando inicien Teams, se les pedirá que proporcionen la autenticación multifactor o de un solo factor (SFA o MFA), en función de lo que la organización haya decidido.</span><span class="sxs-lookup"><span data-stu-id="dd04e-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="dd04e-115">Si los usuarios inician sesión en un equipo unido a un dominio, cuando inicien Teams, es posible que se le pida que realicen un paso de autenticación más, en función de si la organización decidió requerir MFA o si el equipo ya requiere MFA para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="dd04e-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="dd04e-116">Si su equipo ya requiere MFA para iniciar sesión, cuando abran Teams, la aplicación se iniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="dd04e-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="dd04e-117">Si los usuarios han iniciado sesión en un equipo unido a un dominio y no quieren que su nombre de usuario se rellene previamente en la pantalla de inicio de sesión de Teams, los administradores pueden configurar el registro de Windows siguiente para desactivar el rellenado previo del nombre de usuario (UPN):</span><span class="sxs-lookup"><span data-stu-id="dd04e-117">If users are signed in to a domain-joined computer and you don't want their user name pre-populated on the Teams sign-in screen, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="dd04e-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="dd04e-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="dd04e-119">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="dd04e-119">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="dd04e-120">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="dd04e-120">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd04e-121">El rellenado previo para los nombres de usuario que terminan en ".local" o ".corp" está desactivado de forma predeterminada, por lo que no es necesario establecer una clave del registro para desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="dd04e-121">Skipping user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="dd04e-122">Usuarios de Mac</span><span class="sxs-lookup"><span data-stu-id="dd04e-122">Mac users</span></span> 

<span data-ttu-id="dd04e-123">Cuando los usuarios inicien Teams, el equipo no podrá recuperar las credenciales de su cuenta de Office 365 Enterprise o de ninguna de las aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="dd04e-123">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="dd04e-124">En su lugar, verán un mensaje que les pide la SFA o la MFA (según la configuración de su organización).</span><span class="sxs-lookup"><span data-stu-id="dd04e-124">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="dd04e-125">Una vez que los usuarios escriben sus credenciales, no se les pedirá que las proporcionen nuevamente.</span><span class="sxs-lookup"><span data-stu-id="dd04e-125">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="dd04e-126">A partir de ese momento, Teams se inicia automáticamente siempre y cuando estén trabajando en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="dd04e-126">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="dd04e-127">Cambiar de cuentas después de completar la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="dd04e-127">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="dd04e-128">Si los usuarios trabajan en un equipo unido a un dominio (por ejemplo, si su espacio empresarial ha habilitado Kerberos), no podrán cambiar de cuenta de usuario una vez hayan completado la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="dd04e-128">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="dd04e-129">Si los usuarios no están trabajando en un equipo unido a un dominio, podrán cambiar de cuenta.</span><span class="sxs-lookup"><span data-stu-id="dd04e-129">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="dd04e-130">Cerrar la sesión de Teams una vez completada la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="dd04e-130">Signing out of Teams after completing modern authentication</span></span>
<span data-ttu-id="dd04e-131">Para cerrar la sesión de Teams, los usuarios pueden hacer clic en su imagen de perfil en la parte superior de la aplicación y seleccionar **Cerrar sesión**. También pueden hacer clic con el botón derecho en el icono de la aplicación en la barra de tareas y seleccionar **Cerrar sesión**. Una vez que haya finalizado la sesión en Teams, deberán volver a escribir sus credenciales para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd04e-131">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="dd04e-132">Intervalos de direcciones IP y URL</span><span class="sxs-lookup"><span data-stu-id="dd04e-132">URLs and IP address ranges</span></span>
<span data-ttu-id="dd04e-133">Teams requiere conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="dd04e-133">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="dd04e-134">Para comprender los puntos de conexión que deben ser accesibles para los clientes que usan Teams en planes de Office 365, gobierno y otras nubes, lea [Intervalos de direcciones IP y URL de Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="dd04e-134">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="dd04e-135">En la actualidad, Teams necesita acceso (puerto TCP 443) al servicio de Google ssl.gstatic.com (https://ssl.gstatic.com) para todos los usuarios, esto sucede aunque no esté usando Gstatic.</span><span class="sxs-lookup"><span data-stu-id="dd04e-135">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (https://ssl.gstatic.com) for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="dd04e-136">Teams quitará este requisito pronto (principios de 2020), y actualizaremos este artículo en consecuencia en ese momento.</span><span class="sxs-lookup"><span data-stu-id="dd04e-136">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="dd04e-137">Solución de problemas de la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="dd04e-137">Troubleshooting modern authentication</span></span>

<span data-ttu-id="dd04e-138">La autenticación moderna está disponible para cualquier organización que use Teams, por lo que si los usuarios no pueden completar el proceso, es posible que se haya producido un error en el dominio o en la cuenta de Office 365 Enterprise de su organización.</span><span class="sxs-lookup"><span data-stu-id="dd04e-138">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="dd04e-139">Para obtener más información, consulte [¿por qué tengo problemas para iniciar sesión en Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="dd04e-139">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>


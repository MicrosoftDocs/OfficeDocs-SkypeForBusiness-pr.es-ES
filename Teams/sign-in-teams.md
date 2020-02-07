---
title: Iniciar sesión en Microsoft Teams con la autenticación moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Cómo iniciar sesión en Microsoft Teams mediante la autenticación moderna.
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79f04161c070ff4818fdb2dfc212e5c3fc98b2b0
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845141"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="14ee1-103">Iniciar sesión en Microsoft Teams con la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="14ee1-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="14ee1-104">Microsoft Teams usa la autenticación moderna para que la experiencia de inicio de sesión sea sencilla y segura.</span><span class="sxs-lookup"><span data-stu-id="14ee1-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="14ee1-105">Para ver cómo los usuarios inician sesión en Teams, lea [iniciar sesión en Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="14ee1-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="14ee1-106">Cómo funciona la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="14ee1-106">How modern authentication works</span></span>

<span data-ttu-id="14ee1-107">La autenticación moderna es un proceso que permite a los equipos saber que los usuarios ya han escrito sus credenciales (como el correo electrónico y la contraseña del trabajo) en otro lugar y no es necesario que las vuelvan a escribir para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14ee1-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="14ee1-108">La experiencia variará en función de un par de factores, como si los usuarios estuvieran trabajando en Windows o en un equipo Mac.</span><span class="sxs-lookup"><span data-stu-id="14ee1-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="14ee1-109">También variará dependiendo de si su organización ha habilitado la autenticación de factor único o la autenticación multifactor (la autenticación multifactor generalmente implica comprobar las credenciales a través de un teléfono, lo que proporciona un código único, escribe un PIN o presentar una huella digital).</span><span class="sxs-lookup"><span data-stu-id="14ee1-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="14ee1-110">Este es un resumen de cada escenario de autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="14ee1-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="14ee1-111">Usuarios de Windows</span><span class="sxs-lookup"><span data-stu-id="14ee1-111">Windows users</span></span> 

- <span data-ttu-id="14ee1-112">Si los usuarios ya han iniciado sesión en otras aplicaciones de Office a través de su cuenta de Office 365 Enterprise, cuando inicien Teams se les dirigirá directamente a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14ee1-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="14ee1-113">No es necesario que introduzcan sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="14ee1-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="14ee1-114">Si los usuarios no han iniciado sesión en su cuenta de Office 365 Enterprise en ningún otro lugar, cuando inicien Teams, se les pedirá que proporcionen autenticación multifactor o de factor único (fútbolso o MFA), en función de lo que su organización haya decidido que le gustaría proceso.</span><span class="sxs-lookup"><span data-stu-id="14ee1-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="14ee1-115">Si los usuarios han iniciado sesión en un equipo unido a un dominio, cuando inicien Teams, es posible que se le pida un paso más de autenticación, en función de si su organización optó por requerir MFA o si su equipo ya requiere MFA para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="14ee1-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="14ee1-116">Si su equipo ya requiere que MFA inicie sesión, cuando abra Teams, la aplicación se iniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="14ee1-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="14ee1-117">Si los usuarios han iniciado sesión en un equipo unido a un dominio y no desea que su nombre de usuario se haya rellenado previamente en la pantalla de inicio de sesión de Teams, los administradores pueden configurar el siguiente registro de Windows para desactivar el rellenado anterior del nombre de usuario (UPN):</span><span class="sxs-lookup"><span data-stu-id="14ee1-117">If users are signed in to a domain-joined computer and you don't want their user name pre-populated on the Teams sign-in screen, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="14ee1-118">Equipo \ HKEY_CURRENT_USER \Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="14ee1-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="14ee1-119">SkipUpnPrefill (REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="14ee1-119">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="14ee1-120">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="14ee1-120">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="14ee1-121">La omisión del nombre de usuario prerelleno de los nombres de usuario que terminan en ". local" o ". Corp" está activado de forma predeterminada, por lo que no es necesario configurar una clave del registro para desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="14ee1-121">Skipping user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="14ee1-122">Usuarios de Mac</span><span class="sxs-lookup"><span data-stu-id="14ee1-122">Mac users</span></span> 

<span data-ttu-id="14ee1-123">Cuando los usuarios inician Teams, su equipo no podrá recuperar sus credenciales de su cuenta de Office 365 Enterprise ni de ninguna de las otras aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="14ee1-123">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="14ee1-124">En su lugar, verán un mensaje pidiéndole a la persona con la configuración de, según la configuración de su organización.</span><span class="sxs-lookup"><span data-stu-id="14ee1-124">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="14ee1-125">Una vez que los usuarios escriben sus credenciales, no se les pedirá que vuelvan a proporcionarlas.</span><span class="sxs-lookup"><span data-stu-id="14ee1-125">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="14ee1-126">A partir de ese momento, los equipos se inician automáticamente cada vez que trabajan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="14ee1-126">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="14ee1-127">Cambiar de cuenta tras completar la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="14ee1-127">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="14ee1-128">Si los usuarios trabajan en un equipo unido a un dominio (por ejemplo, si su inquilino ha habilitado Kerberos), no puede cambiar las cuentas de usuario una vez que haya completado la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="14ee1-128">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="14ee1-129">Si los usuarios no trabajan en un equipo unido a un dominio, pueden cambiar de cuenta.</span><span class="sxs-lookup"><span data-stu-id="14ee1-129">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="14ee1-130">Cerrar la sesión de Microsoft Teams tras completar la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="14ee1-130">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="14ee1-131">Para cerrar la sesión de Teams, los usuarios pueden hacer clic en su imagen de perfil en la parte superior de la aplicación y, a continuación, seleccionar **Cerrar sesión**. También puede hacer clic con el botón derecho en el icono de la aplicación en la barra de tareas y, a continuación, seleccionar **Cerrar sesión**. Una vez que se cierra la sesión de Teams, es necesario volver a escribir sus credenciales para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14ee1-131">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="14ee1-132">Direcciones URL e intervalos de direcciones IP</span><span class="sxs-lookup"><span data-stu-id="14ee1-132">URLs and IP address ranges</span></span>
<span data-ttu-id="14ee1-133">Teams requiere conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="14ee1-133">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="14ee1-134">Para comprender los puntos de conexión que deben ser accesibles para los clientes que usan equipos en planes de Office 365, administración pública y otras nubes, lea las [instrucciones disponibles aquí](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="14ee1-134">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, please read the [guidance available here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="14ee1-135">Además, también necesitará permitir el acceso a https://ssl.gstatic.com.</span><span class="sxs-lookup"><span data-stu-id="14ee1-135">In addition to this, you'd need to also allow access to https://ssl.gstatic.com.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="14ee1-136">Solución de problemas de autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="14ee1-136">Troubleshooting modern authentication</span></span>

<span data-ttu-id="14ee1-137">La autenticación moderna está disponible para todas las organizaciones que usan Teams, por lo que si los usuarios no pueden completar el proceso, es posible que haya algún problema con su dominio o con la cuenta de Office 365 Enterprise de su organización.</span><span class="sxs-lookup"><span data-stu-id="14ee1-137">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="14ee1-138">Para obtener más información, consulte [¿por qué tengo problemas para iniciar sesión en Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="14ee1-138">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>


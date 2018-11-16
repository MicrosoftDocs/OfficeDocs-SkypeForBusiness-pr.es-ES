---
title: Inicie sesión en Teams Microsoft mediante la autenticación de moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Cómo iniciar sesión Microsoft Teams mediante el uso de autenticación moderna.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01ca138aebae8d0db731118baf3e340aa3332120
ms.sourcegitcommit: bd32d44d27990e373ce6afa38897159473601113
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2018
ms.locfileid: "26544375"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="f5323-103">Inicie sesión en Teams Microsoft mediante la autenticación de moderna</span><span class="sxs-lookup"><span data-stu-id="f5323-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="f5323-104">Microsoft Teams usa autenticación moderna para conservar la experiencia de inicio de sesión sencilla y segura.</span><span class="sxs-lookup"><span data-stu-id="f5323-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="f5323-105">Para ver cómo los usuarios inician sesión los equipos, lea [iniciar sesión en los equipos](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="f5323-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="f5323-106">Moderno cómo funciona la autenticación</span><span class="sxs-lookup"><span data-stu-id="f5323-106">How modern authentication works</span></span>

<span data-ttu-id="f5323-107">Autenticación moderna es un proceso que permite a los equipos a saber que los usuarios ya han escrito sus credenciales (al igual que su correo electrónico del trabajo y la contraseña) en otro lugar, y no necesitan que escribirlas de nuevo para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5323-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="f5323-108">La experiencia de variará en función factores un par, al igual que si los usuarios están trabajando en Windows o en un MAC.</span><span class="sxs-lookup"><span data-stu-id="f5323-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="f5323-109">También varían dependiendo de si su organización ha habilitado la autenticación de factor único o autenticación multifactor (autenticación multifactor normalmente implica la comprobación de credenciales a través de un teléfono, que proporciona un código único, especificar un PIN, o presentar una huella digital).</span><span class="sxs-lookup"><span data-stu-id="f5323-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="f5323-110">Este es un resumen de cada escenario de autenticación moderno.</span><span class="sxs-lookup"><span data-stu-id="f5323-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="f5323-111">Usuarios de Windows</span><span class="sxs-lookup"><span data-stu-id="f5323-111">Windows users</span></span> 

- <span data-ttu-id="f5323-112">Si los usuarios han ya ha iniciado sesión otras aplicaciones de Office a través de su cuenta de Office 365 Enterprise, cuando inician los equipos que se tomaron rectas a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5323-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="f5323-113">No es necesario para que puedan escribir sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="f5323-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="f5323-114">Si los usuarios no están ha iniciado sesión su cuenta de Office 365 Enterprise en ningún otro lugar, cuando inician los equipos, pregunte para proporcionar la autenticación de factor único o varios factor (SFA o MFA), dependiendo de lo que la organización ha decidido que desearían el proceso que implican.</span><span class="sxs-lookup"><span data-stu-id="f5323-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="f5323-115">Si los usuarios se conectan a un equipo unido a un dominio, cuando inician los equipos, que es posible que se le pida para ir a través de una paso de autenticación más, dependiendo de si la organización optó por requieren MFA o si su equipo ya requiere MFA iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="f5323-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="f5323-116">Si su equipo ya requiere MFA iniciar sesión, cuando se abren los equipos, la aplicación automáticamente se inicia.</span><span class="sxs-lookup"><span data-stu-id="f5323-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="f5323-117">Usuarios de Mac</span><span class="sxs-lookup"><span data-stu-id="f5323-117">Mac users</span></span> 

<span data-ttu-id="f5323-118">Cuando los usuarios inicien los equipos, su equipo no podrá extraer sus credenciales de su cuenta de Office 365 Enterprise o cualquiera de sus otras aplicaciones de Office.</span><span class="sxs-lookup"><span data-stu-id="f5323-118">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="f5323-119">En su lugar, verán un mensaje indicándole para SFA o MFA (según la configuración de la organización).</span><span class="sxs-lookup"><span data-stu-id="f5323-119">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="f5323-120">Una vez que los usuarios escriben sus credenciales, no se necesitará a fin de proporcionarles nuevo.</span><span class="sxs-lookup"><span data-stu-id="f5323-120">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="f5323-121">A partir de ese momento, los equipos automáticamente se inicia cada vez que está trabajando en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="f5323-121">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="f5323-122">Cambiar cuentas después de completar la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="f5323-122">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="f5323-123">Si los usuarios están trabajando en un equipo unido a un dominio (por ejemplo, si su inquilino ha habilitado Kerberos), no pueden cambiar las cuentas de usuario una vez que hayan completado la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="f5323-123">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="f5323-124">Si los usuarios no están trabajando en un equipo unido a un dominio, puede cambiar de cuentas.</span><span class="sxs-lookup"><span data-stu-id="f5323-124">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="f5323-125">Cerrar una sesión de Microsoft Teams después de completar la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="f5323-125">Signing out of Microsoft Teams after completing modern authentication</span></span>

<span data-ttu-id="f5323-126">Para desconectarse de los equipos, los usuarios pueden haga clic en su imagen de perfil en la parte superior de la aplicación y, a continuación, seleccione **Cerrar sesión**. Pueden también (ratón) en el icono de la aplicación en la barra de tareas y, a continuación, seleccione **Cerrar la sesión**. Una vez que ha de cerrar la sesión de equipos, que se necesitan escribir sus credenciales de nuevo para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5323-126">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="f5323-127">Solución de problemas de autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="f5323-127">Troubleshooting modern authentication</span></span>

<span data-ttu-id="f5323-128">Autenticación moderna está disponible para todas las organizaciones que usa los equipos, por lo que si los usuarios no pueden completar el proceso, puede haber algún problema con su dominio o cuenta de Office 365 Enterprise de su organización.</span><span class="sxs-lookup"><span data-stu-id="f5323-128">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="f5323-129">Para obtener más información, vea [¿por qué estoy teniendo problemas para iniciar sesión en Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span><span class="sxs-lookup"><span data-stu-id="f5323-129">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>


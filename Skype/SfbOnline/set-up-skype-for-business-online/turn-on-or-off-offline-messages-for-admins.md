---
title: Activar o desactivar los mensajes sin conexión para administradores
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: ec5aad56ef7557c9b7854c6844d65ff3799d1d1c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568760"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="ea446-103">Activar o desactivar los mensajes sin conexión para administradores</span><span class="sxs-lookup"><span data-stu-id="ea446-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="ea446-104">Puedes enviar MENSAJES de Skype Empresarial a tus contactos incluso si no han iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="ea446-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="ea446-105">Esta característica le permite a sus contactos saber que ha intentado hablar con ellos.</span><span class="sxs-lookup"><span data-stu-id="ea446-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="ea446-106">No tiene que esperar hasta que alguien esté en línea para poder enviarle un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ea446-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="ea446-107">Información importante sobre los mensajes sin conexión:</span><span class="sxs-lookup"><span data-stu-id="ea446-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="ea446-108">Los mensajes sin conexión no se archivan en el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="ea446-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="ea446-109">Los mensajes sin conexión se enviarán al buzón del usuario y el usuario recibirá una notificación cuando inicie sesión en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ea446-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="ea446-110">Si el estado del destinatario  del mensaje está establecido en No molestar o **Presentar,** recibirá un mensaje perdido que se envía desde el cliente de Skype Empresarial del destinatario.</span><span class="sxs-lookup"><span data-stu-id="ea446-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="ea446-111">Para obtener más información, vea [Usar la mensajería sin conexión en Skype Empresarial.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)</span><span class="sxs-lookup"><span data-stu-id="ea446-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="ea446-112">Para empezar</span><span class="sxs-lookup"><span data-stu-id="ea446-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="ea446-113">Skype Empresarial Online Connector forma parte actualmente del último módulo de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="ea446-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="ea446-114">Si usa la última versión pública de PowerShell de Teams, no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="ea446-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="ea446-115">Instale el [módulo de PowerShell de Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="ea446-115">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="ea446-116">Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="ea446-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="ea446-117">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectarse a todos los servicios de [Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ea446-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="ea446-118">Activar o desactivar la mensajería instantánea sin conexión</span><span class="sxs-lookup"><span data-stu-id="ea446-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="ea446-119">Los mensajes  sin conexión solo están disponibles en la versión más reciente del cliente de Skype Empresarial hacer clic y ejecutar y no están disponibles cuando se usa un Skype Empresarial de hacer clic y ejecutar anterior o se usó un archivo \*.msi para instalar el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ea446-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="ea446-120">Para habilitar o deshabilitar los mensajes sin conexión que envían mensajes sin conexión para los usuarios de su organización, establezca  _EnableIMAutoArchiving en_ `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="ea446-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="ea446-121">De forma predeterminada, se establece en `True` .</span><span class="sxs-lookup"><span data-stu-id="ea446-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="ea446-122">Para desactivarlo, use el cmdlet **Set-CsClientPolicy** y ejecute:</span><span class="sxs-lookup"><span data-stu-id="ea446-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="ea446-123">Para habilitar o deshabilitar mensajes sin conexión enviar mensajes sin conexión para un usuario, establezca  _EnableIMAutoArchiving en_ `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="ea446-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="ea446-124">De forma predeterminada, esta opción está establecida en  `True`.</span><span class="sxs-lookup"><span data-stu-id="ea446-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="ea446-125">Puede usar una directiva existente o crear una como el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ea446-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ea446-126">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ea446-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ea446-127">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="ea446-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ea446-128">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="ea446-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ea446-129">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="ea446-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="ea446-130">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ea446-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="ea446-131">Seis razones por las que es posible que desee usar Windows PowerShell administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="ea446-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="ea446-132">Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="ea446-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ea446-133">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="ea446-133">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="ea446-134">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea446-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="ea446-135">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ea446-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="ea446-136">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ea446-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="ea446-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ea446-137">Related topics</span></span>
[<span data-ttu-id="ea446-138">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ea446-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="ea446-139">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="ea446-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

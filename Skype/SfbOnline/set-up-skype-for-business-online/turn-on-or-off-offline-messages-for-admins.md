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
ms.openlocfilehash: 03e92118fd915582030b5259654664121ca96c50
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777145"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="767d2-103">Activar o desactivar los mensajes sin conexión para administradores</span><span class="sxs-lookup"><span data-stu-id="767d2-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="767d2-p101">Puede enviar mensajes instantáneos de Skype empresarial a sus contactos incluso si no han iniciado sesión. Esta característica permite que tus contactos sepan que has intentado comunicarte con ellos. No tiene que esperar hasta que alguien esté conectado antes de enviarle un mensaje.</span><span class="sxs-lookup"><span data-stu-id="767d2-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="767d2-107">Información importante sobre los mensajes sin conexión:</span><span class="sxs-lookup"><span data-stu-id="767d2-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="767d2-108">Los mensajes sin conexión no se archivan en el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="767d2-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="767d2-109">Los mensajes sin conexión se enviarán al buzón del usuario y el usuario recibirá una notificación cuando inicie sesión en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="767d2-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="767d2-110">Si el estado del destinatario del mensaje es **no molestar** o **presentando**, recibirá un mensaje perdido enviado desde el cliente de Skype empresarial del destinatario.</span><span class="sxs-lookup"><span data-stu-id="767d2-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="767d2-111">Para obtener más información, consulte [usar mensajería sin conexión en Skype empresarial](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="767d2-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="767d2-112">Para empezar</span><span class="sxs-lookup"><span data-stu-id="767d2-112">To get you started</span></span>

## #

 <span data-ttu-id="767d2-113">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="767d2-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="767d2-114">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="767d2-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="767d2-115">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="767d2-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="767d2-116">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="767d2-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="767d2-117">Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0.</span><span class="sxs-lookup"><span data-stu-id="767d2-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="767d2-118">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="767d2-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="767d2-p103">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="767d2-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>

<span data-ttu-id="767d2-122">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="767d2-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="767d2-123">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="767d2-123">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="767d2-124">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="767d2-124">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="767d2-125">En la ventana de **Windows PowerShell** , conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="767d2-125">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="767d2-126">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="767d2-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```PowerShell
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="767d2-127">Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="767d2-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="767d2-128">Activar o desactivar la mensajería instantánea sin conexión</span><span class="sxs-lookup"><span data-stu-id="767d2-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="767d2-129">Los mensajes sin conexión **solo** están disponibles en la última versión del cliente de Skype empresarial de hacer clic y ejecutar y no están disponibles cuando se usa un antiguo hacer clic y ejecutar de Skype empresarial o se usó un archivo \*. msi para instalar el cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="767d2-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="767d2-130">Para habilitar o deshabilitar los mensajes sin conexión, envíe mensajes sin conexión para los usuarios de `True` su `False`organización, establezca _EnableIMAutoArchiving_ en o.</span><span class="sxs-lookup"><span data-stu-id="767d2-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="767d2-131">De forma predeterminada, esta opción está `True`establecida en.</span><span class="sxs-lookup"><span data-stu-id="767d2-131">By default, this is set to `True`.</span></span>

<span data-ttu-id="767d2-132">Para desactivarlo, use el cmdlet **Set-CsClientPolicy** y ejecute:</span><span class="sxs-lookup"><span data-stu-id="767d2-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="767d2-133">Para habilitar o deshabilitar los mensajes sin conexión, envíe mensajes sin conexión para un `True` usuario `False`, establezca _EnableIMAutoArchiving_ en o.</span><span class="sxs-lookup"><span data-stu-id="767d2-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="767d2-134">De forma predeterminada, esta opción está establecida en  `True`.</span><span class="sxs-lookup"><span data-stu-id="767d2-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="767d2-135">Puede usar una directiva existente o crear una como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="767d2-135">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="767d2-136">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="767d2-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="767d2-137">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="767d2-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="767d2-138">Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="767d2-138">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="767d2-139">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="767d2-139">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="767d2-140">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="767d2-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="767d2-141">Seis motivos por los que es posible que desee usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="767d2-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="767d2-142">Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="767d2-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="767d2-143">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="767d2-143">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="767d2-144">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="767d2-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="767d2-145">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="767d2-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="767d2-146">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="767d2-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="767d2-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="767d2-147">Related topics</span></span>
[<span data-ttu-id="767d2-148">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="767d2-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="767d2-149">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="767d2-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)



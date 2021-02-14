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
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814609"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="aa7c8-103">Activar o desactivar los mensajes sin conexión para administradores</span><span class="sxs-lookup"><span data-stu-id="aa7c8-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="aa7c8-p101">Puede enviar mensajes iMs de Skype Empresarial a sus contactos incluso si no han iniciado sesión. Esta característica permite a sus contactos saber que ha intentado contactar con ellos. No tiene que esperar hasta que alguien esté en línea para poder enviarle un mensaje.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="aa7c8-107">Información importante sobre los mensajes sin conexión:</span><span class="sxs-lookup"><span data-stu-id="aa7c8-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="aa7c8-108">Los mensajes sin conexión no se archivan en el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="aa7c8-109">Los mensajes sin conexión se enviarán al buzón del usuario y se le notificará cuando inicie sesión en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="aa7c8-110">Si el estado del destinatario  del mensaje es No molestar o **Presentando,** recibirá un mensaje perdido que se envía desde el cliente de Skype Empresarial del destinatario.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="aa7c8-111">Para obtener más información, [vea Usar mensajería sin conexión en Skype Empresarial.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)</span><span class="sxs-lookup"><span data-stu-id="aa7c8-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="aa7c8-112">Para empezar</span><span class="sxs-lookup"><span data-stu-id="aa7c8-112">To get you started</span></span>

## #

 <span data-ttu-id="aa7c8-113">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="aa7c8-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="aa7c8-114">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="aa7c8-115">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="aa7c8-116">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="aa7c8-117">Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="aa7c8-118">Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="aa7c8-119">También necesitará instalar el módulo Windows PowerShell para Teams que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>

<span data-ttu-id="aa7c8-120">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="aa7c8-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="aa7c8-121">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="aa7c8-121">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="aa7c8-122">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-122">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="aa7c8-123">En la **Windows PowerShell** de correo electrónico, conéctese a Microsoft 365 u Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="aa7c8-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

   > [!NOTE]
   > <span data-ttu-id="aa7c8-124">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="aa7c8-125">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="aa7c8-126">Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="aa7c8-126">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="aa7c8-127">Activar o desactivar la mensajería instantánea sin conexión</span><span class="sxs-lookup"><span data-stu-id="aa7c8-127">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="aa7c8-128">Los mensajes  sin conexión solo están disponibles en la última versión del cliente hacer clic y ejecutar de Skype Empresarial y no están disponibles cuando se usa una versión anterior de Skype Empresarial o si se usó un archivo \*.msi para instalar el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-128">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="aa7c8-129">Para habilitar o deshabilitar que Mensajes sin conexión envíe mensajes sin conexión a los usuarios de su organización, establezca  _EnableIMAutoArchiving_ en `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="aa7c8-129">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="aa7c8-130">De forma predeterminada, está establecida en `True` .</span><span class="sxs-lookup"><span data-stu-id="aa7c8-130">By default, this is set to `True`.</span></span>

<span data-ttu-id="aa7c8-131">Para desactivarlo, use el cmdlet **Set-CsClientPolicy** y ejecute:</span><span class="sxs-lookup"><span data-stu-id="aa7c8-131">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="aa7c8-132">Para habilitar o deshabilitar que Mensajes sin conexión envíe mensajes sin conexión a un usuario,  _establezca EnableIMAutoArchiving_ en `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="aa7c8-132">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="aa7c8-133">De forma predeterminada, esta opción está establecida en  `True`.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-133">By default, this is set to  `True`.</span></span> <span data-ttu-id="aa7c8-134">Puede usar una directiva existente o crear una como la del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-134">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="aa7c8-135">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="aa7c8-135">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="aa7c8-136">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="aa7c8-137">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="aa7c8-138">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="aa7c8-138">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="aa7c8-139">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aa7c8-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="aa7c8-140">Seis motivos por los que podría desear usar Windows PowerShell administrar Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="aa7c8-140">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="aa7c8-141">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="aa7c8-141">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="aa7c8-142">Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="aa7c8-142">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="aa7c8-143">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa7c8-143">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="aa7c8-144">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aa7c8-144">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="aa7c8-145">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aa7c8-145">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="aa7c8-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aa7c8-146">Related topics</span></span>
[<span data-ttu-id="aa7c8-147">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="aa7c8-147">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="aa7c8-148">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="aa7c8-148">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)



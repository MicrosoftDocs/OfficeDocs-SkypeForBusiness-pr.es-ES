---
title: "Activar o desactivar los mensajes sin conexión para administradores"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 2210f7f0acb2609b7557afe781bbb4349d76c73f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="ac0d1-103">Activar o desactivar los mensajes sin conexión para administradores</span><span class="sxs-lookup"><span data-stu-id="ac0d1-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="ac0d1-104">Puede enviar Skype para IMs de negocio a sus contactos incluso si no has iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="ac0d1-105">Esta característica permite los contactos saber intentando llegar a ellos.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="ac0d1-106">No tiene que esperar hasta que alguien está conectado antes de enviarlos a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-106">You don't have to wait until someone is online before sending them a message.</span></span> 
  
<span data-ttu-id="ac0d1-107">Información importante sobre los mensajes sin conexión:</span><span class="sxs-lookup"><span data-stu-id="ac0d1-107">For Offline messages, it's important to know:</span></span>
  
- <span data-ttu-id="ac0d1-108">Los mensajes sin conexión no se archivan en el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-108">Offline messages won't be archived in the user's mailbox.</span></span>
    
- <span data-ttu-id="ac0d1-109">Se enviarán mensajes sin conexión para el buzón del usuario y se notificará al usuario cuando inician sesión en Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>
    
- <span data-ttu-id="ac0d1-110">Si estado del destinatario del mensaje se establece en **No molestar** o **presentación**, recibirán un mensaje perdido que se envía desde Skype del destinatario para el cliente de negocios.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>
    
<span data-ttu-id="ac0d1-111">Para obtener más información, vea [usar mensajería sin conexión en Skype para el negocio](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="ac0d1-111">For more information, see [Use offline messaging in Skype for Business](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="ac0d1-112">Para empezar</span><span class="sxs-lookup"><span data-stu-id="ac0d1-112">To get you started</span></span>

### 

 <span data-ttu-id="ac0d1-113">**Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**</span><span class="sxs-lookup"><span data-stu-id="ac0d1-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="ac0d1-114">Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ac0d1-115">Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ac0d1-p102">Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-p102">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ac0d1-p103">También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="ac0d1-122">Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="ac0d1-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="ac0d1-123">**Iniciar una sesión de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ac0d1-123">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="ac0d1-124">En el **menú Inicio** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-124">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ac0d1-125">En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:</span><span class="sxs-lookup"><span data-stu-id="ac0d1-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac0d1-126">Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

<span data-ttu-id="ac0d1-127">Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar con todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ac0d1-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="ac0d1-128">Activar o desactivar la mensajería instantánea sin conexión</span><span class="sxs-lookup"><span data-stu-id="ac0d1-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="ac0d1-129">Mensajes sin conexión están **sólo** disponibles en la versión más reciente de la Skype hacer clic en ejecutar para cliente de empresa y no están disponibles cuando se utiliza un Skype hacer clic para ejecutar antiguos de negocio o un archivo \*.msi se utilizó para instalar el Skype para cliente de empresa.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>
  
<span data-ttu-id="ac0d1-130">Para habilitar o deshabilitar mensajes sin conexión enviar los mensajes sin conexión para los usuarios de su organización, establezca _EnableIMAutoArchiving_ en `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="ac0d1-131">De forma predeterminada, se establece en `True`.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-131">By default, this is set to `True`.</span></span>
  
<span data-ttu-id="ac0d1-132">Para desactivarlo, use el cmdlet **Set-CsClientPolicy** y ejecute:</span><span class="sxs-lookup"><span data-stu-id="ac0d1-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="ac0d1-133">Para habilitar o deshabilitar el envío de mensajes sin conexión mensajes sin conexión para un usuario, establezca _EnableIMAutoArchiving_ en `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="ac0d1-134">De forma predeterminada, se establece en `True`.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="ac0d1-135">Puede utilizar una directiva existente o crear uno similar al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ac0d1-135">You can use an existing policy or create one like the example below.</span></span>
  
> 
  ```
  New-CsClientPolicy -Identity OfflineIM
  ```

> 
  ```
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  ```

> 
  ```
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ac0d1-136">¿Quiere saber más sobre Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ac0d1-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ac0d1-p106">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="ac0d1-p106">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ac0d1-140">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ac0d1-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ac0d1-141">Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 </span><span class="sxs-lookup"><span data-stu-id="ac0d1-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ac0d1-p107">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="ac0d1-p107">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ac0d1-144">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac0d1-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ac0d1-145">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ac0d1-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ac0d1-146">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ac0d1-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ac0d1-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ac0d1-147">Related topics</span></span>
[<span data-ttu-id="ac0d1-148">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ac0d1-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="ac0d1-149">Permitir Skype para usuarios de negocios agregar contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="ac0d1-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

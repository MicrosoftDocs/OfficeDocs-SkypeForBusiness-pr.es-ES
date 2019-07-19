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
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 85e8378c41f3d2398982bacee3c568291903ccce
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792998"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Activar o desactivar los mensajes sin conexión para administradores

Puede enviar mensajes instantáneos de Skype empresarial a sus contactos incluso si no han iniciado sesión. Esta característica le permite a sus contactos saber que ha intentado hablar con ellos. No tiene que esperar hasta que alguien esté en línea para poder enviarle un mensaje.

Información importante sobre los mensajes sin conexión:

- Los mensajes sin conexión no se archivan en el buzón del usuario.

- Los mensajes sin conexión se enviarán al buzón del usuario y el usuario recibirá una notificación cuando inicie sesión en Skype empresarial.

- Si el estado del destinatario del mensaje es **no molestar** o **presentando**, recibirá un mensaje perdido enviado desde el cliente de Skype empresarial del destinatario.

Para obtener más información, consulte [usar mensajería sin conexión en Skype empresarial](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Para empezar

## #

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**

1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.

2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.

3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le solicite.

4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.

Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).

## #

 **Iniciar una sesión de Windows PowerShell**

1. En el **menú Inicio** > **Windows PowerShell**.

2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:

    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.

>
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

## <a name="turning-on-or-off-offline-im"></a>Activar o desactivar la mensajería instantánea sin conexión

> [!NOTE]
> Los mensajes sin conexión **solo** están disponibles en la última versión del cliente de Skype empresarial de hacer clic y ejecutar y no están disponibles cuando se usa un antiguo hacer clic y ejecutar de Skype empresarial o se usó un archivo *. msi para instalar el cliente de Skype empresarial.

Para habilitar o deshabilitar los mensajes sin conexión, envíe mensajes sin conexión para los usuarios de `True` su `False`organización, establezca _EnableIMAutoArchiving_ en o. De forma predeterminada, esta opción está `True`establecida en.

Para desactivarlo, use el cmdlet **Set-CsClientPolicy** y ejecute:

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Para habilitar o deshabilitar los mensajes sin conexión, envíe mensajes sin conexión para un `True` usuario `False`, establezca _EnableIMAutoArchiving_ en o. De forma predeterminada, esta opción está establecida en  `True`. Puede usar una directiva existente o crear una como en el ejemplo siguiente.


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos por los que es posible que desee usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)



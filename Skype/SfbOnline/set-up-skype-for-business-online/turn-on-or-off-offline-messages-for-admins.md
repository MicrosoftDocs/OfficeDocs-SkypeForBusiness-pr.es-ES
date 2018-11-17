---
title: Activar o desactivar los mensajes sin conexión para administradores
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 7401d1690f85fcfcc0cefe157b4335da63181693
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561586"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Activar o desactivar los mensajes sin conexión para administradores

Puede enviar Skype para mensajes instantáneos de negocio a sus contactos, incluso si no están firmadas. Esta característica le permite a sus contactos saber que ha intentado hablar con ellos. No tiene que esperar hasta que alguien esté en línea para poder enviarle un mensaje.

Información importante sobre los mensajes sin conexión:

- Los mensajes sin conexión no se archivan en el buzón del usuario.

- Se van a enviar los mensajes sin conexión para el buzón del usuario y se notificará al usuario cuando inicie sesión Skype para la empresa.

- Si el estado del destinatario del mensaje se establece en **No molestar** o **presentar**, recibirán un mensaje perdido que se envía desde Skype el destinatario para clientes empresariales.

Para obtener más información, vea [uso sin conexión de mensajería en Skype para la empresa](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Para empezar

## #

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**

1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.

2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.

3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.

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

Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Configurar el equipo de Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

## <a name="turning-on-or-off-offline-im"></a>Activar o desactivar la mensajería instantánea sin conexión

> [!NOTE]
> Los mensajes sin conexión están **sólo** disponibles en la versión más reciente de la Skype Click-to-Run para cliente empresarial y no están disponibles cuando se usa un Skype de Click-to-Run anterior para la empresa o un archivo *.msi se usó para instalar el Skype para clientes empresariales.

Para habilitar o deshabilitar sin conexión mensajes enviar mensajes sin conexión para los usuarios de su organización, establezca _EnableIMAutoArchiving_ en `True` o `False`. De forma predeterminada, se establece en `True`.

Para desactivarlo, use el cmdlet **Set-CsClientPolicy** y ejecute:

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Para habilitar o deshabilitar el envío de mensajes sin conexión sin conexión, los mensajes para un usuario, establezca _EnableIMAutoArchiving_ en `True` o `False`. De forma predeterminada, esta opción está establecida en  `True`. Puede usar una directiva existente o crear uno al igual que en el ejemplo siguiente.


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)



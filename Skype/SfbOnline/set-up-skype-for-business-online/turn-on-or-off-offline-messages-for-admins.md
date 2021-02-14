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
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Activar o desactivar los mensajes sin conexión para administradores

Puede enviar mensajes iMs de Skype Empresarial a sus contactos incluso si no han iniciado sesión. Esta característica permite a sus contactos saber que ha intentado contactar con ellos. No tiene que esperar hasta que alguien esté en línea para poder enviarle un mensaje.

Información importante sobre los mensajes sin conexión:

- Los mensajes sin conexión no se archivan en el buzón del usuario.

- Los mensajes sin conexión se enviarán al buzón del usuario y se le notificará cuando inicie sesión en Skype Empresarial.

- Si el estado del destinatario  del mensaje es No molestar o **Presentando,** recibirá un mensaje perdido que se envía desde el cliente de Skype Empresarial del destinatario.

Para obtener más información, [vea Usar mensajería sin conexión en Skype Empresarial.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)

## <a name="to-get-you-started"></a>Para empezar

## #

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**

1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.

2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.

3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.

4. También necesitará instalar el módulo Windows PowerShell para Teams que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online.

Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

## #

 **Iniciar una sesión de Windows PowerShell**

1. En el **menú Inicio** > **Windows PowerShell**.

2. En la **Windows PowerShell** de correo electrónico, conéctese a Microsoft 365 u Office 365 ejecutando:

   > [!NOTE]
   > Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.
   >
   > Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>Activar o desactivar la mensajería instantánea sin conexión

> [!NOTE]
> Los mensajes  sin conexión solo están disponibles en la última versión del cliente hacer clic y ejecutar de Skype Empresarial y no están disponibles cuando se usa una versión anterior de Skype Empresarial o si se usó un archivo *.msi para instalar el cliente de Skype Empresarial.

Para habilitar o deshabilitar que Mensajes sin conexión envíe mensajes sin conexión a los usuarios de su organización, establezca  _EnableIMAutoArchiving_ en `True` o `False` . De forma predeterminada, está establecida en `True` .

Para desactivarlo, use el cmdlet **Set-CsClientPolicy** y ejecute:

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Para habilitar o deshabilitar que Mensajes sin conexión envíe mensajes sin conexión a un usuario,  _establezca EnableIMAutoArchiving_ en `True` o `False` . De forma predeterminada, esta opción está establecida en  `True`. Puede usar una directiva existente o crear una como la del ejemplo siguiente.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos por los que podría desear usar Windows PowerShell administrar Microsoft 365 u Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)



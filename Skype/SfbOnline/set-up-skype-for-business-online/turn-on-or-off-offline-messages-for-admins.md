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
ms.openlocfilehash: fc340cff109d33a3a5afeaf6b1b2b09ae7f6ba3b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239166"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Activar o desactivar los mensajes sin conexión para administradores

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Puede enviar mensajes Skype Empresarial a sus contactos incluso si no han iniciado sesión. Esta característica le permite a sus contactos saber que ha intentado hablar con ellos. No tiene que esperar hasta que alguien esté en línea para poder enviarle un mensaje.

Información importante sobre los mensajes sin conexión:

- Los mensajes sin conexión no se archivan en el buzón del usuario.

- Los mensajes sin conexión se enviarán al buzón del usuario y el usuario recibirá una notificación cuando inicie sesión en Skype Empresarial.

- Si el estado del destinatario  del mensaje está establecido en No molestar o **Presentar,** recibirá un mensaje perdido que se envía desde el cliente de Skype Empresarial destinatario.

Para obtener más información, vea [Usar la mensajería sin conexión en Skype Empresarial](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Para empezar

> [!NOTE]
> El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.
1. Instale el [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra un Windows PowerShell de comandos y ejecute los siguientes comandos: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectar a todos los servicios Office 365 en una sola ventana [de Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

## <a name="turning-on-or-off-offline-im"></a>Activar o desactivar la mensajería instantánea sin conexión

> [!NOTE]
> Los mensajes  sin conexión solo están disponibles en la versión más reciente del cliente de hacer clic y ejecutar Skype Empresarial y no están disponibles cuando se usa un Skype Empresarial de hacer clic y ejecutar anterior o se usó un archivo *.msi para instalar el cliente Skype Empresarial.

Para habilitar o deshabilitar los mensajes sin conexión que envían mensajes sin conexión para los usuarios de su organización, establezca  _EnableIMAutoArchiving en_ `True` o `False` . De forma predeterminada, se establece en `True` .

Para desactivarlo, use el cmdlet **Set-CsClientPolicy** y ejecute:

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Para habilitar o deshabilitar mensajes sin conexión enviar mensajes sin conexión para un usuario, establezca  _EnableIMAutoArchiving en_ `True` o `False` . De forma predeterminada, esta opción está establecida en  `True`. Puede usar una directiva existente o crear una como el ejemplo siguiente.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Seis motivos por los que es posible que desee usar Windows PowerShell administrar Microsoft 365 o Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)

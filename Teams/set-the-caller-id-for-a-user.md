---
title: Establecer el identificador de llamada de un usuario
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Obtenga información sobre el identificador de llamada predeterminado de Microsoft 365 y Office 365 (el número de teléfono asignado por un usuario), también conocido como Identificador de línea de llamadas. Puede cambiar o bloquear el identificador de llamada de un usuario.
ms.openlocfilehash: 41883e00955cf5f39f4420fb10ead1be2e131a77
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117158"
---
# <a name="set-the-caller-id-for-a-user"></a>Establecer el identificador de llamada de un usuario
El sistema telefónico de Microsoft 365 y Office 365 proporciona un identificador de llamada predeterminado que es el número de teléfono asignado por el usuario. Si lo desea, puede cambiar o bloquear el identificador de llamada (también denominado identificador de línea de llamada) para un usuario. Para obtener más información sobre cómo usar el identificador de llamada en su organización, vaya a ¿Cómo se puede usar el [identificador de llamada en su organización?](how-can-caller-id-be-used-in-your-organization.md)
  
> [!TIP]
> Actualmente no se pueden bloquear las llamadas entrantes en Skype for Business Online. 
  
Hay algunos ajustes que puede cambiar:
  
> [!NOTE]
> Esto **no es** para las organizaciones locales con Lync o Skype Empresarial Server.
  
- **Cambiar el identificador de llamada saliente** Puede reemplazar el identificador de llamada de un usuario, que es de manera predeterminada su propio número de teléfono, por otro número de teléfono. Por ejemplo, puede cambiar el identificador de llamada del usuario de su número de teléfono a un número de teléfono principal de la empresa, o bien cambiar el identificador de línea de llamada del usuario de su número de teléfono a un número de teléfono principal del departamento jurídico. Puede cambiar el número del identificador de llamada por cualquier número de **servicio** en línea (de pago o gratuito).
    
    > [!NOTE]
    > Si desea usar el parámetro  _Service_, deberá especificar un número de servicio válido.
  
- **Bloquear su identificador de llamada saliente** Puede bloquear el identificador de llamada saliente para que no se envíe en las llamadas RTC salientes de un usuario. Al hacerlo, se bloqueará el número de teléfono para que no se muestre en el teléfono de la persona que llama.
    
- **Bloquear su identificador de llamada entrante** Puede bloquear que un usuario reciba el identificador de llamada en las llamadas RTC entrantes.
    
> [!IMPORTANT]
> Las llamadas de emergencia siempre envían el número de teléfono de los usuarios (identificador de llamada). 
  
De manera predeterminada, estos ajustes del identificador de llamada están **desactivados**. Esto significa que el número de teléfono del usuario de Skype Empresarial Online se puede ver cuando el usuario realiza una llamada a un teléfono RTC.
  
Para obtener más información sobre esta configuración y cómo usarla, vaya [Cómo se puede usar la identificación de llamadas en su organización](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Establecer la configuración de la directiva de identificación de llamadas

> [!NOTE]
> Para todas las opciones de configuración de Identificador de llamadas en  Skype Empresarial Online, debe usar Windows PowerShell y no puede usar el Centro de administración **de Skype Empresarial.** 
  
### <a name="start-powershell"></a>Iniciar PowerShell

- Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Ver toda la configuración de la directiva de identificación de llamadas en su organización

- Para ver toda la configuración de la directiva de identificación de llamadas de su organización, ejecute:

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Vea más ejemplos y detalles [de Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Crear una nueva directiva de identificación de llamadas para su organización


- Para crear una nueva directiva de identificador de llamada que establece el id. de autor de la llamada en anónimo, ejecute:
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > En todos los casos, el campo "Número de servicio" no debe incluir un "+" inicial.

  Vea más ejemplos y detalles [para New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).
    
- Para aplicar la nueva directiva que creó a Amos Marble, ejecute:
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Vea más sobre el [cmdlet Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) para aplicar la configuración a los usuarios.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Establecerlo para que el identificador de llamada entrante esté bloqueado

- Para bloquear el identificador de llamada entrante, ejecute:
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Vea más ejemplos y detalles [para Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).
    
- Para aplicar la configuración de directiva que creó a un usuario de su organización, ejecute:
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    Vea más sobre el [cmdlet Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)
    
### <a name="remove-a-caller-id-policy"></a>Quitar una directiva de identificación de llamadas

Para quitar una directiva de su organización, ejecute:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Para quitar una directiva de un usuario, ejecute:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Seis razones por las que es posible que desee usar Windows PowerShell administrar Microsoft 365 u Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Obtener más información acerca del identificador de línea de llamada y del nombre del usuario de llamada](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

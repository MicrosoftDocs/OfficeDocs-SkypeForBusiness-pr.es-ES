---
title: Establecer el identificador de llamada de un usuario
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Obtenga información sobre Microsoft 365 y Office 365 de llamada predeterminada (número de teléfono asignado por un usuario), también conocido como Identificador de línea de llamada. Puede cambiar o bloquear el identificador de llamada de un usuario.
ms.openlocfilehash: ea3d9676caf0984c19137abe286f792aacfcceca393fd4ccfeff9117edef9011
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54275956"
---
# <a name="set-the-caller-id-for-a-user"></a>Establecer el identificador de llamada de un usuario

Sistema telefónico en Microsoft 365 proporciona un identificador de llamada predeterminado que es el número de teléfono asignado por el usuario. Si lo desea, puede cambiar o bloquear el identificador de llamada (también denominado identificador de línea de llamada) para un usuario. Para obtener más información sobre cómo usar el identificador de llamada en su organización, vaya a ¿Cómo se puede usar el [identificador de llamada en su organización?](how-can-caller-id-be-used-in-your-organization.md)
  
De forma predeterminada, la siguiente configuración de identificador de llamada **está desactivada.** Esto significa que el Teams de teléfono del usuario puede verse cuando ese usuario realiza una llamada a un teléfono RTC. Puede cambiar esta configuración de la siguiente manera:
  
- **Identificador de llamada saliente** Puede reemplazar el identificador de llamada de un usuario, que de forma predeterminada es su número de teléfono, por otro número de teléfono. Por ejemplo, puede cambiar el identificador de llamada del usuario de su número de teléfono a un número de teléfono principal para su empresa o a un número de teléfono principal para el departamento legal. Además, puede establecer el número id. de llamada en cualquier número de servicio en línea (gratuito o gratuito) o en un número de teléfono local mediante enrutamiento directo asignado a una cuenta de recursos usada por un Operador automático o una cola de llamadas.
    
  > [!NOTE]
  > Si desea usar el parámetro *Servicio,* debe especificar un número de servicio válido.
  > Debe usar los cmdlets de PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity en el módulo de PowerShell de Teams 2.3.1 o posterior para el número de cuenta de recurso si no está visible en la lista desplegable.
  
- **Bloquear el identificador de llamada saliente.** Puede bloquear el identificador de llamada saliente para que no se envíe en las llamadas RTC salientes de un usuario. Al hacerlo, se bloqueará el número de teléfono para que no se muestre en el teléfono de la persona que llama.
    
- **Bloquear el identificador de llamada entrante.** Puede bloquear que un usuario reciba el identificador de llamada en las llamadas RTC entrantes.

- **Establecer el nombre de la parte que llama (CNAM).** Para sus Microsoft Teams usuarios, puede enviar un CNAM en las llamadas RTC salientes.
    
> [!IMPORTANT]
> Las llamadas de emergencia siempre envían el número de teléfono de los usuarios (identificador de llamada). 
  

  
Para obtener más información sobre estas opciones de configuración y cómo puede usarlas, vea Cómo se puede usar el [identificador de llamada en su organización.](how-can-caller-id-be-used-in-your-organization.md)
  
## <a name="set-your-caller-id-policy-settings"></a>Establecer la configuración de la directiva de identificación de llamadas

> [!NOTE]
> Para establecer el identificador de llamada en un número de teléfono de cuenta de recurso y establecer el nombre de la parte que llama, use los cmdlets de PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity en el módulo de PowerShell de Teams 2.3.1 o posterior. (Estas opciones no están disponibles actualmente en el centro Microsoft Teams administración). 

Abra un Windows PowerShell de comandos y ejecute los siguientes comandos:

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>Ver, crear y aplicar la configuración de directiva

1. Para ver toda la configuración de la directiva de identificación de llamadas de su organización, ejecute:

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   Para obtener más información, [vea Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).
    
2. Para crear una nueva directiva de identificador de llamada para su organización, use el cmdlet New-CsCallingIdentity llamada:
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    En todos los casos, el campo "Número de servicio" no debe incluir un "+" inicial.

   Para obtener más información, [vea New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).
    
3. Aplique la nueva directiva que creó con el cmdlet Grant-CsCallingIdentity usuario. Por ejemplo, en el ejemplo siguiente se aplica la nueva directiva al usuario Amos Marble.
    
     ```PowerShell
     Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   Para obtener más información, vea [Cmdlet Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)
    

4. Si desea bloquear el identificador de llamada entrante, ejecute:
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   Para obtener más información, [vea Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).
    
5. Para aplicar la configuración de directiva que creó a un usuario de su organización, ejecute:
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   Para obtener más información, [vea Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).

6. Para crear una nueva directiva de identificador de llamada que establece el identificador de llamada en el número de teléfono de la cuenta de recurso especificada y establece el nombre de la parte llamada en Contoso:

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

Si ya ha creado una directiva, puede usar el cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) para aplicar la configuración a los usuarios.
    
### <a name="remove-a-policy-setting"></a>Quitar una configuración de directiva

Para quitar una directiva de su organización, ejecute:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Para quitar una directiva de un usuario, ejecute:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 un único punto de administración que puede simplificar su trabajo diario. Para empezar con Windows PowerShell, vea estos temas:
    
- [Una introducción a Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Seis motivos por los que es posible que desee usar Windows PowerShell administrar Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tiene muchas ventajas en la velocidad, la simplicidad y la productividad en lugar de usar solo el Centro de administración de Microsoft 365 como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
- [Las mejores formas de administrar Microsoft 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [Usar Windows PowerShell para administrar Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Obtener más información acerca del identificador de línea de llamada y del nombre del usuario de llamada](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

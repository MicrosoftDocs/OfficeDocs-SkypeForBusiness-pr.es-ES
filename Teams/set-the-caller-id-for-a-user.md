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
description: Obtenga más información sobre la identificación de llamadas predeterminada de Microsoft 365 y Office 365 (el número de teléfono asignado a un usuario), también conocido como identificador de línea de llamada. Puede cambiar o bloquear la identificación de llamadas de un usuario.
ms.openlocfilehash: 3c39497618927c20d1103b9aaaec82960a06d56c
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255433"
---
# <a name="set-the-caller-id-for-a-user"></a>Establecer el identificador de llamada de un usuario
El sistema telefónico en Microsoft 365 y Office 365 proporciona una identificación de llamadas predeterminada que es el número de teléfono asignado al usuario. Si lo desea, puede cambiar o bloquear el identificador de llamada (también denominado identificador de línea de llamada) para un usuario. Para obtener más información sobre cómo usar la identificación de llamadas en su organización, vaya a [cómo se puede usar la identificación de llamadas en la organización](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Actualmente no se pueden bloquear las llamadas entrantes en Skype for Business Online. 
  
Hay algunos ajustes que puede cambiar:
  
> [!NOTE]
> Esto **no es** para las organizaciones locales con Lync o Skype Empresarial Server.
  
- **Cambiar el identificador de llamada saliente** Puede reemplazar el identificador de llamada de un usuario, que es de manera predeterminada su propio número de teléfono, por otro número de teléfono. Por ejemplo, puede cambiar el identificador de llamada del usuario de su número de teléfono a un número de teléfono principal de la empresa, o bien cambiar el identificador de línea de llamada del usuario de su número de teléfono a un número de teléfono principal del departamento jurídico. Puede cambiar el número del identificador de llamada por cualquier número de **servicio** en línea (de pago o gratuito).
    
    > [!NOTE]
    > Si desea usar el parámetro  _Service_, deberá especificar un número de servicio válido.
  
- **Bloquear la identificación de llamadas salientes** Puedes bloquear la identificación de llamadas salientes para que no se envíen en las llamadas RTC salientes de un usuario. Al hacerlo, se bloqueará el número de teléfono para que no se muestre en el teléfono de la persona que llama.
    
- **Bloquear la identificación de llamadas entrantes** Puede bloquear a un usuario para que no reciba la identificación de llamadas en las llamadas RTC entrantes.
    
> [!IMPORTANT]
> Las llamadas de emergencia siempre envían el número de teléfono de los usuarios (identificador de llamada). 
  
De manera predeterminada, estos ajustes del identificador de llamada están **desactivados**. Esto significa que el número de teléfono del usuario de Skype Empresarial Online se puede ver cuando el usuario realiza una llamada a un teléfono RTC.
  
Para obtener más información sobre esta configuración y cómo usarla, vaya [Cómo se puede usar la identificación de llamadas en su organización](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Establecer la configuración de la Directiva de identificación de llamadas

> [!NOTE]
> Para todas las opciones de identificación de llamadas en Skype empresarial online, debe usar Windows PowerShell y **no puede usar** el centro de **Administración de Skype empresarial**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
    Si necesita más información, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Iniciar una sesión de Windows PowerShell**
    
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana de **Windows PowerShell** , conéctese a Microsoft 365 u Office 365 ejecutando:
    
   > [!NOTE]
   > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Microsoft 365 u Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Ver toda la configuración de la Directiva de identificación de llamadas de su organización

- Para ver todas las opciones de configuración de la Directiva de identificación de llamadas de su organización, ejecute:

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Vea más ejemplos y detalles para [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Crear una nueva Directiva de identificación de llamadas para la organización


- Para crear una nueva Directiva de identificación de llamadas que establezca la identificación de llamadas en Anonymous, ejecute:
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > En todos los casos, el campo "Número de servicio" no debe incluir un "+" inicial.

  Ver más ejemplos y detalles para [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).
    
- Para aplicar la nueva directiva que ha creado a amos Marble, ejecute:
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Para obtener más información, consulta el cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) .
    
Si ya ha creado una directiva, puede usar el cmdlet [set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) para aplicar la configuración a los usuarios.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Configurarlo para que la identificación de llamadas entrantes esté bloqueada

- Para bloquear la identificación de llamadas entrantes, ejecute:
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Ver más ejemplos y detalles para [set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).
    
- Para aplicar la configuración de directiva que ha creado a un usuario de su organización, ejecute:
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    Para obtener más información, consulta el cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) .
    
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

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype empresarial online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que hacer varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que es posible que desee usar Windows PowerShell para administrar Microsoft 365 u Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Obtener más información acerca del identificador de línea de llamada y del nombre del usuario de llamada](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 

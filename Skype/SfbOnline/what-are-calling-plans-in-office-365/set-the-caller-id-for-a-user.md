---
title: Establecer el identificador de llamada de un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going How can caller ID be used in your organization.
ms.openlocfilehash: f57a0a2dc2158949879df8e3755b64183b534f3a
ms.sourcegitcommit: f9a9a7e4b7f6c821a3372f7dcb966a8a6d458752
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "30952411"
---
# <a name="set-the-caller-id-for-a-user"></a>Establecer el identificador de llamada de un usuario
The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Actualmente no se pueden bloquear las llamadas entrantes en Skype for Business Online. 
  
Hay algunos ajustes que puede cambiar:
  
> [!NOTE]
> Esto **no es** para las organizaciones locales con Lync o Skype Empresarial Server.
  
- **Cambiar el identificador de llamada saliente** Puede reemplazar el identificador de llamada de un usuario, que es de manera predeterminada su propio número de teléfono, por otro número de teléfono. Por ejemplo, puede cambiar el identificador de llamada del usuario de su número de teléfono a un número de teléfono principal de la empresa, o bien cambiar el identificador de línea de llamada del usuario de su número de teléfono a un número de teléfono principal del departamento jurídico. Puede cambiar el número del identificador de llamada por cualquier número de **servicio** en línea (de pago o gratuito).
    
    > [!NOTE]
    > Si desea usar el parámetro  _Service_, deberá especificar un número de servicio válido.
  
- **Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.
    
- **Bloque de su identificador de autor de la llamada entrante** Puede bloquear un usuario de recibir identificador de autor de la llamada en las llamadas entrantes de RTC.
    
> [!IMPORTANT]
> Las llamadas de emergencia siempre envían el número de teléfono de los usuarios (identificador de llamada). 
  
De manera predeterminada, estos ajustes del identificador de llamada están **desactivados**. Esto significa que el número de teléfono del usuario de Skype Empresarial Online se puede ver cuando el usuario realiza una llamada a un teléfono RTC.
  
Para obtener más información sobre esta configuración y cómo usarla, vaya [Cómo se puede usar la identificación de llamadas en su organización](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Establecer configuración de la directiva de identificador de su autor de la llamada

> [!NOTE]
> Para todos los valores de identificador de autor de la llamada de Skype para profesionales en línea, debe usar Windows PowerShell y **no se puede usar** el **Skype para el centro de administración de negocio**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
    Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Iniciar una sesión de Windows PowerShell**
    
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
   > [!NOTE]
   > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
   > 
   > ```
   > Import-Module -Name SkypeOnlineConnector
   > ```
   > 
   > ```
   > $credential = Get-Credential
   > ```
   > 
   > ```
   > $session = New-CsOnlineSession -Credential $credential
   > ```
   > 
   > ```
   > Import-PSSession $session
   > ```

Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Configurar el equipo de Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Ver todas las opciones de directiva de identificador de autor de la llamada en la organización

- Para ver todas las configuraciones de directiva del identificador de autor de la llamada en la organización, ejecute:

  ```
  Get-CsCallingLineIdentity |fl
  ```
  Ver más detalles y ejemplos de [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Crear una nueva directiva de identificador de autor de la llamada para la organización


- Para crear una nueva directiva de identificador de autor de la llamada que establece el identificador de autor de la llamada a anónimo, ejecute:
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > En todos los casos, el campo "Número de servicio" no debe incluir un "+" inicial.

  Ver más detalles y ejemplos para [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).
    
- Para aplicar la nueva directiva creó a Amos mármol, ejecute:
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Obtenga más información sobre el cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) .
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) para aplicar la configuración a los usuarios.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Establézcalo por lo que se bloquea el identificador de autor de la llamada entrante

- Para bloquear el identificador de autor de la llamada entrante, ejecute:
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Ver más detalles y ejemplos para [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).
    
- Para aplicar la configuración de la directiva creada a un usuario de la organización, ejecute:
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    Obtenga más información sobre el cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) .
    
### <a name="remove-a-caller-id-policy"></a>Quitar una directiva de identificación de llamadas

Para quitar una directiva de su organización, ejecute:
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Para quitar una directiva de un usuario, ejecute:
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Obtener más información acerca del identificador de línea de llamada y del nombre del usuario de llamada](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 

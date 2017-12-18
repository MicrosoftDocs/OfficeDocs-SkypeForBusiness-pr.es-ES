---
title: "Configurar directivas de conferencia para su organización"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
description: "El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos."
---

# Configurar directivas de conferencia para su organización

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
El servicio de conferencias es una parte importante de Skype Empresarial Online: mediante las conferencias, los grupos de usuarios pueden reunirse en línea para ver diapositivas y vídeo, compartir aplicaciones, cederse archivos, y colaborar y comunicarse de otros modos.
  
Es importante para mantener el control sobre la configuración de conferencia y conferencias. En algunos casos, puede haber problemas de seguridad: de forma predeterminada, cualquier persona, incluidos los usuarios no autenticados, puede participar en reuniones y guardar ninguna de las diapositivas o los documentos que se distribuye durante las reuniones. Además, puede haber problemas legales ocasionales. Por ejemplo, de forma predeterminada, los participantes de la reunión pueden hacer anotaciones en contenido compartido; Sin embargo, estas anotaciones no se guardan cuando se archiva la reunión. Si su organización es necesario para mantener un registro de todas las comunicaciones electrónicas, desea deshabilitar anotaciones.
  
En Skype Empresarial Online, conferencias se administran mediante directivas de conferencias. Directivas de conferencias determinan las características y funcionalidades que se pueden usar en una conferencia, incluido todo o no la conferencia puede incluir IP audio y vídeo para el número máximo de personas que pueden asistir a una reunión. En el ámbito global o en el ámbito por usuario, se pueden configurar directivas de conferencias. Esto proporciona a los administradores enorme flexibilidad cuando se trata de decidir qué capacidades estará disponibles para que los usuarios.
  
Configuración de la directiva se puede configurar en el momento en que se crea una directiva, o puede usar el cmdlet **Set-CsConferencingPolicy** para modificar la configuración de una directiva existente.
  
## Establecer las directivas de conferencia

> [!NOTE]
> Para todas las opciones de directiva de conferencias en Skype Empresarial Online, debe usar Windows PowerShell y **no se puede usar** la **Skype centro de administración de la empresa**. 
  
### Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
    Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Iniciar una sesión de Windows PowerShell**
    
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
  
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

    Si desea obtener más información sobre cómo iniciar Windows PowerShell, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o[Conectarse a Skype Empresarial Online con Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
    
### Bloquear la transferencia de archivos y el uso compartido de escritorios durante las reuniones

- Para crear una nueva directiva de esta configuración, ejecute:
    
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```

    Más información sobre el cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
- Para conceder a la nueva directiva creado a todos los usuarios de su organización, ejecute:
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```

    Más información sobre el cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, usar el cmdlet[Conceder CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración de los usuarios.
  
### Bloquear la grabación de conferencias y evitar que a los participantes de la reunión anónima

- Para crear una nueva directiva de esta configuración, ejecute:
    
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```

    Más información sobre el cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
- Para conceder a la nueva directiva que creó Amos mármol, ejecute:
    
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```

    Más información sobre el cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, usar el cmdlet[Conceder CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración de los usuarios.
  
### Impedir que los participantes anónimos puedan grabar reuniones y que los usuarios externos puedan guardar contenido de las reuniones

- Para crear una nueva directiva de esta configuración, ejecute:
    
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```

    Más información sobre el cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
- Para conceder a la nueva directiva creado a todos los usuarios de su organización, ejecute:
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

    Más información sobre el cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para realizar cambios en la directiva existente y, a continuación, usar el cmdlet[Conceder CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar la configuración de los usuarios.
  
## ¿Quiere saber más sobre Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  


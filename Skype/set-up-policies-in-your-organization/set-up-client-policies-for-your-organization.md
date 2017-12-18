---
title: "Configurar directivas de cliente para su organización"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
description: "Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros."
---

# Configurar directivas de cliente para su organización

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.
  
Configuración de la directiva de cliente se puede configurar en el momento en que se crea una directiva, o puede usar el cmdlet Set-CsClientPolicy para modificar la configuración de una directiva existente.
  
## Establecer las directivas de cliente

> [!NOTE]
> Para toda la configuración de directiva de cliente de Skype empresarial Online, debe usar Windows PowerShell y **no se puede usar** la **Skype centro de administración de la empresa**. 
  
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
    
### Deshabilitar notificaciones de presencia y de iconos gestuales e impedir que se guarden de mensajes instantáneos

- Para crear una nueva directiva de esta configuración, ejecute:
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

    Más información sobre el cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx).
    
- Para conceder a la nueva directiva creado a todos los usuarios de su organización, ejecute:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

    Más información sobre el cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx).
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet de[Conceder CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar la configuración los usuarios.
  
### Permitir que se pueda hacer clic en las URL y los hiperenlaces en MI

- Para crear una nueva directiva de esta configuración, ejecute:
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

    Más información sobre el cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx).
    
- Para conceder a la nueva directiva creado a todos los usuarios de su organización, ejecute:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

    Más información sobre el cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx).
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet de[Conceder CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar la configuración los usuarios.
  
### Impedir que se muestren los contactos recientes

- Para crear una nueva directiva de esta configuración, ejecute:
    
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

    Más información sobre el cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx).
    
- Para conceder a la nueva directiva que creó Amos mármol, ejecute:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

    Más información sobre el cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx).
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet de[Conceder CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar la configuración los usuarios.
  
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
  


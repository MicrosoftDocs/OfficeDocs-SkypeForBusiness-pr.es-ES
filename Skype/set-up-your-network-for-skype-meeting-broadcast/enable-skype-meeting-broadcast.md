---
title: "Habilitar la Difusión de reunión de Skype"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
description: "Antes de que las personas de su organización pueden usar Difusión de reunión de Skype, debe habilitarlo. Para ello, debe saber cómo usar Windows PowerShell. Si no conoce Windows PowerShell, considere la posibilidad de contratar a un asociado de Microsoft para realizar este paso para usted."
---

# Habilitar la Difusión de reunión de Skype

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Antes de que las personas de su organización pueden usar Difusión de reunión de Skype, debe habilitarlo. Para ello, debe saber cómo usar Windows PowerShell. Si no conoce Windows PowerShell, considere la posibilidad de contratar a un [asociado de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar este paso para usted.
  
> [!CAUTION]
> Difusión de reunión de Skype está desactivada de forma predeterminada porque distribución del contenido multimedia de una reunión de difusión utiliza la red de entrega de contenido (CDN) de Microsoft Azure para lograr muy alta escala para admitir miles de la gente que una difusión. El contenido multimedia bloques pasa por la CDN está cifrado y la caché CDN tiene una duración limitada. Además, puede que el componente de Azure CDN no alcanza todavía todos los elementos de las cláusulas de modelo de la UE fruto de la directiva de protección de datos de la UE. Al habilitar esta característica, reconoce este aviso. 
  
## Habilitar Difusión de reunión de Skype mediante el Centro de administración de Skype Empresarial

1. Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. En el Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.
    
3. En la **Skype centro de administración de empresa**, vaya a **las reuniones en línea** > **difundir reuniones** y a continuación, seleccione **Habilitar la difusión de reunión de Skype**.
    
## Habilitar la Difusión de reunión de Skype mediante PowerShell

1. Compruebe que está ejecutando la versión 3.0 o superior de Windows PowerShell.
    
1. Para comprobar que ejecuta la versión 3.0 o superior: **menú Inicio** > **Windows PowerShell**.
    
2. Compruebe la versión escribiendo  _Get-Host_ en la ventana de **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
2. En el **Menú Inicio**, elija **Windows PowerShell**.
    
3. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
  ```
  $Credential = get-credential
  ```

  ```
  $O365Session = New-CsOnlineSession -Credential $credential
  ```

  ```
  Import-PSSession $O365Session
  ```

4. Confirme la configuración actual de Difusión de reunión de Skype ejecutando el siguiente comando:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Compruebe que el parámetro  _EnableBroadcastMeeting_ está establecido como `False`.
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Habilite la Difusión de reunión de Skype para su organización ejecutando el siguiente comando:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    Puede confirmar que está habilitada la configuración ejecutando  `Get-CsBroadcastMeetingConfiguration` de nuevo.
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Después de realizar el cambio, es posible que tarde hasta una hora en surtir efecto en el portal de Difusión de reunión de Skype. 
  
6. Los usuarios pueden contener ahora difundir reuniones con otros usuarios de su empresa. Para obtenerlas iniciado, dirigir a [¿Qué es una Difusión de reunión de Skype?](http://technet.microsoft.com/library/c472c76b-21f1-4e4b-ab58-329a6c33757d%28Office.14%29.aspx)
    
## Configurar su red para difundir reuniones con asistentes externos

Si tiene un firewall y quiere realizar difusiones con personas que no pertenecen a su empresa (que no son una empresa federada), tendrá que configurar su red con estas instrucciones: [Configurar la red para Difusión de reunión de Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.
  
Para omitir este paso y agregue otra empresa para la federación, vea [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
## Vea también
<a name="MT_Footer"> </a>

#### 

[Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)


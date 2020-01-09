---
title: Habilitar la Difusión de reunión de Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Para que las personas de la organización puedan usar la difusión de reunión de Skype, debe habilitarla. Para ello, necesita saber cómo usar Windows PowerShell. Si no conoce Windows PowerShell, considere la posibilidad de contratar un partner de Microsoft para realizar este paso.
ms.openlocfilehash: edf9c372a98da9e09d7e9040c6d035e389c8b1ec
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989145"
---
# <a name="enable-skype-meeting-broadcast"></a>Habilitar la Difusión de reunión de Skype

Para que las personas de la organización puedan usar la difusión de reunión de Skype, debe habilitarla. Para ello, necesita saber cómo usar Windows PowerShell. Si no conoce Windows PowerShell, considere la posibilidad de contratar un [Partner de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar este paso.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Habilitar Difusión de reunión de Skype mediante el Centro de administración de Skype Empresarial

![Un icono que muestra el logotipo](../images/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**

1. Inicie sesión con su cuenta de administrador global de Office 365 o su cuenta de administrador [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)de Skype empresarial en.
    
2. En el centro de administración, vaya a**equipos**del centro de **Administración** > .
    
3. En el **centro de administración de Teams**, vaya a**reuniones de difusión**de **portal** > **en línea** > y, a continuación, seleccione **Habilitar difusión de reunión de Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Habilitar la Difusión de reunión de Skype mediante PowerShell

1. Compruebe que está ejecutando la versión 3.0 o superior de Windows PowerShell.
    
2. Para comprobar que ejecuta la versión 3.0 o superior: **menú Inicio** > **Windows PowerShell**.
    
3. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
4. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le solicite.
    
5. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
6. En el **menú Inicio**, elija **Windows PowerShell**.
    
7. En la ventana de **Windows PowerShell** y conéctese a su organización de Office 365 ejecutando el siguiente comando:
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Confirme la configuración actual de Difusión de reunión de Skype ejecutando el siguiente comando:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Compruebe que el parámetro  _EnableBroadcastMeeting_ está establecido como `False`.
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Habilite la Difusión de reunión de Skype para su organización ejecutando el siguiente comando:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Puede confirmar que la configuración está habilitada ejecutando `Get-CsBroadcastMeetingConfiguration` otra vez.
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Después de realizar el cambio, es posible que tarde hasta una hora en surtir efecto en el portal de Difusión de reunión de Skype. 
  
10. Los usuarios ahora pueden realizar reuniones de difusión con otros usuarios de su empresa. Para que puedan empezar, pídales que lean [¿Qué es una Difusión de reunión de Skype?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurar su red para difundir reuniones con asistentes externos

Si tiene un firewall y quiere realizar difusiones con personas que no pertenecen a su empresa (que no son una empresa federada), tendrá que configurar su red con estas instrucciones: [Configurar la red para Difusión de reunión de Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.
  
Para omitir este paso y, en su lugar, agregar otra empresa a su federación, siga los pasos en [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Temas relacionados

[Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 

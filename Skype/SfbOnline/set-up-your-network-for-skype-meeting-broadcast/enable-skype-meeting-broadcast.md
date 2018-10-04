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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Antes de que los miembros de su organización puedan usar Difusión de reunión de Skype, usted deberá habilitarla. Para llevar a cabo este paso, tiene que saber cómo usar Windows PowerShell. Si no tiene experiencia con Windows PowerShell, analice contratar un socio de Microsoft para que lleve a cabo este paso por usted.
ms.openlocfilehash: 699b82af07b263331ee5508326bf3e7ed015848e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370867"
---
# <a name="enable-skype-meeting-broadcast"></a>Habilitar la Difusión de reunión de Skype

[] Antes de que los miembros de su organización puedan usar Difusión de reunión de Skype, usted deberá habilitarla. Para llevar a cabo este paso, tiene que saber cómo usar Windows PowerShell. Si no tiene experiencia con Windows PowerShell, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Habilitar Difusión de reunión de Skype mediante el Centro de administración de Skype Empresarial

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**

1. Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. En el Centro de administración de Office 365, vaya a **Centros de administración** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocio**, vaya a **las reuniones en línea** > **difundir las reuniones**y, a continuación, seleccione **Habilitar la difusión de reunión de Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Habilitar la Difusión de reunión de Skype mediante PowerShell

1. Compruebe que está ejecutando la versión 3.0 o superior de Windows PowerShell.
    
2. Para comprobar que ejecuta la versión 3.0 o superior: **menú Inicio** > **Windows PowerShell**.
    
3. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
4. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
5. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
6. En el **Menú Inicio**, elija **Windows PowerShell**.
    
7. En la ventana de **Windows PowerShell** y conéctese a su organización de Office 365 ejecutando el siguiente comando:
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Confirme la configuración actual de Difusión de reunión de Skype ejecutando el siguiente comando:
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    Compruebe que el parámetro  _EnableBroadcastMeeting_ está establecido como `False`.
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Habilite la Difusión de reunión de Skype para su organización ejecutando el siguiente comando:
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Puede confirmar que la opción está habilitada volviendo a ejecutar  `Get-CsBroadcastMeetingConfiguration`.
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Después de realizar el cambio, es posible que tarde hasta una hora en surtir efecto en el portal de Difusión de reunión de Skype. 
  
10. Los usuarios ahora pueden realizar reuniones de difusión con otros usuarios de su empresa. Para que puedan empezar, pídales que lean [¿Qué es una Difusión de reunión de Skype?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurar su red para difundir reuniones con asistentes externos

Si tiene un firewall y quiere realizar difusiones con personas que no pertenecen a su empresa (que no son una empresa federada), tendrá que configurar su red con estas instrucciones: [Configurar la red para Difusión de reunión de Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.
  
Para omitir este paso y, en su lugar, agregar otra empresa a su federación, siga los pasos en [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>See also

[Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
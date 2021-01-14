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
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Antes de que las personas de su organización puedan usar la Difusión de reunión de Skype, debe habilitarla. Para ello, debe saber cómo usar el Windows PowerShell. Si no sabe cuál es su Windows PowerShell, considere contratar a un socio de Microsoft para que realice este paso por usted.
ms.openlocfilehash: 1ba8f11913c932d695806ae4fd30db5e8609530f
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865144"
---
# <a name="enable-skype-meeting-broadcast"></a>Habilitar la Difusión de reunión de Skype

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento en el que finalizará el acceso al servicio. Animamos a los clientes a comenzar la actualización a Microsoft Teams, el cliente principal de comunicaciones y trabajo en equipo en Microsoft 365.

Antes de que las personas de su organización puedan usar la Difusión de reunión de Skype, debe habilitarla. Para ello, debe saber cómo usar el Windows PowerShell. Si no tiene experiencia con Windows PowerShell, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.



> [!NOTE]
> El Centro de administración de Microsoft Teams ha sustituido al Centro de administración de Skype Empresarial (portal heredado). Todas las configuraciones para administrar Skype Empresarial se encuentran ahora en el Centro de administración de Teams. Debe tener asignado el rol de administrador de [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de administrador global o de administrador de Skype Empresarial para administrar las características de Skype Empresarial en el Centro de administración de Teams. Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Habilitar Difusión de reunión de Skype mediante el Centro de administración de Skype Empresarial

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

1. Inicie sesión con su cuenta de administrador global o con la cuenta de administrador de Skype Empresarial en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. En el centro de administración, vaya a **Centros de**  >  **administración, Teams.**
    
3. En el **Centro de administración de Teams,** vaya a Difusión de reuniones en línea del **portal** heredado y, a continuación, seleccione Habilitar  >    >   **Difusión de reunión de Skype.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Habilitar la Difusión de reunión de Skype mediante PowerShell

1. Compruebe que está ejecutando la versión 3.0 o superior de Windows PowerShell.
    
2. Para comprobar que ejecuta la versión 3.0 o superior: **menú Inicio** > **Windows PowerShell**.
    
3. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
4. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
5. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
6. En el **menú Inicio,** elija **Windows PowerShell.**
    
7. En la **Windows PowerShell** de correo electrónico, conéctese a Su Microsoft 365 u Office 365 ejecutando:
    
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

    Puede confirmar que la configuración está habilitada ejecutándose de  `Get-CsBroadcastMeetingConfiguration` nuevo.
    
     ![Habilitar cmdlet de organización en una Difusión de reunión de Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Después de realizar el cambio, es posible que tarde hasta una hora en surtir efecto en el portal de Difusión de reunión de Skype. 
  
10. Los usuarios ahora pueden realizar reuniones de difusión con otros usuarios de su empresa. Para que puedan empezar, pídales que lean [¿Qué es una Difusión de reunión de Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurar su red para difundir reuniones con asistentes externos

Si tiene un firewall y quiere realizar difusiones con personas que no pertenecen a su empresa (que no son una empresa federada), tendrá que configurar su red con estas instrucciones: [Configurar la red para Difusión de reunión de Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.
  
Para omitir este paso y, en su lugar, agregar otra empresa a su federación, siga los pasos en [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Temas relacionados

[Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 

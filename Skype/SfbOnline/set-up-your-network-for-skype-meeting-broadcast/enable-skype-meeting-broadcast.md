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
description: Antes de que los usuarios de su organización puedan Skype difusión de reunión, debe habilitarla. Para ello, debe saber cómo usar Windows PowerShell. Si no tiene experiencia con Windows PowerShell, analice contratar un socio de Microsoft para que lleve a cabo este paso por usted.
ms.openlocfilehash: 6cdd7f12483025697b139203907f87f9cd3dc764
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237016"
---
# <a name="enable-skype-meeting-broadcast"></a>Habilitar la Difusión de reunión de Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento en el que finalizará el acceso al servicio. Animamos a los clientes a comenzar la actualización a Microsoft Teams, el cliente principal para las comunicaciones y el trabajo en equipo en Microsoft 365.

Antes de que los usuarios de su organización puedan Skype difusión de reunión, debe habilitarla. Para ello, debe saber cómo usar Windows PowerShell. Si no tiene experiencia con Windows PowerShell, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.



> [!NOTE]
> El Microsoft Teams de administración ha sustituido al Skype Empresarial de administración (portal heredado). Todas las opciones de Skype Empresarial están ahora en el centro Teams administración. Debe tener asignado el rol de administrador de [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global o Skype Empresarial administrador para administrar Skype Empresarial características en el centro Teams administración. Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Habilitar Difusión de reunión de Skype mediante el Centro de administración de Skype Empresarial

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

1. Inicie sesión con su cuenta de administrador global o Skype Empresarial cuenta de administrador en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. En el centro de administración, vaya a Centros **de**  >  **administración Teams**.
    
3. En el **Teams de** administración, vaya a **Portal** heredado En línea Reuniones en línea Difundir reuniones y, a  >    >  continuación, seleccione Habilitar **Skype difusión de reunión**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Habilitar la Difusión de reunión de Skype mediante PowerShell

1. Instale el [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra un Windows PowerShell de comandos y ejecute los siguientes comandos: 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. Confirme la configuración actual de Difusión de reunión de Skype ejecutando el siguiente comando:
    
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

[Introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  

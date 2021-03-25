---
title: Restablecer un id. de conferencia para un usuario en Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre los pasos para restablecer el id. de conferencia de reunión de un usuario en Skype Empresarial Online y obtenga vínculos a herramientas de actualización y migración de reuniones. '
ms.openlocfilehash: 424b0dfb24d6034af20c18a0172221a09bef5ecd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114216"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Restablecer un id. de conferencia para un usuario en Skype Empresarial Online

> [!NOTE]
> Para obtener información sobre cómo restablecer el id. de conferencia en Microsoft Teams, vea Restablecer un id. de [conferencia para un usuario en Microsoft Teams.](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)

Se incluye un id. de conferencia dinámico en la parte inferior de las invitaciones de reunión junto con los números de teléfono de acceso telefónico que pueden usar las personas que llaman para llamar a una reunión. Cuando el usuario marca el número de teléfono, el operador automático de la reunión le pedirá al autor de la llamada que escriba este id. de conferencia para que pueda asistir a la reunión.
  
> [!NOTE]
> Si su proveedor de conferencias es Microsoft, los IDs de conferencia de los usuarios se establecen en Solo dinámico. Esto no se puede cambiar. Los IDs de conferencia solo se establecen automáticamente para los usuarios de Skype Empresarial habilitados para audioconferencias. 

## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el id. de conferencia de un usuario
   
1. En el **Centro de administración de Skype Empresarial,** haga clic en **Usuarios** de audioconferencia, seleccione un usuario y, a continuación, en el panel Acción en  >   **Id.** de conferencia, haga clic en **Restablecer.**
    
2. En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia. De forma predeterminada, los correos electrónicos se envían a los usuarios, pero esto se puede desactivar.
    
> [!NOTE]
> Después de restablecer el id. de conferencia, se enviará al usuario un correo electrónico con el nuevo id. de conferencia. Este correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, a su buzón de Microsoft 365 u Office 365. El correo electrónico contiene el nuevo id. de conferencia, los números de teléfono de acceso telefónico locales predeterminados e instrucciones para usar la Herramienta de actualización de reuniones de Skype Empresarial para actualizar las reuniones existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Puede enviar toda la información de conferencia al usuario en un correo electrónico que incluya  el id. de conferencia y los números de teléfono de acceso telefónico local haciendo clic en Enviar información de conferencia por correo electrónico para el usuario en el panel de acciones. No envía el PIN.
    
- Un id. de conferencia contendrá 7 dígitos y no podrá cambiar su longitud en el Centro de administración de Skype Empresarial ni mediante Windows PowerShell.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- El id. de conferencia de un usuario para conferencias de audioconferencia se puede ver en la parte inferior del panel de acciones en **Audioconferencia** al seleccionar el usuario en la **página** Usuarios.
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Los usuarios pueden usar la Herramienta de reunión de Skype Empresarial para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar la Herramienta de actualización de reuniones de Skype Empresarial, vea:
    
  - [Herramienta de actualización de reuniones para Skype y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Por qué necesita usar Microsoft 365 u Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Temas relacionados

[Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin.md)
---
title: Restablecer un id. de conferencia de un usuario en Skype Empresarial Online
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
description: 'Aprenda los pasos para restablecer el id. de conferencia de reunión de un usuario en Skype Empresarial Online y obtenga vínculos a las herramientas de actualización y migración de reuniones. '
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164709"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Restablecer un id. de conferencia de un usuario en Skype Empresarial Online

> [!NOTE]
> Para obtener información sobre cómo restablecer un id. de conferencia en Microsoft Teams, vea Restablecer un [id. de conferencia para un usuario en Microsoft Teams.](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)

Se incluye un identificador de conferencia dinámico en la parte inferior de las invitaciones a reuniones junto con los números de teléfono de acceso telefónico que pueden usar los autores de las llamadas para llamar a una reunión. Cuando el usuario marca el número de teléfono, el operador automático de la reunión le pedirá al autor de la llamada que introduzca este id. de conferencia para que pueda asistir a la reunión.
  
> [!NOTE]
> Si su proveedor de conferencias es Microsoft, los documentos de conferencia de los usuarios se establecen como Solo dinámicos. Esto no se puede cambiar. Los ID de conferencia solo se establecen automáticamente para los usuarios de Skype Empresarial habilitados para Audioconferencia. 

## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el id. de conferencia de un usuario
   
1. En el **Centro de administración** de Skype Empresarial, haga clic en Usuarios de **Audioconferencia,** seleccione un usuario y, a continuación, en el panel de acciones, en Id. de conferencia,  >  haga clic en **Restablecer.** 
    
2. En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia. De forma predeterminada, los correos electrónicos se envían a los usuarios, pero esto se puede desactivar.
    
> [!NOTE]
> Después de restablecer el id. de conferencia, se enviará al usuario un correo electrónico con el nuevo Id. de conferencia. Este correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su buzón de Microsoft 365 u Office 365. El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico y las instrucciones para usar la herramienta de actualización de reuniones de Skype Empresarial para actualizar las reuniones existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Puede enviar toda la información de conferencia al usuario en un correo electrónico que incluya  el Id. de conferencia y los números de teléfono de acceso telefónico local haciendo clic en Enviar información de conferencia por correo electrónico para el usuario en el panel de acciones. No envía el PIN.
    
- Un id. de conferencia contendrá siete dígitos y no puede cambiar su longitud en el Centro de administración de Skype Empresarial ni mediante el uso de Windows PowerShell.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- El id. de conferencia de un usuario para audioconferencias se puede ver en la parte inferior del panel de acciones en **Audioconferencia** cuando se selecciona el usuario en la **página** Usuarios.
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Los usuarios pueden usar la Herramienta de reuniones de Skype Empresarial para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar la Herramienta de actualización de reuniones de Skype Empresarial, consulte:
    
  - [Herramienta de actualización de reuniones para Skype y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados

[Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin.md)

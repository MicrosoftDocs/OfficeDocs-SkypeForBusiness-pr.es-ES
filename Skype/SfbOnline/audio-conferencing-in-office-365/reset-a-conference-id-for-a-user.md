---
title: Restablecer un identificador de conferencia para un usuario en Skype empresarial online
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
description: 'Obtenga información sobre los pasos para restablecer el identificador de conferencia de un usuario en Skype empresarial online y obtenga vínculos a herramientas de actualización y de migración de reuniones. '
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164709"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Restablecer un identificador de conferencia para un usuario en Skype empresarial online

> [!NOTE]
> Para obtener información sobre cómo restablecer la identificación de conferencia en Microsoft Teams, consulte [restablecer un ID de conferencia para un usuario en Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

En la parte inferior de las invitaciones a reuniones se incluye un identificador de conferencia dinámico junto con los números de teléfono de acceso telefónico local que las personas que llaman pueden usar para llamar a una reunión. Cuando el usuario marca el número de teléfono, el operador automático para la reunión le pedirá a la persona que lo llame para que pueda asistir a la reunión.
  
> [!NOTE]
> Si su proveedor de servicios de conferencia es Microsoft, los identificadores de conferencia de los usuarios se establecen en dinámicos únicamente. Esto no se puede modificar. Los identificadores de conferencia se establecen automáticamente para los usuarios de Skype empresarial habilitados para conferencias de audio. 

## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el identificador de conferencia de un usuario
   
1. En el **centro de administración de Skype empresarial**, haga clic en**usuarios**de **Conferencia** > de audio, seleccione un usuario y, a continuación, en el panel de acciones, en ID de **Conferencia** , haga clic en **restablecer**.
    
2. En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un ID de conferencia y un mensaje de correo electrónico con el nuevo identificador de conferencia. De forma predeterminada, los correos electrónicos se envían a los usuarios, pero esto se puede desactivar.
    
> [!NOTE]
> Después de restablecer el identificador de conferencia, se enviará al usuario un mensaje de correo electrónico con la nueva identificación de conferencia. Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, en el buzón de Microsoft 365 o de Office 365. El correo electrónico contiene el nuevo identificador de conferencia, los números de teléfono de acceso telefónico (s) predeterminados y las instrucciones para usar la herramienta de actualización de reuniones de Skype empresarial para actualizar las reuniones existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Puede enviar toda la información de la Conferencia al usuario en un correo electrónico que incluya el identificador de la Conferencia y los números de teléfono de acceso telefónico local haciendo clic en **enviar información de conferencia por correo electrónico** para el usuario en el panel de acciones. No envía el PIN.
    
- Un identificador de conferencia contendrá 7 dígitos y no podrá cambiar su longitud en el centro de administración de Skype empresarial o mediante Windows PowerShell.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- El identificador de conferencia de un usuario para las conferencias de audio puede verse en la parte inferior del panel de acciones, en **audioconferencias** , cuando selecciona el usuario en la página **usuarios** .
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Los usuarios pueden usar la herramienta de reunión de Skype empresarial para actualizar las reuniones existentes. Para obtener información sobre cómo descargar, instalar y ejecutar la herramienta de actualización de reuniones de Skype empresarial, consulte:
    
  - [Herramienta de actualización de reuniones para Skype y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype empresarial online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que hacer varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados

[Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin.md)

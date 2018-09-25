---
title: Correos electrónicos que se envían a los usuarios cuando cambia la configuración en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vea qué información se envía por correo electrónico automáticamente a los usuarios cuando cambia su configuración de las conferencias de acceso telefónico local en Microsoft Teams. '
ms.openlocfilehash: b1bd7764f7780267d9f2a98a3203f49d2c0e938e
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016168"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Correos electrónicos que se envían a los usuarios cuando cambia la configuración en Microsoft Teams

Los correos electrónicos se enviarán automáticamente a los usuarios que estén [habilitados para Audioconferencia](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) con Microsoft como proveedor de servicios de audioconferencia.
  
De forma predeterminada, hay cuatro tipos de correo electrónico que se van a enviar a los usuarios que están habilitados para conferencias de Audio. Pero, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivarlo. Conferencias de audio en Office 365 va a enviar correo electrónico a los usuarios de correo electrónico cuando:
  
- **Se les asigna una licencia de Audioconferencia o cuando está cambiando el proveedor de servicios de audioconferencia a Microsoft.**
    
     Este correo electrónico incluye el identificador de conferencia, el número de teléfono de conferencia de forma predeterminada para las reuniones, la conferencia de audio PIN para el usuario y las instrucciones y el vínculo que se usará el Skype para Online Meeting actualizar herramienta empresarial que se utiliza para actualizar las reuniones existentes para la usuario. Vea [Asignar Skype para licencias de negocio y equipos de Microsoft](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [Microsoft asignar como el proveedor de conferencia de audio](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [los identificadores dinámicos de conferencias de Audio en su organización](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 
  
    A continuación tiene un ejemplo de este correo electrónico:
    
     ![Skype Empresarial: comprobar licencia](media/audio-conferencing-user-enabled.png)
  
    Puede encontrar más información sobre las licencias en [Licencias complementarias de Skype Empresarial y Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
- **El Id. de conferencia o el número de teléfono de conferencia predeterminado de un usuario cambia.**
    
    Este correo electrónico contiene el identificador de conferencia, número de teléfono de conferencia de forma predeterminada y las instrucciones y vínculos para usar el Skype para Online Meeting actualizar herramienta empresarial que se utiliza para actualizar las reuniones existentes para el usuario. Pero este correo electrónico no incluye los PIN de conferencia de audio del usuario. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
    A continuación tiene un ejemplo de este correo electrónico:
    
     ![La información de conferencias de acceso telefónico local ha cambiado.](media/audio-conferencing-info-change.png)
  
- **El PIN de audioconferencia de un usuario se ha restablecido.**
    
    Este mensaje contiene el PIN de conferencia de audio del organizador, el identificador de conferencia existente y número de teléfono de conferencia predeterminado para el usuario. Vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin-in-teams.md).
    
  
    A continuación tiene un ejemplo de este correo electrónico:
    
     ![La información de las conferencias de acceso telefónico local ha cambiado.](media/audio-conferencing-pin-has-changed.png)
  
- **Cuando se quita la licencia de un usuario o cuando el proveedor de servicios de audioconferencia cambia de Microsoft a otro proveedor o a Ninguno.**
    
    Esto sucede cuando se quita la licencia de **Conferencias de Audio** de un usuario o cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a un proveedor de conferencia de audio de terceros o al establecer el proveedor en **Ninguno**. Este correo electrónico contiene las instrucciones y la información del usuario usar el Skype para la herramienta de actualización de reunión en línea de negocio para quitar la información específica de conferencias de audio, como el ID predeterminado conferencia teléfono número o conferencia.
    
    Consulte [Asignar o cancelar licencias para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    A continuación tiene un ejemplo de este correo electrónico:
    
     ![Las conferencias de acceso telefónico local están desactivadas.](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios incluidos en la dirección de correo electrónico y el nombre para mostrar que se incluye en la información *de* contacto. De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y Mostrar nombre con Windows PowerShell. Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué sucede si no desea que se les envíen correos electrónicos?

Cuando se deshabilitación el envío de correos electrónicos a los usuarios, no se enviará el correo electrónico incluso cuando un usuario obtiene asigna una licencia. En este caso, el identificador de conferencia, predeterminado el número de teléfono de conferencia y, lo que es más importante, su PIN de conferencia de audio no se enviará al usuario. Cuando esto sucede, debe indicar al usuario mediante el envío de un correo electrónico independiente o mediante una llamada a ellos.
  
De manera predeterminada, los correos electrónicos se envían a los usuarios, pero, si quiere evitar que reciban correos electrónicos para el uso de audioconferencias, puede usar Microsoft Teams o Windows PowerShell. 

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si se produce algún cambio en la configuración del acceso telefónico local**.

4. Haga clic en **Guardar**.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
**Uso de Windows PowerShell**
  
Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

De manera predeterminada, el remitente de los mensajes será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell. 

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
  
## <a name="related-topics"></a>Temas relacionados

[Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)

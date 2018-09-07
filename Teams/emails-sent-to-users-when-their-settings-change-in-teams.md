---
title: Correos electrónicos enviados a los usuarios cuando cambie su configuración en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información acerca de qué información se envía automáticamente a los usuarios por correo electrónico cuando cambie su configuración de conferencia de acceso telefónico en Microsoft Teams. '
ms.openlocfilehash: a352ecb335469e1e988c625f638c6136675dc5fc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23871049"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Correos electrónicos enviados a los usuarios cuando cambie su configuración en Microsoft Teams

Los correos electrónicos se enviarán automáticamente a los usuarios que están [habilitados para conferencias de Audio](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) con Microsoft como proveedor de conferencias de audio.
  
De forma predeterminada, hay cuatro tipos de correo electrónico que se van a enviar a los usuarios que están habilitados para conferencias de Audio. Pero, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivarlo. Conferencias de audio en Office 365 va a enviar correo electrónico a los usuarios de correo electrónico cuando:
  
- **Una licencia de conferencias de Audio se asigna a ellos o cuando se cambia el proveedor de conferencia de audio a Microsoft.**
    
     Este correo electrónico incluye el identificador de conferencia, el número de teléfono de conferencia de forma predeterminada para las reuniones, la conferencia de audio PIN para el usuario y las instrucciones y el vínculo que se usará el Skype para Online Meeting actualizar herramienta empresarial que se utiliza para actualizar las reuniones existentes para la usuario. Vea [Asignar Skype para licencias de negocio y equipos de Microsoft](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [Microsoft asignar como el proveedor de conferencia de audio](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [los identificadores dinámicos de conferencias de Audio en su organización](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![Skype Empresarial: comprobar licencia](media/audio-conferencing-user-enabled.png)
  
    Puede encontrar más información acerca de las licencias por vean [Skype para profesionales y los equipos de Microsoft complemento licencias](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
- **Cambia el id. de conferencia o número de teléfono de conferencia predeterminado de un usuario.**
    
    Este correo electrónico contiene el identificador de conferencia, número de teléfono de conferencia de forma predeterminada y las instrucciones y vínculos para usar el Skype para Online Meeting actualizar herramienta empresarial que se utiliza para actualizar las reuniones existentes para el usuario. Pero este correo electrónico no incluye los PIN de conferencia de audio del usuario. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
    Este es un ejemplo de este correo electrónico:
    
     ![La información de conferencias de acceso telefónico local ha cambiado.](media/audio-conferencing-info-change.png)
  
- **Se restablece el NIP de un usuario de conferencias de audio.**
    
    Este mensaje contiene el PIN de conferencia de audio del organizador, el identificador de conferencia existente y número de teléfono de conferencia predeterminado para el usuario. Vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin-in-teams.md).
    
  
    Este es un ejemplo de este correo electrónico:
    
     ![El PIN para las conferencias de acceso telefónico local ha cambiado.](media/audio-conferencing-pin-has-changed.png)
  
- **Se ha quitado la licencia de un usuario o cuando se cambia el proveedor de conferencia de audio de Microsoft a otro proveedor o ninguno.**
    
    Esto sucede cuando se quita la licencia de **Conferencias de Audio** de un usuario o cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a un proveedor de conferencia de audio de terceros o al establecer el proveedor en **Ninguno**. Este correo electrónico contiene las instrucciones y la información del usuario usar el Skype para la herramienta de actualización de reunión en línea de negocio para quitar la información específica de conferencias de audio, como el ID predeterminado conferencia teléfono número o conferencia.
    
    Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Este es un ejemplo de este correo electrónico:
    
     ![Las conferencias de acceso telefónico local están desactivadas.](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios incluidos en la dirección de correo electrónico y el nombre para mostrar que se incluye en la información *de* contacto. De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y Mostrar nombre con Windows PowerShell. Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué pasa si no desea que se les envíen correos electrónicos?

Cuando se deshabilitación el envío de correos electrónicos a los usuarios, no se enviará el correo electrónico incluso cuando un usuario obtiene asigna una licencia. En este caso, el identificador de conferencia, predeterminado el número de teléfono de conferencia y, lo que es más importante, su PIN de conferencia de audio no se enviará al usuario. Cuando esto sucede, debe indicar al usuario mediante el envío de un correo electrónico independiente o mediante una llamada a ellos.
  
De forma predeterminada, los correos electrónicos se enviarán a los usuarios, pero si desea impedir que recibir el correo electrónico para conferencias de audio, puede usar Microsoft Teams o Windows PowerShell. 

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de acceso telefónico**.

4. Haga clic en **Guardar**.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
**Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.**
  
Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y Mostrar nombre con Windows PowerShell. 

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  
  
## <a name="related-topics"></a>Temas relacionados

[Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)

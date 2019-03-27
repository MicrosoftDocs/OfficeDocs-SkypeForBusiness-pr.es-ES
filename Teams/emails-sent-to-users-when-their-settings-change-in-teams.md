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
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vea qué información se envía por correo electrónico automáticamente a los usuarios cuando cambia su configuración de las conferencias de acceso telefónico local en Microsoft Teams. '
ms.openlocfilehash: 67e4945095b9ed7e69632741e04b4ac384741feb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883422"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Correos electrónicos que se envían a los usuarios cuando cambia la configuración en Microsoft Teams

Los correos electrónicos se enviarán automáticamente a los usuarios que estén [habilitados para Audioconferencia](set-up-audio-conferencing-in-teams.md) con Microsoft como proveedor de servicios de audioconferencia.

De manera predeterminada, hay cuatro tipos de correos electrónicos que se enviarán a los usuarios habilitados para Audioconferencia. Sin embargo, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivar esta función. Audioconferencia en Office 365 enviará un correo electrónico a los usuarios en las siguientes circunstancias:

- **Se les asigna una licencia de Audioconferencia o cuando está cambiando el proveedor de servicios de audioconferencia a Microsoft.**

     Este correo electrónico incluye el Id. de conferencia, el número de teléfono de conferencia predeterminado para las reuniones, el PIN del usuario para audioconferencias, así como las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype Empresarial Online que se utiliza para actualizar reuniones existentes del usuario. Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md) o [Microsoft asignar como el proveedor de conferencia de audio](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [identificadores dinámicos de Audioconferencia en su organización](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 

    A continuación tiene un ejemplo de este correo electrónico:

     ![Skype Empresarial: comprobar licencia](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Para obtener más información acerca de las licencias, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

- **El Id. de conferencia o el número de teléfono de conferencia predeterminado de un usuario cambia.**

    Este correo electrónico contiene el Id. de conferencia, el número de teléfono de conferencia predeterminado, y las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype Empresarial Online que se usa para actualizar reuniones existentes para el usuario. Sin embargo, en este correo electrónico no se incluye el PIN de audioconferencia del usuario. Vea [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md).

    A continuación tiene un ejemplo de este correo electrónico:

     ![La información de conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **El PIN de audioconferencia de un usuario se ha restablecido.**

    Este correo electrónico contiene el PIN de audioconferencia del organizador, el Id. de conferencia existente y el número de teléfono de la conferencia predeterminado para el usuario. Vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).
    
     A continuación tiene un ejemplo de este correo electrónico:
    
     ![La información de las conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Cuando se quita la licencia de un usuario o cuando el proveedor de servicios de audioconferencia cambia de Microsoft a otro proveedor o a Ninguno.**

    Esto se produce cuando la licencia de **Audioconferencia** se quita de un usuario o cuando el proveedor de servicios de audioconferencia de un usuario cambia de Microsoft a un proveedor de servicios de audioconferencia de terceros, o bien cuando se establece el proveedor en **Ninguno**. Este correo electrónico contiene las instrucciones e información para que el usuario pueda usar la herramienta de actualización de reuniones de Skype Empresarial Online para quitar información específica de las audioconferencias, como el número de teléfono o el Id. de conferencia predeterminados.

    Consulte [Asignar o cancelar licencias para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    A continuación tiene un ejemplo de este correo electrónico:

     ![Las conferencias de acceso telefónico local están desactivadas.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios. De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar el nombre para mostrar con Windows PowerShell. Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué sucede si no desea que se les envíen correos electrónicos?

Cuando se deshabilita el envío de correos electrónicos a los usuarios, estos no se enviarán en ningún momento, ni tan siquiera cuando se asigne una licencia a un usuario. En este caso, no se enviaría al usuario el Id. de conferencia, el número de teléfono de conferencia predeterminado ni, lo más importante, el PIN de audioconferencia. Cuando esto suceda, debe informar al usuario mediante un correo electrónico por separado o llamándole.

De manera predeterminada, los correos electrónicos se envían a los usuarios, pero, si quiere evitar que reciban correos electrónicos para el uso de audioconferencias, puede usar Microsoft Teams o Windows PowerShell. 

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

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

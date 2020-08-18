---
title: Correos electrónicos que se envían a los usuarios cuando cambia la configuración
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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Vea qué información se envía por correo electrónico automáticamente a los usuarios cuando cambia su configuración de las conferencias de acceso telefónico local en Microsoft Teams. '
ms.openlocfilehash: 1cef5f0ea8865820f6f6f83e29fe5f66799b70ae
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788694"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Correos electrónicos que se envían a los usuarios cuando cambia la configuración en Microsoft Teams

Los correos electrónicos se enviarán automáticamente a los usuarios que estén [habilitados para Audioconferencia](set-up-audio-conferencing-in-teams.md) con Microsoft como proveedor de servicios de audioconferencia.

De manera predeterminada, hay cuatro tipos de correos electrónicos que se enviarán a los usuarios habilitados para Audioconferencia. Sin embargo, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivar esta función. Las conferencias de audio en Microsoft 365 u Office 365 enviarán correos electrónicos al correo electrónico de los usuarios cuando:

- **Se les asigna una licencia de Audioconferencia o cuando está cambiando el proveedor de servicios de audioconferencia a Microsoft.**

     Este correo electrónico incluye el Id. de conferencia, el número de teléfono de conferencia predeterminado para las reuniones, el PIN del usuario para audioconferencias, así como las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype Empresarial Online que se utiliza para actualizar reuniones existentes del usuario. Consulte [asignar licencias de complemento de Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) o [asignar Microsoft como proveedor](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)de servicios de audioconferencia.

    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [identificadores dinámicos de Audioconferencia en su organización](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 

    A continuación tiene un ejemplo de este correo electrónico:

     ![Skype Empresarial: comprobar licencia](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Para más información sobre las licencias, vea [licencias complementarias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

- **El Id. de conferencia o el número de teléfono de conferencia predeterminado de un usuario cambia.**

    Este correo electrónico contiene el Id. de conferencia, el número de teléfono de conferencia predeterminado, y las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype Empresarial Online que se usa para actualizar reuniones existentes para el usuario. Sin embargo, en este correo electrónico no se incluye el PIN de audioconferencia del usuario. Vea [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md).

    A continuación tiene un ejemplo de este correo electrónico:

     ![La información de conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **El PIN de audioconferencia de un usuario se ha restablecido.**

    Este correo electrónico contiene el PIN de audioconferencia del organizador, el Id. de conferencia existente y el número de teléfono de la conferencia predeterminado para el usuario. Vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).
    
     A continuación tiene un ejemplo de este correo electrónico:
    
     ![La información de las conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Cuando se quita la licencia de un usuario o cuando el proveedor de servicios de audioconferencia cambia de Microsoft a otro proveedor o a Ninguno.**

    Esto sucede cuando se quita la licencia de **audioconferencia** de un usuario o cuando se configura el proveedor de servicios de audioconferencia como **ninguno**.

    Consulte [asignar o quitar licencias de Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    Este es un ejemplo de este correo electrónico:

     ![Las conferencias de acceso telefónico local están desactivadas.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios. De forma predeterminada, el remitente de los mensajes de correo electrónico será de Microsoft 365 u Office 365, pero puede cambiar el nombre para mostrar con Windows PowerShell. Para obtener más información, vea la [referencia de Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué pasa si no desea que se les envíen correos electrónicos?

Cuando deshabilite el envío de correos electrónicos a los usuarios, el correo electrónico no se enviará aunque se asigne una licencia a un usuario. En este caso, el identificador de la Conferencia, el número de teléfono de conferencia predeterminado y, lo que es más importante, su PIN de audioconferencia no se enviará al usuario. Cuando esto sucede, debe decir al usuario enviándoles un mensaje de correo electrónico o llamándolos.

De forma predeterminada, los correos electrónicos se enviarán a los usuarios, pero si quiere evitar que reciban correo electrónico para las conferencias de audio, puede usar Microsoft Teams o Windows PowerShell. 

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **puentes de conferencia** , haga clic en **configuración del puente**. 

3. En el panel **configuración de puente** , habilite o deshabilite **el envío automático de correos electrónicos a los usuarios si cambia la configuración de acceso telefónico local**.

4. Haga clic en **Guardar **.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

Para obtener más información, vea la [referencia de Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .


## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

De forma predeterminada, el remitente de los mensajes de correo electrónico será de Microsoft 365 u Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell. 

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer. To get started with Windows PowerShell, see these topics:

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="related-topics"></a>Temas relacionados

[Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)

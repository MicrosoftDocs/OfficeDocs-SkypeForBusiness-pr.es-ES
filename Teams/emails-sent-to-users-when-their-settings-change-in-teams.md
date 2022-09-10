---
title: Correos electrónicos que se envían a los usuarios cuando cambia la configuración
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Obtenga información sobre qué información se envía automáticamente a los usuarios por correo electrónico cuando cambia la configuración de las conferencias de acceso telefónico local en Microsoft Teams. '
ms.openlocfilehash: b2ebb07562300a02058f3bfeaad103347299ba0c
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642141"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Correos electrónicos que se envían a los usuarios cuando cambia la configuración en Microsoft Teams

Los correos electrónicos se enviarán automáticamente a los usuarios [habilitados para Audioconferencia](set-up-audio-conferencing-in-teams.md) con Microsoft como proveedor de servicios de audioconferencia.

De forma predeterminada, hay cuatro tipos de correo electrónico que se enviarán a los usuarios habilitados para Audioconferencia. Pero, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivarlo. Audioconferencia en Microsoft 365 o Office 365 enviará correo electrónico a los usuarios cuando:

- **Se les asigna una licencia de Audioconferencia o cuando cambia el proveedor de servicios de audioconferencia a Microsoft.**

     Este correo electrónico incluye el id. de conferencia, el número de teléfono de conferencia predeterminado para las reuniones, el PIN de audioconferencia del usuario y las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Teams que se usa para actualizar las reuniones existentes para el usuario. Consulte [Asignar licencias de complementos de Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Consulte el artículo [Ver y restablecer un id. de conferencia asignado a un usuario en Microsoft Teams](see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams.md) para obtener más información.

    Este es un ejemplo de este correo electrónico:

     ![Teams Comprobar licencia.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Para obtener más información sobre las licencias, consulte [Licencias complementarias de Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

- **Cambia el id. de conferencia o número de teléfono de conferencia predeterminado de un usuario.**

    Este correo electrónico contiene el id. de conferencia, el número de teléfono de conferencia predeterminado y las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Teams que se usa para actualizar las reuniones existentes para el usuario. Pero este correo electrónico no incluye el PIN de audioconferencia del usuario. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

    Este es un ejemplo de este correo electrónico:

     ![La información de conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **Se restablece el PIN de audioconferencia de un usuario.**

    Este correo electrónico contiene el PIN de audioconferencia del organizador, el id. de conferencia existente y el número de teléfono de conferencia predeterminado para el usuario. Vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).

     Este es un ejemplo de este correo electrónico:

     ![El PIN para las conferencias de acceso telefónico local ha cambiado.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Se quita la licencia de un usuario o cuando el proveedor de servicios de audioconferencia cambia de Microsoft a otro proveedor o a Ninguno.**

    Esto ocurre cuando se quita la licencia de **Audioconferencia** de un usuario o al establecer el proveedor de servicios de audioconferencia en **Ninguno**.

    Consulte [Asignar o quitar licencias de Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    Este es un ejemplo de este correo electrónico:

     ![Las conferencias de acceso telefónico local están desactivadas.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios. De forma predeterminada, el remitente de los correos electrónicos será de Microsoft 365 o Office 365, pero puede cambiar el nombre para mostrar con Windows PowerShell. Consulte la [referencia de Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué pasa si no desea que se les envíen correos electrónicos?

Al deshabilitar el envío de correos electrónicos a los usuarios, el correo electrónico no se enviará incluso cuando se asigne una licencia a un usuario. En este caso, el Id. de conferencia, el número de teléfono de conferencia predeterminado y, lo más importante, su PIN de audioconferencia no se enviarán al usuario. Cuando esto ocurre, debe avisar al usuario enviándole un correo electrónico independiente o llamándole.

De forma predeterminada, los correos electrónicos se enviarán a los usuarios, pero si desea evitar que reciban correos electrónicos para audioconferencia, puede usar Microsoft Teams o Windows PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.

2. En la parte superior de la página **Puentes de conferencia** , haga clic en **Configuración del puente**.

3. En el panel **Configuración del puente** , habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si cambia la configuración de acceso telefónico local**.

4. Haga clic en **Guardar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Usar Windows PowerShell

También puede usar el módulo Microsoft Teams PowerShell y ejecutar:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.

Consulte la [referencia de Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

De forma predeterminada, el remitente de los correos electrónicos será de Microsoft 365 o Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell.

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Las mejores formas de administrar Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Temas relacionados

[Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)

---
title: Ver, cambiar y restablecer un identificador de conferencia asignado a un usuario en Skype empresarial online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Obtenga información sobre cómo asignar un identificador de conferencia a un usuario en Skype empresarial online y cuáles deben ser los parámetros de IDs de conferencia. '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643610"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Ver y restablecer un Id. de conferencia asignado a un usuario en Skype for Business Online

> [!Note]
> Para obtener información acerca de los identificadores de conferencia de usuario en Microsoft Teams, consulte [ver y restablecer un ID de conferencia asignado a un usuario en Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

Un identificador de conferencia se asigna automáticamente a un usuario de Skype empresarial cuando está configurado para conferencias de audio en Microsoft 365 u Office 365 y usa Microsoft como proveedor de servicios de audioconferencia. El identificador de conferencia asignado se envía en la invitación a la reunión cuando la reunión está programada. A cada una de las reuniones que una programación de usuario obtiene se les asigna un identificador de conferencia único.

Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.

An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Ver y restablecer los identificadores de conferencia

### <a name="to-view-the-conference-id"></a>Para ver el identificador de conferencia

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

Puede ver el Id. de conferencia y enviárselo a los usuarios.

1. Inicie sesión con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial**.

3. En el **centro de administración de Skype for Business**> **Audioconferencias** > **Usuarios**, seleccione el usuario que necesita el Id. de conferencia.

4. En la página Acción, busque en **Id. de conferencia**.

    > [!TIP]
    > Puede enviar toda la información de la Conferencia al usuario en un correo electrónico que incluya el identificador de la Conferencia y los números de teléfono de audio haciendo clic en el vínculo **enviar información de conferencia por correo electrónico** después de seleccionar al usuario en la página **usuarios** .

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

You can use Windows PowerShell to view the conference ID for a user. To do so, run:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Para obtener más información sobre el cmdlet [, vea Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) .


### <a name="to-reset-the-conference-id"></a>Para restablecer el identificador de conferencia

Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

1. Inicie sesión con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial**.

3. En el **centro de administración de Skype empresarial** >  , los usuarios de la**Conferencia de audio**  >  **Users**, en el panel de acciones, en **ID de conferencia**, haga clic en **restablecer**.

4. En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un ID de conferencia y un mensaje de correo electrónico con el nuevo identificador de conferencia.

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

Puede restablecer el id. de conferencia de un usuario mediante Windows PowerShell. Para ello, ejecute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

   > [!IMPORTANT]
   >  Una vez que se crea un nuevo identificador de conferencia o se restablece uno, la persona que llama no puede usar el antiguo identificador de conferencia. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. Para ver cómo descargar, instalar y ejecutar la herramienta, consulte la herramienta [de actualización de reuniones para Skype empresarial y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype empresarial online, herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)y [Skype empresarial online, herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079).

- Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).

- El identificador de conferencia debe cumplir la longitud en dígitos establecidos en el puente de audioconferencia. No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.

- El identificador de conferencia de todos los usuarios de la audioconferencia será de 9 dígitos de forma predeterminada, y no se podrá cambiar el número de dígitos.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype empresarial online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que hacer varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencia en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)


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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo asignar un identificador de conferencia a un usuario en Skype empresarial online y cuáles deben ser los parámetros de IDs de conferencia. '
ms.openlocfilehash: 65a27315898ec0673d68842e7d5249cbad2d7298
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2019
ms.locfileid: "35793008"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Ver y restablecer un Id. de conferencia asignado a un usuario en Skype for Business Online

> [!Note]
> Para obtener información acerca de los identificadores de conferencia de usuario en Microsoft Teams, consulte [ver y restablecer un ID de conferencia asignado a un usuario en Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.

Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.

An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Ver y restablecer los identificadores de conferencia

### <a name="to-view-the-conference-id"></a>Para ver el identificador de conferencia

![Un icono que muestra el logotipo](../images/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**

Puede ver el Id. de conferencia y enviárselo a los usuarios.

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial**.

3. En el **centro de administración de Skype for Business**> **Audioconferencias** > **Usuarios**, seleccione el usuario que necesita el Id. de conferencia.

4. En la página Acción, busque en **Id. de conferencia**.

    > [!TIP]
    > Puede enviar toda la información de la Conferencia al usuario en un correo electrónico que incluya el identificador de la Conferencia y los números de teléfono de audio haciendo clic en el vínculo **enviar información de conferencia por correo electrónico** después de seleccionar al usuario en la página **usuarios** .

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

You can use Windows PowerShell to view the conference ID for a user. To do so, run:

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>Para restablecer el identificador de conferencia

Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.

![Un icono que muestra el logotipo](../images/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial**.

3. En el **Centro**> de administración de Skype empresarial,**los usuarios**de la**Conferencia** > de audio, en el panel de acciones, en **ID de conferencia**, haga clic en **restablecer**.

4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

   > [!IMPORTANT]
   >  After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

- Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).

- The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.

- El identificador de conferencia de todos los usuarios de la audioconferencia será de 7 dígitos de forma predeterminada, y no se podrá cambiar el número de dígitos.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Learn about these advantages in the following topics:

  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)


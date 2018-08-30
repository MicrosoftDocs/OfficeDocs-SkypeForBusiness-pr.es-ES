---
title: Ver, modificar y restablecer un Id. de conferencia asignado a un usuario en Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a asignar un Id. de conferencia a un usuario de Skype for Business Online y cuáles deben ser los parámetros de los identificadores de conferencia. '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252312"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Ver y restablecer un Id. de conferencia asignado a un usuario en Skype for Business Online

> [!Note]
> Para obtener información acerca de los identificadores de conferencia de usuario en equipos de Microsoft, consulte [Ver y restablecer un Id. de conferencia asignado a un usuario de Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

Se asigna automáticamente un Id. de conferencia a un usuario de Skype for Business cuando está configurado para audioconferencias en Office 365 y utiliza Microsoft como proveedor de audioconferencias. El Id. de conferencia asignado se envía en la invitación a la reunión cuando se programa esta última. Se asignará un Id. de conferencia único a cada reunión que programe un usuario.

Aunque se creará y asignará a un usuario automáticamente un Id. de conferencia estático, en ocasiones es posible que un usuario no desee utilizarlo y se desee establecerlo en un número determinado, o bien que los usuarios hayan olvidado o perdido su Id. de conferencia. Puede utilizar el **centro de administración de Skype for Business** y Windows PowerShell para ver, cambiar y restablecer su Id. de conferencia.

Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN. Para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias, [haga clic aquí](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Ver y restablecer los identificadores de conferencia

### <a name="to-view-the-conference-id"></a>Para ver el Id. de conferencia

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usando el centro de administración de Skype for Business**

Puede ver el Id. de conferencia y enviárselo a los usuarios.

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya a **Centro de administración de Office 365** > **Skype for Business**.

3. En el **centro de administración de Skype for Business**> **Audioconferencias** > **Usuarios**, seleccione el usuario que necesita el Id. de conferencia.

4. En la página Acción, busque en **Id. de conferencia**.

    > [!TIP]
    > Puede enviar toda la información de conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de audio haciendo clic en el enlace **Enviar información de la conferencia por correo electrónico** después de seleccionar el usuario en la página **Usuarios** .

**Usar Windows PowerShell**

Puede usar Windows PowerShell para ver el Id. de conferencia para un usuario. Para ello, ejecute:

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>Para restablecer el Id. de conferencia

Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usando el centro de administración de Skype for Business**

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya a **Centro de administración de Office 365** > **Skype for Business**.

3. En el **centro de administración de Skype for Business**> **Audioconferencias** > **Usuarios**, en el panel Acción en **Id. de conferencia**, haga clic en **Restablecer**.

4. En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un Id. de conferencia y se enviará un correo electrónico al usuario con el nuevo Id. de conferencia.

**Usar Windows PowerShell**

Puede restablecer el Id. de conferencia de un usuario mediante Windows PowerShell. Para ello, ejecute:

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?

   > [!IMPORTANT]
   >  Tras la creación de un nuevo Id. de conferencia o tras restablecer uno, las personas que llaman ya no pueden utilizar el Id. de conferencia anterior. Debe notificar a los usuarios para que reprogramen sus invitaciones de reunión existentes para asegurarse de que se agrega a las invitaciones el nuevo Id. de conferencia. Los usuarios pueden utilizar la herramienta de migración de Skype for Business para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar la herramienta, vea: [Herramienta de actualización de reunión de Skype for Business y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, herramienta de migración de reunión (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047) y [Skype for Business Online, herramienta de migración de reunión (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

- Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).

- El Id. de conferencia tiene que cumplir con los requisitos de longitud de dígitos configurados en el puente de conferencia de acceso telefónico local. No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.

- El Id. de conferencia de todos los usuarios de conferencia de audioconferencia será de siete dígitos de manera predeterminada, y el número de dígitos no se puede cambiar.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)


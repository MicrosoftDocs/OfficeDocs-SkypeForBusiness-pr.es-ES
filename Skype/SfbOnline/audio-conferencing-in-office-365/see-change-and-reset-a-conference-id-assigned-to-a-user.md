---
title: Ver, cambiar y restablecer un id. de conferencia asignado a un usuario en Skype Empresarial Online
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
description: 'Obtenga información sobre cómo asignar un id. de conferencia a un usuario en Skype Empresarial Online y cuáles deben ser los parámetros de id. de conferencia. '
ms.openlocfilehash: 79c83999fdf9a9736dfe1ee425337edf938d3375
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110016"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Ver y restablecer un Id. de conferencia asignado a un usuario en Skype for Business Online

> [!Note]
> Para obtener información sobre los identificadores de conferencia de usuario en Microsoft Teams, vea Ver y restablecer un id. de conferencia asignado a un usuario [en Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

Un id. de conferencia se asigna automáticamente a un usuario de Skype Empresarial cuando se configura para conferencias de audio en Microsoft 365 u Office 365 y usa Microsoft como proveedor de audioconferencias. El id. de conferencia asignado se envía en la invitación a la reunión cuando se programa la reunión. Se asignará un Id. de conferencia único a cada reunión que programe un usuario.

Aunque un id. de conferencia se creará automáticamente y se asignará a un usuario, es posible que haya ocasiones en las que un usuario no quiera usar este y quiera establecerlo en un número determinado, o cuando los usuarios no puedan recordar o haber perdido su id. de conferencia. Puede usar el Centro **de administración de Skype Empresarial** y Windows PowerShell para ver, cambiar y restablecer su id. de conferencia.

Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN. Para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias, [haga clic aquí](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Ver y restablecer los identificadores de conferencia

### <a name="to-view-the-conference-id"></a>Para ver el id. de conferencia

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

Puede ver el Id. de conferencia y enviárselo a los usuarios.

1. Inicie sesión con su cuenta de trabajo o escuela.

2. Vaya al Centro de administración > **Skype Empresarial.**

3. En el **centro de administración de Skype for Business**> **Audioconferencias** > **Usuarios**, seleccione el usuario que necesita el Id. de conferencia.

4. En la página Acción, busque en **Id. de conferencia**.

    > [!TIP]
    > Puede enviar toda la información de conferencia al usuario en un correo electrónico que  incluya el id. de conferencia y  los números de teléfono de audio haciendo clic en el vínculo Enviar información de conferencia por correo electrónico después de seleccionar el usuario en la página Usuarios.

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

Puede usar Windows PowerShell para ver el Id. de conferencia para un usuario. Para ello, ejecute:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Vea [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) para obtener más información sobre el cmdlet.


### <a name="to-reset-the-conference-id"></a>Para restablecer el id. de conferencia

Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.

![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

1. Inicie sesión con su cuenta de trabajo o escuela.

2. Vaya al Centro de administración > **Skype Empresarial.**

3. En el **Centro de administración de Skype Empresarial** Usuarios de >  **audioconferencias**, en el panel de acciones en Id. de  >  conferencia, haga clic en **Restablecer**. 

4. En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia.

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

Puede restablecer el id. de conferencia de un usuario mediante Windows PowerShell. Para ello, ejecute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

   > [!IMPORTANT]
   >  Después de crear un id. de conferencia nuevo o restablecer uno, los autores de la llamada no pueden usar el id. de conferencia antiguo. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. Para ver cómo descargar, instalar y ejecutar la herramienta, vea: Herramienta de actualización de reuniones para Skype Empresarial y [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype Empresarial Online, Herramienta de migración de reuniones [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)y Skype Empresarial Online, Herramienta de migración de reuniones [(32 bits).](https://www.microsoft.com/download/details.aspx?id=54079)

- Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).

- El id. de conferencia debe cumplir la longitud de los dígitos establecidos en el puente de audioconferencia. No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.

- El id. de conferencia de todos los usuarios de audioconferencia será de 9 dígitos de forma predeterminada y el número de dígitos no se puede cambiar.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Por qué necesita usar Microsoft 365 u Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencias en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
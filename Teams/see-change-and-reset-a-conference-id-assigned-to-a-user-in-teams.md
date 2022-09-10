---
title: Ver, cambiar y restablecer el id. de conferencia de un usuario
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
- seo-marvel-apr2020
description: Obtenga información sobre cómo asignar un id. de conferencia a un usuario en Microsoft Teams y cuáles deben ser los parámetros de los identificadores de conferencia.
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642121"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Ver y restablecer un id. de conferencia asignado a un usuario en Microsoft Teams

Se asigna automáticamente un id. de conferencia a un usuario de Microsoft Teams cuando se configura para audioconferencia en Microsoft 365 o Office 365 y se usa Microsoft como el proveedor de servicios de audioconferencia. El id. de conferencia asignado se envía en la invitación a la reunión cuando la reunión está programada. Se asignará un Id. de conferencia único a cada reunión que programe un usuario.
  
Aunque se creará y asignará automáticamente un id. de conferencia a un usuario, puede haber ocasiones en las que un usuario no desee usar este y desee establecerlo en un número determinado, o cuando los usuarios no puedan recordar o hayan perdido su id. de conferencia. Puede usar el Centro de administración de Microsoft Teams o Windows PowerShell para ver, cambiar y restablecer su id. de conferencia.
  
Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN. Vea [Restablecer un id. de conferencia de un usuario en Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Ver y restablecer los identificadores de conferencia

### <a name="to-view-the-conference-id"></a>Para ver el id. de conferencia

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>Ver el id. de conferencia con el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y, a continuación, seleccione el usuario en la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Audioconferencia**, busque en **Id. de conferencia**.

    > [!TIP]
    > Puede enviar toda la información de conferencia al usuario en un correo electrónico que incluya el id. de conferencia y los números de teléfono de audio haciendo clic en el vínculo **Enviar información de conferencia por correo electrónico** .
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>Ver el id. de conferencia con Windows PowerShell

Consulte la [referencia de Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.

### <a name="to-reset-the-conference-id"></a>Para restablecer el id. de conferencia

Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>Restablecer el id. de conferencia con el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y, a continuación, seleccione el usuario en la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Audioconferencia**, haga clic en **Restablecer id**. de conferencia.

4. En la ventana **Restablecer id. de conferencia** , haga clic en **Restablecer**. Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>Restablecer el id. de conferencia con Windows PowerShell

Consulte la [referencia de Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

> [!IMPORTANT]
> Después de crear o restablecer un id. de conferencia, los autores de llamadas no podrán usar el id. de conferencia anterior. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.

- El id. de conferencia debe cumplir la longitud en dígitos establecida en el puente de audioconferencia. No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Microsoft 365 para Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)

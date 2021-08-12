---
title: Establecer Microsoft Teams interfaz de usuario de dispositivos Android
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo configurar la interfaz de usuario en Teams dispositivos Android.
ms.openlocfilehash: f743a0f51015e7bd8fdabd41d120a187774c3370
ms.sourcegitcommit: f3c2559a89e1c4b3514e102cf94c38a697b4bc57
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2021
ms.locfileid: "53725706"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Establecer Microsoft Teams interfaz de usuario de dispositivos Android

Microsoft Teams Los dispositivos Android pueden mostrar una interfaz de usuario específica en función del tipo de licencia asignada a la cuenta que ha iniciado sesión. Puede invalidar este comportamiento y controlar qué interfaz se muestra. En este artículo se detalla cómo se elige la interfaz de usuario predeterminada y cómo puede cambiar la interfaz con una directiva de Powershell.

Hay tres tipos de interfaces de usuario en Teams dispositivos Android:

1. Usuario
2. Área común
3. Reunión

Si [](/microsoftteams/user-access) asigna una licencia de usuario a una cuenta, como una licencia E3 o una licencia E5, el dispositivo Teams mostrará la interfaz de usuario final predeterminada que está totalmente característica para la mayoría de los escenarios de usuario. Sin embargo, si un dispositivo está realizando una función específica, como un teléfono de área común o una sala de reuniones, hay interfaces de usuario específicas para estos usos.

Las tres imágenes siguientes muestran cómo cambia la interfaz de usuario en función de la licencia asignada a la cuenta de usuario. En la primera imagen, se asigna a la cuenta de usuario una licencia E5. Se trata de una licencia de usuario, por lo que el dispositivo muestra la interfaz de usuario final predeterminada:

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="Interfaz de modo de usuario":::

En esta imagen, se ha asignado a la cuenta de usuario una [licencia de teléfono de área común.](/microsoftteams/set-up-common-area-phones) Los teléfonos de área común se usan principalmente para realizar y recibir llamadas telefónicas. Como tal, el teclado de marcado se muestra en la pantalla:

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="Interfaz de teléfono de área común":::

Por último, esta imagen muestra una cuenta de usuario con una [Salas de Microsoft Teams licencia estándar asignada.](/MicrosoftTeams/rooms/rooms-licensing) Salas de Teams licencias están pensadas para usarse en salas de reuniones o espacios compartidos, por lo que la interfaz de usuario cambia para que sea más fácil unirse a una reunión mostrando la vista calendario:

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="Interfaz de reunión":::

> [!NOTE]
> Cambiar la interfaz de usuario no afecta a su capacidad para usar otras características con licencia. Por ejemplo, aunque la vista predeterminada de la licencia salas de grupo es la vista calendario, aún puede realizar y recibir llamadas telefónicas de red telefónica de cambio público (RTC) si la cuenta está correctamente licenciada y configurada.

> [!IMPORTANT]
> Hay otros elementos de la interfaz que cambian. Por ejemplo, para evitar que los usuarios finales cierren sesión en un teléfono de área común o en un dispositivo de la sala de reuniones, la opción "Cerrar sesión" en estos dispositivos se mueve a una parte del menú de configuración que requiere permisos de administrador para acceder.

## <a name="override-automatic-user-interface-detection"></a>Invalidar la detección automática de la interfaz de usuario

En algunos casos, es posible que elija asignar una licencia a una cuenta que no coincida con su uso previsto. Por ejemplo, puede asignar una licencia de usuario a una cuenta destinada a iniciar sesión en Salas de Teams android. De forma predeterminada, vería la interfaz de usuario final en lugar de la interfaz de la sala de reuniones. Para invalidar la interfaz predeterminada, cree una nueva Teams [ip Teléfono directiva](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) y apliquen a esa cuenta.

> [!NOTE]
> La licencia asignada a la cuenta de usuario debe tener al menos los mismos derechos de licencia que la interfaz de usuario deseada. La licencia de Teléfono área común solo permite la interfaz de usuario del teléfono de área común. La licencia de la sala de reuniones permite las interfaces de usuario de la sala de reuniones y del área común del teléfono. Una licencia E3 o E5 admite todos los modos de inicio de sesión.

A continuación se muestra un ejemplo de cómo invalidar la detección automática de licencias. En este ejemplo, suponga que se ha asignado una licencia de E3 a una cuenta de recurso de sala de conf-adams@contoso.com llamada conf-adams@contoso.com. Cuando esta cuenta haya iniciado sesión, quiere que los usuarios vean la interfaz de usuario de la sala de reuniones.

### <a name="create-a-new-policy-and-assign-to-user"></a>Crear una nueva directiva y asignarla al usuario

1. Inicie una sesión Windows PowerShell sesión remota y conéctese a Microsoft Teams mediante el siguiente cmdlet:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Cree una nueva Teams ip Teléfono directiva y establezca el modo de inicio de sesión en "MeetingSignIn":

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Ahora puede asignar esta nueva directiva a la cuenta de recursos de la sala de reuniones:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Después de conceder la directiva a la cuenta de recursos de la sala de reuniones, tendrá que esperar a que se replique la asignación de directiva. También tendrá que cerrar sesión en el dispositivo e iniciar sesión de nuevo.

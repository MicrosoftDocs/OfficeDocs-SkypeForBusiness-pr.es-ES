---
title: Establecer la interfaz de usuario de dispositivos Android de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
description: Obtenga información sobre cómo configurar la interfaz de usuario en dispositivos Android de Teams.
ms.openlocfilehash: 859c1d9d0f7a946f37b53ad81dc2a0637bb26621
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269325"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Establecer la interfaz de usuario de dispositivos Android de Microsoft Teams

Los dispositivos Android de Microsoft Teams pueden mostrar una interfaz de usuario específica en función del tipo de licencia asignada a la cuenta con la que se ha iniciado sesión. Puede invalidar este comportamiento y controlar qué interfaz se muestra. En este artículo se detalla cómo se elige la interfaz de usuario predeterminada y cómo se puede cambiar la interfaz mediante una directiva de Powershell.

Existen tres tipos de interfaces de usuario en dispositivos Android de Teams:

1. Usuario
2. Área común
3. Reunión

Si [asigna una licencia de usuario](/microsoftteams/user-access) a una cuenta, como una licencia E3 o E5, el dispositivo de Teams mostrará la interfaz de usuario final predeterminada que está totalmente destacada en la mayoría de los escenarios de usuario. Sin embargo, si un dispositivo está realizando una función específica, como un teléfono de área común o una sala de reuniones, hay interfaces de usuario específicas para estos usos.

Las tres imágenes siguientes muestran cómo cambia la interfaz de usuario en función de la licencia asignada a la cuenta de usuario. 

## <a name="end-user-interface"></a>Interfaz de usuario final 

A la cuenta de usuario se le asigna una licencia E5. Esta es una licencia de usuario, así que el dispositivo muestra la interfaz de usuario final predeterminada:

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Interfaz de modo de usuario.":::

## <a name="common-area-interface"></a>Interfaz de área común

En esta imagen, a la cuenta de usuario se le ha asignado una [licencia de Teléfono de área común](/microsoftteams/set-up-common-area-phones). Los teléfonos de área comunes se usan principalmente para realizar y recibir llamadas telefónicas. Por lo tanto, el teclado de marcado se muestra en la pantalla:

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Interfaz de teléfono de área común.":::

## <a name="meeting-interface"></a>Interfaz de reunión

Esta imagen muestra una cuenta de usuario con una [licencia de Salas de Microsoft Teams Estándar](/MicrosoftTeams/rooms/rooms-licensing) asignada. Salas de Teams licencias están diseñadas para usarse en salas de reuniones o espacios compartidos, por lo que la interfaz de usuario cambia para que sea más fácil unirse a una reunión mostrando la vista calendario:

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Interfaz de reunión.":::

> [!NOTE]
> El cambio de la interfaz de usuario no afecta a la capacidad de usar otras características con licencia. Por ejemplo, aunque la vista predeterminada de la licencia de salas de equipo sea la vista de calendario, todavía puede realizar y recibir llamadas de teléfono de la red telefónica conmutada (RTC) si la cuenta está correctamente licenciada y configurada.

> [!IMPORTANT]
> Hay otros elementos de la interfaz que cambian. Por ejemplo, para evitar que los usuarios finales cierren sesión en un teléfono de área común o un dispositivo de sala de reuniones, la opción "Cerrar sesión" de estos dispositivos se mueve a una parte del menú de configuración que requiere permisos de administrador para acceder.

## <a name="override-automatic-user-interface-detection"></a>Invalidar la detección automática de la interfaz de usuario

En algunos casos, puede optar por asignar una licencia a una cuenta que no coincida con su uso previsto. Por ejemplo, puede asignar una licencia de usuario a una cuenta destinada a iniciar sesión en Salas de Teams en Android. De forma predeterminada, vería la interfaz de usuario final en lugar de la interfaz de la sala de reuniones. Para invalidar la interfaz predeterminada, cree una nueva [directiva de teléfono IP de Teams](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) y aplíctela a esa cuenta.

> [!NOTE]
> La licencia asignada a la cuenta de usuario debe tener al menos los mismos derechos de licencia que la interfaz de usuario deseada. La licencia del teléfono del área común sólo permite la interfaz de usuario del teléfono del área común. La licencia de la sala de reuniones permite las interfaces de usuario del teléfono de la sala de reuniones y del área común. Una licencia E3 o E5 admite todos los modos de inicio de sesión.

El siguiente es un ejemplo de cómo invalidar la detección automática de licencias. En este ejemplo, supongamos que se ha asignado una licencia E3 a una cuenta de recursos de sala de reuniones denominada conf-adams@contoso.com. Cuando esta cuenta haya iniciado sesión, quiere que los usuarios vean la interfaz de usuario de la sala de reuniones.

### <a name="create-a-new-policy-and-assign-to-user"></a>Crear una nueva directiva y asignarla al usuario

1. Inicie una sesión de Windows PowerShell remota y conéctese a Microsoft Teams con el siguiente cmdlet:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Cree una nueva directiva de teléfono IP de Teams y establezca el modo de inicio de sesión en "MeetingSignIn":

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Ahora puede asignar esta nueva directiva a la cuenta de recursos de la sala de reuniones:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Después de conceder la directiva a la cuenta de recursos de la sala de reuniones, tendrá que esperar a que la asignación de directiva se replique. También tendrás que cerrar sesión en el dispositivo y volver a iniciarla.

## <a name="impact-on-microsoft-teams-admin-center"></a>Impacto en el Centro de administración de Microsoft Teams

El Centro de administración de Microsoft Teams le permite administrar dispositivos de Microsoft Teams. Para obtener más información sobre la administración de dispositivos con el Centro de administración de Teams, vea [Administrar los dispositivos en Microsoft Teams](device-management.md).


El Centro de administración de Teams ofrece la posibilidad de administrar los teléfonos de Teams. Los teléfonos se filtran en una de las tres pestañas en función de su función: teléfonos de usuario, teléfonos de área común y teléfonos de conferencia. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Encabezado Teléfonos en el Centro de administración de Teams.":::

Al igual que con la detección de la interfaz de usuario, los teléfonos de Teams se categorizan en función de la licencia asignada a la cuenta que inicia sesión en el teléfono. Por ejemplo, si una cuenta a la que se asigna una licencia de teléfono de área común inicia sesión en un teléfono, ese teléfono se mostrará tanto en la sección predeterminada **Todos los teléfonos** como en la sección **Teléfonos del área común** .

Si quiere que un teléfono aparezca en una sección diferente, puede asignar una licencia diferente al teléfono o crear y asignar una directiva de teléfono IP de Teams como [se describió anteriormente](#override-automatic-user-interface-detection).

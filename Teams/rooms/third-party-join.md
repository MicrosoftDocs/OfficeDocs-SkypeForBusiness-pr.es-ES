---
title: Habilitar dispositivos de salas de Teams para unirse a reuniones de terceros
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este artículo se describe cómo configurar su organización y los dispositivos de Salas de Teams para que admitan la unión a reuniones de terceros a Cisco WebEx y Zoom.
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682389"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Habilitar dispositivos de salas de Teams para unirse a reuniones de terceros

Los dispositivos de salas de Microsoft Teams admiten una experiencia de un solo toque para unirse a reuniones en línea de terceros, lo que también se conoce como unión directa como invitado. Cuando esté habilitado, puede usar un dispositivo de salas de Teams para unirse a reuniones hospedadas en Cisco WebEx y Zoom de la forma más sencilla posible para unirse a reuniones hospedadas en Microsoft Teams.

Antes de unirse a reuniones de terceros desde un dispositivo de Salas de Teams, debe hacer lo siguiente:

1. Configure el buzón de sala de Exchange Online del dispositivo salas de Teams para procesar invitaciones a reuniones de terceros.
2. Asegúrese de que su organización no tenga directivas que le impidan conectarse a servicios de reuniones de terceros.
3. Configure sus dispositivos de Salas de Teams para permitir reuniones de terceros.

En las secciones siguientes se muestra cómo realizar cada uno de estos pasos.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Paso 1: Permitir el procesamiento de las invitaciones del calendario para las reuniones de terceros

Lo primero que debe hacer para habilitar una experiencia de unión con un solo toque desde un dispositivo de salas de grupo es establecer las reglas de procesamiento del calendario del buzón de sala de Exchange Online del dispositivo. El buzón de sala necesita permitir reuniones externas y mantener el cuerpo y el asunto del mensaje para que pueda ver la dirección URL necesaria para unirse a la reunión de terceros. Para establecer estas opciones de buzón de sala con el cmdlet [Set-CalendarProcessing,](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) haga lo siguiente:

1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea Conectarse a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) con autenticación básica o Conectarse a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)usando multifactor de autenticación, dependiendo de su método de autenticación.

2. Para obtener el nombre principal de usuario (UPN) del buzón de sala, ejecute el siguiente comando para obtener el nombre principal de usuario (UPN) del buzón de sala:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Busque el nombre del buzón de sala asociado a su dispositivo de salas de Teams y tome nota de su UPN.

4. Cuando encuentre el UPN del buzón de sala, ejecute el siguiente comando. Cambie `<UserPrincipalName>` por el UPN del buzón de sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Obtenga más información [sobre PowerShell de Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Paso 2: Configurar la Protección contra amenazas de Office 365 y la reescritura de vínculos

Para habilitar la experiencia de unirse con un solo toque, la información del vínculo para unirse a la reunión de terceros debe estar presente y ser legible en la invitación a la reunión. Si su organización usa la característica vínculos seguros de protección contra amenazas avanzada de [Office 365,](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) o si usa una solución de terceros que analiza todas las direcciones URL entrantes y salientes en busca de amenazas, puede cambiar las direcciones URL de unión a la reunión y hacer que la reunión no se pueda reconocer en el dispositivo de Teams Rooms. Para asegurarse de que esto no ocurre, tiene que agregar las direcciones URL del servicio de reuniones de terceros a la lista de vínculos seguros de ATP "no se reescriba" ni a la lista de excepciones de reescritura de URL de terceros.

Para agregar direcciones URL de servicio de reuniones de terceros a la lista de vínculos seguros de ATP "no reescribir", siga los pasos de Configurar una lista personalizada de url de no reescritura con vínculos seguros de [ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) Si usa una solución de terceros, consulte las instrucciones de esa solución para agregar direcciones URL a su lista de excepciones de reescritura de URL.

Estas son algunas entradas de ejemplo que puede que necesite agregar a la lista de vínculos seguros de ATP "no reescribir" o a la lista de excepciones de reescritura de URL de terceros:

- **Cisco WebEx**`*.webex.com*`
- **Zoom,** `*.zoom.us*` `*.zoom.com*` , `*.zoomgov.com*`

Para obtener una lista completa de direcciones URL para agregar a la lista de vínculos seguros de ATP "no reescribir" o la lista de excepciones de reescritura de URL de terceros, póngase en contacto con el proveedor de servicios de reuniones de terceros del que desea aceptar invitaciones de reunión. 

> [!CAUTION]
> Agregue solo las direcciones URL en las que confía a la lista de vínculos seguros de ATP "no reescribir" ni a la lista de excepciones de reescritura de URL de terceros.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Paso 3: Habilitar reuniones de terceros en el dispositivo

El último paso que debe realizar es permitir que cada dispositivo de Salas de Teams se una a reuniones de terceros. Las reuniones de terceros requieren un nombre de usuario y una dirección de correo electrónico para unirse a ellas. Si el nombre de usuario y la dirección de correo electrónico que necesita usar son diferentes del buzón de sala del dispositivo, deberá agregarlos al dispositivo. Puede hacerlo en la configuración del dispositivo o en el archivo de configuración XML.

### <a name="use-device-settings"></a>Usar la configuración del dispositivo

Para configurar el dispositivo Salas de Teams con su pantalla táctil, haga lo siguiente:

1. En el dispositivo Salas de Microsoft Teams, seleccione **Más...**.
2. Seleccione **Configuración y,** a continuación, escriba el nombre de usuario y la contraseña del administrador del dispositivo.
3. Vaya a la **pestaña Reuniones** y seleccione **Cisco WebEx,** **Zoom** o ambos.
4. Si quiere unirse a las reuniones con el nombre de usuario y la dirección de correo electrónico asociados al buzón de sala, seleccione **Unirse con la información de la sala.**
5. Si desea unirse a las reuniones con una  dirección de correo electrónico y un nombre de usuario alternativos, seleccione Unirse con información personalizada y escriba el nombre de usuario y la dirección de correo electrónico que le gustaría usar.
6. Seleccione **Guardar y salir.** Se reiniciará el dispositivo.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar el archivo SkypeSettings.xml de configuración

Las siguientes opciones de configuración se pueden agregar al `SkypeSettings.xml` archivo ubicado `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` en. Para obtener más información sobre el archivo, consulte Administrar de forma remota una configuración de consola de Salas de `SkypeSettings.xml` Microsoft Teams con un archivo de configuración [XML.](xml-config-file.md)

Para habilitar las reuniones de Cisco WebEx, establezca el `WebExMeetingsEnabled` elemento XML en **"True",** tal como se muestra a continuación.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Para habilitar las reuniones de zoom, establezca el `ZoomMeetingsEnabled` elemento XML en **True,** tal y como se muestra a continuación.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Opcionalmente, puede especificar un nombre de usuario y una dirección de correo electrónico personalizados para unirse a reuniones de terceros con los siguientes elementos XML. Si los valores que proporciona no son válidos, el dispositivo salas de Teams usará de forma predeterminada el nombre de usuario y la dirección de correo electrónico del buzón de sala.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Para unirse a una reunión de Cisco WebEx desde un dispositivo de salas de Teams, la reunión de Cisco debe hospedarse con la versión de aplicación web Cisco WBS 40.7 o posterior.


---
title: Habilitar Salas de Teams dispositivos para unirse a reuniones de terceros
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
description: En este artículo se explica cómo configurar su organización y Salas de Teams dispositivos para admitir la unión de reuniones de terceros a Cisco WebEx y Zoom.
ms.openlocfilehash: ef14d1f342c6f2b34ad7c948a2688fa39a09801d
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796694"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Habilitar Teams room para unirse a reuniones de terceros

Salas de Microsoft Teams dispositivos admiten una experiencia de un solo toque para unirse a reuniones en línea de terceros, también conocida como unirse a invitado directo. Cuando esté habilitado, puede usar un dispositivo Salas de Teams para unirse a reuniones hospedadas en Cisco WebEx y Zoom con la mayor facilidad posible para unirse a reuniones hospedadas en Microsoft Teams.

Para poder unirse a reuniones de terceros desde Salas de Teams dispositivo, debe hacer lo siguiente:

1. Configure el Salas de Teams del Exchange Online de sala para procesar invitaciones para reuniones de terceros.
2. Asegúrese de que su organización no tiene directivas que le impidan conectarse a servicios de reuniones de terceros.
3. Configure sus Salas de Teams para permitir reuniones de terceros.

En las secciones siguientes se muestra cómo realizar cada uno de estos pasos.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Paso 1: Permitir el procesamiento de invitaciones de calendario para reuniones de terceros

Lo primero que debe hacer para habilitar una experiencia de unirse con un solo toque desde un dispositivo de salas de grupo es establecer las reglas de procesamiento del calendario para el buzón de sala Exchange Online del dispositivo. El buzón de sala necesita permitir reuniones externas y mantener el cuerpo y el asunto del mensaje para que pueda ver la dirección URL necesaria para unirse a la reunión de terceros. Para establecer estas opciones de buzón de sala con el cmdlet [Set-CalendarProcessing,](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) haga lo siguiente:

1. Conectar para Exchange Online PowerShell. Para obtener más información, vea Conectar para Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) con autenticación básica o Conectar para Exchange Online PowerShell con autenticación [multifactor,](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)según el método de autenticación.

2. Obtenga el nombre principal de usuario (UPN) del buzón de sala si no lo conoce ejecutando el siguiente comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Busque el nombre del buzón de sala asociado a su Salas de Teams y anote su UPN.

4. Después de encontrar el UPN del buzón de sala, ejecute el siguiente comando. Reemplazar `<UserPrincipalName>` por el UPN del buzón de sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Obtenga más información [sobre Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Paso 2: Configurar Office 365 protección contra amenazas y reescribir vínculos

Para habilitar la experiencia de unirse con un solo toque, la información del vínculo de unirse a la reunión de terceros debe estar presente y legible en la invitación a la reunión. Si su organización usa la característica de vínculos Caja fuerte protección contra amenazas avanzada de [Office 365](/microsoft-365/security/office-365-security/atp-safe-links) o si usa una solución de terceros que examina todas las direcciones URL entrantes y salientes en busca de amenazas, puede cambiar las direcciones URL de la combinación de reuniones y hacer que la reunión no sea reconocible por el dispositivo Salas de Teams. Para asegurarse de que esto no sucede, debe agregar las direcciones URL del servicio de reunión de terceros a la lista de vínculos de ATP Caja fuerte "no reescribir" o a la lista de excepciones de reescritura url de terceros.

Para agregar direcciones URL de servicio de reunión de terceros a la lista vínculos de ATP Caja fuerte "no reescribir", siga los pasos de Configurar una lista personalizada de direcciones URL de [do-not-rewrite](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)con vínculos de Caja fuerte ATP. Si usa una solución de terceros, consulte las instrucciones de esa solución para agregar direcciones URL a su lista de excepciones de reescritura de direcciones URL.

Estas son algunas entradas de ejemplo que es posible que deba agregar a la lista de vínculos de ATP Caja fuerte "no reescribir" o a la lista de excepciones de reescritura url de terceros:

- **Cisco WebEx**`*.webex.com*`
- **Zoom** `*.zoom.us*` , `*.zoom.com*` , `*.zoomgov.com*`

Para obtener una lista completa de direcciones URL para agregar a la lista de vínculos de ATP Caja fuerte "no reescribir" o la lista de excepciones de reescritura de url de terceros, póngase en contacto con el proveedor de servicios de reuniones de terceros desde el que desea aceptar invitaciones a reuniones. 

> [!CAUTION]
> Agregue solo direcciones URL en las que confía a su lista de Caja fuerte vínculos de ATP "no reescribir" o la lista de excepciones de reescritura url de terceros.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Paso 3: Habilitar reuniones de terceros en el dispositivo

El último paso que debe hacer es permitir que cada Salas de Teams dispositivo se una a reuniones de terceros. Las reuniones de terceros requieren un nombre de usuario y una dirección de correo electrónico para unirse a ellas. Si el nombre de usuario y la dirección de correo electrónico que necesita usar son diferentes del buzón de sala del dispositivo, debe agregarlo al dispositivo. Puede hacerlo en la configuración del dispositivo o en el archivo de configuración XML.

### <a name="use-device-settings"></a>Usar la configuración del dispositivo

Para configurar el Salas de Teams con su pantalla táctil, haga lo siguiente:

1. En el Salas de Microsoft Teams, seleccione **Más ...**.
2. Seleccione **Configuración** y, a continuación, escriba el nombre de usuario y la contraseña del administrador del dispositivo.
3. Vaya a la **pestaña Reuniones** y seleccione **Cisco WebEx,** **Zoom** o ambos.
4. Si desea unirse a reuniones con el nombre de usuario y la dirección de correo electrónico asociadas con el buzón de sala, seleccione **Unirse con la información del salón.**
5. Si desea unirse a reuniones con un nombre  de usuario y una dirección de correo electrónico alternativos, seleccione Unirse con información personalizada y escriba el nombre de usuario y la dirección de correo electrónico que le gustaría usar.
6. Seleccione **Guardar y salir**. El dispositivo se reiniciará.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar el SkypeSettings.xml de configuración

Se pueden agregar las siguientes opciones de configuración al `SkypeSettings.xml` archivo ubicado en `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Para obtener más información sobre el archivo, vea Administrar una configuración Salas de Microsoft Teams consola de forma `SkypeSettings.xml` remota con un archivo de configuración [XML.](xml-config-file.md)

Para habilitar las reuniones de Cisco WebEx, establezca el elemento `WebExMeetingsEnabled` XML en **Verdadero,** como se muestra a continuación.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Para habilitar las reuniones de Zoom, establezca el elemento `ZoomMeetingsEnabled` XML en **True**, como se muestra a continuación.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Opcionalmente, puede especificar un nombre de usuario personalizado y una dirección de correo electrónico para unirse a reuniones de terceros con los siguientes elementos XML. Si los valores que proporcione no son válidos, el dispositivo Salas de Teams usará de forma predeterminada el nombre de usuario y la dirección de correo electrónico del buzón de sala.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Para unirse a una reunión de Cisco WebEx desde un dispositivo Salas de Teams, la reunión de Cisco debe hospedarse en WebEx Meetings Pro con la versión WBS 40.7 de la aplicación web de Cisco WebEx o posterior. 

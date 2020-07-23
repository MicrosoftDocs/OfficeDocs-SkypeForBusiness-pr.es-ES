---
title: Habilitar los dispositivos de salas de equipos para unirse a reuniones de terceros
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
description: En este artículo se describe cómo configurar la organización y los dispositivos de salas de equipos para admitir la Unión de reuniones de terceros con Cisco WebEx y el zoom.
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372219"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Habilitar los dispositivos de la sala de equipos para unirse a reuniones de terceros

Los dispositivos de salas de Microsoft Teams admiten una experiencia de un solo toque para unirse a reuniones en línea de terceros. Cuando está habilitado, puede usar un dispositivo de salas de equipos para unirse a reuniones hospedadas en Cisco WebEx y ampliar el zoom<sup>1</sup> de la misma manera que puede unirse a las reuniones hospedadas en Microsoft Teams.

Para poder unirse a reuniones de terceros desde un dispositivo de salas de equipos, debe hacer lo siguiente:

1. Configurar el buzón de Exchange online del dispositivo de las salas de equipos para procesar invitaciones para reuniones de terceros
2. Asegúrese de que su organización no tiene ninguna directiva que le impida conectarse a servicios de reuniones de terceros
3. Configurar los dispositivos de las salas de equipos para permitir reuniones de terceros

En las secciones siguientes se muestra cómo realizar cada uno de estos pasos.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Paso 1: permitir el procesamiento de invitaciones al calendario para reuniones de terceros

Lo primero que debe hacer para habilitar una experiencia de unión con un solo toque desde un dispositivo de salas de equipo es establecer las reglas de procesamiento del calendario para el buzón de correo de la sala de Exchange online del dispositivo. El buzón de sala debe permitir reuniones externas y mantener el cuerpo y el asunto del mensaje para que pueda ver la dirección URL necesaria para unirse a la reunión de terceros. Para configurar estas opciones de buzón de sala con el cmdlet [set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , haga lo siguiente:

1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea [conectarse a Exchange Online PowerShell con autenticación básica](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) o [conectarse a Exchange Online PowerShell con la autenticación multifactor](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), según el método de autenticación.

2. Obtenga el nombre principal de usuario (UPN) del buzón de sala si no lo conoce ejecutando el siguiente comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. Buscar el nombre del buzón de sala asociado a su dispositivo de salas de equipos y tomar nota de su UPN

4. Después de encontrar el UPN del buzón de sala, ejecute el siguiente comando. Reemplazar `<UserPrincipalName>` por el UPN del buzón de sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Obtenga más información sobre [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Paso 2: configurar la protección contra amenazas de Office 365 y la reescritura de vínculos

Para habilitar la experiencia de combinación única, la información del vínculo para unirse a la reunión de la reunión de terceros debe estar presente y es legible en la invitación a la reunión. Si su organización usa la característica de [vínculos seguros de la protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)   , o si usa una solución de terceros que analice todas las direcciones URL entrantes y salientes en busca de amenazas, puede cambiar las direcciones URL de la combinación de reuniones para que el dispositivo de las salas de equipos no reconozca la reunión. Para asegurarse de que esto no suceda, debe agregar las direcciones URL del servicio de reunión de terceros a la lista de vínculos seguros de ATP "no rescribir" o a la lista de excepciones de reescritura de direcciones URL de terceros.

Para agregar direcciones URL de los servicios de reuniones de terceros a la lista de vínculos seguros de ATP "do not Write", siga los pasos que se indican en [configurar una lista de direcciones URL de hacer y desescritura personalizada con vínculos seguros de ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide). Si usa una solución de terceros, consulte las instrucciones de esa solución para agregar direcciones URL a la lista de excepciones de reescritura de URL.

Estas son algunas entradas de ejemplo que es posible que tenga que agregar a la lista de vínculos seguros de ATP "do not Write" o a la lista de excepciones de reescritura de direcciones URL de terceros:

- **Cisco WebEx**`*.webex.com*`
- **Zoom** `*zoom.us*` , `*zoom.com*``*zoomgov.com*`

Para obtener una lista completa de las direcciones URL que se agregarán a la lista de vínculos seguros de ATP "do not Write" o a la lista de excepciones de reescritura de direcciones URL de terceros, póngase en contacto con el proveedor de servicios de reuniones de terceros en el que desea aceptar las invitaciones a reuniones. 

> [!CAUTION]
> Agregue solo direcciones URL en las que confía a la lista de vínculos seguros de ATP "no rescribir" o lista de excepciones de reescritura de direcciones URL de terceros.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Paso 3: habilitar las reuniones de terceros en el dispositivo

El último paso que debe realizar es permitir que cada dispositivo de salas de equipos se una a reuniones de terceros. Las reuniones de terceros requieren un nombre de usuario y una dirección de correo electrónico para unirse a ellas. Si el nombre de usuario y la dirección de correo electrónico que necesita usar son diferentes a los del buzón de sala del dispositivo, tendrá que agregarlos al dispositivo. Puede hacerlo en la configuración del dispositivo o en el archivo de configuración XML.

### <a name="use-device-settings"></a>Usar la configuración del dispositivo

Para configurar el dispositivo de salas de equipos con su pantalla táctil, haga lo siguiente:

1. En el dispositivo de salas de Microsoft Teams, seleccione **más...**
2. Seleccione **configuración**y, a continuación, escriba el nombre de usuario y la contraseña del administrador del dispositivo
3. Vaya a la ficha **reuniones**   y seleccione **Cisco WebEx**, **zoom**<sup>1</sup>o ambos
4. Si desea unirse a las reuniones con el nombre de usuario y la dirección de correo electrónico asociados con el buzón de sala, seleccione **unirse con la información de la sala**
5. Si desea unirse a las reuniones con un nombre de usuario y una dirección de correo electrónico alternativos, seleccione **unirse con la información personalizada** y escriba el nombre de usuario y la dirección de correo electrónico que desea usar.
6. Seleccione **Guardar y salir**. El dispositivo se reiniciará.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar el archivo de configuración SkypeSettings.xml

La siguiente configuración se puede Agregar al archivo que se `SkypeSettings.xml` encuentra en `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Para obtener más información sobre el `SkypeSettings.xml` archivo, consulte [administrar de forma remota la configuración de una consola de salas de Microsoft Teams con un archivo de configuración XML](xml-config-file.md).

Para habilitar las reuniones de Cisco WebEx, establezca el `WebExMeetingsEnabled` elemento XML en **true**, como se indica a continuación.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Para habilitar las reuniones de zoom<sup>1</sup> , establezca el `ZoomMeetingsEnabled` elemento XML en **true**, como se indica a continuación.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

De manera opcional, puede especificar un nombre de usuario y una dirección de correo electrónico personalizados para unirse a reuniones de terceros con los siguientes elementos XML. Si los valores que proporciona no son válidos, el dispositivo salas de equipos predeterminado usará el nombre de usuario y la dirección de correo electrónico del buzón de sala.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Para unirse a una reunión de Cisco WebEx desde un dispositivo de salas de equipos, la reunión de Cisco debe estar hospedada mediante la versión WBS 40,7 o posterior de la aplicación web Cisco WebEx.

<sup>1</sup> la combinación de reuniones de zoom solo está disponible para seleccionar los clientes de Microsoft Team Rooms a través del programa de acceso de tecnología (TAP).

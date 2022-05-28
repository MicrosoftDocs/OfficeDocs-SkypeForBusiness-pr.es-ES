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
ms.localizationpriority: medium
description: En este artículo se describe cómo configurar su organización y Salas de Teams dispositivos para que admitan la reunión de terceros que se une a Cisco WebEx y Zoom.
ms.openlocfilehash: a9421d234981343d268e74a2f03a949f3761ae0f
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761422"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>Habilitar Salas de Teams dispositivos para unirse a reuniones de terceros

> [!NOTE]
> Actualmente, esta característica solo está disponible en Salas de Teams en Windows.

Salas de Microsoft Teams dispositivos admiten una experiencia de un solo toque para unirse a reuniones en línea de terceros, también denominada Unión directa de invitado. Cuando se habilita, puede utilizar Salas de Teams para unirse a reuniones hospedadas en Cisco WebEx y Zoom tan fácilmente como puede unirse a reuniones hospedadas en Microsoft Teams.

Para poder unirse a reuniones de terceros desde Salas de Teams, debe hacer lo siguiente:

1. Configure el buzón de sala Exchange Online del Salas de Teams para procesar invitaciones para reuniones de terceros.
2. Asegúrese de que su organización no tiene ninguna directiva que le impida conectarse a servicios de reuniones de terceros.
3. Configure Salas de Teams para permitir reuniones de terceros.

En las siguientes secciones se muestra cómo realizar cada uno de estos pasos.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Paso 1: Permitir el procesamiento de invitaciones de calendario para reuniones de terceros

Lo primero que debe hacer para habilitar una experiencia de unión con un solo toque desde salas de equipo es establecer las reglas de procesamiento del calendario para el buzón de sala Exchange Online del dispositivo. El buzón de sala debe permitir reuniones externas y mantener el cuerpo y el asunto del mensaje para que pueda ver la dirección URL necesaria para unirse a la reunión de terceros. Para establecer estas opciones de buzón de sala mediante el cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , haga lo siguiente:

1. Conectar a Exchange Online PowerShell. Para obtener más información, vea [Conectar para Exchange Online PowerShell con autenticación básica](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) o [Conectar para Exchange Online PowerShell con la autenticación multifactor](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), según el método de autenticación.

2. Obtenga el nombre principal de usuario (UPN) del buzón de sala si no lo sabe ejecutando el siguiente comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Busque el nombre del buzón de sala asociado a su dispositivo de Salas de Teams y anote su UPN.

4. Después de encontrar el UPN del buzón de sala, ejecute el siguiente comando. Reemplace `<UserPrincipalName>` por el UPN del buzón de sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Obtenga más información sobre [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Paso 2: Configurar Office 365 protección contra amenazas y volver a escribir vínculos

Para habilitar la experiencia de unirse con un solo toque, la información del vínculo para unirse a la reunión de terceros debe estar presente y se puede leer en la invitación a la reunión. Si su organización usa la característica de vínculos [seguros Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide), o si usa una solución de terceros que analiza todas las direcciones URL entrantes y salientes en busca de amenazas, puede cambiar las direcciones URL de unión a la reunión y hacer que la reunión no se reconozca por el dispositivo Salas de Teams. Para asegurarse de que esto no sucede, debe agregar las direcciones URL del servicio de reunión de terceros a Defender para [Office 365 Caja fuerte la lista Vínculos **no reescribir**](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide) o la lista de excepciones de reescritura de url de terceros.

 Si usa una solución de terceros, consulte las instrucciones de esa solución para agregar direcciones URL a su lista de excepciones de reescritura de url.

Estas son algunas entradas de ejemplo que puede que necesite agregar a su Defender para Office 365 Caja fuerte Vínculos *No reescribir* lista o lista de excepciones de reescritura de URL de terceros:

- **Cisco WebEx** `*.webex.com/*`
- **Zoom** `*.zoom.us/*`, , `*.zoom.com/*``*.zoomgov.com/*`

Para obtener una lista completa de las direcciones URL que puede agregar a su Defender para Office 365 Caja fuerte Vínculos *No volver a escribir* lista o lista de excepciones de reescritura de URL de terceros, póngase en contacto con el proveedor de servicios de reuniones de terceros desde el que desea aceptar invitaciones de reunión.

> [!CAUTION]
> Agregue solo direcciones URL de confianza a su Microsoft Defender para Office 365 Caja fuerte Vínculos *No vuelva a escribir* lista ni lista de excepciones de reescritura de URL de terceros.

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>Paso 3: Habilitar reuniones de terceros en Salas de Teams

El último paso que debe realizar es permitir que Salas de Teams se unan a reuniones de terceros. Las reuniones de terceros requieren un nombre de usuario y una dirección de correo electrónico para unirse a ellas. Si el nombre de usuario y la dirección de correo electrónico que necesita usar son diferentes del buzón de sala del dispositivo, deberá agregarlos al dispositivo. Puede hacerlo en la configuración de Salas de Teams o en el archivo de configuración XML.

### <a name="use-device-settings"></a>Usar la configuración del dispositivo

Para configurar Salas de Teams con la consola de pantalla táctil, haz lo siguiente:

1. En la consola Salas de Microsoft Teams, selecciona **Más ...**.
2. Selecciona **Configuración** y, a continuación, escribe el nombre de usuario y la contraseña del administrador del dispositivo.
3. Vaya a la pestaña **Reuniones** y seleccione **Cisco WebEx**, **Zoom** o ambos.
4. Si desea unirse a reuniones con el nombre de usuario y la dirección de correo electrónico asociados al buzón de sala, seleccione **Unirse con la información del salón**.
5. Si desea unirse a reuniones con un nombre de usuario y una dirección de correo electrónico alternativos, seleccione **Unirse con información personalizada** y escriba el nombre de usuario y la dirección de correo electrónico que desea usar.
6. Seleccione **Guardar y salir**. El dispositivo se reiniciará.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar el archivo de configuración SkypeSettings.xml

Las siguientes opciones de configuración se pueden agregar al `SkypeSettings.xml` archivo ubicado en `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Para obtener más información sobre el `SkypeSettings.xml` archivo, vea [Administrar una configuración de la consola de Salas de Microsoft Teams de forma remota con un archivo de configuración XML](xml-config-file.md).

Para habilitar las reuniones Cisco WebEx, establezca el `WebExMeetingsEnabled` elemento XML en **True**, como se indica a continuación.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Para habilitar las reuniones de zoom, establezca el `ZoomMeetingsEnabled` elemento XML en **True**, como se indica a continuación.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Opcionalmente, puede especificar un nombre de usuario y una dirección de correo electrónico personalizados para unirse a reuniones de terceros mediante los siguientes elementos XML. Si los valores que proporciona no son válidos, el dispositivo de Salas de Teams usará de forma predeterminada el nombre de usuario y la dirección de correo electrónico del buzón de sala.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Para unirse a una reunión de Cisco WebEx de un dispositivo de Salas de Teams, la reunión de Cisco necesita ser hospedada en las reuniones de WebEx Pro usando la versión de la aplicación web de Cisco WebEx WBS 40.7 o posterior. 

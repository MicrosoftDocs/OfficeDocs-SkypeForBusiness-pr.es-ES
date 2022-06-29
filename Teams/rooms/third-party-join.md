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
description: En este artículo se describe cómo configurar su organización y Salas de Teams dispositivos para que admitan la reunión de terceros que se une a Cisco Webex y Zoom.
ms.openlocfilehash: 23eefeb564e3333b1bc2105a1fc4d57a0ff41bbe
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529682"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>Habilitar Salas de Teams dispositivos para unirse a reuniones de terceros

Salas de Microsoft Teams dispositivos admiten una experiencia de un solo toque para unirse a reuniones en línea de terceros, también denominada Unión directa de invitado. Cuando se habilita, puede usar Salas de Teams para unirse a reuniones hospedadas en Cisco Webex y Zoom, del mismo modo que puede unirse a reuniones hospedadas en Microsoft Teams.

Dispositivos y servicios compatibles:

- MTR en Windows, todos los modelos certificados – Zoom, Cisco Webex

- MTR en modelos certificados Para Android, Poly, Yealink y Logitech: Zoom

> [!NOTE]
> Para unirse a una reunión cisco webex de un dispositivo Salas de Teams, la reunión de Cisco necesita ser hospedada en las reuniones de Webex Pro usando la versión de la aplicación web de Cisco Webex WBS 40.7 o posterior. 

Para poder unirse a reuniones de terceros desde Salas de Teams, debe hacer lo siguiente:

1. Configure el buzón de sala Exchange Online del Salas de Teams para procesar invitaciones para reuniones de terceros.
2. Asegúrese de que su organización no tiene ninguna directiva que le impida conectarse a servicios de reuniones de terceros.
3. Configure Salas de Teams para permitir reuniones de terceros.

En las siguientes secciones se muestra cómo completar cada uno de estos pasos.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Paso 1: Permitir el procesamiento de invitaciones de calendario para reuniones de terceros

Lo primero que debe hacer para habilitar una experiencia de unión con un solo toque desde salas de equipo es establecer las reglas de procesamiento del calendario para el buzón de sala Exchange Online del dispositivo. El buzón de sala debe permitir reuniones externas y mantener el cuerpo y el asunto del mensaje para que pueda ver la dirección URL necesaria para unirse a la reunión de terceros. Para establecer estas opciones de buzón de sala mediante el cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing.) , haga lo siguiente:

1. Conéctese a Exchange Online PowerShell. Para obtener más información, vea [Conectarse a Exchange Online PowerShell con autenticación básica](/powershell/exchange/connect-to-exchange-online-powershell) o [Conectarse a Exchange Online PowerShell mediante la autenticación multifactor](/powershell/exchange/mfa-connect-to-exchange-online-powershell), según el método de autenticación.

2. Obtenga el nombre principal de usuario (UPN) del buzón de sala si no lo sabe ejecutando el siguiente comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Busque el nombre del buzón de sala asociado a su dispositivo de Salas de Teams y anote su UPN.

4. Después de encontrar el UPN del buzón de sala, ejecute el siguiente comando. Reemplace `<UserPrincipalName>` por el UPN del buzón de sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Obtenga más información sobre [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Paso 2: Configurar Office 365 protección contra amenazas y volver a escribir vínculos

Para habilitar la experiencia de unirse con un solo toque, la información del vínculo para unirse a la reunión de terceros debe estar presente y se puede leer en la invitación a la reunión. Si su organización usa la característica de vínculos [seguros Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/safe-links), o si usa una solución de terceros que analiza todas las direcciones URL entrantes y salientes en busca de amenazas, puede cambiar las direcciones URL de unión a la reunión y hacer que la reunión no se reconozca por el dispositivo Salas de Teams. Para asegurarse de que esto no sucede, debe agregar las direcciones URL del servicio de reunión de terceros a Defender para [Office 365 lista Vínculos seguros **No volver a escribir**](/microsoft-365/security/office-365-security/safe-links) o la lista de excepciones de reescritura de url de terceros.

 Si usa una solución de terceros, consulte las instrucciones de esa solución para agregar direcciones URL a su lista de excepciones de reescritura de url.

Estas son algunas entradas de ejemplo que puede que necesite agregar a su Defender para Office 365 Vínculos seguros *No reescribir* lista o lista de excepciones de reescritura de URL de terceros:

- **Cisco Webex** `*.webex.com/*`
- **Zoom** `*.zoom.us/*`, , `*.zoom.com/*``*.zoomgov.com/*`

Para obtener una lista completa de las direcciones URL que desea agregar a su Defender para Office 365 vínculos seguros *No volver a escribir* lista o lista de excepciones de reescritura de URL de terceros, póngase en contacto con el proveedor de servicios de reuniones de terceros desde el que desea aceptar invitaciones de reunión.

> [!CAUTION]
> Agregar solo direcciones URL de confianza a los Microsoft Defender para Office 365 Vínculos seguros *No vuelva a escribir* lista ni lista de excepciones de reescritura de URL de terceros.

## <a name="step-3a-enable-third-party-meetings-on-teams-rooms-on-windows"></a>Paso 3a: Habilitar reuniones de terceros en Salas de Teams en Windows

El último paso que debe realizar es permitir que Salas de Teams se unan a reuniones de terceros. Las reuniones de terceros requieren un nombre de usuario y una dirección de correo electrónico para unirse a ellas. Si el nombre de usuario y la dirección de correo electrónico que necesita usar son diferentes del buzón de sala del dispositivo, deberá agregarlos al dispositivo. Puede hacerlo en la configuración de Salas de Teams o en el archivo de configuración XML. Puede hacerlo en la configuración de Salas de Teams en cualquier Salas de Teams compatible o en el archivo de configuración XML para Salas de Teams en Windows.

### <a name="use-device-settings"></a>Usar la configuración del dispositivo

Para configurar Salas de Teams en Windows con la consola de pantalla táctil, haz lo siguiente:

1. En la consola de Salas de Microsoft Teams, selecciona **Más**.
2. Selecciona **Configuración** y, a continuación, escribe el nombre de usuario y la contraseña del administrador del dispositivo.
3. Vaya a la pestaña Reuniones y seleccione un proveedor de reuniones de **terceros** que desee habilitar (por ejemplo, **Webex**, **Zoom**, etc.).
4. Si desea unirse a reuniones con el nombre de usuario y la dirección de correo electrónico asociados al buzón de sala, seleccione **Unirse con la información del salón**.
5. Si desea unirse a reuniones con un nombre de usuario y una dirección de correo electrónico alternativos, seleccione **Unirse con información personalizada** y escriba el nombre de usuario y la dirección de correo electrónico que desea usar.
6. Seleccione **Guardar y salir**. El dispositivo se reiniciará.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar el archivo de configuración SkypeSettings.xml

Las siguientes opciones de configuración se pueden agregar al `SkypeSettings.xml` archivo ubicado en `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Para obtener más información sobre el `SkypeSettings.xml` archivo, vea [Administrar una configuración de la consola de Salas de Microsoft Teams de forma remota con un archivo de configuración XML](xml-config-file.md).

Para habilitar las reuniones de Cisco Webex, establezca el `WebexMeetingsEnabled` elemento XML en **True**, como se indica a continuación.

```xml
<WebexMeetingsEnabled>True</WebexMeetingsEnabled>
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
## <a name="step-3b-enable-third-party-meetings-on-teams-rooms-on-android"></a>Paso 3b: Habilitar reuniones de terceros en Salas de Teams en Android

Para configurar Salas de Teams en Android con la consola de pantalla táctil o la pantalla frontal de la sala, haga lo siguiente:

1.  En la consola de Salas de Microsoft Teams o en la pantalla frontal de la sala, seleccione **Más**.
2.  Selecciona **Configuración** y:
    -   Si usa una cuenta personal (por ejemplo, una cuenta con una licencia E5), elija la opción **Reuniones** .
    -   Si usa una cuenta compartida (por ejemplo, una cuenta de recursos con una licencia de Salas de Teams), elija **Configuración del dispositivo**, busque **Teams Administración configuración**, escriba una contraseña de administrador y elija una opción **Reuniones**.
      > [!NOTE]
      > Algunos fabricantes de dispositivos requieren una contraseña de administrador para poder acceder a la **configuración del dispositivo** .

    ![Configuración de reuniones para MTR en Android](..\media\mtrandroid.png)

3.  Seleccione un proveedor de reuniones de terceros que quiera habilitar.
4.  Si desea unirse a reuniones con un nombre de usuario y una dirección de correo electrónico personalizados, seleccione **Unirse con un nombre y un correo electrónico personalizados**. Para actualizar la información personal personalizada, presiona **Editar información personalizada** e introduce tu nombre y dirección de correo electrónico preferidos.


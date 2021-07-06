---
title: Configurar reuniones coordinadas con Salas de Microsoft Teams y Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Configure Salas de Teams dispositivos y Surface Hub para unirse a reuniones cuando un dispositivo u otro se une a una reunión.
ms.openlocfilehash: b81d6fca5c263bb8ba1dcd07e80167425bd42fc0
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278683"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurar reuniones coordinadas con Salas de Microsoft Teams y Surface Hub

Si tienes uno o varios dispositivos Salas de Microsoft Teams o Surface Hubs en una sala de reuniones, puedes configurar Reuniones coordinadas. Reuniones coordinadas te permite configurar tus dispositivos Salas de Teams y Surface Hubs para que, al unirte a una reunión en un dispositivo, los demás dispositivos de la sala también se unan a la misma reunión. Puede configurar sus cámaras, altavoces y micrófonos para que los participantes que le den la mejor experiencia estén habilitados mientras otros están deshabilitados. Esto evita el temido eco y el ruido de comentarios que los participantes pueden experimentar al agregar varios dispositivos a una reunión.

Para configurar reuniones coordinadas, debes asegurarte de que tus dispositivos Salas de Teams y Surface Hubs ya están configurados correctamente para participar en reuniones. Lo más importante es que cada dispositivo debe tener su propio buzón de Exchange sala. Para obtener información sobre cómo configurarlas, vea los artículos siguientes:

- [Implementar Salas de Microsoft Teams](../rooms/rooms-deploy.md)
- [Crear Surface Hub cuenta de dispositivo 2S](/surface-hub/surface-hub-2s-account)

Después de confirmar que tus dispositivos Salas de Teams y Surface Hubs pueden aceptar automáticamente reuniones y unirse a ellas correctamente, puedes configurar reuniones coordinadas.

Los pasos siguientes deben completarse para cada sala de reuniones por separado. Los dispositivos de una sala de reuniones no deben configurarse para reuniones coordinadas con dispositivos en otras salas de reuniones.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Paso 1: Planear la experiencia de reunión coordinada

Antes de realizar los cambios de configuración, debe decidir qué dispositivos harán lo que en cada sala de reuniones. Es decir, para una sala de reuniones determinada, debe decidir qué dispositivo tendrá el micrófono activo, la cámara y la pizarra. La forma de configurar los dispositivos depende de su entorno específico, pero estas son algunas recomendaciones generales para empezar con:

- **Micrófono** Salas de Teams dispositivo
- **Cámara** Salas de Teams dispositivo (activado de forma predeterminada) y Surface Hub (desactivado de forma predeterminada, pero permitido que los participantes puedan estar activados)
- **Pizarra Surface Hub**

> [!IMPORTANT]
> Asegúrese de habilitar el micrófono solo en un dispositivo. Si lo habilita en más de un dispositivo, experimentará eco de audio y comentarios.

## <a name="step-2-get-your-devices-upns"></a>Paso 2: Obtener los UPN de tus dispositivos

Cuando configuras una experiencia de reunión coordinada en una sala de reuniones, debes decirles a los dispositivos Salas de Teams y Surface Hubs de esa sala con qué dispositivos coordinar. Para ello, agregue el nombre principal de usuario (UPN) de los dispositivos con los que debe coordinarse a su configuración. Si no conoce los UPN de cada uno de los dispositivos que desea configurar para reuniones coordinadas, puede encontrarlos con el Centro de administración de Microsoft 365. 

Debe tener asignado un rol de administrador para obtener acceso a la Centro de administración de Microsoft 365. Para obtener más información, vea [Acerca de los roles de administrador.](/microsoft-365/admin/add-users/about-admin-roles)

Para obtener los UPN de tus dispositivos Salas de Teams y Surface Hubs, haz lo siguiente:

1. Inicie sesión en el Centro de administración de Microsoft 365 visitando https://admin.microsoft.com .
2. Vaya a **Usuarios**  >  **usuarios activos.**
3. Busque el nombre de su Salas de Teams o Surface Hub en  la columna Nombre para  mostrar (puede usar el cuadro Buscar si tiene muchos usuarios).
4. Busque el UPN en la columna **Nombre** de usuario (tendrá un aspecto parecido a alias@contoso.com o alias@contoso.onmicrosoft.com).
5. Repita este procedimiento para cada dispositivo que participará en reuniones coordinadas.

## <a name="step-3-create-a-deployment-worksheet"></a>Paso 3: Crear una hoja de cálculo de implementación

Después de planear la experiencia de reunión coordinada y recopilar una lista de los UPN de los dispositivos, es una buena idea crear una hoja de cálculo de implementación. Una hoja de cálculo de implementación le ayudará a visualizar la configuración que desea establecer en todos los dispositivos, lo que le permite validar las opciones y comprobar si hay errores.

En una aplicación de hoja de cálculo, agregue filas para lo siguiente en la primera columna:

| Setting                | Descripción      |
|------------------------|-----------------|
| **Audio predeterminado**      | Determina en qué dispositivo estará activo el micrófono cuando se inicie una reunión. Solo un dispositivo (normalmente un dispositivo Salas de Teams) puede tener este campo establecido en, mientras que el resto de los dispositivos debe tener este campo configurado para evitar el eco de audio y los `true` `false` comentarios.          |
| **Audio habilitado**      | Determina si los participantes de una reunión pueden activar o desactivar el micrófono. Los dispositivos en los que **se** establece el valor predeterminado de audio deben tener esta configuración establecida en para que los participantes no puedan activar accidentalmente un micrófono y causar eco de audio o `false` `false` comentarios.<p>Si **audio predeterminado** está establecido en , esta configuración se ignora y los participantes pueden silenciar o activar el `true` micrófono.          |
| **Vídeo predeterminado**      | Determina en qué dispositivo estará activa la cámara cuando se inicie una reunión. Para obtener la mejor experiencia, le recomendamos que solo el Salas de Teams esté establecido en mientras todos los demás dispositivos `true` están establecidos en `false` .          |
| **Vídeo habilitado**      | Determina si los participantes de una reunión pueden activar o desactivar la cámara. Puede establecer esta opción en cualquier otro dispositivo del evento en el que los participantes quieran compartir diferentes perspectivas de vídeo (por ejemplo, si un participante usa la pizarra `true` Surface Hub vídeo). Si no desea que los participantes activen o desactiven una cámara en un dispositivo, establezca esta opción en `false` .<p> Si **video predeterminado** está establecido en , esta configuración se ignora y los `true` participantes pueden activar o desactivar la cámara.         |
| **Pizarra predeterminada** | Determina si el Salas de Teams mostrará una pizarra compartida por uno de los participantes de la reunión. Le recomendamos que establezca esta opción en si tiene una Surface Hub y si `false` `true` no tiene una. Esta configuración no tiene ningún efecto en Surface Hubs. Surface Hubs siempre mostrará una pizarra compartida por los participantes de la reunión.         |
| **Pizarra habilitada** | Determina si los participantes de una reunión pueden activar o desactivar la pizarra. Si no desea que los participantes activen o desactiven la pizarra en un dispositivo, establezca esta opción en `false` . <p>Si **whiteboard predeterminado** está establecido en , esta configuración se ignora y `true` los participantes pueden activar o desactivar la pizarra.
| **Cuentas de confianza**   | Esta es una lista separada por comas de UPN para cada dispositivo de sala de Teams o Surface Hub desde el que el dispositivo debe aceptar las solicitudes de unirse a la reunión o a qué solicitudes de unirse a la reunión se deben enviar. |

En las columnas siguientes, agrega cada uno de tus dispositivos Salas de Teams y Surface Hubs. En cada columna, rellene los valores que corresponden a la experiencia que desea para la sala de reuniones. Este es un ejemplo con un dispositivo Salas de Teams y otro Surface Hub:

- Teams dispositivo
  - El audio y el vídeo están **activados** cuando se inicia una reunión. Los participantes **pueden activar** o desactivar el audio y el vídeo.
  - La visualización de una pizarra compartida está desactivada.
- Surface Hub
  - El audio se **apaga cuando** se inicia una reunión. Los participantes **no pueden activar** o desactivar el audio.
  - El vídeo se **apaga cuando** se inicia una reunión. Los participantes **pueden** activar o desactivar el vídeo.

| Setting                | Teams Sala      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audio predeterminado**      | `true`          | `false`          |
| **Audio habilitado**      | `true`          | `false`          |
| **Vídeo predeterminado**      | `true`          | `false`          |
| **Vídeo habilitado**      | `true`          | `true`           |
| **Pizarra predeterminada** | `false`         | `false`          |
| **Cuentas de confianza**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Paso 4: Configurar Salas de Teams dispositivo

Puede configurar reuniones coordinadas en un dispositivo Salas de Teams con la pantalla táctil del dispositivo o, si necesita configurar muchos dispositivos y desea hacerlo desde una ubicación central, puede usar un archivo de configuración XML.

Use la hoja de cálculo que creó en el paso anterior para ayudarle a configurar los dispositivos.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usar la Salas de Teams táctil del dispositivo

Para configurar reuniones coordinadas en un dispositivo, haga lo siguiente:

1. Seleccione **... Más**  >  **Configuración**.
2. Escriba la contraseña del administrador y seleccione **Sí.**
3. Seleccione **Reuniones coordinadas**.
4. En **Opciones,** establezca **Reunión coordinada en** _on_.
5. Si **el valor predeterminado de** Audio en la hoja de cálculo es , establezca Activar el micrófono de este dispositivo para activarlo, de lo `true` contrario, déjelo _desactivado._ 
6. Si **el audio habilitado** en la hoja de cálculo está , seleccione Permitir que los usuarios habiliten al unirse a una reunión en Activar el micrófono de este `true` **dispositivo.**  Esta opción no se puede desactivar si **Activar** el micrófono de este dispositivo está activado.
7. Si **el valor predeterminado de** Vídeo en la hoja de cálculo es , establezca Activar la cámara de este dispositivo para activarla, de lo `true` contrario, déjela _desactivada._ 
8. Si **vídeo habilitado** en la hoja de cálculo está , seleccione Permitir que los usuarios habiliten al unirse a una reunión en Activar la cámara `true` de este **dispositivo.**  Esta opción no se puede desactivar si **Activar** la cámara de este dispositivo está _activada._
9. Si **whiteboard predeterminado** en la hoja de cálculo es , establezca Activar la pizarra en este dispositivo para activarla, de lo `true` contrario,  déjela  _desactivada._
10. En **Cuentas de dispositivo de confianza,** escriba cada UPN enumerado en Cuentas de **confianza** en la hoja de cálculo. Separe varios UPN con comas.
11. Seleccione **Guardar y salir**.

Después de seleccionar **Guardar y salir,** el dispositivo se reiniciará y estará listo para participar en reuniones coordinadas.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usar el Salas de Teams de configuración XML

Las reuniones coordinadas se pueden configurar con el Salas de Teams de configuración `SkypeSettings.xml` XML del dispositivo. El `SkypeSettings.xml` archivo no es un archivo estático. Cuando se inicia Salas de Teams dispositivo, se comprueba `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` si hay un archivo denominado `SkypeSettings.xml` . Si el archivo existe, el dispositivo leerá y aplicará la configuración especificada en el archivo. Una vez que haya terminado de aplicar la configuración, el archivo se eliminará. Para obtener más información sobre el `SkypeSettings.xml` archivo, vea [Administrar la configuración de la consola con un archivo de configuración XML.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

A continuación se muestra la sintaxis de la configuración reuniones coordinadas en el archivo de configuración:

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

Para configurar reuniones coordinadas en un dispositivo, haga lo siguiente:

1. En un editor de archivos de texto, como Visual Studio Code o Bloc de notas, pegue el XML anterior en un archivo nuevo.

2. Establezca cada uno de los elementos XML en el valor `true` correspondiente o en la hoja de `false` cálculo. Por ejemplo, si **el valor predeterminado de Audio** es , establece `true` `<Audio default="true">` .

3. Asegúrese de cambiar `TrustedAccounts` a la lista de UPN.

4. Guarde el archivo con el nombre `SkypeSettings.xml` .

5. Coloque el archivo en Salas de Teams carpeta del `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` dispositivo. Puede hacer esto de varias maneras:

    - **Copiar el archivo en el Salas de Teams dispositivo** Deberá habilitar el uso compartido de archivos y crear un recurso compartido de red para poder copiar archivos en el dispositivo. Después de hacerlo, puede conectarse al recurso compartido de red y copiar el archivo en el dispositivo. Para obtener más información, [vea Salas de Microsoft Teams tareas de mantenimiento y operaciones](../rooms/rooms-operations.md).
    - **Usar una directiva de grupo** Cree una directiva de grupo para copiar el archivo en el dispositivo. Para obtener más información, vea [Información general sobre directivas de grupo.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Descargar el archivo en el Salas de Teams dispositivo** Puede iniciar sesión en el dispositivo con el modo administrador y, a continuación, copiar el archivo en el dispositivo desde un recurso compartido de red o una unidad USB. Para obtener más información, vea [Cambiar al modo de administrador.](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)
    
6. Reinicie el dispositivo. Puede hacerlo de dos maneras:

    - **PowerShell remoto** Puede ejecutar el comando Apagar en el dispositivo con PowerShell remoto. Para obtener más información, vea [Administración remota con PowerShell.](../rooms/rooms-operations.md)
    - **Ejecutar Reiniciar-EQUIPO** Puede ejecutar el cmdlet en el equipo local y especificar el nombre del equipo del `Restart-Computer` dispositivo que desea reiniciar. Para obtener más información, vea [Reiniciar equipo.](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)

## <a name="step-5-configure-surface-hub"></a>Paso 5: Configurar Surface Hub

Puedes usar el Windows de configuración para crear un paquete de aprovisionamiento que puedes usar para aplicar la configuración de reuniones coordinadoras a tus Surface Hubs. Pegará el archivo XML que creó anteriormente en Windows de configuración para crear el paquete de aprovisionamiento.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Crear un archivo de configuración XML de reuniones coordinadas para Surface Hub

Tanto Windows diseñador de configuración como Microsoft Intune se usan para aplicar la configuración reuniones coordinadas a surface hubs. La configuración se define con XML. Antes de ir más lejos, debe crear el XML que se aplicará.

A continuación se muestra la sintaxis del archivo de configuración XML Reuniones coordinadas.

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

Haga lo siguiente para preparar el XML para Windows de configuración o Microsoft Intune:

1. En un editor de archivos de texto, como Visual Studio Code o Bloc de notas, pegue el XML anterior en un archivo nuevo.

2. Establezca cada uno de los elementos XML en el valor `true` correspondiente o en la hoja de `false` cálculo. Por ejemplo, si **el valor predeterminado de Audio** es , establece `true` `<Audio default="true">` .

3. Asegúrese de cambiar `TrustedAccounts` a la lista de UPN.

4. Windows El Diseñador de configuración requiere que el XML esté en una sola línea. Quite todos los saltos de línea entre cada línea para que el XML sea similar al siguiente:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Guarde el archivo en el equipo.

Después de crear el archivo de configuración XML, siga los pasos de Administrar Microsoft Teams configuración en [Surface Hub](surface-hub-manage-config.md) para aplicarlo a Surface Hubs.
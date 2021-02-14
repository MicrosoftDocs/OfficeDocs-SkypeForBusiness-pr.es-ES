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
description: Configure dispositivos de salas de Teams y Surface Hub para unirse a reuniones cuando un dispositivo u otro se una a una reunión.
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803942"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurar reuniones coordinadas con salas de Microsoft Teams y Surface Hub

Si tiene uno o varios dispositivos de salas de Microsoft Teams o Surface Hub en una sala de reuniones, puede configurar reuniones coordinadas. Reuniones coordinadas le permite configurar los dispositivos de salas de Teams y Surface Hub para que, cuando se una a una reunión en un dispositivo, los otros dispositivos de la sala también se unan a la misma reunión. Puede configurar las cámaras, los altavoces y los micrófonos para que los participantes puedan disfrutar de la mejor experiencia mientras que los demás estén deshabilitados. Esto evita el eco temible y el ruido de comentarios que los participantes pueden experimentar al agregar varios dispositivos a una reunión.

Para configurar reuniones coordinadas, necesita asegurarse de que los dispositivos de las salas de Teams y los Surface Hubs ya están configurados correctamente para participar en las reuniones. Lo más importante es que cada dispositivo necesita tener su propio buzón de sala de Exchange. Para obtener información sobre cómo configurarlas, vea los artículos siguientes:

- [Implementar Salas de Microsoft Teams](../rooms/rooms-deploy.md)
- [Crear una cuenta de dispositivo Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Después de confirmar que los dispositivos de las salas de Teams y los Surface Hubs pueden aceptar automáticamente reuniones y unirse a ellas correctamente, puede configurar reuniones coordinadas.

Los pasos siguientes deben completarse para cada sala de reuniones por separado. Los dispositivos de una sala de reunión no deben configurarse para reuniones coordinadas con dispositivos de otras salas de reunión.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Paso 1: Planear la experiencia de reuniones coordinadas

Antes de realizar cambios en la configuración, debe decidir qué dispositivos harán qué en cada sala de reunión. Es decir, para una sala de reuniones determinada, necesita decidir qué dispositivo tendrá el micrófono activo, la cámara y la pizarra. La manera de configurar los dispositivos depende de su entorno específico, pero aquí tiene algunas recomendaciones generales con las que empezar:

- **Micrófono** Dispositivo salas de Teams
- **Cámara** Dispositivo Salas de Teams (activado de forma predeterminada) y Surface Hub (desactivado de forma predeterminada, pero que los participantes pueden desactivar)
- **Pizarra interactiva** Surface Hub

> [!IMPORTANT]
> Asegúrese de habilitar el micrófono solo en un dispositivo. Si lo habilita en más de un dispositivo, experimentará eco de audio y comentarios.

## <a name="step-2-get-your-devices-upns"></a>Paso 2: Obtener los UPN de sus dispositivos

Cuando configure una experiencia de reunión coordinada en una sala de reunión, tendrá que decirle a los dispositivos de salas de Teams y a los Surface Hub de esa sala con qué dispositivos coordinar. Para ello, agregue el nombre principal de usuario (UPN) de los dispositivos con los que debe coordinar la configuración. Si no conoce los UPN de cada uno de los dispositivos que desea configurar para reuniones coordinadas, los encontrará en el Centro de administración de Microsoft 365. 

Debe tener asignado un rol de administrador para acceder al Centro de administración de Microsoft 365. Para obtener más información, vea [Acerca de los roles de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

Para obtener los UPN de los dispositivos De salas de Teams y Surface Hub, haga lo siguiente:

1. Visite el centro de administración de Microsoft 365 para iniciar https://admin.microsoft.com sesión.
2. Vaya a **Usuarios**  >  **activos.**
3. Busque el nombre de su dispositivo Salas  de Teams o Surface  Hub en la columna Nombre para mostrar (puede usar el cuadro de búsqueda si tiene muchos usuarios).
4. Busque el UPN en la columna **Nombre de** usuario (tendrá un aspecto parecido a alias@contoso.com o alias@contoso.onmicrosoft.com).
5. Repita este procedimiento para todos los dispositivos que participarán en reuniones coordinadas.

## <a name="step-3-create-a-deployment-worksheet"></a>Paso 3: Crear una hoja de cálculo de implementación

Después de planear la experiencia de reunión coordinada y recopilar una lista de los UPN de los dispositivos, es buena idea crear una hoja de cálculo de implementación. Una hoja de cálculo de implementación le ayudará a visualizar la configuración que desea establecer en todos los dispositivos, lo que le permite validar las opciones y comprobar si hay errores.

En una aplicación de hoja de cálculo, agregue filas para lo siguiente en la primera columna:

| Setting                | Descripción      |
|------------------------|-----------------|
| **Audio predeterminado**      | Determina en qué dispositivo estará activo el micrófono cuando se inicie una reunión. Solo un dispositivo (normalmente un dispositivo de salas de Teams) puede tener este campo establecido, mientras que el resto de los dispositivos deben tener este campo configurado para evitar el eco de audio y `true` `false` los comentarios.          |
| **Audio habilitado**      | Determina si los participantes de una reunión pueden activar o desactivar el micrófono. Los dispositivos **en los** que el audio predeterminado está establecido deben tener esta configuración establecida para que los participantes no puedan activar accidentalmente el micrófono y causar eco de audio `false` o `false` comentarios.<p>Si **el valor predeterminado** de audio es Audio, esta configuración se ignora y los participantes pueden desactivar o activar `true` el micrófono.          |
| **Vídeo predeterminado**      | Determina en qué dispositivo estará activa la cámara cuando se inicia una reunión. Para obtener la mejor experiencia, le recomendamos que solo se establezca el dispositivo salas de Teams mientras el resto de dispositivos `true` estén establecidos `false` en.          |
| **Vídeo habilitado**      | Determina si los participantes de una reunión pueden activar o desactivar la cámara. Puede establecer esta opción en cualquier otro dispositivo en el que los participantes del evento quieran compartir diferentes perspectivas de vídeo (por ejemplo, si un participante usa la pizarra interactiva de `true` Surface Hub). Si no desea que los participantes activen o desactiven una cámara en un dispositivo, establezca esta opción en `false` .<p> Si **el valor predeterminado** del vídeo es `true` Vídeo, esta configuración se ignora y los participantes pueden activar o desactivar la cámara.         |
| **Pizarra predeterminada** | Determina si el dispositivo Salas de Teams mostrará una pizarra compartida por uno de los participantes de la reunión. Te recomendamos que establezcas esta opción si tienes Surface Hub y si `false` `true` no tienes ninguna. Esta configuración no tiene ningún efecto en Surface Hubs. Surface Hubs siempre mostrará una pizarra compartida por los participantes de la reunión.         |
| **Pizarra habilitada** | Determina si los participantes de una reunión pueden activar o desactivar la pizarra. Si no desea que los participantes activen o desactiven la pizarra en un dispositivo, establezca esta opción en `false` . <p>Si el valor predeterminado de Whiteboard es **Whiteboard,** esta configuración se ignora y los participantes pueden activar o desactivar la `true` pizarra.
| **Cuentas de confianza**   | Esta es una lista separada por comas de UPN para cada dispositivo de la sala de Teams o Surface Hub desde el que el dispositivo debe aceptar las solicitudes para unirse a la reunión o desde qué reunión deben enviarse las solicitudes para unirse. |

En las columnas siguientes, agregue cada uno de los dispositivos de Salas de Teams y Surface Hub. En cada columna, rellene los valores que corresponden a la experiencia que desea para la sala de reuniones. Este es un ejemplo con un dispositivo Salas de Teams y un Surface Hub:

- Dispositivo de Teams
  - El audio y el vídeo **se activados** cuando se inicia una reunión. Los participantes **pueden** activar o desactivar el audio y el vídeo.
  - La visualización de una pizarra compartida está desactivada.
- Surface Hub
  - El audio se **desactivará** cuando se inicie una reunión. Los participantes **no pueden activar** o desactivar el audio.
  - El vídeo se **desactivará** cuando se inicie una reunión. Los participantes **pueden** activar o desactivar el vídeo.

| Setting                | Sala de Teams      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audio predeterminado**      | `true`          | `false`          |
| **Audio habilitado**      | `true`          | `false`          |
| **Vídeo predeterminado**      | `true`          | `false`          |
| **Vídeo habilitado**      | `true`          | `true`           |
| **Pizarra predeterminada** | `false`         | `false`          |
| **Cuentas de confianza**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Paso 4: Configurar el dispositivo salas de Teams

Puede configurar reuniones coordinadas en un dispositivo de salas de Teams con la pantalla táctil del dispositivo o, si necesita configurar varios dispositivos y desea hacerlo desde una ubicación central, puede usar un archivo de configuración XML.

Use la hoja de cálculo que creó en el paso anterior para ayudarle a configurar los dispositivos.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usar la pantalla táctil del dispositivo Salas de Teams

Para configurar reuniones coordinadas en un dispositivo, haga lo siguiente:

1. **Seleccione... Más**  >  **opciones de configuración.**
2. Escriba la contraseña de administrador y seleccione **Sí.**
3. Seleccione **Reuniones coordinadas.**
4. En **Opciones,** establezca **Reunión coordinada** en _On._
5. Si **el valor predeterminado de audio** en la hoja de cálculo es , establezca activar el micrófono de este dispositivo, de lo `true` contrario,  déjelo _desactivado._
6. Si **el audio está habilitado** en la hoja de cálculo, seleccione Permitir que las personas habiliten al unirse a una reunión en Activar el micrófono de este `true` **dispositivo.**  Esta opción no se puede desactivar si **activar** el micrófono de este dispositivo está activado.
7. Si **el vídeo predeterminado** en la hoja de cálculo está establecido, establezca activar la cámara de este dispositivo, de lo `true` contrario, déjelo  _desactivado._
8. Si **el vídeo habilitado** en la hoja de cálculo está habilitado, seleccione Permitir que las personas habiliten al unirse a una reunión en Activar la `true` **cámara de este dispositivo.**  Esta opción no se puede desactivar si Activar la cámara **de** este dispositivo está establecida en _Activado._
9. Si **el valor predeterminado de Whiteboard** en la hoja de cálculo es Activar pizarra en este dispositivo, de lo `true` contrario,  déjelo  _desactivado._
10. En **Cuentas de dispositivo de confianza,** escriba cada UPN que aparezca en cuentas de **confianza** en la hoja de cálculo. Separe los upN múltiples con comas.
11. Seleccione **Guardar y salir.**

Después de seleccionar **Guardar y salir,** el dispositivo se reiniciará y estará listo para participar en reuniones coordinadas.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usar el archivo de configuración XML de salas de Teams

Las reuniones coordinadas se pueden configurar con el archivo de configuración XML del dispositivo Salas `SkypeSettings.xml` de Teams. El `SkypeSettings.xml` archivo no es un archivo estático. Cuando se inicia el dispositivo Salas de Teams, comprueba `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` si hay un archivo `SkypeSettings.xml` denominado. Si el archivo existe, el dispositivo lee y aplica la configuración especificada en el archivo. Una vez que haya terminado de aplicar la configuración, el archivo se elimina. Para obtener más información sobre el `SkypeSettings.xml` archivo, vea [Administrar la configuración de la consola con un archivo de configuración XML.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

La siguiente es la sintaxis de la configuración Reuniones coordinadas en el archivo de configuración:

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

1. En un editor de archivos de texto, como Visual Studio Código o Bloc de notas, pegue el XML anterior en un archivo nuevo.

2. Establezca cada uno de los elementos XML en el valor `true` o correspondiente de la hoja de `false` cálculo. Por ejemplo, si **el valor predeterminado de audio** es , `true` `<Audio default="true">` establecido.

3. Asegúrese de cambiar `TrustedAccounts` a la lista de UPN.

4. Guarde el archivo con el `SkypeSettings.xml` nombre.

5. Coloque el archivo en la carpeta del dispositivo Salas de `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` Teams. Puede hacerlo de varias maneras:

    - **Copiar el archivo en el dispositivo salas de Teams** Debe habilitar el uso compartido de archivos y crear un recurso compartido de red para poder copiar archivos en el dispositivo. Después de hacerlo, puede conectarse al recurso compartido de red y copiar el archivo en el dispositivo. Para obtener más información, consulte operaciones y mantenimiento de salas [de Microsoft Teams.](../rooms/rooms-operations.md)
    - **Usar una directiva de grupo** Cree una directiva de grupo para copiar el archivo en el dispositivo. Para obtener más información, vea [Introducción a la directiva de grupo.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Descargar el archivo en el dispositivo salas de Teams** Puede iniciar sesión en el dispositivo con el modo de administración y, a continuación, copiar el archivo en el dispositivo desde un recurso compartido de red o una unidad USB. Para obtener más información, [vea Cambiar al modo de administración.](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)
    
6. Reinicie el dispositivo. Puede hacerlo de varias maneras:

    - **PowerShell remoto** Puede ejecutar el comando Desconexión en el dispositivo con PowerShell remoto. Para obtener más información, [vea Administración remota con PowerShell.](../rooms/rooms-operations.md)
    - **Ejecutar Reiniciar-Equipo** Puede ejecutar el cmdlet en el equipo local y especificar el nombre del equipo `Restart-Computer` del dispositivo que quiere reiniciar. Para obtener más información, [vea Reiniciar-Equipo.](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)

## <a name="step-5-configure-surface-hub"></a>Paso 5: Configurar Surface Hub

Puedes usar el Diseñador de configuración de Windows para crear un paquete de aprovisionamiento que puedes usar para aplicar la configuración Reuniones coordinadas a tus Surface Hubs. Pegará el archivo XML que creó anteriormente en el Diseñador de configuración de Windows para crear el paquete de aprovisionamiento.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Crear un archivo de configuración XML de reuniones coordinadas para Surface Hub

Tanto el Diseñador de configuración de Windows como Microsoft Intune se usan para aplicar la configuración reuniones coordinadas a sus Surface Hubs. La configuración se define mediante XML. Antes de continuar, debe crear el XML que se aplicará.

La siguiente es la sintaxis del archivo de configuración XML Reuniones coordinadas.

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

Haga lo siguiente para preparar el XML para el Diseñador de configuración de Windows o Microsoft Intune:

1. En un editor de archivos de texto, como Visual Studio Código o Bloc de notas, pegue el XML anterior en un archivo nuevo.

2. Establezca cada uno de los elementos XML en el valor `true` o correspondiente de la hoja de `false` cálculo. Por ejemplo, si **el valor predeterminado de audio** es , `true` `<Audio default="true">` establecido.

3. Asegúrese de cambiar `TrustedAccounts` a la lista de UPN.

4. El Diseñador de configuración de Windows requiere que el XML esté en una sola línea. Quite todos los saltos de línea entre cada línea para que el XML sea similar al siguiente:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Guarde el archivo en el equipo.

Una vez que hayas creado el archivo de configuración XML, usa los pasos de Administrar la configuración de Microsoft Teams en [Surface Hub](surface-hub-manage-config.md) para aplicarlo a tus Surface Hubs.

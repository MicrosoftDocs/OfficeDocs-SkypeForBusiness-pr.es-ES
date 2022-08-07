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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Configura Salas de Teams dispositivos y Surface Hub para que se unan a reuniones cuando un dispositivo u otro se una a una reunión.
ms.openlocfilehash: f34e3637c9c9716c6f8ec87865c3c570820a0357
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270485"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurar reuniones coordinadas con Salas de Microsoft Teams y Surface Hub

Si tiene uno o más dispositivos Salas de Microsoft Teams o Surface Hub en una sala de reuniones, puede configurar Reuniones coordinadas. Reuniones coordinadas le permite configurar sus dispositivos Salas de Teams y Surface Hubs para que, cuando se una a una reunión en un dispositivo, los demás dispositivos de la sala también se unan a la misma reunión. Puedes configurar las cámaras, los altavoces y los micrófonos para que los que proporcionen a los participantes la mejor experiencia se habiliten mientras que los demás estén deshabilitados. Esto evita el temido eco y los participantes del ruido de comentarios pueden experimentar al agregar varios dispositivos a una reunión.

Para configurar reuniones coordinadas, debe asegurarse de que sus dispositivos de Salas de Teams y Surface Hub ya están configurados correctamente para participar en las reuniones. Lo más importante es que cada dispositivo debe tener su propio buzón de exchange. Para obtener información sobre cómo configurarlos, consulte los artículos siguientes:

- [Implementar Salas de Microsoft Teams](../rooms/rooms-deploy.md)
- [Crear una cuenta de dispositivo Surface Hub 2S](/surface-hub/surface-hub-2s-account)

Después de confirmar que los dispositivos Salas de Teams y Surface Hub pueden aceptar automáticamente reuniones y unirse a ellas correctamente, puede configurar Reuniones coordinadas.

Los pasos siguientes deben completarse por separado para cada sala de reuniones.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Paso 1: Planear la experiencia de reunión coordinada

Antes de realizar los cambios de configuración, debe decidir qué dispositivos harán qué en cada sala de reuniones. Es decir, para una sala de reuniones determinada, debe decidir qué dispositivo tendrá el micrófono, la cámara y la pizarra activos. La forma de configurar los dispositivos depende de tu entorno específico, pero estas son algunas recomendaciones generales con las que empezar:

- **Micrófono** Salas de Teams dispositivo
- **Cámara** Salas de Teams dispositivo (activado de forma predeterminada) y Surface Hub (desactivado de forma predeterminada, pero permitido que los participantes lo activen)
- **Pizarra** Surface Hub

> [!IMPORTANT]
> Asegúrate de habilitar el micrófono solo en un dispositivo. Si lo habilita en más de un dispositivo, experimentará eco de audio y comentarios.

## <a name="step-2-get-your-devices-upns"></a>Paso 2: Obtener los UPN de los dispositivos

Al configurar una experiencia de reunión coordinada en una sala de reuniones, necesita indicar a los dispositivos Salas de Teams y Surface Hub de esa sala con qué dispositivos coordinar. Para ello, agregue el nombre principal de usuario (UPN) de los dispositivos con los que debe coordinarse a su configuración. Si no conoce los UPN de cada uno de los dispositivos que desea configurar para reuniones coordinadas, puede encontrarlos con la Centro de administración de Microsoft 365. 

Debe tener asignado un rol de administrador para acceder a la Centro de administración de Microsoft 365. Para obtener más información, vea [Acerca de los roles de administrador](/microsoft-365/admin/add-users/about-admin-roles).

Para obtener los UPN de tus dispositivos Salas de Teams y Surface Hubs, haz lo siguiente:

1. Inicia sesión en la Centro de administración de Microsoft 365 visitando https://admin.microsoft.com.
2. Vaya a **Usuarios** > **activos**.
3. Busca el nombre de tu dispositivo Salas de Teams o Surface Hub en la columna **Nombre para mostrar** (puedes usar el cuadro **de búsqueda** si tienes muchos usuarios).
4. Busque el UPN en la columna **Nombre de usuario** (tendrá un aspecto parecido a alias@contoso.com o alias@contoso.onmicrosoft.com).
5. Repita este procedimiento para cada dispositivo que participará en reuniones coordinadas.

## <a name="step-3-create-a-deployment-worksheet"></a>Paso 3: Crear una hoja de cálculo de implementación

Una vez que haya planeado la experiencia de reunión coordinada y recopilado una lista de los UPN de sus dispositivos, es una buena idea crear una hoja de cálculo de implementación. Una hoja de cálculo de implementación le ayudará a visualizar la configuración que desea establecer en todos los dispositivos, lo que le permite validar las opciones y comprobar si hay errores.

En una aplicación de hoja de cálculo, agregue filas para lo siguiente en la primera columna:

| Setting                | Descripción      |
|------------------------|-----------------|
| **Audio predeterminado**      | Determina en qué dispositivo estará activo el micrófono cuando se inicie una reunión. Solo un dispositivo (normalmente un dispositivo de Salas de Teams) puede tener este campo establecido`true`, mientras que el resto de los dispositivos deben tener este campo configurado para `false` evitar el eco de audio y los comentarios.          |
| **Audio habilitado**      | Determina si los participantes de una reunión pueden activar o desactivar el micrófono. Los dispositivos en los que el **valor predeterminado de Audio** esté establecido `false` deberían tener esta configuración establecida para `false` que los participantes no puedan activar accidentalmente un micrófono y generar eco de audio o comentarios.<p>Si **audio predeterminado** está establecido en `true`, esta configuración se ignora y los participantes pueden silenciar o reactivar el micrófono.          |
| **Vídeo predeterminado**      | Determina en qué dispositivo estará activa la cámara cuando se inicie una reunión. Para obtener la mejor experiencia, recomendamos que solo se establezca `true` el dispositivo Salas de Teams mientras que el resto de dispositivos estén establecidos en `false`.          |
| **Vídeo habilitado**      | Determina si los participantes de una reunión pueden activar o desactivar la cámara. Puedes establecerlo `true` en cualquier otro dispositivo del evento en el que los participantes quieran compartir diferentes perspectivas del vídeo (por ejemplo, si un participante usa la pizarra interactiva de Surface Hub). Si no desea que los participantes activen o desactiven una cámara en un dispositivo, establezca esta opción `false`en .<p> Si **el valor predeterminado del vídeo** es `true`, esta configuración se ignora y los participantes pueden activar o desactivar la cámara.         |
| **Pizarra predeterminada** | Determina si el dispositivo de Salas de Teams mostrará una pizarra compartida por uno de los participantes de la reunión. Te recomendamos que establezcas esta opción en `false` si tienes un Surface Hub y `true` si no tienes ninguna. Esta configuración no tiene ningún efecto en Surface Hubs. Los Surface Hub siempre mostrarán una pizarra compartida por los participantes de la reunión.         |
| **Pizarra habilitada** | Determina si los participantes de una reunión pueden activar o desactivar la pizarra interactiva. Si no desea que los participantes activen o desactiven la pizarra en un dispositivo, establezca esta opción `false`en . <p>Si **el valor predeterminado de Whiteboard** es `true`, esta configuración se ignora y los participantes pueden activar o desactivar la pizarra.
| **Cuentas de confianza**   | Esta es una lista de UPN separados por comas para cada dispositivo de sala de Teams o Surface Hub desde la que el dispositivo debe aceptar convocatorias de unión a una reunión, o a la que se deben enviar convocatorias de unión a la reunión. |

En las columnas siguientes, agrega cada uno de los dispositivos Salas de Teams y Surface Hub. En cada columna, rellene los valores que correspondan a la experiencia que desee para la sala de reuniones. Este es un ejemplo con un dispositivo Salas de Teams y un Surface Hub:

- Dispositivo de Teams
  - El audio y el vídeo se **activan** cuando se inicia una reunión. Los participantes **pueden** activar o desactivar el audio y el vídeo.
  - La visualización de una pizarra compartida está desactivada.
- Surface Hub
  - El audio se **desactiva** cuando se inicia una reunión. Los participantes **no pueden** activar o desactivar el audio.
  - El vídeo se **desactiva** cuando se inicia una reunión. Los participantes **pueden** activar o desactivar el vídeo.

| Setting                | Sala de Teams      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audio predeterminado**      | `true`          | `false`          |
| **Audio habilitado**      | `true`          | `false`          |
| **Vídeo predeterminado**      | `true`          | `false`          |
| **Vídeo habilitado**      | `true`          | `true`           |
| **Pizarra predeterminada** | `false`         | `false`          |
| **Cuentas de confianza**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Paso 4: Configurar Salas de Teams dispositivo

Puede configurar reuniones coordinadas en un dispositivo Salas de Teams mediante la pantalla táctil del dispositivo o, si necesita configurar muchos dispositivos y desea hacerlo desde una ubicación central, puede usar un archivo de configuración XML.

Use la hoja de cálculo que creó en el paso anterior para ayudarle a configurar los dispositivos.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usar la pantalla táctil del dispositivo Salas de Teams

Para configurar reuniones coordinadas en un dispositivo, haga lo siguiente:

1. Seleccione **... Más** > **opciones de configuración**.
2. Escriba la contraseña de administrador y seleccione **Sí**.
3. Seleccione **Reuniones coordinadas**.
4. En **Opciones**, establezca **Reunión coordinada** _en Activado_.
5. Si **audio predeterminado** en la hoja de cálculo es `true`, establezca **Activar el micrófono de este dispositivo** en activado, de lo contrario, _déjelo desactivado_.
6. Si **El audio habilitado** en la hoja de cálculo es `true`, seleccione **Permitir que los usuarios habiliten al unirse a una reunión** **en Activar el micrófono de este dispositivo**. Esta opción no se puede desactivar si **Activar el micrófono de este dispositivo** está activado.
7. Si **El vídeo predeterminado** en la hoja de cálculo es `true`, establezca **Activar la cámara de este dispositivo** en activado, de lo contrario, _déjelo desactivado_.
8. Si **El vídeo habilitado** en la hoja de cálculo es `true`, seleccione **Permitir que los usuarios habiliten al unirse a una reunión** **en Activar la cámara de este dispositivo**. Esta opción no se puede desactivar si **Activar la cámara de este dispositivo** está _activada_.
9. Si **whiteboard predeterminado** en la hoja de cálculo es `true`, establezca **Activar pizarra en este dispositivo** _en activado_, de lo contrario, _déjela desactivada_.
10. En **Cuentas de dispositivo de confianza**, escriba cada UPN que aparece en **Cuentas de confianza** en la hoja de cálculo. Separe varios UPN con comas.
11. En el dispositivo de confianza, desactive la proximidad y el mando a distancia de la sala. 
12. Seleccione **Guardar y salir**.

Después de seleccionar **Guardar y salir**, el dispositivo se reiniciará y estará listo para participar en reuniones coordinadas.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usar el archivo de configuración XML de Salas de Teams

Las reuniones coordinadas se pueden configurar mediante el archivo de configuración XML del `SkypeSettings.xml` dispositivo Salas de Teams. El `SkypeSettings.xml` archivo no es un archivo estático. Cuando se inicia el dispositivo Salas de Teams, comprueba `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` si hay un archivo denominado `SkypeSettings.xml`. Si el archivo existe, el dispositivo lee y aplica la configuración especificada en el archivo. Cuando haya terminado de aplicar la configuración, el archivo se elimina. Para obtener más información sobre el archivo, vea [Administrar la configuración de la](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)`SkypeSettings.xml` consola con un archivo de configuración XML.

La siguiente es la sintaxis de la configuración de Reuniones coordinadas en el archivo de configuración:

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

1. En un editor de archivos de texto, como Visual Studio Code o bloc de notas, pegue el XML anterior en un archivo nuevo.

2. Establezca cada uno de los elementos XML en el valor o `false` el correspondiente `true` en la hoja de cálculo. Por ejemplo, si **audio predeterminado** es `true`, establezca `<Audio default="true">`.

3. Asegúrese de cambiar `TrustedAccounts` a la lista de UPN.

4. Guarde el archivo con el nombre `SkypeSettings.xml`.

5. Coloque el archivo en la carpeta del dispositivo de `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` Salas de Teams. Puede hacerlo de varias maneras:

    - **Copiar el archivo en el dispositivo Salas de Teams** Deberá habilitar el uso compartido de archivos y crear un recurso compartido de red para poder copiar archivos en el dispositivo. Después de hacerlo, puedes conectarte al recurso compartido de red y copiar el archivo en el dispositivo. Para obtener más información, vea [Salas de Microsoft Teams mantenimiento y operaciones](../rooms/rooms-operations.md).
    - **Usa una directiva de grupo** Crear una directiva de grupo para copiar el archivo en el dispositivo. Para obtener más información, vea [Directiva de grupo Información general](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Descargar el archivo en el dispositivo Salas de Teams** Puede iniciar sesión en el dispositivo con el modo Administración y, a continuación, copiar el archivo en el dispositivo desde un recurso compartido de red o una unidad USB. Para obtener más información, consulte [Cambiar al modo Administración](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Reinicia el dispositivo. Puede hacerlo de dos maneras:

    - **PowerShell remoto** Puede ejecutar el comando Shutdown en el dispositivo con Remote PowerShell. Para obtener más información, consulte [Administración remota con PowerShell](../rooms/rooms-operations.md).
    - **Ejecutar Reiniciar equipo** Puede ejecutar el cmdlet en el `Restart-Computer` equipo local y especificar el nombre del equipo del dispositivo que desea reiniciar. Para obtener más información, consulta [Reiniciar equipo](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Paso 5: Configurar Surface Hub

Puedes usar el Diseñador de configuración de Windows para crear un paquete de aprovisionamiento que puedes usar para aplicar la configuración de Coordinación de reuniones a surface hubs. Pegará el archivo XML que creó anteriormente en el Diseñador de configuración de Windows para crear el paquete de aprovisionamiento.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Crear un archivo de configuración XML de reuniones coordinadas para Surface Hub

Diseñador de configuración de Windows y Microsoft Intune se usan para aplicar la configuración de Reuniones coordinadas a surface hubs. La configuración se define mediante XML. Antes de ir más allá, debe crear el XML que se aplicará.

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

Siga este procedimiento para preparar el XML para el Diseñador de configuración de Windows o Microsoft Intune:

1. En un editor de archivos de texto, como Visual Studio Code o bloc de notas, pegue el XML anterior en un archivo nuevo.

2. Establezca cada uno de los elementos XML en el valor o `false` el correspondiente `true` en la hoja de cálculo. Por ejemplo, si **audio predeterminado** es `true`, establezca `<Audio default="true">`.

3. Asegúrese de cambiar `TrustedAccounts` a la lista de UPN.

4. El Diseñador de configuración de Windows requiere que el XML esté en una sola línea. Quite todos los saltos de línea entre cada línea para que el ARCHIVO XML tenga el siguiente aspecto:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Guarde el archivo en el equipo.

Después de crear el archivo de configuración XML, sigue los pasos de [Administrar la configuración de Microsoft Teams en Surface Hub](surface-hub-manage-config.md) para aplicarlo a Surface Hub.

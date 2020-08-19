---
title: Configurar reuniones coordinadas con Microsoft Team salas y Surface Hub
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
description: Configure los dispositivos de salas de equipos y Surface hub para que se unan a las reuniones cuando un dispositivo o el otro se unan a una reunión.
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803942"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Configurar reuniones coordinadas con Microsoft Team salas y Surface Hub

Si tiene uno o varios dispositivos de Microsoft Team Rooms o Surface Hub en una sala de reuniones, puede configurar reuniones coordinadas. Reuniones coordinadas le permite configurar los dispositivos de salas de equipos y Surface hub para que cuando se una a una reunión en un dispositivo, los otros dispositivos del salón también se unan a la misma reunión. Puede configurar las cámaras, los altavoces y los micrófonos de modo que los que proporcionen a los participantes tengan la mejor experiencia habilitada mientras otros están deshabilitados. Esto evita los temidos participantes de eco y retroalimentación que pueden experimentar al agregar varios dispositivos a una reunión.

Para configurar reuniones coordinadas, debe asegurarse de que los dispositivos de salas de salas de equipos y Surface Hub ya están configurados correctamente para participar en reuniones. Lo más importante es que cada dispositivo debe tener su propio buzón de sala de Exchange. Para obtener información sobre cómo configurarlos, vea los artículos siguientes:

- [Implementar Salas de Microsoft Teams](../rooms/rooms-deploy.md)
- [Crear cuenta de dispositivo de Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Después de confirmar que los dispositivos de las salas de reuniones de su equipo y los Surface Hub pueden aceptar reuniones automáticamente y unirse a ellas correctamente, puede configurar reuniones coordinadas.

Debe completar los pasos siguientes para cada sala de reunión por separado. Los dispositivos de una sala de reuniones no deberían estar configurados para reuniones coordinadas con dispositivos de otras salas de reuniones.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Paso 1: planear la experiencia de reunión coordinada

Antes de realizar cambios en la configuración, debe decidir qué dispositivos harán qué en cada sala de reuniones. Es decir, para una sala de reuniones determinada, debe decidir qué dispositivo tendrá el micrófono, la cámara y la pizarra activos. La configuración de los dispositivos depende de su entorno específico, pero a continuación le ofrecemos algunas recomendaciones generales para empezar:

- **Micrófono** Dispositivo salas de equipos
- **Cámara** Dispositivo salas de equipos (activada de forma predeterminada) y Surface Hub (desactivada de forma predeterminada, pero permitida por los participantes)
- **Pizarra** Surface Hub

> [!IMPORTANT]
> Asegúrese de habilitar el micrófono solo en un dispositivo. Si lo habilitas en más de un dispositivo, disfrutarás de eco y comentarios de audio.

## <a name="step-2-get-your-devices-upns"></a>Paso 2: obtener los UPN de sus dispositivos

Al configurar una experiencia de reunión coordinada en una sala de reuniones, debe contar los dispositivos de las salas de la sala y los Surface Hub en los que se coordinan los dispositivos. Esto se realiza agregando el nombre principal de usuario (UPN) de los dispositivos con los que debe coordinarse la configuración. Si no conoce los UPN de cada uno de los dispositivos que desea configurar para las reuniones coordinadas, puede encontrarlos en el centro de administración de Microsoft 365. 

Para obtener acceso al centro de administración de Microsoft 365, debe tener asignado un rol de administrador. Para obtener más información, consulte [acerca de los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

Para obtener los UPN de sus dispositivos de salas de sala de equipos y Surface Hub, haga lo siguiente:

1. Para iniciar sesión en el centro de administración de Microsoft 365, visite https://admin.microsoft.com .
2. Vaya a **usuarios**  >  **activos**.
3. Busque el nombre del dispositivo de salas de las salas de equipos o del concentrador de Surface en la columna **nombre para mostrar** (puede usar el cuadro de **búsqueda** si tiene muchos usuarios).
4. Busque el UPN en la columna **username** (tendrá un aspecto similar a alias@contoso.com o alias@contoso.onmicrosoft.com).
5. Repita este paso para cada dispositivo que vaya a participar en reuniones coordinadas.

## <a name="step-3-create-a-deployment-worksheet"></a>Paso 3: crear una hoja de cálculo de implementación

Una vez planeada su experiencia de reunión coordinada y recopilada una lista de los UPN de sus dispositivos, es una buena idea crear una hoja de cálculo de implementación. Una hoja de cálculo de implementación le ayudará a visualizar la configuración que desea establecer en todos los dispositivos, lo que le permitirá validar las opciones y comprobar si hay errores.

En una aplicación de hoja de cálculo, agregue las filas siguientes en la primera columna:

| Setting                | Descripción      |
|------------------------|-----------------|
| **Valor predeterminado de audio**      | Determina en qué dispositivo estará activo el micrófono cuando se inicie una reunión. Solo un dispositivo (generalmente un dispositivo de salas de equipos) puede tener este campo establecido en `true` mientras que el resto de los dispositivos debe tener este campo establecido en `false` para evitar el eco y la retroalimentación de audio.          |
| **Audio habilitado**      | Determina si los participantes de una reunión pueden activar o desactivar el micrófono. Los dispositivos en los que se establece el **valor predeterminado de audio** `false` deben tener esta configuración establecida en para `false` que los participantes no puedan activar accidentalmente un micrófono y causar eco o comentarios de audio.<p>Si se establece el **valor predeterminado de audio** `true` , se omite esta configuración y los participantes pueden desactivar o reactivar el micrófono.          |
| **Valor predeterminado de vídeo**      | Determina el dispositivo en el que la cámara estará activa cuando se inicie una reunión. Para obtener la mejor experiencia, le recomendamos que solo se establezca el dispositivo salas de equipos `true` mientras todos los demás dispositivos están configurados en `false` .          |
| **Vídeo habilitado**      | Determina si los participantes de una reunión pueden activar o desactivar la cámara. Puede establecer esta configuración en `true` en cualquier otro dispositivo de los participantes del evento que deseen compartir diferentes perspectivas de vídeo (como si un participante usa la pizarra de Surface hub). Si no desea que los participantes enciendan o apaguen una cámara en un dispositivo, establezca este valor en `false` .<p> Si el **valor predeterminado de vídeo** se establece en `true` , esta configuración se omite y los participantes pueden activar o desactivar la cámara.         |
| **Pizarra predeterminada** | Determina si el dispositivo salas de equipos mostrará una pizarra compartida por uno de los participantes de la reunión. Le recomendamos que establezca esta configuración en `false` si tiene un Surface Hub y `true` no tiene uno. Esta configuración no tiene efecto en Surface Hub. Surface Hub siempre mostrará una pizarra compartida por los participantes de la reunión.         |
| **Pizarra habilitada** | Determina si los participantes de una reunión pueden activar o desactivar la pizarra. Si no desea que los participantes puedan activar o desactivar la pizarra en un dispositivo, establezca este valor en `false` . <p>Si la opción **predeterminada de whiteboard** está configurada en `true` , esta configuración se ignora y los participantes pueden activar o desactivar la pizarra.
| **Cuentas de confianza**   | Esta es una lista separada por comas de UPN para cada dispositivo de la sala de equipos o Surface Hub en el que el dispositivo debe aceptar solicitudes de participación en la reunión de, o a las que se deben enviar solicitudes de unirse a la reunión. |

En las columnas siguientes, agregue cada uno de los dispositivos de las salas de equipos y Surface Hub. En cada columna, rellene los valores que correspondan a la experiencia que desea para la sala de reuniones. Este es un ejemplo con un dispositivo de salas de equipos y un Surface Hub:

- Dispositivo de Teams
  - El audio y el vídeo **se activan cuando se** inicia una reunión. Los participantes **pueden** activar o desactivar el audio y el vídeo.
  - Mostrar una pizarra compartida está desactivado.
- Surface Hub
  - El audio se **desactiva cuando se** inicia una reunión. Los participantes **no pueden** activar o desactivar el audio.
  - El vídeo se **desactiva cuando se** inicia una reunión. Los participantes **pueden** activar o desactivar el vídeo.

| Setting                | Sala de equipos      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Valor predeterminado de audio**      | `true`          | `false`          |
| **Audio habilitado**      | `true`          | `false`          |
| **Valor predeterminado de vídeo**      | `true`          | `false`          |
| **Vídeo habilitado**      | `true`          | `true`           |
| **Pizarra predeterminada** | `false`         | `false`          |
| **Cuentas de confianza**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Paso 4: configurar el dispositivo salas de equipo

Puede configurar reuniones coordinadas en un dispositivo de salas de equipos con la pantalla táctil del dispositivo o, si necesita configurar muchos dispositivos y desea hacerlo desde una ubicación central, puede usar un archivo de configuración XML.

Use la hoja de cálculo que creó en el paso anterior para ayudarle a configurar los dispositivos.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Usar la pantalla táctil del dispositivo de las salas de equipos

Para configurar reuniones coordinadas en un dispositivo, haga lo siguiente:

1. Seleccione **... Más**  >  **Opciones de configuración**.
2. Escriba la contraseña de administrador y seleccione **sí**.
3. Seleccione **reuniones coordinadas**.
4. En **Opciones**, establezca **reunión coordinada** en _activado_.
5. Si el **valor predeterminado de audio** de la hoja de cálculo es `true` , **activa activar el micrófono de este dispositivo** , de lo contrario, dejarlo _desactivado_.
6. Si el **audio habilitado** en la hoja de cálculo es `true` , seleccione **permitir que los usuarios puedan habilitar al unirse a una reunión** en **activar el micrófono de este dispositivo**. Esta opción no se puede desactivar si **activa el micrófono de este dispositivo** .
7. Si el **vídeo predeterminado** de la hoja de cálculo es `true` , **Active la cámara del dispositivo** como activado; de lo contrario, déjelo como _desactivado_.
8. Si el **vídeo está habilitado** en la hoja de cálculo `true` , seleccione **permitir que los usuarios puedan habilitar al unirse a una reunión** en **activar la cámara de este dispositivo**. Esta opción no se puede desactivar si **activa la cámara de este dispositivo** _._
9. Si la **pizarra predeterminada** de la hoja de cálculo es `true` , **Active la pizarra en este dispositivo** como _activado; de_lo contrario, déjelo _desactivado_.
10. En **cuentas de dispositivos de confianza**, escriba los UPN que aparecen en **cuentas de confianza** en la hoja de cálculo. Separa varios UPN con comas.
11. Seleccione **Guardar y salir**.

Después de seleccionar **Guardar y salir**, el dispositivo se reiniciará y estará listo para participar en reuniones coordinadas.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Usar el archivo de configuración XML de Team Rooms

Las reuniones coordinadas se pueden configurar con el archivo de configuración XML del dispositivo de las salas de equipos `SkypeSettings.xml` . El `SkypeSettings.xml` archivo no es un archivo estático. Cuando se inicia el dispositivo salas de equipos, se busca `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` un archivo denominado `SkypeSettings.xml` . Si el archivo existe, el dispositivo lee y aplica la configuración especificada en el archivo. Una vez que haya terminado de aplicar la configuración, el archivo se eliminará. Para obtener más información sobre el `SkypeSettings.xml` archivo, vea [administrar la configuración de la consola con un archivo de configuración XML](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

Esta es la sintaxis de la configuración de reuniones coordinadas en el archivo de configuración:

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

1. En un editor de archivos de texto, como el código de Visual Studio o el Bloc de notas, pegue el código XML anterior en un archivo nuevo.

2. Establezca cada uno de los elementos XML en el correspondiente `true` o `false` en el valor de la hoja de cálculo. Por ejemplo, si el **valor predeterminado de audio** es `true` , establezca `<Audio default="true">` .

3. Asegúrese de cambiar `TrustedAccounts` a la lista de UPN.

4. Guarde el archivo con el nombre `SkypeSettings.xml` .

5. Coloque el archivo en la carpeta del dispositivo de salas de equipos `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Puede hacerlo de varias maneras:

    - **Copie el archivo en el dispositivo salas de equipos** Deberás habilitar el uso compartido de archivos y crear un recurso compartido de red antes de poder copiar archivos en tu dispositivo. Después de hacerlo, puede conectarse al recurso compartido de red y copiarlo en el dispositivo. Para obtener más información, vea [mantenimiento y operaciones de salas de Microsoft Teams](../rooms/rooms-operations.md).
    - **Usar una directiva de grupo** Crear una directiva de grupo para copiar el archivo en el dispositivo. Para obtener más información, consulte [Introducción a la Directiva de grupo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Descargar el archivo en el dispositivo de salas de equipos** Puede iniciar sesión en el dispositivo con el modo de administrador y, a continuación, copiar el archivo en el dispositivo desde un recurso compartido de red o una unidad USB. Para obtener más información, vea [cambiar al modo de administrador](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Reinicie el dispositivo. Puede hacerlo de varias maneras:

    - **PowerShell remoto** Puede ejecutar el comando shutdown en el dispositivo mediante PowerShell remoto. Para obtener más información, vea [administración remota con PowerShell](../rooms/rooms-operations.md).
    - **Ejecutar restart-Computer** Puede ejecutar el `Restart-Computer` cmdlet en su equipo local y especificar el nombre del equipo del dispositivo que desea reiniciar. Para obtener más información, consulte [restart-Computer](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Paso 5: configurar Surface Hub

Puede usar el diseñador de configuración de Windows para crear un paquete de aprovisionamiento que puede usar para aplicar la configuración de coordinación de reuniones a Surface Hub. Pegará el archivo XML que ha creado anteriormente en el diseñador de configuración de Windows para crear el paquete de aprovisionamiento.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Crear un archivo de configuración XML de reuniones coordinadas para Surface Hub

Tanto el diseñador de configuración de Windows como Microsoft Intune se usan para aplicar la configuración de reuniones coordinadas a sus Surfaceistas. La configuración se define mediante XML. Antes de ir más allá, debe crear el XML que se aplicará.

A continuación se encuentra la sintaxis del archivo de configuración XML de reuniones coordinadas.

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

Siga este procedimiento para preparar el diseñador de configuración de XML para Windows o Microsoft Intune:

1. En un editor de archivos de texto, como el código de Visual Studio o el Bloc de notas, pegue el código XML anterior en un archivo nuevo.

2. Establezca cada uno de los elementos XML en el correspondiente `true` o `false` en el valor de la hoja de cálculo. Por ejemplo, si el **valor predeterminado de audio** es `true` , establezca `<Audio default="true">` .

3. Asegúrese de cambiar `TrustedAccounts` a la lista de UPN.

4. El diseñador de configuración de Windows requiere que el código XML esté en una sola línea. Quite todos los saltos de línea entre las líneas para que el código XML tenga el siguiente aspecto:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Guarde el archivo en el equipo.

Una vez que haya creado el archivo de configuración XML, siga los pasos que se indican en [administrar la configuración de Microsoft Teams en Surface Hub](surface-hub-manage-config.md) para aplicarlo a sus Surface hubs.

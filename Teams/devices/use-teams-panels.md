---
title: Cómo usar dispositivos de paneles de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: Este artículo proporciona instrucciones sobre cómo usar dispositivos de paneles de Teams.
ms.openlocfilehash: f9d67ce6c41e351239457edc4a605964c7bcae27
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268445"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Cómo usar paneles de Microsoft Teams

Los paneles de Microsoft Teams son dispositivos de pantalla digital compactos que se monta justo fuera de los espacios de reunión, normalmente junto a las entradas. Estos paneles táctiles son dispositivos de Microsoft Teams dedicados que ofrecen una vista rápida del espacio de la reunión y la reunión programada. Con los vibrantes indicadores led codificados por colores e indicadores de pantalla de inicio, puedes determinar si el espacio está disponible o reservado desde una distancia. Puede usar paneles de Teams para reservar un espacio de reunión disponible para una reunión ad hoc, en el lugar.

Los dispositivos de paneles de Teams vienen preinstalados con Microsoft Teams y muestran los detalles de las reuniones que se programan a través de los calendarios de Outlook o Teams.

En este artículo se proporciona orientación, tanto a los usuarios finales como a los administradores, sobre cómo usar los dispositivos de paneles de Teams. También proporciona respuestas a las [preguntas más frecuentes](#frequently-asked-questions) sobre el uso de estos dispositivos.

Para obtener información general sobre los dispositivos de paneles y las instrucciones sobre cómo planificarlos, entregarlos y administrarlos en su organización, consulte [Implementar paneles de Microsoft Teams](teams-panels.md).

Para un inicio rápido, consulte [Introducción a los paneles de Teams](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be).

## <a name="teams-panels-end-user-experience"></a>Experiencia de los paneles de Teams para el usuario final

Explore la [pantalla inicio](#explore-teams-panels-home-screen) de su dispositivo de paneles de Teams para ver los detalles del espacio de reunión y la reunión. O bien, pulsa y desplázate por el panel de pantalla táctil para realizar otras acciones.

Use los dispositivos de paneles de Teams para:

- [Ver los detalles y la disponibilidad del espacio de la reunión, los detalles de la reunión, las próximas reservas](#explore-teams-panels-home-screen)
- [Reservar un espacio de reunión disponible](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Informar de un problema](#report-a-problem)
- [Ver o actualizar la configuración de un dispositivo](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Explorar la pantalla principal de los paneles de Teams

La pantalla Inicio es la interfaz visual principal del dispositivo de paneles de Teams.  

En la pantalla Inicio, puede ver los detalles de la ubicación y la reunión, reservar un espacio, ver las próximas reservas e identificar el estado de disponibilidad actual.

La siguiente captura de pantalla muestra diferentes partes o mosaicos en la pantalla principal de los paneles de Teams:

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Esta captura de pantalla muestra diferentes áreas en la pantalla principal de los paneles de Teams.":::

Consulte la tabla siguiente para obtener una descripción de cada mosaico:

Azulejo | Descripción
:---|:---
**1.Detalles de la hora, el día, la fecha y el espacio de reunión actuales** | Muestra la hora actual, el día, la fecha y el nombre del espacio de reunión. El nombre del espacio de reunión es el nombre de la cuenta de recursos que inició sesión en los paneles.
**2-Disponibilidad del espacio de reunión y detalles de la reunión** | Indica la disponibilidad del espacio de reunión y muestra los detalles de la reunión. Vea [el mosaico Disponibilidad del espacio de reunión y detalles de la reunión](#meeting-space-availability-and-meeting-details-tile).
**3-Calendario próximo** | Muestra el calendario y la disponibilidad del espacio de reunión hasta 24 horas a partir de la hora actual. Desplázate hacia arriba o hacia abajo para determinar qué intervalos de tiempo están disponibles y cuáles están reservados.
**4-Configuración** | Muestra el icono **Configuración** . Púlsalo para informar de un problema o actualizar la configuración del dispositivo disponible.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Mosaico Disponibilidad del espacio de reunión y detalles de la reunión

La apariencia de este icono y sus capacidades varían según la disponibilidad del espacio de reunión y el tipo de reserva.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>El espacio de reunión está reservado para una reunión programada

El mosaico aparece en color púrpura para un espacio de reunión reservado para una reunión programada (programada a través de Outlook o Teams). Muestra el título de la reunión en un texto destacado, las horas de inicio y finalización de la reunión y el nombre del organizador de la reunión. Para una reunión de Teams, también aparece el logotipo de Teams. Con los detalles de la reunión visibles, los asistentes pueden confirmar fácilmente que se encuentran en el espacio de reunión adecuado, en el momento adecuado y en la reunión adecuada.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Pantalla principal de paneles de Teams que muestra que el espacio de reunión está reservado para una reunión programada.":::

> [!NOTE]
>
> - Después de programar una reunión, el calendario puede tardar hasta 90 segundos en sincronizarse y reflejarse en la pantalla de paneles.
> - Para las [reuniones programadas marcadas como privadas](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d), se muestra **Reunión privada** en lugar del título de la reunión real.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>El espacio de reunión está reservado para una reunión ad hoc

El mosaico aparece en color púrpura para un espacio de reunión [reservado para una reunión ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Muestra **Reservado** en un texto destacado junto con las horas de inicio y finalización de la reunión. Las reuniones ad hoc se programan automáticamente como reuniones de Teams, por lo que el logotipo de Teams siempre aparece en la pantalla.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Pantalla principal de paneles de Teams que muestra que el espacio de reunión está reservado para una reunión ad hoc.":::

#### <a name="meeting-space-is-available"></a>El espacio de reunión está disponible

El icono aparece en verde para un espacio de reunión disponible. Muestra **Disponible** en texto destacado y también aparece un botón **Reservar** que puede pulsar para [reservar el espacio de reunión para una reunión ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Puede comprobar el calendario próximo del espacio de reunión (mosaico de la parte inferior derecha) para decidir la hora de finalización de la reunión ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Esta captura de pantalla muestra cómo aparece la pantalla principal de los paneles de Teams cuando el espacio de reunión está disponible.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Reservar espacios de reunión para reuniones ad hoc

Puede reservar un [espacio de reunión disponible](#meeting-space-is-available) directamente desde paneles para una reunión ad hoc. Todas las reuniones ad hoc se programan automáticamente como reuniones de Teams. Sin embargo, una vez reservado, no se puede liberar o no se puede reservar ese espacio de reunión a través de paneles. Solo los administradores de la cuenta de recursos del dispositivo pueden cancelar la reunión ad hoc (a través de Outlook o el calendario de Teams) para liberar espacio.

Para reuniones ad hoc que se reservan directamente desde paneles:

- La hora de inicio es siempre la hora actual y, por lo tanto, no puede programarla para una hora futura.
- La hora de finalización puede ser hasta la próxima reunión programada o hasta 24 horas a partir de la hora actual, lo que sea anterior. Compruebe el **icono Calendario próximo** en la pantalla Inicio para determinar los intervalos de tiempo durante los cuales el espacio de reunión está disponible o reservado.

Para reservar un espacio de reunión disponible para una reunión ad hoc:

1. En la pantalla Inicio, pulse el botón **Reservar** .
    :::image type="content" source="../media/panels-reserve.png" alt-text="Pantalla principal de paneles de Teams que muestra el botón Reservar.":::
2. En la pantalla **Reunión ad hoc** , revise las opciones de hora de finalización disponibles. Puede usar las flechas derecha o izquierda para examinar las opciones de hora de finalización disponibles.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Pantalla de reunión ad hoc que muestra los intervalos de tiempo de finalización.":::

    > [!Note]
    >
    > - Las opciones de hora de finalización se muestran en intervalos de 15 minutos de una hora.
    > - La hora de finalización predeterminada es el siguiente intervalo de 15 minutos, que es al menos cinco minutos después de la hora actual. Por ejemplo, si la hora actual es 1:57 p.m., la hora de finalización predeterminada se muestra como 2:15 p.m. y no como 14:00. Esto evita que los usuarios reserven el espacio durante cinco minutos o menos. En la captura de pantalla anterior, la hora de finalización predeterminada se muestra como 2:00 p.m., que es el siguiente intervalo de 15 minutos que es al menos cinco minutos después de la hora actual (1:53 p.m.).
    > - Una excepción a la regla anterior es cuando la hora de inicio de la próxima reunión está dentro de los cinco minutos de la hora actual. En estos casos, puede reservar el espacio hasta la próxima hora de inicio de la reunión. Por ejemplo, si la hora actual es la 1:57 p.m. y la siguiente hora de inicio de la reunión es las 2:00 p.m., las 2:00 p.m. se muestra como la única opción de hora de finalización y puede reservar el espacio durante tres minutos.

3. Pulse el intervalo de tiempo de finalización deseado y, a continuación, pulse **Reservar**.

    Aparece una ventana de confirmación con un emoji de pulgar hacia arriba, la hora de inicio y finalización de la reunión y el nombre del espacio de la reunión.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Mensaje de confirmación de reunión ad hoc.":::
El mosaico derecho de la pantalla Inicio aparece ahora en color púrpura y muestra el texto **Reservado** y el logotipo de Teams. Esto indica que el espacio de reunión está ahora reservado para una reunión ad hoc de Teams.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Pantalla principal que muestra que el espacio de reunión está reservado para una reunión ad hoc.":::

    > [!NOTE]
    > Si el espacio de reunión es una sala de Microsoft Teams, puede _unirse a_ esta reunión de Teams con la sala de Microsoft Teams de la sala o los dispositivos Surface Hub.

### <a name="report-a-problem"></a>Informar de un problema

Para informar de un problema con el dispositivo o el espacio de reunión, para solicitar una actualización de características o para proporcionar comentarios, use el icono **Configuración** de la pantalla Inicio.

1. Pulse el icono de engranaje **configuración** en la pantalla de inicio.

2. Pulse la opción **Informar de un problema** .

    La pantalla **Enviar comentarios** se muestra en un formato de formulario.
3. En la lista desplegable **Tipo** , seleccione el tipo de solicitud.
4. En la lista desplegable **Problema** , seleccione la categoría.
5. En el campo **de texto Título** , escriba el título con el teclado de paneles.
6. En el campo de texto debajo **de Título**, escriba detalles adicionales, si es necesario.

    > [!NOTE]
    > No incluyas ninguna información de identificación personal.

7. Revise sus entradas y pulse **Enviar**.

### <a name="view-or-update-a-device-setting"></a>Ver o actualizar la configuración de un dispositivo

Hay varias opciones de configuración del dispositivo, como acerca de, accesibilidad, reinicio y directiva de privacidad que puede ver o actualizar directamente desde los paneles. La configuración del dispositivo disponible puede diferir en función del fabricante de equipos originales (OEM) del dispositivo. Para obtener información sobre la configuración específica del dispositivo, consulta la documentación del OEM.

Para ver o actualizar la configuración de un dispositivo:

1. Pulse el icono **Configuración** en la pantalla Inicio.
2. En la pantalla **Configuración** , pulse **Configuración del dispositivo**.
3. En la pantalla **Configuración del dispositivo** , pulsa en la opción que quieras ver o actualizar.
4. Siga el aviso en pantalla para ver o actualizar la configuración.

## <a name="teams-panels-admin-experience"></a>Experiencia de administración de paneles de Teams

Si eres el administrador de la [cuenta de recursos de Panel de Teams](teams-panels.md\#resource-account-provisioning), también eres el administrador de **Panels App** en el dispositivo. Como administrador de la **aplicación paneles** , puede hacer todas las funciones que se mencionan en la sección de [la experiencia del usuario final](#teams-panels-end-user-experience) , además de administrar la configuración de la **aplicación paneles** en el dispositivo.

Los dispositivos de paneles proporcionan dos tipos de configuración de administración. Debe ser administrador de dispositivos para tener acceso a la configuración de administración disponible. Los usuarios finales no pueden acceder a esta configuración.

- Administración opciones de configuración específicas para el dispositivo, como la pantalla, la hora y fecha, el idioma, Bluetooth, la Wi-Fi, etc. Consulta la documentación del OEM para obtener más información sobre esta configuración.
- Administración ajustes específicos de la **aplicación Paneles** en el dispositivo, como el color del indicador LED y el papel tapiz. Solo un administrador de **la aplicación Paneles** puede acceder a esta configuración. Dado que la configuración de la **aplicación Paneles** está disponible como parte de la configuración de administración, debe tener credenciales de inicio de sesión de administrador para que el dispositivo y la **aplicación paneles** accedan a la configuración de **la aplicación paneles** .

> [!NOTE]
> Las actualizaciones a la configuración de la **aplicación de paneles** realizadas a través del dispositivo son aplicables solo a ese dispositivo específico. Estas actualizaciones no afectarán a otros dispositivos de paneles de su organización. Por ejemplo, si cambias la imagen de fondo de pantalla inicio desde la configuración de la **aplicación Paneles** , la imagen de fondo cambiará solo para ese dispositivo específico.

### <a name="access-panels-app-settings"></a>Configuración de la aplicación Paneles de acceso

Puede acceder a la configuración específica de la **aplicación de paneles** mediante la opción Configuración de aplicaciones de **paneles** en la configuración de administración. Los pasos para acceder a la **configuración de la aplicación paneles** pueden diferir en función del OEM del dispositivo.

Para acceder a la opción **Configuración de la aplicación Paneles** :

1. Pulse el icono **Configuración** en la pantalla Inicio.
2. En la pantalla **Configuración** , pulse **Configuración del dispositivo**.
3. Pulse en **configuración Administración**.

    > [!NOTE]
    > Según el OEM del dispositivo, es posible que tengas que escribir la contraseña de administrador del dispositivo ahora o después del paso siguiente.

4. Desplázate hacia abajo para encontrar la opción **Configuración de la aplicación Paneles** . Púlsalo.
5. Pulse el botón **Configuración de la aplicación Paneles** en la pantalla de la derecha.
    Se muestra la pantalla con la configuración de la **aplicación de paneles** disponible.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="Esta captura de pantalla muestra la pantalla con la configuración de la aplicación Paneles disponibles.":::

    Usa esta pantalla para actualizar la siguiente configuración de la **aplicación Paneles** para tu dispositivo:

    - [Papel pintado](#update-the-wallpaper)
    - [Indicador LED](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>Emparejar un Panel de Teams con una sala de Microsoft Teams en Android

Para emparejar una Panel de Teams y una sala de Teams en Android, ambos dispositivos deben haber iniciado sesión en la misma cuenta de recursos.

En la Panel de Teams, inicie sesión con sus credenciales de administrador.

1. Vaya a **Configuración > Configuración de dispositivo > Administración Configuración > paneles de la aplicación Paneles > Reuniones > emparejamiento de dispositivos.**

2. Aparecerá un código de seis dígitos en la Salas de Teams en la parte frontal de la pantalla de la sala de Android. Escriba el código en el Panel de Teams.  

#### <a name="meeting-check-in-and-room-release"></a>Registro de la reunión y liberación de la sala

La configuración de registro y de liberación de la sala permite a los usuarios registrarse en una reunión en los paneles de Teams en la sala que reservaron al comienzo de la reunión. Si un usuario no realiza la facturación dentro de un período de tiempo determinado después de la hora de inicio de la reunión, la sala se libera y está disponible para que otros puedan reservarla.

Cuando los paneles de Teams están emparejados con una sala de Microsoft Teams en Android, se pueden habilitar las notificaciones de protección para que aparezcan en la pantalla del frente de la sala cuando las reuniones se ejecutan tarde.

Para habilitar el registro y la liberación de salas, consulte [Protección y liberación de salas en paneles de Microsoft Teams](check-in-and-room-release.md).

#### <a name="room-capacity-warning"></a>Advertencia de capacidad de la sala

Los paneles de Teams que están emparejados con una sala de Teams en Android pueden mostrar un mensaje de advertencia cuando una sala de reuniones tiene o no capacidad. Para usar esta característica, la sala de Teams debe tener una cámara que admita el recuento de personas. Salas de Teams en las advertencias de capacidad de sala de soporte técnico de Android sin un Panel de Teams.

Las advertencias de capacidad de la sala están desactivadas de forma predeterminada. Para activar la configuración desde el Panel de Teams, primero [empareje un Panel de Teams con una sala de Microsoft Teams en Android](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android). El panel y la sala de Teams deben haber iniciado sesión en la misma cuenta de recursos.

 A continuación, ve a **Configuración > Configuración del dispositivo > Administración configuración > configuración de la aplicación Panel**. A continuación, en **Reuniones**, active **La notificación de ocupación máxima de la sala**.

#### <a name="view-room-equipment"></a>Ver el equipamiento de la sala

Cuando esta característica está activada, los usuarios finales pueden ver qué equipo está disponible en un espacio de una Panel de Teams.

Esta función está desactivada de manera predeterminada y se puede habilitar por dispositivo. Para activarlo, use [Set-Place](/powershell/module/exchange/set-place?view=exchange-ps) en PowerShell para configurar los nombres para mostrar de `AudioDeviceName`, `DisplayDeviceName`, `VideoDeviceName`, `Tags`y `IsWheelChairAccessible`.

O bien, puede habilitar esta característica en el Centro de administración de Exchange. Vea [Editar un recurso](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) para obtener más información.



#### <a name="update-the-wallpaper"></a>Actualizar el papel tapiz

Cambiar la imagen de fondo de la pantalla Inicio.

1. [**Configuración de la aplicación paneles de acceso**](#access-panels-app-settings).
2. Pulsa **Fondos de pantalla**.
3. En **Elegir la imagen**, seleccione una imagen para establecerla como imagen de fondo de la pantalla Inicio. Obtener una vista previa de la imagen seleccionada en **Fondo**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Esta captura de pantalla muestra la pantalla de configuración del fondo de pantalla.":::
4. Volver a la pantalla Inicio y comprueba que el fondo de pantalla esté actualizado.

#### <a name="change-the-busy-state-led-color"></a>Cambiar el color del LED de estado ocupado

Los administradores pueden elegir rojo o púrpura como color LED para indicar que el espacio de reunión está ocupado o reservado. El color DEL LED para indicar que hay un espacio disponible siempre es verde y no se puede cambiar.

1. [**Configuración de la aplicación paneles de acceso**](#access-panels-app-settings).
2. Pulsa **Configuración de LED**.
3. En **Elegir el color LED**, selecciona el color deseado.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Esta captura de pantalla muestra la configuración del estado de ocupado del color LED.":::
4. Volver a la pantalla Inicio y comprueba que se actualice el color del LED del estado ocupado. Si el espacio de reunión está disponible actualmente, intente programar una reunión de prueba para comprobar el cambio en el color del LED para el estado ocupado.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

Encuentre respuestas a las preguntas más frecuentes sobre los dispositivos de paneles de Teams.

**¿En el futuro puedo ver los detalles de programación de un espacio de reunión?**  
En el **mosaico Calendario próximo** (inferior derecha) de la pantalla Inicio, puede ver los detalles de programación de un espacio de reunión para un máximo de 24 horas en el futuro a partir de la hora actual.

**¿Puedo reservar un espacio de reunión para un momento futuro desde el dispositivo de paneles de Teams?**  
No, no puede reservar un espacio de reunión para un momento futuro de los paneles. La hora de inicio es siempre la hora actual para una reunión ad hoc programada a partir de paneles.

**¿Cuánto tiempo puedo reservar un espacio de reunión disponible para una reunión ad hoc?**  
Puede reservar un espacio de reunión disponible desde su hora actual hasta la próxima hora programada, o hasta un máximo de 24 horas desde su hora actual, lo que sea anterior. Por ejemplo, si la hora actual es de 10 a.m. y la siguiente hora de inicio de la reunión es de 14:00, puede reservar el espacio de reunión de 10 a.m. a 2 p.m.

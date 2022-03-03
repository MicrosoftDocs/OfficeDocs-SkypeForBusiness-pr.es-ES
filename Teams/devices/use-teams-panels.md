---
title: Cómo usar dispositivos Microsoft Teams paneles
ms.author: czawideh
author: cazawideh
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
search.appverid: MET150
ms.localizationpriority: medium
description: En este artículo se proporcionan instrucciones sobre cómo usar Teams dispositivos de paneles.
ms.openlocfilehash: bd1a7a865d6e07cec47838a518d19523afef5134
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "63050906"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Cómo usar Microsoft Teams paneles

Microsoft Teams son dispositivos de visualización digital compactos que se instalan justo fuera de los espacios de reunión, normalmente junto a las entradas. Estos paneles táctiles están dedicados Microsoft Teams dispositivos que proporcionan una vista general sobre su espacio de reunión y la reunión programada. Con los dinámicos indicadores LED y pantalla inicio codificados por colores, puede determinar si el espacio está disponible o reservado a distancia. Puede usar paneles Teams para reservar un espacio de reunión disponible para una reunión ad hoc, en el momento.

Teams dispositivos de paneles vienen preinstalados con Microsoft Teams y muestran detalles de la reunión que se programan Outlook o Teams calendarios.

En este artículo se proporcionan instrucciones, tanto para los usuarios finales como para los administradores, sobre cómo usar los Teams paneles. También proporciona respuestas a las preguntas [más frecuentes sobre](#frequently-asked-questions) el uso de estos dispositivos.

Para obtener información general sobre los dispositivos de paneles y las instrucciones sobre cómo planearlos, entregarlos y administrarlos en su organización, vea Implementar [Microsoft Teams paneles](teams-panels.md).

Para un inicio rápido, consulte Introducción a [Teams paneles](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be).

## <a name="teams-panels-end-user-experience"></a>Teams de paneles finales

Explore la [pantalla Inicio de su](#explore-teams-panels-home-screen) dispositivo Teams paneles para ver el espacio de reunión y los detalles de la reunión. O bien, pulse y desplácese por el panel de pantalla táctil para realizar otras acciones.

Use los dispositivos Teams paneles para:

- [Ver detalles y disponibilidad del espacio de reunión, detalles de la reunión, próximas reservas](#explore-teams-panels-home-screen)
- [Reservar un espacio de reunión disponible](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Informar de un problema](#report-a-problem)
- [Ver o actualizar una configuración de dispositivo](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Explorar Teams pantalla inicio

La pantalla Inicio es la interfaz visual principal del dispositivo Teams paneles.  

Desde la pantalla Inicio, puede ver los detalles de la reunión y la ubicación, reservar un espacio, ver próximas reservas e identificar el estado de disponibilidad actual.

La siguiente captura de pantalla muestra diferentes partes o mosaicos en la Teams pantalla inicio de paneles:

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Esta captura de pantalla muestra diferentes áreas en la Teams pantalla inicio.":::

Consulte la tabla siguiente para obtener una descripción de cada mosaico:

Mosaico | Descripción
:---|:---
**1-Detalles de la hora, el día, la fecha y el espacio de reunión actuales** | Muestra el nombre actual de la hora, el día, la fecha y el espacio de reunión. El nombre del espacio de reunión es el nombre de la cuenta de recursos que ha iniciado sesión en los paneles.
**Disponibilidad del espacio de dos reuniones y detalles de la reunión** | Indica la disponibilidad del espacio de reunión y muestra los detalles de la reunión. Vea [El icono Disponibilidad del espacio de reunión y detalles de la reunión](#meeting-space-availability-and-meeting-details-tile).
**Calendario de 3 próximas** | Muestra el calendario y la disponibilidad del espacio de reunión durante un máximo de 24 horas desde la hora actual. Desplácese hacia arriba o hacia abajo para determinar qué franjas horarias están disponibles y cuáles están reservadas.
**4-Configuración** | Muestra el **Configuración** de datos. Pón clic en él para informar de un problema o actualizar la configuración del dispositivo disponible.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Icono de disponibilidad de espacio de reunión y detalles de la reunión

La apariencia de este icono y sus capacidades varían según la disponibilidad del espacio de reunión y el tipo de reserva.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>El espacio de reunión está reservado para una reunión programada

El mosaico aparece en color púrpura para un espacio de reunión reservado para una reunión programada (programada a través de Outlook o Teams). Muestra el título de la reunión en texto prominente, horas de inicio y finalización de la reunión y el nombre del organizador de la reunión. Para una reunión Teams, también aparece Teams logotipo. Con los detalles de la reunión destacados, los asistentes pueden confirmar fácilmente que están en el espacio de reunión adecuado, en el momento adecuado y para la reunión correcta.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams paneles inicio que muestran que el espacio de reunión está reservado para una reunión programada.":::

> [!NOTE]
>
> - Después de programar una reunión, el calendario puede tardar hasta 90 segundos en sincronizarse y reflejarse en la pantalla de paneles.
> - Para una [reunión programada que se marca como privada](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)**, la** reunión privada se muestra en lugar del título real de la reunión.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>El espacio de reunión está reservado para una reunión ad hoc

El mosaico aparece en color púrpura para un espacio de reunión reservado [para una reunión ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Muestra Reservado **en** texto prominente junto con las horas de inicio y finalización de la reunión. Las reuniones ad hoc se programan automáticamente Teams reuniones, por lo que el logotipo de Teams siempre aparece en la pantalla.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams paneles de inicio que muestran que el espacio de reunión está reservado para una reunión ad hoc.":::

#### <a name="meeting-space-is-available"></a>El espacio de reunión está disponible

El mosaico aparece en verde para un espacio de reunión disponible. Muestra Disponible **en** texto prominente y también aparece un  botón Reservar que puede pulsar para reservar el espacio de reunión [para una reunión ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Puede comprobar el calendario próximo del espacio de reunión (mosaico inferior derecho) para decidir la hora de finalización de la reunión ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Esta captura de pantalla muestra cómo aparece Teams pantalla inicio de los paneles cuando el espacio de reunión está disponible.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Reservar espacios de reunión para reuniones ad hoc

Puede reservar un espacio [de reunión disponible directamente](#meeting-space-is-available) desde paneles para una reunión ad hoc. Todas las reuniones ad hoc se programan automáticamente como Teams reuniones. Sin embargo, una vez reservado, no se puede liberar o no reservar ese espacio de reunión a través de paneles. Solo los administradores de la cuenta de recursos del dispositivo pueden cancelar la reunión ad hoc (a través de Outlook o Teams calendario) para anular la reserva del espacio.

Para reuniones ad hoc que se reservan directamente desde paneles:

- La hora de inicio siempre es la hora actual y, como tal, no puede programarla para una hora futura.
- La hora de finalización puede ser hasta la siguiente reunión programada o hasta 24 horas desde la hora actual, lo que sea anterior. Compruebe el **icono Calendario próximo** en la pantalla Inicio para determinar las franjas de tiempo durante las que el espacio de reunión está disponible o reservado.

Para reservar un espacio de reunión disponible para una reunión ad hoc:

1. En la pantalla Inicio, pulse el **botón** Reservar.
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams paneles inicio que muestran el botón Reservar.":::
2. En la **pantalla Reunión ad hoc** , revise las opciones de hora de finalización disponibles. Puede usar las flechas derecha o izquierda para examinar las opciones de hora de finalización disponibles.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Pantalla de reunión ad hoc que muestra las franjas horarias de finalización.":::

    > [!Note]
    >
    > - Las opciones de hora de finalización se muestran en intervalos de 15 minutos de una hora.
    > - La hora de finalización se muestra de forma predeterminada en el siguiente intervalo de 15 minutos, que es al menos cinco minutos después de la hora actual. Por ejemplo, si la hora actual es 1:57 p.m., la hora de finalización predeterminada se muestra como 2:15 p.m. y no 2:00 p.m. Esto impide que los usuarios reserven el espacio durante cinco minutos o menos. En la captura de pantalla anterior, la hora de finalización predeterminada se muestra como 2:00 p.m., que es el siguiente intervalo de 15 minutos que es al menos cinco minutos después de la hora actual (1:53 p.m.).
    > - Una excepción a la regla anterior es cuando la hora de inicio de la siguiente reunión está dentro de cinco minutos desde la hora actual. En estos casos, puede reservar el espacio hasta la próxima hora de inicio de la reunión. Por ejemplo, si la hora actual es 1:57 p. m. y la siguiente hora de inicio de la reunión es a las 2:00 p.m., a continuación, las 2:00 p.m. se muestra como la única opción de hora de finalización y puede reservar el espacio durante tres minutos.

3. Pulse el intervalo de tiempo de finalización deseado y, a continuación, pulse **Reservar**.

    Aparecerá una ventana de confirmación con un emoji de pulgar hacia arriba, la hora de inicio y finalización de la reunión y el nombre del espacio de reunión.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Mensaje de confirmación de reunión ad hoc.":::
El icono derecho de la pantalla Inicio ahora aparece en color púrpura y muestra el **texto reservado y** el Teams texto. Esto indica que el espacio de reunión ahora está reservado para una reunión ad hoc Teams reunión.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Pantalla principal que muestra que el espacio de reunión está reservado para una reunión ad hoc.":::

    > [!NOTE]
    > Si el espacio de reunión es una sala Microsoft Teams, puede unirse  a esta reunión Teams con la sala de Microsoft Teams o Surface Hub dispositivos.

### <a name="report-a-problem"></a>Informar de un problema

Para informar de un problema con el dispositivo o el espacio de reunión, para solicitar una actualización de características o para proporcionar comentarios, use  el icono Configuración en la pantalla Inicio.

1. Pulse el **icono Configuración** engranaje de la pantalla Inicio.

2. Pulse la **opción Informar de un** problema.

    La **pantalla Enviar comentarios** se muestra en un formato de formulario.
3. En la **lista** desplegable Tipo, seleccione el tipo de solicitud.
4. En la **lista desplegable** Problema, seleccione la categoría.
5. En el **campo de** texto Título, escriba el título con el teclado de paneles.
6. En el campo de texto debajo **de Título**, escriba detalles adicionales, si es necesario.

    > [!NOTE]
    > No incluya ninguna información de identificación personal.

7. Revise las entradas y pulse **Enviar**.

### <a name="view-or-update-a-device-setting"></a>Ver o actualizar una configuración de dispositivo

Hay varias opciones de configuración de dispositivo, como acerca de, accesibilidad, reinicio y directiva de privacidad que puede ver o actualizar directamente desde paneles. La configuración del dispositivo disponible puede diferir en función del Fabricante de equipos originales (OEM) de su dispositivo. Para obtener información sobre la configuración específica de su dispositivo, consulte la documentación de OEM.

Para ver o actualizar una configuración de dispositivo:

1. Pulse el **icono Configuración** en la pantalla Inicio.
2. En la **Configuración**, pulse **Configuración del dispositivo**.
3. En la **pantalla Configuración** dispositivo, pulse la configuración que desea ver o actualizar.
4. Siga el mensaje en la pantalla para ver o actualizar la configuración.

## <a name="teams-panels-admin-experience"></a>Teams de administración de paneles

Si es el administrador de Teams cuenta de recursos del [panel](teams-panels.md\#resource-account-provisioning), también es el administrador de **la aplicación Paneles** en el dispositivo. Como administrador **de la aplicación** Paneles, puede realizar todas las funciones que se mencionan en [](#teams-panels-end-user-experience) la sección experiencia del usuario final, además de administrar la  configuración de la aplicación Paneles en el dispositivo.

Los dispositivos de paneles proporcionan dos tipos de configuración de administrador. Debe ser administrador de dispositivos para obtener acceso a la configuración de administrador disponible. Los usuarios finales no pueden acceder a esta configuración.

- Configuración de administrador que es específica del dispositivo, como pantalla, hora y fecha, idioma, bluetooth, WiFi, y así sucesivamente. Consulte la documentación de OEM para obtener más información sobre esta configuración.
- Configuración de administrador que es específica de **la aplicación Paneles** en el dispositivo, como el fondo de pantalla y el color del indicador LED. Solo un administrador de **la aplicación Paneles** puede acceder a esta configuración. Puesto **que la** configuración de la aplicación Paneles está disponible como parte de la configuración de administrador, debe tener credenciales de inicio de sesión de administrador tanto para el dispositivo como para **la** aplicación Paneles para acceder a la configuración **de la aplicación** Paneles.

> [!NOTE]
> Las actualizaciones de la configuración **de la aplicación** Paneles realizadas a través del dispositivo solo se aplican a ese dispositivo específico. Esas actualizaciones no afectarán a otros dispositivos de paneles de su organización. Por ejemplo, si cambia la imagen de fondo de pantalla inicio desde  la configuración de la aplicación Paneles, la imagen de fondo solo cambiará para ese dispositivo específico.

### <a name="access-panels-app-settings"></a>Configuración de la aplicación Paneles de Access

Puede obtener acceso a **la configuración** específica de la aplicación Paneles mediante la opción **Paneles de Configuración** en la configuración de administración. Los pasos para acceder a **la aplicación Paneles Configuración** pueden diferir en función del OEM del dispositivo.

Para obtener acceso a **la opción Configuración** paneles:

1. Pulse el **icono Configuración** en la pantalla Inicio.
2. En la **Configuración**, pulse **Configuración del dispositivo**.
3. Pulse el **botón Administrador Configuración**.

    > [!NOTE]
    > Según el OEM del dispositivo, es posible que deba escribir la contraseña de administrador del dispositivo ahora o después del paso siguiente.

4. Desplácese hacia abajo para buscar la **opción Configuración** paneles. Pónsallo.
5. Pulse el **botón Panel de Configuración** de la pantalla derecha.
    Se muestra la pantalla con la configuración **de la aplicación** Paneles disponible.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="Esta captura de pantalla muestra la pantalla con la configuración de la aplicación Paneles disponible.":::

    Use esta pantalla para actualizar la siguiente configuración **de la aplicación Paneles** para el dispositivo:

    - [Fondo de pantalla](#update-the-wallpaper)
    - [Indicador LED](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>Emparejar un panel Teams con una sala Microsoft Teams en Android

En el panel Teams, inicie sesión con sus credenciales de administrador.  

1. Vaya a **Configuración > Dispositivo Configuración > administrador Configuración > aplicaciones paneles Configuración > reuniones > emparejamiento de dispositivos.**

2. Aparecerá un código de seis dígitos en el Salas de Teams en la pantalla frontal de la sala de Android. Escriba el código en el Teams panel.  

#### <a name="meeting-check-in-and-room-release"></a>Entrada de reunión y versión de sala

La configuración de la versión de la sala y el check-in permiten a los usuarios realizar el check-in en una reunión en Teams Paneles en la sala que reservaron al principio de la reunión. Si un usuario no hace el check-in dentro de una cantidad de tiempo establecida después de la hora de inicio de la reunión, la sala se libera y está disponible para que otras personas puedan reservar.

Cuando un panel Teams está emparejado con una sala de Microsoft Teams en Android, las notificaciones de check-in se pueden habilitar para que aparezcan en la pantalla del front0of-room cuando las reuniones se retrasan.

Para habilitar la protección y la versión de la sala, vea Protección y [la versión de la sala en Microsoft Teams paneles](check-in-and-room-release.md).

#### <a name="update-the-wallpaper"></a>Actualizar el fondo de pantalla

Cambiar la imagen de fondo de pantalla inicio.

1. [Aplicación **Paneles de Access Configuración**](#access-panels-app-settings).
2. Pulse **Fondos de pantalla**.
3. En **Elegir la imagen**, seleccione una imagen para establecerla como imagen de fondo de la pantalla inicio. Obtenga una vista previa de la imagen seleccionada en **Fondo**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Esta captura de pantalla muestra la pantalla de configuración del fondo de pantalla.":::
4. Vuelva a la pantalla Inicio y compruebe que el fondo de pantalla está actualizado.

#### <a name="change-the-busy-state-led-color"></a>Cambiar el color del LED de estado ocupado

Los administradores pueden elegir rojo o púrpura como color LED para indicar que el espacio de reunión está ocupado o reservado. El color del LED para indicar un espacio disponible siempre es verde y no se puede cambiar.

1. [Aplicación **Paneles de Access Configuración**](#access-panels-app-settings).
2. Pulse **LED Configuración**.
3. En **Elegir el color del LED**, seleccione el color deseado.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Esta captura de pantalla muestra la configuración de estado ocupado del color del LED.":::
4. Vuelva a la pantalla Inicio y compruebe que el color del LED para el estado ocupado está actualizado. Si el espacio de reunión está disponible actualmente, intente programar una reunión de prueba para comprobar el cambio en el color del LED para el estado ocupado.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

Encuentre respuestas a preguntas más frecuentes sobre los dispositivos Teams paneles.

**¿Hasta qué punto en el futuro puedo ver los detalles de programación de un espacio de reunión?**  
En el **icono Calendario** próximo (inferior derecha) de la pantalla Inicio, puede ver los detalles de programación de un espacio de reunión durante un máximo de 24 horas en el futuro a partir de la hora actual.

**¿Puedo reservar un espacio de reunión para un futuro desde el dispositivo Teams paneles?**  
No, no puede reservar un espacio de reunión para un futuro desde paneles. La hora de inicio siempre es la hora actual para una reunión ad hoc programada desde paneles.

**¿Cuánto tiempo puedo reservar un espacio de reunión disponible para una reunión ad hoc?**  
Puede reservar un espacio de reunión disponible a partir de la hora actual hasta la próxima hora programada de la reunión, o hasta un máximo de 24 horas desde la hora actual, lo que sea anterior. Por ejemplo, si la hora actual es 10 a.m. y la siguiente hora de inicio de la reunión es las 2 p. m., puede reservar el espacio de reunión de 10 a. m. a 2 p. m.

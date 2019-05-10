---
title: Configurar un operador automático en la nube
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Obtenga información sobre cómo configurar y probar a automáticos en la nube para administración de la organización eficaz de las llamadas.
ms.openlocfilehash: e98233bd610cd83afdbc727a5edeba77951d1989
ms.sourcegitcommit: ca7a22da082ac5336f31ffd76f3d4aef6c76285b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2019
ms.locfileid: "33868819"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Configurar un operador automático en la nube

Operadores automáticos permiten a las personas que llaman a su organización y navegue a un sistema de menús a obtienen al departamento de derecho, cola, persona o el operador de llamada. Puede crear a un operador automático para la organización mediante el centro de administración de Microsoft Teams. Para crear un nuevo operador automático de, vaya a **voz** en el panel de navegación izquierdo y, a continuación, seleccione **operadores automáticos** > **Agregar nuevo**.

Si desea obtener más información sobre los operadores automáticos, consulte [¿Qué son los operadores automáticos de la nube?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> En este artículo se aplica a Microsoft Teams y Skype para profesionales en línea.



## <a name="step-1---get-started"></a>Paso 1: Introducción

- Un operador automático es necesario tener una cuenta de recurso asociado. Para obtener información detallada sobre las cuentas de recursos, vea [Administrar cuentas de recursos en los equipos](manage-resource-accounts.md) .
- Si tiene previsto asignar un número de enrutamiento directa, debe adquirir y asignar las siguientes licencias para las cuentas de recursos \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico\).
- Si se asigna un número de servicio de Microsoft en su lugar, debe adquirir y asignar las licencias siguientes a la cuenta del recurso \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico y un Plan de llamar a\).

> [!NOTE] 
> Microsoft está trabajando en un modelo de licencias adecuado para aplicaciones como automáticos en la nube y las colas de llamadas, para ahora tiene que usar el modelo de licencias de usuario.

> [!CAUTION]
> Para obtener y usar los números de teléfono gratuitos, necesita configurar créditos de comunicaciones. Para ello, consulte [¿Qué son los créditos de comunicaciones?](what-are-communications-credits.md) y [Configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).

> [!TIP]
> Para redirigir las llamadas a un operador o una opción de menú que es un usuario con una licencia de **Sistema telefónico** en línea, debe habilitarlos para Enterprise Voice o asignar al llamar a los planes en Office 365 a ellos. Vea [Asignar Skype para licencias de negocio](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md). También puede usar Windows PowerShell. Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2---create-a-new-auto-attendant"></a>Paso 2: crear un operador automático nuevo

> [!IMPORTANT]
> Cada operador automático es necesario tener asociado a una [cuenta del recurso](manage-resource-accounts.md). Debe crear la cuenta del recurso en primer lugar, a continuación, puede asociar para el operador automático.

### <a name="using-the-microsoft-teams-admin-center"></a>Desde el centro de administración de Microsoft Teams

En el **Centro de administración de equipos de Microsoft**, haga clic en **voz** > **operadores automáticos**, a continuación, haga clic en **+ nuevo**:

#### <a name="general-info-page"></a>Página de información general

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Número 1](media/sfbcallout1.png)

**Nombre** Escriba un nombre para mostrar descriptivo para el operador automático. El nombre es obligatorio, y puede contener hasta 64 caracteres, espacios incluidos. Se enumerará en la columna **Nombre** en la ficha **Operadores automáticos**.

* * *

![Número 2](media/sfbcallout2.png)

**Cuenta de recurso** Haga clic en este botón para seleccionar una o más cuentas de recursos para conectarse a su nuevo operador automático. Todos los operadores automáticos deben tener una cuenta de recurso asociado. Una cuenta de recurso puede tener un número de teléfono asociado a la cuenta, pero es posible que no. Un operador automático de nivel superior normalmente tienen una cuenta de recurso con un número de teléfono asignado, pero el operador automático anidados de (se utiliza como un menú de nivel 2 que se conecta el primer operador automático de nivel a) no es posible que tienen un número de teléfono asignado a su cuenta del recurso.

* * *

![Número 3](media/sfbcallout3.png)

**Zona horaria**: debe establecer la zona horaria para el operador automático, pero no es necesario que se corresponda con la zona horaria de la dirección principal que se muestra para su organización. Cada operador automático puede tener una zona horaria diferente, y el horario laboral establecido para el operador automático se ajustará en función de la zona horaria seleccionada.

* * *

![Número 4](media/sfbcallout4.png)

**Idioma** Seleccione el idioma que desea usar para el operador automático desde cualquiera de los idiomas disponibles que aparecen. El idioma que establezca aquí es el idioma que usará el operador automático para interactuar con las personas que llaman a este operador automático y todos los mensajes del sistema se reproducirá en este idioma.

* * *

![Número 5](media/sfbcallout5.png)

**Operador**: este ajuste es opcional y no es necesario activarlo para el operador automático. Sin embargo, puede establecer la opción de **operador** para las personas que llaman en que puedan interrumpir la ejecución de los menús para hablar con una persona que les ayudará a.

Automáticamente se asigna la tecla 0 a Operador.

Si configurar esta opción, también tendrá que indicar a las personas que llamar en que esto es una opción disponible en el **menú Opciones de edición** en la página de **control de llamadas de horario comercial** . Si establece un operador en el operador automático, debe escribir el texto del mensaje correspondiente en el cuadro **escucharán los autores de llamadas** o cambiar su archivo de audio para incluir esta opción. Por ejemplo, "Para hablar con el operador, pulse cero."

Puede elegir entre las siguientes opciones para designar un operador:

- **Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365.

     > [!Note]
     > La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.

- Una **cola de llamadas** que haya configurado.
- Puede establecer que el autor de la llamada se derive a un correo de voz. Para ello, seleccione la **persona de la compañía** y establecer las llamadas de esta persona se transfieran directamente al correo de voz.

* * *

![Número 6](media/sfbcallout6.png)

**Habilitar las entradas de voz** Reconocimiento de voz está disponible si está seleccionada esta opción. Las personas que llaman en pueden usar la entrada de voz en el [idioma que establece](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Puede deshabilitar el reconocimiento de voz si se establece en off si desea que sólo permiten a los usuarios utilizar su teclado del teléfono.

* * *

Cuando haya terminado con las selecciones, haga clic en **siguiente**.

#### <a name="business-hours-page"></a>Página de horario comercial

De forma predeterminada, se establecen horario en 9 a.m. a 5 p.m., del lunes al viernes.  Todas las horas que no se incluyan en el horario laboral se consideran no laborales. Puede hacer clic en **Seleccionar las 24 horas 7** para hacer que todas las horas de horario. A menos que seleccione la opción **Seleccionar las 24 horas 7** , se usará la página **después de configuración de llamadas de horas** para configurar la administración para después del horario laboral para el operador automático de llamadas.

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Número 1](media/sfbcallout1.png)

De forma predeterminada, se establecen horario en el lunes al viernes, de 9:00 am - 5:00 pm. Seleccione **Borrar todas las horas de** opción para anular la selección de todas las horas de horas de la programación. Al seleccionar **Restablecer a predeterminado**, horario se restablecerá al lunes al viernes, de 9:00 am - 5:00 pm.

* * *

![Número 2](media/sfbcallout2.png)

Para cambiar el horario comercial, resalte el horario comercial que desea establecer con el calendario. El calendario le permite seleccionar el horario comercial en intervalos de 30 minutos, y el horario que seleccione aquí se basará en la zona horaria que haya configurado en la página **Información general**. Para configurar un descanso (almuerzo, por ejemplo), anule la selección o arrastre para anular la selección de la hora en el calendario. Puede establecer varios descansos dentro del horario comercial.

* * *

Cuando haya terminado con las selecciones, haga clic en **siguiente**.

#### <a name="business-hours-call-settings"></a>Configuración de llamadas de horario comercial

> [!TIP]
> Si utiliza una programación de horario comercial, también tendrá que configurar una llamada de tener que proporcionar para después del horario de uso de la página **después de control de llamadas de horas** , que le proporcionará las mismas opciones que la **configuración de llamadas de horario comercial**.

Puede configurar el saludo, mensajes de voz y los menús que las personas que escuchará llamada al número de teléfono de operador automático de la organización durante el horario laboral.

![Control de llamadas de horario comercial. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
 ![Horario continuado de control de llamadas.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![Número 1](media/sfbcallout1.png)

**Saludo** Un saludo de horario comercial es opcional y se puede establecer en **ningún saludo**. En este caso, el autor de la llamada no escuchará ningún mensaje o un saludo antes de la llamada se controla mediante una de las acciones que seleccione. También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.

- **No hay saludo** Ningún saludo se reproducirá cuando llama personas el número de teléfono de operador automático.
- **Cargar un archivo de audio** Si selecciona esta opción, grabar el saludo y, a continuación, cargue el archivo de audio (en un formato .wav,. mp3 o .wma).
- **Escriba un mensaje de saludo** Si elige esta opción, escriba el texto que desea que el sistema para leer (hasta 1000 caracteres). Por ejemplo, puede escribir "Bienvenidos a Contoso. Su llamada es muy importante para nosotros." en el cuadro **Los autores de llamadas escucharán**.

* * *

![Número 2](media/sfbcallout2.png)

Puede seleccionar lo que ocurre con las llamadas que se reciben durante el horario comercial. Puede elegir entre las siguientes acciones:

- **Desconectar** Si se selecciona, la persona que llama sera desconectada tras escuchar un saludo de horario comercial.
- **Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:
  - **Persona de empresa** con una licencia de **Sistema de teléfono** que está habilitada para Enterprise Voice o asignada al llamar a los planes en Office 365. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione la **persona en la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.

    > [!Note]
    > **Persona de empresa** puede ser un usuario en línea o un usuario hospedado local mediante Skype para Business Server 2015 o Lync Server 2013.

   - Otro **operador automático**

   Puede usar a un operador automático existente para crear un segundo nivel de opciones de menú que contiene un submenú. Estos se denominan a operadores automáticos anidados. Para enviar la llamada a un operador automático anidadas, seleccione la **persona en la empresa** y asignar una cuenta de recursos, uno que ya tiene un operador automático asociado o uno que se va a asociar a un operador automático de una vez que haya terminado de crear este operador automático.

- También puede utilizarse el **menú Opciones de reproducción** para que le permite configurar un símbolo del sistema que desee que se reproduzca.

* * *

![Número 3](media/sfbcallout3.png)

**Texto del menú**: para crear un mensaje para el menú principal puede usar la característica Texto a voz o cargar un archivo de audio (.wav, .mp3 o .wma). Puede escribir el símbolo del sistema en el cuadro **establecer la navegación de menús para los autores de llamadas** o registrar un archivo de audio y diga, por ejemplo: "para ventas, diga o presione o diga 1. Pulse o diga 2 para Servicios. Pulse o diga 3 para Atención al cliente. Para hablar con el operador, pulse o diga 0. Para escuchar este mensaje de nuevo, pulse la tecla de asterisco o diga Repetir". **Escriba un mensaje de saludo** Si opta por esto, debe escribir el texto que desea que el sistema para leer (hasta 1000 caracteres). **Cargar un archivo de audio**: si elige esta opción, deberá grabar el saludo y cargar el archivo de audio (en formato .wav, .mp3 o .wma).

* * *

![Número 4](media/sfbcallout4.png)

**Programa de instalación de las opciones de menú** Pueden agregar o quitar opciones de menú utilizando los botones de clave en el teclado numérico. Para agregar una opción de menú, presione **+ asignar una tecla de acceso telefónico**. Una fila de opciones correspondiente aparecerá debajo. Para eliminar una opción de menú, haga clic en a la izquierda de la clave correspondiente en el control del teclado y haga clic en el icono de eliminación anterior. Se quitará la fila de asignación de teclas.

> [!TIP]
> Debe actualizar menú mensajes de texto o volver a registrar el audio por separado cuando se agrega a la eliminación de opciones porque no se realiza automáticamente para el símbolo del sistema de menú existente.  
>
>Cualquier opción de menú se puede agregar y quitar en cualquier orden, y las asignaciones de teclas no tienen que ser continuo. Es posible, por ejemplo, para crear un menú con las teclas de 0, 1 y 3 que se asignan a opciones, mientras no se usa la tecla 2.

> [!NOTE]
> Las claves de \* (las veces) y \# (atrás) están reservados por el sistema y no se pueden reasignar. Si está habilitado el reconocimiento de voz, al presionar * corresponderá con "Repetir" y # se corresponden con los comandos de voz "Atrás".

Para configurar las opciones de menú, después de seleccionar las claves de acceso telefónico, necesitará:

- Escriba el **comando de voz** de la opción. Esto puede tener hasta 64 caracteres y puede contener varias palabras como "Servicio de atención al cliente" o "operaciones y motivos". Si está habilitado el reconocimiento de voz, automáticamente se reconocerá el nombre y la persona que llama podrá, o bien presionar 3, decir "tres" o decir "servicio de asistencia al cliente" para seleccionar la opción asignada a la tecla 3.
- Seleccione donde se enviarán si se presiona la tecla correspondiente, o se selecciona la opción utilizando el reconocimiento de la llamada. La llamada se puede enviar al:

  - **Operador** Si el operador ya está configurado, se asigna automáticamente a la tecla 0, pero también se puede eliminar o volverse a asignar a una tecla diferente. Si el operador no está establecido para alguna tecla, entonces el comando de voz "Operador" se deshabilitará también.
  - **Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a un plan de llamadas en Office 365. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione la **persona de la empresa** y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.

    > [!Note]
    > La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013. 
    - Otro **operador automático**

       Puede usar a un operador automático existente para crear un segundo nivel de opciones de menú que contiene un submenú. Estos se denominan a operadores automáticos anidados. Para enviar la llamada a un operador automático anidadas, seleccione la **persona en la empresa** y asignar una cuenta de recursos, uno que ya tiene un operador automático asociado o uno que se va a asociar a un operador automático de una vez que haya terminado de crear este operador automático.

        > [!Note]
        > El **Horario comercial** de operadores automáticos anidados (o de segundo nivel) también se utilizará, lo que incluye las llamadas enviadas desde otros operadores automáticos que se hayan configurado.

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![Número 5](media/sfbcallout5.png)

**Marcado por nombre** Si elige esta opción, esto permitirá que a las personas que llaman a buscar personas en su organización con búsqueda en el directorio. Puede seleccionar qué personas se mostrarán como disponibles o no disponibles para el marcado por nombre mediante la configuración de esas opciones en la página **Ámbito de marcado**. Cualquier usuario en línea con una licencia de **sistema telefónico** o cualquier usuario hospedado localmente utilizando Skype for Business Server 2015 o Lync Server 2013, puede encontrarse con el marcado por nombre.


* * *

Cuando haya terminado con las selecciones, haga clic en **siguiente**.

#### <a name="holiday-call-settings"></a>Configuración de la llamada de días festivos

Puede agregar un máximo de 20 días festivos programados a cada operador automático.

> [!TIP]
> Puede ir el la pantalla de la **configuración de toda la organización** > **días festivos** para crear los días festivos, o bien puede crearlos como parte de la creación de un nuevo controlador de llamadas.

![Configuración de días festivos en el operador automático](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Número 1](media/sfbcallout1.png)

Si ya ha creado a otros operadores automáticos, es posible que vea una opción que puede usar o editar en lo que necesita en esta lista. Si no es así, debe crear un nuevo controlador de llamadas.

Para agregar un nuevo controlador de llamada, haga clic en **+ nuevo controlador de llamadas**.

* * *

![Configurar los días festivos de operador automático de continuado](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Número 1](media/sfbcallout1.png)

En la ventana nueva, escriba un nombre para el nuevo controlador de llamadas en la parte superior de la pantalla.

![Número 2](media/sfbcallout2.png)

Si el nombre de las vacaciones ya existe en la lista desplegable de **días festivos** , puede usarlo. Si el nombre del día festivo que necesita no existe ya, seleccione **Crear nuevo de días festivos** en la lista desplegable y asignar un nombre y una fecha para el día festivo nuevo en la nueva pantalla que aparece. Haga clic en **Guardar** cuando esté listo.

Los nombres de días festivos pueden constar de hasta 64 caracteres y deben ser únicos para el mismo operador automático. Por ejemplo, no puede tener dos días festivos denominados "Navidad" en el mismo operador automático.

![Número 3](media/sfbcallout3.png)

**Saludo** El saludo es opcional y se puede establecer en **ningún saludo**. En este caso, el autor de la llamada no escuchará ningún mensaje o saludo antes de que la llamada se gestione mediante una de las opciones que seleccione. También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.

- **No hay saludo** Ningún saludo se reproducirá cuando llama personas el número de teléfono de operador automático.
- **Cargar un archivo de audio** Si selecciona esta opción, grabar el saludo de días festivos y, a continuación, cargue el archivo de audio (en un formato .wav,. mp3 o .wma)
- **Escriba un mensaje de saludo** Si elige esta opción, escriba el texto que desea que el sistema para leer (hasta 1000 caracteres). Por ejemplo, puede escribir "¡Feliz año nuevo! Nuestras oficinas están cerradas en este momento". en el cuadro **Escriba un mensaje de saludo** .

![Número 4](media/sfbcallout4.png)

**Acciones** Puede seleccionar lo que ocurre con las llamadas que se reciben durante este día festivo. Puede elegir entre las siguientes opciones:

- **Desconectar** La persona que llama será desconectada tras escuchar el saludo de días festivos.
- **Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:
  - Una **persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione la **persona de la empresa**y establezca esta persona para que sus llamadas se desvían directamente al correo de voz.

    > [!Note]
    > La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013. 

  - Una **cola de llamadas** para transferir la llamada a una cola existente de llamada que ha configurado.
  - Otro **operador automático**, para crear un segundo nivel de opciones de menú que contiene un submenú. Estos se denominan a operadores automáticos anidados.

    > [!Note]
    > De forma predeterminada, todas las llamadas que llegan durante un período de días festivos se establecen en desconectar después de saludo (si hay alguno), por lo que debe especificar un redireccionamiento si se desea obtener un comportamiento diferente.

#### <a name="select-dial-scope-page"></a>Página Seleccionar ámbito de marcado

En esta página, puede configurar qué usuarios de la organización estará enumerados en su directorio y están disponibles para marcado por nombre cuando una persona que llama la organización.

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![Número 1](media/sfbcallout1.png) con la opción **incluir** , tiene dos opciones:

- **Total de usuarios en línea**: esta opción le permite incluir a todas las personas de su organización en la búsqueda en directorios. Se enumerarán todos los usuarios en línea con una licencia de **sistema telefónico**, así como los usuarios hospedados localmente utilizando Skype for Business Server 2015 o Lync Server 2013 que tengan planes de llamada en Office 365.
- **Grupo de usuario personalizadas** Si utiliza esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que se ha creado en la organización y las personas que agregan a este grupo de Office 365, lista de distribución o grupo de seguridad que están bien **usuarios en línea con un Licencia de sistema de teléfono** u hospedado local mediante Skype para Business Server 2015 o Lync Server 2013. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.

* * *

![Número 2](media/sfbcallout2.png)

Uso de la opción **Excluir** , tiene dos opciones:

- **Ninguno**: esta opción indica que no se debe excluir a ningún usuario de la búsqueda en directorios.
- **Grupo de usuario personalizadas** Si utiliza esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que se ha creado en su organización, y todas las personas agregaron a este grupo de Office 365, lista de distribución o grupos de seguridad se excluirá de búsqueda en el directorio. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.

> [!NOTE]
> Puede tardar hasta 36 horas para un nuevo usuario para que su nombre aparezca en el directorio cuando alguien utiliza marcado por nombre con el reconocimiento de voz.

Después de escribir todos los campos necesarios y configurar los menús y las opciones de administración de llamadas, haga clic en **Enviar**.

## <a name="editing-and-testing-auto-attendants"></a>Edición y la prueba de operadores automáticos

Después de guardar un operador automático, este se mostrará en la página **Operadores automáticos**. Esto le permitirá ver rápidamente algunas de las opciones que ha configurado, incluidos el nombre, número de teléfono, idioma y estado.

Si desea realizar cambios en un operador automático, seleccione al operador automático y, a continuación, en el panel de acciones, haga clic en **Editar**.

Puede colocar una llamada de prueba a su operador automático también rápidamente mediante el botón **de prueba** en el panel de acciones.

## <a name="want-to-know-more"></a>¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar operadores automáticos.

### <a name="auto-attendant-cmdlets"></a>Cmdlets para operadores automáticos

Estos son los cmdlets que necesita para administrar un operador automático.

- [Nueva CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csattendant?view=skype-ps) 
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [Nueva CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [Nueva CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [Nueva CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [Nueva CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [CsAutoAttendantHolidays de importación](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [Nueva CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a>Más información sobre Windows PowerShell

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Teams Microsoft mediante un único punto de administración que puede simplificar su trabajo diario, cuando haya varias tareas para hacer. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre sólo desde el centro de administración de Microsoft 365 como cuando desea realizar cambios en la configuración de muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Administración de Office 365 con PowerShell de Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico de Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtener números de teléfono de servicio](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)

[Ejemplo de pequeña empresa: configurar un operador automático](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)  

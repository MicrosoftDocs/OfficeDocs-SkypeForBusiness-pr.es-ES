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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Aprenda a configurar y probar los operadores automáticos de la nube para Microsoft Teams.
ms.openlocfilehash: 6ac4ccea48e70a8bba5e11511379fef5c5a2a861
ms.sourcegitcommit: e89c2234fc5aa8f7eeef66ba1ae093a0f7beda85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "37349254"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Configurar un operador automático en la nube

Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para obtener acceso al Departamento adecuado, a la cola de llamadas, a la persona o al operador. Puede crear un operador automático para su organización mediante el centro de administración de Microsoft Teams. Para crear un nuevo operador automático, vaya a **voz** en el navegación izquierdo y, después, seleccione >  **operadores automáticos**,**Agregar nuevo**.

Si desea obtener más información sobre los operadores automáticos, vea [¿Qué son los operadores automáticos de la nube?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Este artículo se aplica a Microsoft Teams y a Skype empresarial online.

## <a name="step-1--get-started"></a>Paso 1: introducción

- Es necesario un operador automático para tener una cuenta de recursos asociada. Consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) para obtener información sobre las cuentas de recursos y todas las licencias necesarias.

> [!TIP]
> Para redirigir las llamadas a un operador o una opción de menú que sea un usuario en línea con una licencia de **sistema telefónico** , tendrá que habilitarlos para telefonía IP empresarial. Consulte [asignar licencias de Skype empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [asignar licencias de Microsoft Teams](assign-teams-licenses.md). También puede usar Windows PowerShell. Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-a-new-auto-attendant"></a>Paso 2: crear un nuevo operador automático

> [!IMPORTANT]
> Cada operador automático debe tener una [cuenta de recursos](manage-resource-accounts.md)asociada. Debe crear primero la cuenta de recursos y, a continuación, asociarla al operador automático.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

En el **centro de administración de Microsoft Teams**, haga clic en**operadores automáticos**de **voz** > y, a continuación, haga clic en **+ nuevo**:

#### <a name="general-info-page"></a>Página de información general

![Captura de pantalla de la página mi operador automático](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

**Nombre** Escriba un nombre descriptivo para mostrar para el operador automático. El nombre es obligatorio, y puede contener hasta 64 caracteres, espacios incluidos. Aparece en la columna **nombre** de la ficha **operadores automáticos** .

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

<a name="phonenumber"> </a>

**Cuenta de recursos** Haga clic en este botón para seleccionar una o más cuentas de recursos para conectarse al nuevo operador automático. Es necesario que todos los operadores automáticos tengan una cuenta de recursos asociada. Una cuenta de recursos puede tener un número de teléfono asociado a la cuenta, pero un número de teléfono no es obligatorio. Un operador automático de nivel superior suele tener una cuenta de recursos con un número de teléfono asignado, pero el operador automático anidado (usado como un menú de nivel 2 al que se conecta el operador automático de primer nivel) podría no tener asignado un número de teléfono a su cuenta de recursos.

* * *

![Icono del número 3, que hace referencia a una llamada en la](media/sfbcallout3.png)
 <a name="timezone"> </a> captura de pantalla anterior

**Zona horaria**: debe establecer la zona horaria para el operador automático, pero no es necesario que se corresponda con la zona horaria de la dirección principal que se muestra para su organización. Cada operador automático puede tener una zona horaria diferente y el horario de oficina establecido para el operador automático se establece en función de la zona horaria que seleccione aquí.

* * *

![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout4.png)

<a name="language"> </a>

**Idioma** Seleccione el idioma que desea usar para su operador automático en cualquiera de los idiomas disponibles en la lista. El idioma que establezca aquí es el idioma que usa el operador automático para interactuar con personas que llaman a este operador automático y todas las solicitudes del sistema se reproducen en este idioma.

* * *

![Icono del número 5, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout5.png)

<a name="operator"> </a>

**Operador** Esto es opcional, pero puede configurar la opción de **operador** para permitir que los autores de llamadas interrumpan los menús y hablen con una persona.

La tecla 0 está asignada al operador de forma predeterminada.

Si establece un operador, también tendrá que indicar a los usuarios que llamen sobre la opción en las **Opciones del menú Editar** en la página **Administración de llamadas de horario laboral** . Si estableces un operador en tu operador automático, deberás escribir el texto del mensaje correspondiente en el cuadro de la **persona que llamarás** o cambiaremos el archivo de audio para incluir esta opción. Por ejemplo, "Para hablar con el operador, pulse cero."

Tiene varias formas de configurar el operador:

- **Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365.

     > [!Note]
     > La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.

- **Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.
- Puedes configurarlo para que la persona que llama se envíe al buzón de voz. Para ello, seleccione **una persona de su empresa** y configure las llamadas de esta persona para que se desvíen directamente al buzón de voz.

* * *

![Icono del número 6, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout6.png)

**Habilitar las entradas de voz** El reconocimiento de voz está disponible si esta opción está seleccionada. Las personas que llaman pueden usar la entrada de voz en el [idioma que haya establecido](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Si solo quiere permitir que los usuarios usen el teclado del teléfono, puede deshabilitar el reconocimiento de voz si lo establece en desactivado.

* * *

Cuando haya terminado con las selecciones, haga clic en **siguiente**.

#### <a name="business-hours-page"></a>Página de horario comercial

De forma predeterminada, el horario laboral se establece en 9:00 am a 5:00 PM, de lunes a viernes. Todas las horas que no se incluyen en el horario comercial se consideran horas de oficina. Puede hacer clic en **seleccionar 24/7** para hacer todas las horas de trabajo. A menos que seleccione la opción **seleccionar 24/7** , se usará la página de **configuración de llamada de poshorario** para configurar las reglas de administración de llamadas para el operador automático después del horario laboral.

![Captura de pantalla de la página de horario comercial](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

De forma predeterminada, el horario laboral se establece de lunes a viernes, 9:00 a.m.-5:00 p.m. Seleccione **borrar todas las horas** para anular la selección de todas las horas de la programación. Cuando selecciona **Restablecer valores predeterminados**, el horario laboral se restablece a lunes a viernes, 9:00 a.m.-5:00 p.m.

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

Para cambiar el horario de oficina, resalte las horas laborales que desea establecer en el calendario. El calendario le permite seleccionar el horario laboral en intervalos de 30 minutos y las horas laborales que seleccione aquí se basan en la zona horaria que estableció en la página de **información general** . Para configurar un descanso (almuerzo, por ejemplo), anule la selección o arrastre para anular la selección de la hora en el calendario. Puede establecer varios descansos dentro del horario comercial.

* * *

Cuando haya terminado con las selecciones, haga clic en **siguiente**.

#### <a name="business-hours-call-settings"></a>Configuración de llamadas a horario laboral

> [!TIP]
> Si usa una programación de horario laboral personalizada, también tendrá que configurar la mano de la llamada para después del horario comercial mediante la página de **Administración de llamadas de poshorario** , que le dará las mismas opciones que la **configuración de llamadas a horario laboral**.

Puede configurar los saludos, los avisos y los menús que los usuarios escuchan al llamar al número de teléfono vinculado al operador automático de su organización durante el horario laboral.

![Captura de pantalla de la página](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![de tratamiento de llamadas de horario comercial captura de pantalla de la sección acciones de la página de administración de llamadas en horario comercial](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

<a name="greetingsandrouting"> </a>

**Saludo** Un saludo de horario laboral es opcional y puede configurarse como **sin saludo**. En este caso, el autor de la llamada no escuchará un mensaje o saludo antes de que una de las acciones que seleccione haya controlado la llamada. También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.
- **Cargar un archivo de audio** Si elige esta opción, grabe el saludo y, a continuación, cargue el archivo de audio (en formato. wav,. mp3 o. WMA).
- **Escribir un mensaje de bienvenida** Si elige esta opción, escriba el texto que quiere que lea el sistema (hasta 1000 caracteres). Por ejemplo, puede escribir "Bienvenidos a Contoso. Su llamada es muy importante para nosotros." en el cuadro **Los autores de llamadas escucharán**.

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

Puede seleccionar lo que ocurre con las llamadas que se reciben durante el horario comercial. Puede elegir entre las siguientes acciones:

<a name="redirectcalls"> </a>

- **Desconectar** Si se selecciona, la persona que llama sera desconectada tras escuchar un saludo de horario comercial.
- **Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:
  - **Persona en la empresa** con una licencia de **sistema telefónico** habilitada para telefonía IP empresarial o planes de llamadas asignados en Office 365. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione **persona en la empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.

    > [!Note]
    > Una **persona en la empresa** puede ser un usuario en línea o un usuario local que use Skype empresarial Server 2015 o Lync Server 2013.

   - Otro **operador automático**

   Puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contengan un submenú. Estos se denominan a operadores automáticos anidados. Para enviar la llamada a un operador automático anidado, seleccione **persona en la empresa** y asigne una cuenta de recurso, ya sea una cuenta que ya tenga un operador automático asociado o que vaya a asociar a un operador automático una vez que haya terminado de crear este operador automático.

- **Las opciones de menú reproducir** también se pueden usar para configurar el aviso que desea reproducir.

* * *

![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout3.png)

**Texto del menú**: para crear un mensaje para el menú principal puede usar la característica Texto a voz o cargar un archivo de audio (.wav, .mp3 o .wma). Puede escribir el mensaje en el cuadro **establecer la navegación del menú para las personas que llaman** o grabar un archivo de audio y decir, por ejemplo: "para ventas, diga o presione o diga 1. Pulse o diga 2 para Servicios. Pulse o diga 3 para Atención al cliente. Para hablar con el operador, pulse o diga 0. Para escuchar este mensaje de nuevo, pulse la tecla de asterisco o diga Repetir". **Escribir un mensaje de bienvenida** Si ha elegido esta acción, debe introducir el texto que quiere que lea el sistema (hasta 1000 caracteres). **Cargar un archivo de audio**: si elige esta opción, deberá grabar el saludo y cargar el archivo de audio (en formato .wav, .mp3 o .wma).

* * *

![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout4.png)

**Configuración de opciones de menú** Las opciones de menú con botones de teclas del teclado numérico se pueden agregar o quitar. Para agregar una opción de menú, presione **+ asignar una tecla de marcado**. A continuación, aparece una fila de opciones correspondiente. Para eliminar una opción de menú, simplemente haga clic a la izquierda de la tecla correspondiente en el control del teclado y haga clic en el icono eliminar de arriba. Se quitará la fila de asignación de teclas.

> [!TIP]
> Tendrá que actualizar el mensaje de texto o volver a grabar el audio por separado al agregar opciones de eliminación, ya que no se realizará automáticamente en la solicitud de menú existente.  
>
>Cualquier opción del menú se puede Agregar y quitar en cualquier orden, y las asignaciones de teclas no tienen que ser continuas. Es posible, por ejemplo, crear un menú con las teclas 0, 1 y 3 asignadas a las opciones, mientras que la clave 2 no se usa.

> [!NOTE]
> Las teclas \* (repetir) y \# (atrás) están reservadas por el sistema y no se pueden reasignar. Si el reconocimiento de voz está habilitado, presionar * se corresponde con "repetir" y # se corresponde con los comandos de voz "atrás".

Para configurar las opciones de menú, después de seleccionar las teclas de marcado, tendrá que:

- Escriba el **comando de voz** de la opción. Puede tener hasta 64 caracteres y puede contener varias palabras, como "servicio al cliente" o "operaciones y motivos". Si está habilitado el reconocimiento de voz, automáticamente se reconocerá el nombre y la persona que llama podrá, o bien presionar 3, decir "tres" o decir "servicio de asistencia al cliente" para seleccionar la opción asignada a la tecla 3.
- Seleccione el lugar donde se enviará la llamada si se presiona la tecla correspondiente o se selecciona la opción con reconocimiento de voz. La llamada se puede enviar al:

  - **Operador** Si el operador ya está configurado, se asigna automáticamente a la tecla 0, pero también se puede eliminar o volverse a asignar a una tecla diferente. Si el operador no está establecido para alguna tecla, entonces el comando de voz "Operador" se deshabilitará también.
  - **Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a un plan de llamadas en Office 365. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione **una persona de su empresa** y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.

    > [!Note]
    > **La persona de su empresa** puede ser un usuario en línea o un usuario local alojado con Skype empresarial Server o Lync Server 2013.
    - Otro **operador automático**

       Puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contengan un submenú. Estos se denominan a operadores automáticos anidados. Para enviar la llamada a un operador automático anidado, seleccione **persona en la empresa** y asigne una cuenta de recurso, ya sea una cuenta que ya tenga un operador automático asociado o que vaya a asociar a un operador automático una vez que haya terminado de crear este operador automático.

        > [!Note]
        > El **Horario comercial** de operadores automáticos anidados (o de segundo nivel) también se utilizará, lo que incluye las llamadas enviadas desde otros operadores automáticos que se hayan configurado.

       - **Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.

* * *

![Icono del número 5, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout5.png)

**Marcado por nombre** Si elige esta opción, los usuarios que llamen para buscar personas de su organización podrán usar la búsqueda en el directorio. Puede seleccionar qué personas se mostrarán como disponibles o no disponibles para el marcado por nombre mediante la configuración de esas opciones en la página **Ámbito de marcado**. Cualquier usuario en línea con una licencia de **sistema telefónico** o cualquier usuario local que use Skype empresarial Server o Lync Server 2013 puede encontrarse con el marcado por nombre.

* * *

Cuando haya terminado con las selecciones, haga clic en **siguiente**.

#### <a name="holiday-call-settings"></a>Configuración de llamadas navideñas

Puede agregar un máximo de 20 días festivos programados a cada operador automático.

> [!TIP]
> Puede ir a la pantalla a lo **ancho** > de la organización**días festivos** para crear días no laborables o puede crearlos como parte de la creación de un nuevo controlador de llamadas.

![Captura de pantalla de la página de configuración de llamadas de vacaciones](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

Si ya ha creado otros operadores automáticos, es posible que vea la opción que puede usar o modificar lo que necesita en esta lista. De lo contrario, tendrás que crear un nuevo controlador de llamadas.

Para agregar un nuevo controlador de llamadas, haz clic en el **controlador de llamadas + nuevo**.

* * *

![Captura de pantalla que muestra cómo agregar un nuevo controlador de llamadas](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

En la nueva ventana, escriba un nombre para el nuevo controlador de llamadas en la parte superior de la pantalla.

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

Si el nombre de tu día no laborable ya existe en la lista desplegable de **días festivos** , puedes usarlo. Si el nombre de la festividad que necesita aún no existe, seleccione **crear nuevo día festivo** en la lista desplegable y asigne un nombre y una fecha para el nuevo día festivo en la nueva pantalla que aparece. Haz clic en **Guardar** cuando esté listo.

Los nombres de días festivos pueden constar de hasta 64 caracteres y deben ser únicos para el mismo operador automático. Por ejemplo, no puede tener dos días festivos denominados "Navidad" en el mismo operador automático.

![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout3.png)

**Saludo** El saludo es opcional y puede configurarse como **sin saludo**. En este caso, el autor de la llamada no escuchará ningún mensaje o saludo antes de que la llamada se gestione mediante una de las opciones que seleccione. También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.

- **Sin saludo** No se reproducirá ningún saludo cuando las personas llamen al número de teléfono del operador automático.
- **Cargar un archivo de audio** Si elige esta opción, grabe el saludo de las vacaciones y, a continuación, cargue el archivo de audio (en formato. wav,. mp3 o. WMA).
- **Escribir un mensaje de bienvenida** Si elige esta opción, escriba el texto que quiere que lea el sistema (hasta 1000 caracteres). Por ejemplo, puede escribir "¡Feliz año nuevo! Nuestras oficinas están cerradas en este momento". en el cuadro **Escriba un mensaje de saludo** .

![Icono del número 4, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout4.png)

**Acciones** Puede seleccionar qué sucede con las llamadas que llegan durante este día festivo. Puede elegir entre las siguientes opciones:

- **Desconectar** La persona que llama será desconectada tras escuchar el saludo de días festivos.
- **Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:
  - Una **persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione **una persona de su empresa**y configure esta persona para que sus llamadas se desvíen directamente al buzón de voz.

    > [!Note]
    > La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013.

   - **Aplicación de voz** Seleccione el nombre de una cuenta de recursos asociada a una cola de llamadas o a un operador automático que ya se ha creado.

    > [!Note]
    > De forma predeterminada, todas las llamadas que llegan durante un período de días festivos se establecen en desconectar después de saludo (si hay alguno), por lo que debe especificar un redireccionamiento si se desea obtener un comportamiento diferente.

#### <a name="select-dial-scope-page"></a>Página Seleccionar ámbito de marcado

En esta página, puede configurar los usuarios de su organización que aparecerán en el directorio y que estarán disponibles para marcar por su nombre cuando sea una persona que llame a su organización.

![Captura de pantalla que muestra la página ámbito de marcado](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![Icono del número 1, que hace referencia a una llamada en la](media/sfbcallout1.png) captura de pantalla anterior con la opción **incluir** , tiene dos opciones:

- **Total de usuarios en línea**: esta opción le permite incluir a todas las personas de su organización en la búsqueda en directorios. Se mostrarán todos los usuarios conectados que tengan una licencia de **sistema telefónico** , así como los usuarios locales que utilicen Skype empresarial Server o Lync Server 2013 que tengan planes de llamadas en Office 365.
- **Grupo de usuarios personalizado** Si usa esta opción, puede buscar un grupo de Office 365, una lista de distribución o un grupo de seguridad que se haya creado en su organización y las personas que se han agregado a este grupo de Office 365, una lista de distribución o un grupo de seguridad que sean **usuarios conectados con un Licencia de sistema telefónico** o se ha hospedado de forma local con Skype empresarial server 2015 o Lync Server 2013. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.

* * *

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout2.png)

Con la opción **excluir** tiene dos opciones:

- **Ninguno**: esta opción indica que no se debe excluir a ningún usuario de la búsqueda en directorios.
- **Grupo de usuarios personalizado** Si usa esta opción, puede buscar un grupo de Office 365, una lista de distribución o un grupo de seguridad que se haya creado en su organización, y todas las personas agregadas a este grupo de Office 365, lista de distribución o grupos de seguridad se excluirán de la búsqueda en directorio. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.

> [!NOTE]
> Es posible que tarde hasta 36 horas para que un nuevo usuario tenga su nombre en el directorio cuando alguien usa el marcado por nombre con reconocimiento de voz.

Después de especificar todos los campos obligatorios y configurar los menús y las opciones de administración de llamadas, haga clic en **Enviar**.

## <a name="editing-and-testing-auto-attendants"></a>Editar y probar los operadores automáticos

Después de guardar un operador automático, este se mostrará en la página **Operadores automáticos**. Esto le permitirá ver rápidamente algunas de las opciones que ha configurado, como el nombre, el número de teléfono, el idioma y el estado.

Si desea realizar cambios en un operador automático, seleccione el operador automático y, a continuación, en el panel de acciones, haga clic en **Editar**.

También puede hacer una llamada de prueba a su operador automático con el botón **probar** del panel de acciones.

## <a name="auto-attendant-cmdlets"></a>Cmdlets para operadores automáticos

También puede usar Windows PowerShell para crear y configurar operadores automáticos. Estos son los cmdlets que necesita para administrar un operador automático:

- [Nuevo: CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [Nuevo: CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [Nuevo: CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [Nuevo: CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [Exportar-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [Nuevo: CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [Importar-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [Nuevo: CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Más información sobre Windows PowerShell

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Microsoft Teams con un único punto de administración que puede simplificar su trabajo diario, cuando tenga que hacer varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Administrar Office 365 con Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico de Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtener números de teléfono de servicio](/microsoftteams/getting-service-phone-numbers)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)

[Ejemplo de pequeña empresa: configurar un operador automático](/microsoftteams/tutorial-org-aa)  

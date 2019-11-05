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
ms.openlocfilehash: b1756cc58e485971157c0429e8180a5f5e507ec8
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972481"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Configurar un operador automático en la nube

Los operadores automáticos permiten a los usuarios llamar a su organización y navegar por un sistema de menús para hablar con el Departamento adecuado, la cola de llamadas, la persona o un operador. Puede crear operadores automáticos para su organización con el centro de administración de Microsoft Teams o con PowerShell. Para crear un operador automático, vaya a **voz** en el navegación izquierdo y, después, seleccione >  **operadores automáticos**,**Agregar nuevo**.

Si desea obtener más información sobre los operadores automáticos, vea [¿Qué son los operadores automáticos de la nube?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Este artículo se aplica a Microsoft Teams y a Skype empresarial online.

Los números de teléfono no se asignan directamente al operador automático, sino a una [cuenta de recursos](manage-resource-accounts.md) asociada al operador automático.

Las implementaciones de operadores automáticos suelen implicar varios operadores automáticos. Normalmente, los operadores automáticos de *primer nivel* tienen una cuenta de recursos con un número de teléfono asignado. Un operador automático anidado se usa como un menú de segundo nivel al que el operador automático de *primer nivel* se conecta como una llamada. No es necesario que un operador automático *anidado* tenga asignado un número de teléfono a su cuenta de recursos.

## <a name="step-1--get-started"></a>Paso 1: introducción

- Es necesario un operador automático para tener una cuenta de recursos asociada. Consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) para obtener información sobre las cuentas de recursos y todas las licencias necesarias. 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> Para redirigir las llamadas a un operador o una opción de menú que sea un usuario en línea con una licencia de sistema telefónico, tendrá que habilitarlos para telefonía IP empresarial. Consulte [asignar licencias de Skype empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) o [asignar licencias de Microsoft Teams](assign-teams-licenses.md). También puede usar Windows PowerShell. Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-auto-attendants"></a>Paso 2: crear operadores automáticos

> [!IMPORTANT]
> Cada operador automático debe tener una [cuenta de recursos](manage-resource-accounts.md)asociada. Debe crear primero la cuenta de recursos y, a continuación, asociarla al operador automático.

### <a name="with-the-microsoft-teams-admin-center"></a>Con el centro de administración de Microsoft Teams

En el **centro de administración de Microsoft Teams**, haga clic en**operadores automáticos**de **voz** > y, a continuación, haga clic en **+ Agregar**:

#### <a name="general-info-page"></a>Página de información general

![Captura de pantalla de la página mi operador automático](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Icono del número 1, una llamada en el](media/teamscallout1.png)
**nombre** de la captura de pantalla anterior, escriba un nombre para mostrar para el operador automático. El nombre es obligatorio, y puede contener hasta 64 caracteres, espacios incluidos. El **nombre** que designe aquí aparecerá en una columna en la pestaña de **operadores automáticos** .

<a name="phonenumber"> </a>

* * *

![Icono del número 2, llamada en el](media/teamscallout2.png)
 <a name="operator"> </a> 
 **operador** de captura de pantalla anterior, esto es opcional (pero se recomienda). Puede configurar la opción de **operador** para permitir que los autores de llamadas interrumpan los menús y hablen con una persona designada.

La tecla 0 está asignada al operador de forma predeterminada.

Si establece un operador, indique a los usuarios que llamen sobre la opción de las **Opciones del menú Editar** en la página **flujo de llamadas** . Si estableces un operador en tu operador automático, escribes el texto del mensaje correspondiente en el cuadro los autores de las **llamadas escucharán** o cambiarán el archivo de audio para incluir esta opción. Por ejemplo, "Para hablar con el operador, pulse cero."

Tiene varias formas de configurar el operador:

- **Ningún operador** deshabilita las opciones "operador" y "presionar 0". Este es el valor predeterminado actual.
- **La persona de su organización** asigna a una persona una licencia de sistema telefónico habilitada para telefonía IP empresarial o planes de llamadas asignados en Office 365. También puedes configurarlo para que la persona que llama se envíe al buzón de voz. Para enviar una llamada al buzón de voz, seleccione una **persona de la organización** y establezca la configuración de esa cuenta para enviar llamadas directamente al buzón de voz.

     > [!Note]
     > **La persona de su organización** puede ser un usuario en línea o un usuario local alojado con Skype empresarial Server.

- **Aplicación de voz**  Seleccione el nombre de la cuenta de recursos vinculada a un operador automático o a una cola de llamadas que ya se ha creado. Las personas que llaman que solicitan un operador se redirigen allí.  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<a name="timezone"> </a>

![Icono del número 3, una llamada en la](media/teamscallout3.png) **zona horaria** de captura de pantalla anterior, se requiere establecer la zona horaria para el operador automático. La configuración puede ser la misma que la zona horaria de la dirección principal que se muestra para su organización, u otra zona horaria. Cada operador automático puede tener una zona horaria diferente. El horario comercial establecido para el operador automático también usa esta zona horaria.

* * *

![Icono del número 4, una llamada en el](media/teamscallout4.png)
 <a name="language"> </a> 
 **idioma** de captura de pantalla anterior, seleccione el idioma que desea usar para el operador automático. El operador automático usa ese idioma con las personas que llaman y todas las solicitudes del sistema se reproducen en este idioma.

 * * *

![Icono del número 5, una llamada en la captura de pantalla](media/teamscallout5.png)
anterior**habilitar las entradas de voz** el reconocimiento de voz está disponible si esta opción está seleccionada. Las personas que llaman pueden usar la entrada de voz en el [idioma que establezcas](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Si solo quiere permitir que los usuarios usen el teclado del teléfono para hacer selecciones, puede dejar el reconocimiento de voz establecido en **desactivado**.

* * *  

Cuando haya terminado con las selecciones, haga clic en **siguiente**.

#### <a name="call-flow"></a>Flujo de llamadas

<a name="greetingsandrouting"> </a>

> [!TIP]
> Puede configurar una programación de horario comercial personalizada, con diferentes comportamientos de flujo de llamadas durante y después del horario comercial. Para establecer una programación personalizada, establezca el [flujo de llamadas opcionales para después de las horas](#call-flow-for-after-hours). De forma predeterminada, los operadores automáticos usan los flujos de llamadas de horario laboral.

Puede configurar saludos, avisos y menús personalizados que los usuarios escucharán cuando lleguen a su operador automático.

![Captura de pantalla: sección de saludo de la página de administración de llamadas](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

**Reproducir primero un mensaje de bienvenida** Un saludo es opcional y puede configurarse como **sin saludo**, **reproducir un archivo de audio**o **escribir un mensaje de bienvenida**.

> [!NOTE]
> Un saludo es más valioso para un operador automático de primer nivel. Un operador automático anidado a menudo no necesita un saludo.

![Icono del número 1, una llamada en la captura de pantalla](media/teamscallout1.png) anterior si selecciona **sin saludo**, la persona que llama no escuchará un mensaje o saludo antes de que una de las acciones que seleccione más tarde controle la llamada. 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

![Icono del número 2, una llamada en la captura de pantalla](media/teamscallout2.png) anterior si selecciona **reproducir un archivo de audio** , puede usar el botón **Cargar archivo** para cargar un mensaje de saludo grabado guardado como audio. WAV,. MP3 o. Formato WMA. La grabación no puede tener más de 5 MB.

![Icono del número 3, una llamada en la captura de pantalla](media/teamscallout3.png) anterior **escribir un mensaje de saludo** si elige esta opción, escriba el texto que quiere que lea el sistema (hasta 1000 caracteres) en el campo proporcionado. Por ejemplo, escriba "Bienvenido a contoso. Su llamada es muy importante para nosotros." El resultado se crea mediante el software de texto a voz.

* * *

Puede seleccionar lo que sucede junto a llamadas de las siguientes acciones en el **después, enrutar la** sección de llamada. La configuración es **desconectar**, **redirigir llamada**o **reproducir opciones de menú**.

Si selecciona **desconectar**, la persona que llama se desconecta cuando se reproduce el saludo. 

<a name="redirectcalls"> </a>

![Icono del número 4, una llamada en la captura de pantalla](media/teamscallout4.png) anterior **llamada de redireccionamiento** envía el autor de la llamada al destino elegido sin elegir las opciones. Los valores posibles son:

  - **Persona en la organización** La cuenta que elija debe tener habilitada una licencia de sistema telefónico para telefonía IP empresarial o tener un plan de llamadas asignado en Office 365. Puedes configurarlo para que la persona que llama pueda enviarse al buzón de voz: selecciona una **persona en la organización** y configura esa cuenta para que las llamadas se desvíen directamente al buzón de voz.

  > [!Note]
  > Una **persona en la organización** puede ser un usuario en línea o un usuario local alojado con Skype empresarial Server.

  - **Aplicación de voz** Seleccione un operador automático o una cola de llamadas que ya se haya configurado. Buscas el operador automático o la cola de llamadas por el nombre de la cuenta de recursos asociada con el servicio.

<!-- - **Auto attendant** Select the name of an existing auto attendant.
- **Call queue** Select the name of an auto attendant that has already been created.
- **External phone number** routes the caller to a phone number outside your local system.
- **Operator** directs the call to a user you designate as an Operator. If you haven't previously set up an operator, an option to create one now shows up. The 0 key is assigned to Operator by default. Options for setting an Operator are:

  - **No operator** disables the "Operator" and "Press 0" options.
  - **Person in your organization** can be an Online user or a user hosted on-premises using Skype for Business Server. They must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. Search for the operator in the **Destination for your operator** field.
  - **Auto attendant** lets you choose the name of an existing auto attendant.
  - **Call queue** lets you select an existing call queue.
  - **Group Voicemail** routes the call to a voicemail box that you select. -->

 * * *

![Captura de pantalla: sección acciones de la página de administración de llamadas](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

![Icono del número 1, una llamada en la captura de pantalla](media/teamscallout1.png) anterior al seleccionar la **opción reproducir opciones de menú** puede seleccionar si desea usar un archivo de audio o introducir texto que se representará como texto a voz para proporcionar opciones de menú de marcado a las personas que llamen. Seleccione esta opción en lugar de las opciones de llamada o **desconexión** **de redireccionamiento** .


![Icono del número 2, una llamada en la captura de pantalla](media/teamscallout2.png) anterior **reproducir un archivo de audio** le permite configurar un mensaje y opciones para que la persona que llama elija. 
- Si selecciona **reproducir un archivo de audio** , puede usar el botón **Cargar archivo** para cargar un mensaje de saludo grabado guardado como audio en. WAV,. MP3 o. Formato WMA. La grabación no puede tener más de 5 MB.

- **Escribir un mensaje de bienvenida** Si elige esta opción, escriba el texto que quiere que el sistema Lea (hasta 1000 caracteres) en el campo proporcionado. Por ejemplo, escriba "Bienvenido a contoso. Su llamada es muy importante para nosotros." El resultado se crea mediante el software de texto a voz.

**Establecer opciones de menú** En este cuadro de diálogo se pueden agregar o quitar comandos de voz o de teclado. Para eliminar una opción de menú, quite la entrada de comando de voz y establezca **redirección para** volver a **seleccionar**.

> [!TIP]
> Actualice el texto del mensaje del menú o vuelva a grabar las indicaciones de audio al quitar las opciones. El mensaje de menú reproducido para las personas que llaman no se actualiza automáticamente.  
>
> Cualquier opción del menú se puede Agregar y quitar en cualquier orden, y las asignaciones de teclas no tienen que ser continuas. Es posible, por ejemplo, crear un menú con las teclas 0, 1 y 3 asignadas a las opciones, mientras que la clave 2 no se usa.

> [!NOTE]
> Las teclas \* (repetir) y \# (atrás) están reservadas por el sistema y no se pueden reasignar. Si el reconocimiento de voz está habilitado, presionar * se corresponde con "repetir" y # se corresponde con los comandos de voz "atrás".

![Icono del número 3, una llamada en la captura de pantalla](media/teamscallout3.png) anterior para configurar una opción de menú, haga clic en la **tecla + asignar una tecla de marcado** e introduzca la información de las siguientes opciones:

![Icono del número 4, una llamada en la captura de pantalla](media/teamscallout4.png)anterior la columna**comando de voz** de una opción puede tener un máximo de 64 caracteres y puede contener varias palabras, como "servicio al cliente" o "operaciones y motivos".   Si el reconocimiento de voz está habilitado, el nombre se reconoce automáticamente y la persona que llama puede presionar 3, decir "tres" o decir "servicio al cliente" para seleccionar la opción asignada a la tecla 3. Este texto se representa también por texto a voz para la solicitud de confirmación del servicio, que puede ser algo como "transferencia de la llamada al operador".

![Icono del número 5, llamada en la captura de pantalla](media/teamscallout5.png) anterior el **redireccionamiento a** conjuntos de opciones donde la llamada se muestra si se presiona la tecla correspondiente, o se selecciona la opción con reconocimiento de voz. La llamada se puede enviar al:

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- **Operador** Si un operador ya está configurado, la opción se asigna automáticamente a la clave 0, pero también se puede eliminar o reasignar a una clave diferente. El autor de la llamada que selecciona esta opción se envía al operador designado. Si el operador no se establece en ninguna tecla, el comando de voz "operador" también está deshabilitado. 
- Una **persona en la organización** puede ser un usuario en línea o un usuario local alojado con Skype empresarial Server. El usuario debe tener una licencia de sistema telefónico habilitada para telefonía IP empresarial o planes de llamadas asignados en Office 365. Busque la persona en el campo **Buscar por nombre** .

  - **Aplicación de voz** Seleccione un operador automático o una cola de llamadas que ya se haya configurado. Busque el operador automático o la cola de llamadas por el nombre de la cuenta de recursos asociada con la aplicación.

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

![Icono del número 6, una llamada en la captura de pantalla](media/teamscallout6.png)anterior buscar en el**directorio** de esta sección, puede habilitar el **marcado por nombre** y la **extensión de marcado por extensión** para el operador automático.   Puede establecer quién está y no incluido en estos servicios en la página de ámbito de marcado opcional. La búsqueda en el directorio se establece en **ninguno** de forma predeterminada.

**Marcado por nombre** Si habilita esta opción, las personas que llaman pueden buscar personas de su organización mediante el **marcado por nombre**. Dicen que el nombre del usuario y el reconocimiento de voz coinciden con el usuario. Puede establecer quién está y no incluido en estos servicios en la página de ámbito de marcado opcional. Cualquier usuario en línea con una licencia de sistema telefónico o cualquier usuario local que use Skype empresarial Server es un usuario elegible y puede encontrarse con el marcado por nombre.

[!INCLUDE [preview-feature](includes/preview-feature.md)]

**Marcado por extensión** (esta característica de vista previa aún no está disponible para el público en general) Si habilita esta opción, las personas que llaman pueden conectarse con los usuarios de su organización escribiendo su extensión de teléfono. Puede seleccionar qué usuarios aparecen como disponibles o no disponibles para **marcar por extensión** en la página de ámbito de marcado opcional. Cualquier usuario en línea con una licencia de sistema telefónico o cualquier usuario local que use Skype empresarial Server es un usuario elegible y puede encontrarse con la función de marcado por extensión.

> [!IMPORTANT]
> Siga estos pasos:
>- Los usuarios que desea que estén disponibles para marcar por extensión necesitan tener una extensión especificada como parte de su número de teléfono o número de teléfono móvil asignado en el [centro de administración de Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/add-users?view=o365-worldwide#use-the-new-admin-center-to-add-users).  El formato requerido para introducir la extensión en el campo número de teléfono del usuario es `+<phonenumber>;ext=<extension>` o `x<extension>`.
>- La asignación de una extensión en el centro de administración de Teams no es compatible actualmente. Debe usar el comando [set-MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) de PowerShell o el centro de administración de Microsoft 365.
>- Pueden pasar hasta 12 horas antes de que los cambios de los atributos PhoneNumber y PhoneNumber de AAD estén disponibles.
>- NO defina una extensión para el LineUri de un usuario. Esto no es compatible actualmente.
>- Se puede configurar un operador automático para marcado por nombre o por extensión de marcado, pero no para ambos.

> [!NOTE]
> Si desea usar el **marcado por nombre** y las características de **marcado por extensión** , puede crear un operador automático principal (habilitado para **marcado por nombre**) que pide a las personas que llamen a las personas que eligen una opción de menú si conocen la extensión del usuario y establecen esa opción en transferir la llamada a un operador automático habilitado para marcado por extensión.

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

Cuando haya terminado con las selecciones, puede hacer clic en **siguiente** si desea cambiar la configuración avanzada o hacer clic en **Enviar** si desea usar la configuración predeterminada para cosas como:
- Flujo de llamadas para después del horario
- Flujo de llamadas para días festivos
- Ámbito de marcado
- Cuentas de recursos

Puesto que el operador automático debe tener una cuenta de recursos, tiene la opción de continuar con la página de la **cuenta de recursos** y asociar una cuenta de recursos que ya haya configurado, o crear una cuenta de recursos y asociarla con el operador como se describe en [administrar cuentas de recursos en Microsoft Teams](manage-resource-accounts.md). No podrá usar este operador automático hasta que se haya asociado a una cuenta de recursos. para ello, haga clic en el botón **siguiente** de la parte inferior de la pantalla y, a continuación, haga clic en **cuentas de recursos** en el navegación izquierdo para ir directamente a la página cuentas de recursos y asociar el operador automático a una cuenta de recursos.

#### <a name="advanced-settings-optional"></a>Configuración avanzada (opcional)

Hay cuatro pantallas adicionales que puede configurar o dejar como valores predeterminados.

##### <a name="call-flow-for-after-hours"></a>Flujo de llamadas para después del horario

De forma predeterminada, el horario laboral de un operador automático se establece en 9:00-17:00, de lunes a viernes.  <!--24/7-->y las opciones de flujo de llamadas para las llamadas de *poshorario* están deshabilitadas porque todas las horas se consideran *horas laborales*. Al seleccionar la opción **configurar horas de negocios personalizadas** , el **flujo de llamadas para la página de poshoras** configura las reglas de administración de llamadas usadas por el operador automático después de las horas de trabajo. Las opciones disponibles son las mismas, la diferencia es la capacidad de establecer una programación para distintos menús y comportamientos.

Es posible que un sistema de operadores automáticos solo necesite establecer el comportamiento del control de llamadas después del horario para el operador automático de primer nivel. Es posible que el operador automático de primer nivel no pueda llamar a los operadores automáticos anidados, pero también es posible que el sistema defina un comportamiento posterior al horario de servicio para cada operador automático que use.

Inicialmente, el horario laboral se define para que comience en 12:00 AM y termina en 12:00 PM, de domingo a sábado. Todas las horas que no están en horario laboral se consideran fuera del *horario*laboral.


![captura de pantalla de la configuración del flujo de llamadas de poshora](media/aa-afterhour.png)
 * * *

![Icono del número 1, una llamada en la captura de pantalla](media/teamscallout1.png) anterior, puede hacer clic en **seleccionar 24/7** para hacer todas las horas laborales de trabajo para este operador automático.

![Icono del número 2, una llamada en la captura de pantalla](media/teamscallout2.png) anterior seleccione la opción **restablecer a predeterminado** para revertir todos los cambios en la programación y volver a la definición predeterminada de horario comercial como 9:00 am a 5:00 PM de lunes a viernes.

![Icono del número 3, una llamada en la captura de pantalla](media/teamscallout3.png) anterior, seleccione **borrar todas las horas** para borrar la programación por completo. No se recomienda seleccionar esta opción y dejar las horas establecidas, así que use esta opción solo si desea rehacer por completo el horario laboral.

![Icono del número 4, una llamada en el anterior icono de](media/teamscallout4.png)![captura de pantalla del número 5, una llamada en la captura](media/teamscallout5.png) de pantalla anterior para personalizar la hora de inicio o finalización de un día de la semana, haga clic en **iniciar** o **Finalizar en** el momento que desee restablecer y Seleccione la nueva hora en la lista que aparece.   La lista le permite seleccionar el horario laboral en intervalos de 15 minutos y las horas laborales que seleccione aquí se basan en la zona horaria que estableció en la página de **información general** .

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

![Icono del número 6, una llamada en la captura de pantalla](media/teamscallout6.png) anterior para configurar un salto (una pausa para comer, por ejemplo), seleccione **Agregar nueva hora** para el día de la semana para crear una nueva fila de la tabla y seleccione nuevas horas de inicio y finalización. Puede establecer varios descansos dentro del horario comercial.

Las opciones de [flujo de llamadas](#call-flow) disponibles en horario laboral son las mismas que las disponibles durante el horario laboral. Desplácese hacia abajo en la página información para establecer las opciones de flujo de llamadas después de horas.

* * *

Cuando haya terminado con las selecciones, haga clic en **siguiente**. También puede hacer clic en **cuentas de recursos** en el navegación izquierdo para ir directamente a la página cuentas de recursos y asociar el operador automático a una cuenta de recursos.

##### <a name="call-flow-during-holidays"></a>Flujo de llamadas durante los días festivos

<a name="holidaygreetings"> </a>

Puede agregar un máximo de 20 días festivos programados a cada operador automático. Es posible que su organización ya haya definido días no laborables, tal y como se describe en [configuración de días festivos en Microsoft Teams](set-up-holidays-in-teams.md). Si no es así, verá la siguiente pantalla: 

![Captura de pantalla: no hay días festivos configurados](media/aa-no-holidays.png)

![Icono del número 1, una llamada en la captura de pantalla](media/teamscallout1.png) anterior para establecer un flujo **de llamada personalizado** para un día festivo en el operador automático, haga clic en **+ Agregar** .
> [!TIP]
> Para crear días no laborables, puede ir a la pantalla en la **configuración** > de toda la organización**días festivos**.  



![Captura de pantalla: agregar un controlador de llamadas](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

![Icono del número 1, una llamada en la captura de pantalla](media/teamscallout1.png) anterior, escriba un **nombre** para el nuevo flujo de llamadas.

![Icono del número 2, una llamada en la captura de pantalla](media/teamscallout2.png) anterior si ya ha creado días festivos, los verá en el menú desplegable de **días festivos** y puede seleccionarlos. Es posible que vea una opción no usada que puede modificar en lo que necesita. De lo contrario, haga clic en **Agregar** en la parte inferior de la lista desplegable para crear un nuevo día festivo.  Consulte [configurar días festivos en Microsoft Teams](set-up-holidays-in-teams.md) para conocer los pasos que se usan para crear un día festivo. 

Un nombre de flujo de llamadas de días festivos puede tener un máximo de 64 caracteres y debe ser único para la organización. Por ejemplo, no puede tener dos flujos de llamadas de festividades denominado "Navidad" en la misma organización. El operador automático puede tener un flujo de llamadas por cada festividad que haya configurado, pero es posible que desee tener un conjunto común de comportamientos planificados que no sean un saludo personalizado.

![Icono del número 3, una llamada en la captura de pantalla](media/teamscallout3.png) anterior las opciones de [Greetings](#call-flow) disponibles para un flujo de llamadas de días festivos son las mismas opciones disponibles en el horario laboral. Las **acciones** que se realizan después de la reproducción del saludo también son similares, excepto en que las únicas acciones disponibles son **desconectar** o **redirigir a**y, cuando se elige la opción **redirigir a** , el operador no es una de las opciones disponibles . No se puede configurar un menú específico para un flujo de días no laborables.

> [!NOTE]
> De forma predeterminada, todas las llamadas recibidas durante un período de vacaciones se **desconectan** después del saludo (si procede), por lo que debes especificar un redireccionamiento si deseas un comportamiento personalizado.

![Captura de pantalla de la página flujos de llamada de días festivos](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

Haga clic en guardar para terminar de crear el flujo de llamadas de días festivos. Una vez que hayas creado un flujo de llamadas de días festivos, aparecerá en la pantalla **flujos de llamada durante los días festivos** .

Haga clic en **siguiente** para establecer el ámbito de marcado, **atrás** para realizar cambios en los flujos de la llamada después de la hora y en **Enviar** si ha terminado. También puede hacer clic en **cuentas de recursos** en el navegación izquierdo para ir directamente a la página cuentas de recursos y asociar el operador automático a una cuenta de recursos.

#### <a name="dial-scope"></a>Ámbito de marcado

<a name="dialscope"> </a>

![Captura de pantalla que muestra la página ámbito de marcado](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

En esta página, puede establecer quién aparece en el directorio y disponible para marcar por su nombre cuando una persona llama a su organización. El marcado por nombre está **desactivado** de forma predeterminada en una pantalla anterior. Todos los usuarios con una extensión estarán disponibles si seleccionó **marcar por extensión** anteriormente.

![Icono del número 1, una llamada en la captura de pantalla](media/teamscallout1.png) anterior **incluye** las opciones de esta sección son **todos los usuarios en línea** o **grupos de usuarios personalizados** .

Si selecciona **todos los usuarios en línea**, todos los usuarios elegibles se incluyen en la búsqueda en directorios.

**Grupos de usuarios personalizados** Esta opción le permite buscar y seleccionar un grupo de Office 365, una lista de distribución o un grupo de seguridad ya creado en su organización. Los usuarios se agregan al directorio si se encuentran en el grupo de Office 365, una lista de distribución o un grupo de seguridad elegido y son **usuarios en línea con una licencia de sistema de teléfono** o se hospedan de forma local con Skype empresarial Server. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad al directorio.

<a name="dialscope"> </a>

En esta página, puede configurar los usuarios de su organización que aparecerán en el directorio y que estarán disponibles para marcar por su nombre cuando sea una persona que llame a su organización.

![Icono del número 2, una llamada en la captura de pantalla](media/teamscallout2.png) anterior **excepto** las opciones de esta sección le permiten excluir a determinados usuarios o grupos de usuarios del directorio de la organización.

Si selecciona **ninguno**, todos los usuarios elegibles se incluyen en la búsqueda de directorio.

**Grupo de usuarios personalizado** Puede buscar un grupo de Office 365, una lista de distribución o un grupo de seguridad que se haya creado en su organización. Los usuarios de ese grupo se excluyen de la búsqueda de directorios. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad.


Si deja la configuración predeterminada cuando el marcado por nombre está habilitado, todos los usuarios elegibles se incluyen en la búsqueda de directorio.

> [!NOTE]
> Es posible que tarde hasta 36 horas para que un nuevo usuario tenga su nombre en el directorio. Cuando alguien usa el marcado por nombre con reconocimiento de voz, es posible que no estén disponibles nuevas cuentas para esta característica.

Después de especificar todos los campos obligatorios y configurar los menús y las opciones de administración de llamadas, haga clic en **siguiente** para asociar una cuenta de recursos.

#### <a name="resource-accounts"></a>Cuentas de recursos

Todos los operadores automáticos deben tener una cuenta de recursos asociada.  Los operadores automáticos de primer nivel necesitarán definitivamente al menos una cuenta de recursos con un número de servicio asociado. Si lo desea, puede asignar varias cuentas de recursos a un operador automático, cada uno con un número de servicio diferente.

Si aún no ha configurado una cuenta de recursos para su operador automático, verá la siguiente pantalla: 

![captura de pantalla: administración opcional de cuenta de recursos](media/aa-ra-optional.png) 

![Icono del número 1, una llamada en la captura de pantalla](media/teamscallout1.png) anterior para agregar una o más cuentas de recursos existentes y sin asignar al operador automático, haga clic en **Agregar cuentas** y buscar y selecciónelas en los cuadros de diálogo proporcionados.

![captura de pantalla de la vista de resumen del nuevo operador](media/aa-assigned.png)

![Icono del número 1, una llamada en la captura de pantalla](media/teamscallout1.png) anterior para agregar una cuenta de recursos adicional, haga clic en **+ Agregar cuenta**.

![Icono del número 2, una llamada en la captura de pantalla anterior](media/teamscallout2.png) La cuenta de recursos o cuentas asignadas a este operador automático se muestran en una lista.

## <a name="edit-auto-attendants"></a>Editar operadores automáticos

Después de guardar el nuevo operador automático, aparece en la página de **operadores automáticos** . Esta página le permite ver rápidamente algunas de las opciones que ha configurado, como el nombre, la cuenta de recursos asociada, el idioma y el operador asignado.

![captura de pantalla de la lista de operadores](media/aa-list.png)

Si desea cambiar la configuración del operador automático, seleccione el operador automático y, a continuación, en el panel de acciones, haga clic en **Editar**.

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a>Crear un operador automático con PowerShell

También puede usar PowerShell para crear y configurar operadores automáticos. Estos son los cmdlets que necesita para administrar un operador automático:

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

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Microsoft Teams desde un único punto de administración que pueda simplificar su trabajo diario. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como la realización de cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Administrar Office 365 con Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico de Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtener números de teléfono de servicio](/microsoftteams/getting-service-phone-numbers)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)

[Ejemplo de pequeña empresa: configurar un operador automático](/microsoftteams/tutorial-org-aa)  

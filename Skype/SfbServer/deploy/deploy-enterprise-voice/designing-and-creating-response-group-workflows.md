---
title: Diseñar y crear flujos de trabajo de grupos de respuesta en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Diseñar y crear flujos de trabajo de grupos de respuesta, en Skype empresarial Server Enterprise Voice. Se cubren tanto los flujos de trabajo de grupo de extensiones como los flujos de trabajo interactivos.
ms.openlocfilehash: 9e056070bb01b5ee3cc7f32a8f9d07520fcb2030
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240528"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>Diseñar y crear flujos de trabajo de grupos de respuesta en Skype empresarial

Diseñar y crear flujos de trabajo de grupos de respuesta, en Skype empresarial Server Enterprise Voice. Se cubren tanto los flujos de trabajo de grupo de extensiones como los flujos de trabajo interactivos.

Un flujo de trabajo define el comportamiento de una llamada desde el momento en que suena el teléfono hasta que alguien la atiende. El flujo de trabajo especifica la cola que se va a usar para poner la llamada en espera e indica el método de enrutamiento que se va a usar en los flujos de trabajo de grupo de búsqueda o las preguntas y respuestas que se deben usar para los flujos de trabajo de grupo de respuesta interactivo

Un flujo de trabajo también define configuraciones como el mensaje de bienvenida, la música en espera, horario laboral y los días festivos.

> [!NOTE]
> Debe crear grupos de agentes y colas antes de crear un flujo de trabajo que use dichos elementos.

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>Crear o modificar un flujo de trabajo de un grupo de captura

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Para usar la herramienta de configuración de grupos de respuesta para crear o modificar un flujo de trabajo de Hunt Group

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y después en **Flujo de trabajo**.

4. En la página **Flujo de trabajo**, haga clic en **Crear o editar un flujo de trabajo**.

5. En el campo de búsqueda **Seleccionar un servicio**, escriba la totalidad o parte del nombre del servicio **ApplicationServer** que hospeda el flujo de trabajo que desea crear o cambiar. En la lista de servicios resultante, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.

    > [!NOTE]
    > Se abrirá la herramienta de configuración de grupos de respuesta. También puede abrir la herramienta de configuración de grupo de respuesta directamente desde un explorador web escribiendo la siguiente URL:\<https://\>webPoolFqdn/RgsConfig.

6. Siga uno de estos pasos:

   - En **crear un flujo de trabajo**, junto a **grupo de captura**, haga clic en **crear**.

   - En **Administrar un flujo de trabajo existente**, localice el flujo de trabajo que desea cambiar y, a continuación, en **Acción**, haga clic en **Editar**.

7. Si está listo para que los usuarios empiecen a llamar al flujo de trabajo, seleccione **Activar el flujo de trabajo**.

    > [!NOTE]
    >  Si va a crear un flujo de trabajo administrado, debe seleccionar **activar el flujo de trabajo**. Después de guardar el flujo de trabajo administrado activo, puede modificarlo y desactivarlo.

8. Para permitir que los usuarios federados puedan llamar al grupo, active la casilla **Habilitar para federación**. También debe tener una directiva de acceso externo que se aplique a la aplicación de grupo de respuesta configurada para la Federación.

    > [!NOTE]
    > La Directiva de acceso externo global se aplica a la aplicación de grupo de respuesta. Puede configurar la directiva global para la Federación de grupos de respuesta mediante el panel de control de Skype empresarial Server o mediante el cmdlet **set-CsExternalAccessPolicy** para establecer el parámetro EnableOutsideAccess en true. Recuerde que la configuración de la directiva global se aplica a todos los usuarios, a menos que se les haya asignado una directiva de usuario o de sitio. Por lo tanto, antes de cambiar la configuración de los grupos de respuesta, asegúrese de que la configuración de la federación cumpla los requisitos de la organización. Para más información sobre la aplicación de las directivas a los usuarios, consulte [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Para obtener más información sobre la configuración de Federación, consulte [set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).

    > [!NOTE]
    > Los usuarios que se hospedan en Skype empresarial online no pueden realizar llamadas a grupos de respuesta hospedados en una implementación local. Esto se aplica en ambas implementaciones híbridas y en los casos en los que una implementación local se federa con una implementación de Skype empresarial online.

9. Para ocultar la identidad de los agentes durante las llamadas, active la casilla **Habilitar anonimato de agente**.

    > [!NOTE]
    > Las llamadas anónimas no pueden empezar con mensajería instantánea (MI) ni un vídeo, aunque el agente o la persona que llame pueda agregar MI o un vídeo después de establecer la llamada. Asimismo, un agente anónimo puede poner llamadas en espera, transferir llamadas (tanto transferencias a otras líneas como consultas), además de estacionar y recuperar llamadas. Las llamadas anónimas no admiten conferencias, uso compartido de aplicaciones ni de escritorio, transferencia de archivos, función de pizarra, colaboración de datos y grabación de llamadas. Los agentes que usen el complemento VDI de Lync pueden recibir llamadas entrantes anónimas, pero no realizar llamadas salientes anónimas.

10. En **Especifique la dirección del grupo que recibirá las llamadas**, escriba la dirección del identificador uniforme de recursos (URI) del SIP primario del grupo que responderá las llamadas al flujo de trabajo.

    > [!NOTE]
    > El URI principal de un flujo de trabajo es la forma cómo se identifica y se denomina el flujo de trabajo. El URI de SIP que especifique se creará como un objeto de contacto en los servicios de dominio de Active Directory. Para crear el URI, el objeto debe ser único en Active Directory.

11. En **nombre para mostrar**, escriba el nombre que desea mostrar para el flujo de trabajo (por ejemplo, grupo de respuesta de ventas).

    > [!NOTE]
    > No incluya los caracteres "<" o ">" en el nombre para mostrar. No use los siguientes nombres para mostrar porque están reservados: **RGS Presence Watcher** o **Announcement Service**.

12. En **Número de teléfono**, especifique el URI de línea para el grupo de respuesta (por ejemplo, +14255550165).

13. En **Número para mostrar**, escriba el número tal como desea que aparezca para el grupo de respuesta (por ejemplo, +1 (425) 555-0165).

14. Faculta En **Descripción**, escriba una descripción para el flujo de trabajo tal y como desea que aparezca en la tarjeta de contacto en Skype empresarial.

15. En **Tipo de flujo de trabajo**, seleccione **Administrado** si este flujo de trabajo va a ser administrado por un administrador de grupos de respuesta. Siga este procedimiento para asignar administradores de grupos de respuesta al flujo de trabajo:

    a. Escriba el URI del SIP de un administrador para este flujo de trabajo y haga clic en **Agregar**.

    b. Escriba el URI del SIP de otros administradores que desee agregar al flujo de trabajo y haga clic en **Agregar**.

    > [!IMPORTANT]
    > A todos los usuarios designados administradores de un grupo de respuestas se les asigna el rol CsResponseGroupManager. Los usuarios a los que no se haya asignado este rol no pueden administrar grupos de respuesta.

16. En **Paso 2 Seleccionar un idioma**, haga clic en el idioma que desea utilizar para reconocimiento de voz y conversión de texto a voz.

17. Si desea definir un mensaje de bienvenida, en el **Paso 3 Configurar un mensaje de bienvenida**, active la casilla **Reproducir un mensaje de bienvenida** y luego lleve a cabo uno de estos procedimientos:

    - Para escribir el mensaje de bienvenida como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.

    > [!NOTE]
    > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    - Para usar una grabación de un archivo de audio de Windows Media (.wma) o WAVE (.wav) para el mensaje de bienvenida, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo de audio y luego haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.

    > [!NOTE]
    > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener más información acerca de los formatos de archivo compatibles, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

18. En **Paso 4 Especificar horario comercial**, en el cuadro **Su zona horaria**, haga clic en la zona horaria para el flujo de trabajo.

    > [!NOTE]
    > La zona horaria es aquella donde residen los autores de las llamadas y los agentes del flujo de trabajo. Se usa para calcular las horas de apertura y de cierre. Por ejemplo, si el flujo de trabajo se configura para usar la zona horaria Hora oriental de América del Norte y el flujo de trabajo se programa para abrirse a las 7:00 horas y cerrarse a las 23:00 horas, se supone que las horas de apertura y de cierre son, respectivamente, 7:00 horas en horario oriental y 23:00 horas en horario oriental. (Debe escribir las horas en el formato de 24 horas).

19. Para seleccionar el tipo de programación de horario comercial que quiere usar, siga uno de los procedimientos siguientes:

    - Para usar una programación predefinida de horario comercial, haga clic en **Usar una programación preestablecida** y después seleccione el horario que desea utilizar en la lista desplegable.

      > [!NOTE]
      > Debe definir al menos una programación preestablecida previamente para poder seleccionar esta opción. Puede definir programaciones preestablecidas con el cmdlet **New-CSRgsHoursOfBusiness**. Para obtener más información, consulte [(opcional) definir las horas de trabajo de los grupos de respuesta en Skype empresarial](optional-define-response-group-business-hours.md).

      > [!NOTE]
      > Cuando selecciona una programación preestablecida, **Día**, **Abrir** y **Cerrar** se rellenan automáticamente con los días y las horas en los que el grupo de respuesta se encuentra disponible.

    - Para usar una programación personalizada que se aplique solo a este flujo de trabajo, haga clic en **Usar una programación personalizada**.

20. Si está creando una programación personalizada para este flujo de trabajo, haga clic en las casillas correspondientes a los días de la semana durante los que se encuentra disponible el grupo de respuesta.

21. Si va a crear una programación personalizada, escriba las horas de **apertura** y **cierre** para cada día de la semana en el que está disponible el grupo de respuesta.

    > [!NOTE]
    > Las horas de **Abrir** y **Cerrar** deben mostrarse en formato de 24 horas. Por ejemplo, si en su oficina se trabaja de 9 a 5 y se cierra al mediodía para el almuerzo, el horario comercial se especificará de la siguiente manera: **Abrir** 9:00, **Cerrar** 12:00, **Abrir** 13:00 y **Cerrar** 17:00.

22. Si desea reproducir un mensaje cuando la oficina no esté abierta, active la casilla **Reproducir un mensaje cuando el grupo de respuesta esté fuera del horario comercial** y después especifique el mensaje que se va a reproducir siguiendo uno de los procedimientos siguientes:

    - Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.

      > [!NOTE]
      > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    - Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.

      > [!NOTE]
      > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener más información sobre los formatos de audio admitidos, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

23. Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):

    - Para desconectar la llamada, haga clic en **Desconectar llamada**.

    - Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y escriba la dirección de correo de voz. El formato de la dirección de correo de voz es * \<nombre de usuario\>**\<\> * @nombreDeDominio (por ejemplo, Bob@contoso.com).

    - Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y escriba la dirección de usuario. El formato de la dirección de usuario _ \<es\>nombre_@_\<\>_ de usuario nombreDeDominio.

    - Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y escriba el número de teléfono. El formato del número de teléfono es * \<\>*@*\<domainname\> * (por ejemplo, + 14255550121@contoso.com). El nombre de dominio se usa para redirigir al autor de la llamada al destino correcto.

24. En **Paso 5 Especificar vacaciones**, haga clic en las casillas para uno o más conjuntos de vacaciones que definan los días en los que el grupo de respuesta no esté laboralmente disponible.

    > [!NOTE]
    > Defina las vacaciones y los conjuntos de vacaciones antes de configurar el flujo de trabajo. Para ello, use los cmdlets **New-CsRgsHoliday** y **New-CsRgsHolidaySet**. Para obtener más información, consulte [(opcional) definir conjuntos de días festivos de grupos de respuesta en Skype empresarial](optional-define-response-group-holiday-sets.md).

25. Si desea reproducir un mensaje durante las vacaciones, active la casilla **Reproducir un mensaje durante las vacaciones** y después especifique el mensaje que se va a reproducir con uno de los siguientes procedimientos:

    - Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.

    > [!NOTE]
    > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    - Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.

      > [!NOTE]
      > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener más información sobre los formatos de audio admitidos, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

26. Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):

    - Para desconectar la llamada, haga clic en **Desconectar llamada**.

    - Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y escriba la dirección de correo de voz. El formato de la dirección de correo de voz es * \<nombre de usuario\>**\<\> * @nombreDeDominio (por ejemplo, Bob@contoso.com).

    - Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y escriba la dirección de usuario. El formato de la dirección de usuario _ \<es\>nombre_@_\<\>_ de usuario nombreDeDominio.

    - Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y escriba el número de teléfono. El formato del número de teléfono es * \<\>*@*\<domainname\> * (por ejemplo, + 14255550121@contoso.com). El nombre de dominio se usa para redirigir al autor de la llamada al destino correcto.

27. En el **Paso 6 Configurar una cola**, en **Seleccione la cola que recibirá las llamadas**, seleccione la cola donde desea que los autores de las llamadas se mantengan en espera hasta que un agente esté disponible.

28. En el **Paso 7 Configurar música en espera**, elija la música que desea que escuchen los autores de las llamadas mientras esperan a un agente; para ello lleve a cabo uno de procedimientos siguientes:

    - Para usar la grabación habitual de música en espera, haga clic en **Usar predeterminado**.

    - Para usar una grabación de un archivo de audio para la música en espera, haga clic en **Seleccionar un archivo de música**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **un archivo de música**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.

      > [!NOTE]
      > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener más información sobre los formatos de audio admitidos, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

29. Haga clic en **Implementar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>Para usar el shell de administración de Skype empresarial para crear o modificar un flujo de trabajo de grupo de captura

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

3. Cree el mensaje de bienvenida que se reproducirá y guárdelo en una variable. En la línea de comandos, ejecute:

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    Por ejemplo:

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > Para usar un archivo de audio para el mensaje, ejecute el cmdlet **Import-CsRgsAudioFile**. Para obtener más información, consulte [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).

4. Obtenga la identidad de la cola o la pregunta a la que se dirigirán las llamadas. En la línea de comandos, ejecute:

   ```
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    Para obtener detalles sobre la creación de la cola, vea [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).

5. Defina la acción que se ejecutará cuando un flujo de trabajo se abra en horas de trabajo y guárdela en una variable. En la línea de comandos, ejecute:

   ```
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > Para los flujos de trabajo de grupo de búsqueda, la acción habitual será dirigir la llamada a una cola. Este parámetro es necesario para los flujos de trabajo activos. No se necesita para los flujos de trabajo inactivos.

    Por ejemplo:

   ```
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. Si desea definir horas laborables y vacaciones, debe crearlas antes de crear o modificar el flujo de trabajo. Para obtener más información, consulte [(opcional) definir las horas de trabajo de los grupos de respuesta en Skype empresarial](optional-define-response-group-business-hours.md) y [(opcional) definir conjuntos de días festivos de grupos de respuesta en Skype empresarial](optional-define-response-group-holiday-sets.md).

7. Si desea tener mensajes para las llamadas que se reciben en un horario no laborable o en época de vacaciones, use el cmdlet **New-CsRgsPrompt** para definir el mensaje y el cmdlet **New-CsRgsCallAction** para definir la acción que se ejecutará después del mensaje. Para obtener más información, vea [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) y [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).

8. Recupere el nombre del servicio del grupo de respuesta de Lync Server y asígnelo a una variable. En la línea de comandos, ejecute:

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. Cree o modifique el flujo de trabajo. Para crear un flujo de trabajo, use **New-CsRgsWorkflow**. Para modificar un flujo de trabajo, use **Set-CsRgsWorkflow**. En la línea de comandos, escriba lo siguiente:

   ```
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    Por ejemplo:

   ```
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > Todos los usuarios que hayan sido designados administradores de flujos de trabajo deben tener asignado el rol CsResponseGroupManager.

     > [!NOTE]
     > Para obtener detalles sobre parámetros opcionales adicionales, vea [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) o [set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>Diseñar un flujo de trabajo interactivo

Puede usar la respuesta de voz interactiva (IVR) para obtener información de las personas que llaman y dirigir la llamada a la cola correspondiente. Las parejas de preguntas y respuestas determinan qué cola se va a usar. En función de la respuesta de la persona que llama, el autor de la llamada escuchará una pregunta de seguimiento o se redirigirá a la cola correspondiente. Las preguntas de IVR y las respuestas de la persona que llama se proporcionan al agente de respuesta que acepta la llamada, proporcionando información valiosa al agente.

### <a name="overview-of-ivr-features"></a>Información general de las características de IVR

La aplicación de grupo de respuesta ofrece capacidades de reconocimiento de voz y de texto a voz en 26 idiomas. Puede formular preguntas al IVR mediante texto a voz o un archivo wave (.wave) o Windows Media Audio (.wma). Los autores de las llamadas pueden responder mediante voz o tono de marcado de frecuencia múltiple (DTMF).

Los flujos de trabajo interactivos admiten hasta dos niveles de preguntas; cada una de las preguntas tiene cuatro respuestas posibles. El IVR hace una pregunta a la persona que llama y, dependiendo de la respuesta de la llamada, dirige a la persona que llama a una cola o hace una segunda pregunta. La segunda pregunta también puede tener cuatro respuestas posibles. Según la respuesta a la pregunta de segundo nivel, el autor de la llamada se enruta a la cola adecuada.

> [!NOTE]
> Al diseñar flujos de llamadas mediante el shell de administración de Skype empresarial Server, puede definir cualquier número de niveles de preguntas IVR y cualquier cantidad de respuestas. Sin embargo, para mejorar la usabilidad, le recomendamos que no use más de tres niveles de preguntas, con no más de cinco respuestas por pregunta. Además, si diseña un flujo de llamada que tiene más de dos niveles de preguntas con más de cuatro respuestas cada una, no puede editar el flujo de llamadas con el panel de control de Skype empresarial Server.

Las preguntas de IVR y las respuestas de la persona que llama se proporcionan al agente que responde que acepta la llamada.

### <a name="working-with-speech-technologies"></a>Trabajar con tecnologías de voz

Las tecnologías de voz, como el reconocimiento de voz y el texto a voz, pueden mejorar la experiencia del cliente y permitir que las personas tengan acceso a la información con mayor naturalidad y eficacia. Sin embargo, puede haber casos en que el motor de síntesis de voz no reconozca correctamente el texto especificado o la respuesta de voz del usuario. Por ejemplo, el motor de síntesis de texto a voz traduce el símbolo "#" como la palabra "número". Este problema se puede mitigar de la siguiente manera:

- El motor de síntesis de voz proporciona el autor de la llamada cinco intentos para responder a la pregunta. Si el autor de la llamada aporta una respuesta incorrecta (es decir, la respuesta no es ninguna de las especificadas), o si no responde, tendrá otra oportunidad para responder. El autor de la llamada tendrá cinco intentos para responder a la pregunta antes de ser desconectado. Puede configurar el IVR para que reproduzca un mensaje personalizado después de cada error del autor de la llamada. La pregunta se repite cada vez.

- Para reducir al máximo la posibilidad de que el motor de voz interprete el ruido ambiental como una respuesta, use respuestas más largas. Por ejemplo, cada respuesta debe tener más de una sílaba y debe sonar de forma significativamente distinta a las demás.

- Si sus preguntas tienen respuestas de voz y de DTMF, configure las respuestas de voz con palabras que representen el concepto, en lugar de la respuesta de DTMF. Por ejemplo, en lugar de "Pulse o diga uno", use "Pulse 1 o diga facturación".

- Después de diseñar IVR, llame al flujo de trabajo, escuche las indicaciones, responda a cada una de ellas mediante voz y compruebe que IVR suena y se comporta como se espera. A continuación, puede modificar el IVR para corregir los posibles problemas de interpretación. Siguiendo el ejemplo anterior, si necesita hacer referencia a la tecla #, puede volver a escribir la indicación del IVR para usar el nombre de la tecla, en lugar del símbolo #. Por ejemplo, "Para hablar con el departamento de ventas, presione la tecla almohadilla".

### <a name="ivr-design-examples"></a>Ejemplos de diseño de IVR

Los siguientes apartados contienen ejemplos de escenarios de IVR y pares de preguntas y respuestas.

#### <a name="ivr-with-one-level-of-questions"></a>IVR con preguntas de un nivel

En el ejemplo siguiente se muestra un IVR con un nivel de preguntas. Usa el reconocimiento de voz para detectar la respuesta de la persona que llama.

 **Pregunta:** "Gracias por llamar a Recursos Humanos. Si desea hablar con Nóminas, diga nóminas. Si no, diga Recursos humanos".

- **Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de nóminas.

- **Se ha seleccionado la opción 2:** el autor de la llamada se enruta al equipo de recursos humanos.

En la figura siguiente se muestra el flujo de la llamada.

 **Flujo de llamada interactiva de un nivel**

![Diseñar flujos de llamadas a través de la respuesta interactiva de voz](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>IVR con dos niveles de preguntas

En el ejemplo siguiente, se muestra un IVR con dos niveles de preguntas. Permite a los autores de las llamadas responder mediante voz o el teclado numérico DTMF.

 **Pregunta:** "Gracias por llamar al Centro de Asistencia Técnica. Si tiene un problema de acceso a la red, pulse o diga 1. Si tiene un problema de software, pulse o diga 2. Si tiene un problema de hardware, pulse o diga 3".

- **Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de asistencia de red.

- **Se ha seleccionado la opción 2:** se hace una pregunta de seguimiento al autor de la llamada:

    **Pregunta:** "Si se trata de un problema con el sistema operativo, pulse o diga 1. Si se trata de un problema con una aplicación interna, pulse o diga 2. Si no se trata de ninguna de estas opciones, pulse o diga 3".

  - **Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de asistencia de sistemas operativos.

  - **Se ha seleccionado la opción 2:** el autor de la llamada se enruta al equipo de asistencia de aplicaciones internas.

  - **Se ha seleccionado la opción 3:** el autor de la llamada se enruta al equipo de asistencia de software.

- **Se ha seleccionado la opción 3:** se hace una pregunta de seguimiento al autor de la llamada:

    **Pregunta:** "Si se trata de un problema con la impresora, pulse 1. En caso contrario, pulse 2".

  - **Se ha seleccionado la opción 1:** el autor de la llamada se enruta al equipo de asistencia de impresoras.

  - **Se ha seleccionado la opción 2:** el autor de la llamada se enruta al equipo de asistencia de hardware.

En la figura siguiente se muestra el flujo de la llamada.

 **Flujo de llamada interactiva de dos niveles**

![Diseñar flujos de llamadas a través de la respuesta interactiva de voz](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>Procedimientos recomendados

En la lista siguiente se describen algunas técnicas recomendadas para diseñar IVR:

- Permita el autor de la llamada llegar rápidamente a la tarea. Evite el exceso de información o mensajes de marketing largos en el IVR.

- Si desea incluir un mensaje largo, puede añadirlo a la primera pregunta, en lugar del mensaje de bienvenida. Los autores de las llamadas pueden omitir el mensaje si forma parte de la primera pregunta, respondiéndola, pero no pueden omitir el mensaje de bienvenida.

- Habla en el idioma de la persona que llama. Evite usar un lenguaje rebuscado. Hable con naturalidad.

- Escriba indicaciones efectivas. Quite todas las opciones innecesarias. Estructurar la información para que la respuesta esperada de la persona que llama esté al final de la oración. Por ejemplo, "para hablar con el equipo de ventas, presione 1".

- Haga que las respuestas de voz sean fáciles para el usuario. Por ejemplo, si incluye respuestas de DTMF y de voz, use algo así: "Para hablar con el equipo de ventas, pulse 1 o diga ventas".

- Pruebe el IVR con un grupo de usuarios antes de implementarlo en toda la organización.

## <a name="creating-or-modifying-an-interactive-workflow"></a>Crear o modificar un flujo de trabajo interactivo

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Para usar la herramienta de configuración de grupos de respuesta para crear o modificar un flujo de trabajo interactivo

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y después en **Flujo de trabajo**.

4. En la página **Flujo de trabajo**, haga clic en **Crear o editar un flujo de trabajo**.

5. En el campo de búsqueda **Seleccionar un servicio**, escriba total o parcialmente el nombre del servicio de **ApplicationServer** que hospeda el flujo de trabajo que desea crear o modificar. En la lista de servicios resultante, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.

    > [!NOTE]
    > Se abrirá la herramienta de configuración de grupos de respuesta. También puede abrir la herramienta de configuración de grupo de respuesta directamente desde un explorador web escribiendo la siguiente URL:\<https://\>webPoolFqdn/RgsConfig.

6. Siga uno de estos pasos:

   - En **Crear un nuevo flujo de trabajo**, junto a **Interactivo**, haga clic en **Crear**.

   - En **Administrar un flujo de trabajo existente**, localice el flujo de trabajo que desea cambiar y, a continuación, en **Acción**, haga clic en **Editar**.

7. Si todavía no está listo para que los usuarios comiencen a llamar al flujo de trabajo, desactive la casilla **Activar el flujo de trabajo**.

    > [!NOTE]
    >  Si va a crear un flujo de trabajo administrado, debe seleccionar **activar el flujo de trabajo**. Después de guardar el flujo de trabajo administrado activo, puede modificarlo y desactivarlo.

8. Para permitir que los usuarios federados puedan llamar al grupo, active la casilla **Habilitar para federación**. También debe tener una directiva de acceso externo que se aplique a la aplicación de grupo de respuesta configurada para la Federación.

    > [!NOTE]
    > La Directiva de acceso externo global se aplica a la aplicación de grupo de respuesta. Puede configurar la directiva global para la Federación de grupos de respuesta mediante el panel de control de Skype empresarial Server o mediante el cmdlet **set-CsExternalAccessPolicy** para establecer el parámetro EnableOutsideAccess en true. Recuerde que la configuración de la directiva global se aplica a todos los usuarios, a menos que se les haya asignado una directiva de usuario o de sitio. Por lo tanto, antes de cambiar la configuración de los grupos de respuesta, asegúrese de que la configuración de la federación cumpla los requisitos de la organización. Para más información sobre la aplicación de las directivas a los usuarios, consulte [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Para obtener más información sobre la configuración de Federación, consulte **set-CsExternalAccessPolicy** in Documentation..

    > [!NOTE]
    > Los usuarios que se hospedan en Skype empresarial online no pueden realizar llamadas a grupos de respuesta hospedados en una implementación local. Esto se aplica en ambas implementaciones híbridas y en los casos en los que una implementación local se federa con una implementación de Skype empresarial online.

9. Para ocultar la identidad de los agentes durante las llamadas, active la casilla **Habilitar anonimato de agente**.

    > [!NOTE]
    > Las llamadas anónimas no pueden empezar con mensajería instantánea (MI) ni un vídeo, aunque el agente o la persona que llame pueda agregar MI o un vídeo después de establecer la llamada. Asimismo, un agente anónimo puede poner llamadas en espera, transferir llamadas (tanto transferencias a otras líneas como consultas), además de estacionar y recuperar llamadas. Las llamadas anónimas no admiten conferencias, uso compartido de aplicaciones ni de escritorio, transferencia de archivos, función de pizarra, colaboración de datos y grabación de llamadas. Los agentes que usen el complemento VDI de Lync pueden recibir llamadas entrantes anónimas, pero no realizar llamadas salientes anónimas.

10. En **Especifique la dirección del grupo que recibirá las llamadas**, escriba la dirección del identificador uniforme de recursos (URI) del SIP primario del grupo que responderá las llamadas al flujo de trabajo.

11. En **Nombre para mostrar**, escriba el nombre que desea mostrar para el flujo de trabajo (por ejemplo, Grupo de respuesta IVR de ventas).

    > [!NOTE]
    > No incluyas los caracteres\<"" o\>"" en el nombre para mostrar. No use los siguientes nombres para mostrar porque están reservados: **RGS Presence Watcher** o **Announcement Service**.

12. En **Número de teléfono**, escriba el URI de línea para el grupo de respuesta (por ejemplo, +14255550165).

13. En **Número para mostrar**, escriba el número tal como desea que aparezca para el grupo de respuesta (por ejemplo, +1 (425) 555-0165).

14. Faculta En **Descripción**, escriba una descripción para el flujo de trabajo que desea que aparezca en la tarjeta de contacto en Skype empresarial.

15. En **Tipo de flujo de trabajo**, seleccione **Administrado** si este flujo de trabajo va a ser administrado por un administrador de grupos de respuesta. Siga este procedimiento para asignar administradores de grupos de respuesta al flujo de trabajo:

    a. Escriba el URI del SIP de un administrador para este flujo de trabajo y haga clic en **Agregar**.

    b. Escriba el URI del SIP de otros administradores que desee agregar al flujo de trabajo y haga clic en **Agregar**.

    > [!IMPORTANT]
    > A todos los usuarios designados como administradores de un grupo de respuestas se les asigna el rol CsResponseGroupManager. Los usuarios a los que no se haya asignado este rol no pueden administrar grupos de respuesta.

16. En **Paso 2 Seleccionar un idioma**, haga clic en el idioma que se usará para el reconocimiento de voz y texto a voz.

17. Si desea definir un mensaje de bienvenida, en el **Paso 3 Configurar un mensaje de bienvenida**, active la casilla **Reproducir un mensaje de bienvenida** y luego lleve a cabo uno de estos procedimientos:

    - Para escribir el mensaje de bienvenida como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.

    > [!NOTE]
    > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    - Para usar una grabación de archivos de Wave o Windows Media Audio para el mensaje de bienvenida, haga clic en **Seleccionar una grabación**. Si desea cargar un nuevo archivo de audio, haga clic en el vínculo de **una grabación**. En la nueva ventana de explorador, haga clic en **Examinar**, seleccione el archivo de audio que desea usar y haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.

    > [!NOTE]
    > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener más información acerca de los formatos de archivo compatibles, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

18. En **Paso 4 Especificar horario comercial**, en el cuadro **Su zona horaria**, haga clic en la zona horaria del flujo de trabajo.

    > [!NOTE]
    > La zona horaria se refiere a la zona donde residen los autores de llamadas y los agentes del flujo de trabajo. Se usa para calcular las horas de apertura y cierre. Por ejemplo, si el flujo de trabajo está configurado para usar la zona horaria Hora oriental de América del Norte y el flujo de trabajo está programado para abrir a las 7:00 y cerrar a 23:00, se supone que las horas de apertura y cierre son las 7:00 (Hora del este) y las 23:00 (Hora del este) respectivamente. Escriba las horas en la notación de 24 horas.

19. Para seleccionar el tipo de programación de horario comercial que quiere usar, siga uno de los procedimientos siguientes:

    - Para usar una programación predefinida de horario comercial, haga clic en **Usar una programación preestablecida** y después seleccione el horario que desea utilizar en la lista desplegable.

      > [!NOTE]
      > Debe definir al menos una programación preestablecida previamente para poder seleccionar esta opción. Para definir las programaciones preestablecidas, use el cmdlet **New-CsRgsHoursOfBusiness** . Para obtener más información, consulte [(opcional) definir las horas de trabajo de los grupos de respuesta en Skype empresarial](optional-define-response-group-business-hours.md). Cuando selecciona una programación preestablecida, **Día**, **Abrir** y **Cerrar** se rellenan automáticamente con los días y las horas en los que el grupo de respuesta se encuentra disponible.

    - Para usar una programación personalizada que se aplique solo a este flujo de trabajo, haga clic en **Usar una programación personalizada**.

20. Si está creando una programación personalizada para este flujo de trabajo, haga clic en las casillas correspondientes a los días de la semana durante los que se encuentra disponible el grupo de respuesta.

21. Si va a crear una programación personalizada, escriba las horas de **apertura** y **cierre** cuando el grupo de respuesta estará disponible.

     > [!NOTE]
     > Las horas de **Abrir** y **Cerrar** deben mostrarse en formato de 24 horas. Por ejemplo, si en su oficina se trabaja de 9 a 5 y se cierra al mediodía para el almuerzo, el horario comercial se especificará de la siguiente manera: **Abrir** 9:00, **Cerrar** 12:00, **Abrir** 13:00 y **Cerrar** 17:00.

22. Si desea reproducir un mensaje cuando la oficina no esté abierta, active la casilla **Reproducir un mensaje cuando el grupo de respuesta esté fuera del horario comercial** y después especifique el mensaje que se va a reproducir siguiendo uno de los procedimientos siguientes:

    - Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.

      > [!NOTE]
      > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    - Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.

    > [!NOTE]
    > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener más información acerca de los formatos de archivo compatibles, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

23. Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):

    - Para desconectar la llamada, haga clic en **Desconectar llamada**.

    - Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y escriba la dirección de correo de voz. El formato de la dirección de correo de voz es * \<nombre de usuario\>**\<\> * @nombreDeDominio (por ejemplo, Bob@contoso.com).

    - Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y escriba la dirección de usuario. El formato de la dirección de usuario _ \<es\>nombre_@_\<\>_ de usuario nombreDeDominio.

    - Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y escriba el número de teléfono. El formato del número de teléfono es * \<\>*@*\<domainname\> * (por ejemplo, + 14255550121@contoso.com). El nombre de dominio se usa para redirigir al autor de la llamada al destino correcto.

24. En **Paso 5 Especificar vacaciones**, haga clic en las casillas para uno o más conjuntos de vacaciones que definan los días en los que el grupo de respuesta no esté laboralmente disponible.

    > [!NOTE]
    > Defina las vacaciones y los conjuntos de vacaciones antes de configurar el flujo de trabajo. Para ello, use los cmdlets **New-CsRgsHoliday** y **New-CsRgsHolidaySet**. Para obtener más información, consulte [(opcional) definir conjuntos de días festivos de grupos de respuesta en Skype empresarial](optional-define-response-group-holiday-sets.md).

25. Si desea reproducir un mensaje durante las vacaciones, active la casilla **Reproducir un mensaje durante las vacaciones** y después especifique el mensaje que se va a reproducir con uno de los siguientes procedimientos:

    - Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.

      > [!NOTE]
      > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    - Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.

      > [!NOTE]
      > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener más información sobre los formatos de audio admitidos, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

26. Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):

    - Para desconectar la llamada, haga clic en **Desconectar llamada**.

    - Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y escriba la dirección de correo de voz. El formato de la dirección de correo de voz es * \<nombre de usuario\>**\<\> * @nombreDeDominio (por ejemplo, Bob@contoso.com).

    - Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y escriba la dirección de usuario. El formato de la dirección de usuario _ \<es\>nombre_@_\<\>_ de usuario nombreDeDominio.

    - Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y escriba el número de teléfono. El formato del número de teléfono es * \<\>*@*\<domainname\> * (por ejemplo, + 14255550121@contoso.com). El nombre de dominio se usa para redirigir al autor de la llamada al destino correcto.

27. En **Paso 6 Configurar música en espera**, elija lo que desea que escuchen los autores de las llamadas mientras esperan a un agente con uno de los procedimientos siguientes:

    - Para usar la grabación de música en espera predeterminada, haga clic en **Predeterminada**.

    - Para usar una grabación de archivo de audio para la música en espera, haga clic en **Seleccionar un archivo de música**. Si desea cargar un nuevo archivo de audio, haga clic en el vínculo de   **un archivo de música**. En la nueva ventana de explorador, haga clic en **Examinar**, seleccione el archivo de audio que desea usar y haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.

    > [!NOTE]
    > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener más información acerca de los formatos de archivo compatibles, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

28. En **Paso 7 Configurar una respuesta interactiva de voz**, en   **El usuario escuchará el siguiente texto o mensaje grabado**, especifique la pregunta que desea formular a los autores de las llamadas, como se indica a continuación:

    - Para especificar la pregunta en formato de texto, haga clic en **Usar texto a voz** y escriba la pregunta en el cuadro de texto.

    > [!NOTE]
    > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    > [!NOTE]
    > El motor de conversión de texto a voz traduce el símbolo "#" como la palabra "número". Si necesita hacer referencia a la tecla #, debe usar el nombre de tecla, en lugar de el símbolo, en el mensaje de asistencia por voz. Por ejemplo, "Para hablar con el departamento de ventas, presione la tecla almohadilla".

    - Para usar un archivo de audio pregrabado que contiene la pregunta, haga clic en **Seleccionar una grabación** y en el vínculo **una grabación** para cargar el archivo. En la nueva ventana de explorador, haga clic en **Examinar**, seleccione el archivo de audio y haga clic en **Abrir**. Haga clic en **cargar** para cargar el archivo y, a continuación, también puede escribir la pregunta en el cuadro de texto (esto permite que la pregunta y la respuesta de la persona que llama se desvíen al agente de respuesta).

      > [!NOTE]
      > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener más información acerca de los formatos de archivo compatibles, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

29. En **Respuesta 1**, especifique la primera respuesta posible a la pregunta con este procedimiento:

    > [!IMPORTANT]
    > No use comillas (") en las respuestas de voz porque provocan un error de IVR.

    > [!NOTE]
    > Puede elegir si los autores de la llamada pueden responder con voz, con el teclado alfanumérico o con ambos.

    - Si desea permitir que el autor de la llamada responda con voz, escriba la respuesta en **Especificar una respuesta de voz**.

    - Si desea permitir que el autor de la llamada presione una tecla del teclado para responder, en **Dígito**, haga clic en el dígito del teclado.

30. Para especificar si desea redirigir al autor de la llamada a una cola o hacer otra pregunta, haga lo siguiente:

    - Para redirigir al autor de la llamada a una cola, haga clic en **Enviar a una cola** y, en **Seleccionar una cola**, haga clic en la cola que desea usar.

    - Para hacer otra pregunta, haga clic en **Formular otra pregunta**, en **Usar texto a voz** y escriba la pregunta o haga clic en **Seleccionar una grabación**. Use los grupos de respuesta de esta sección para especificar hasta cuatro respuestas posibles para la pregunta adicional y la cola que se desea usar para cada respuesta. Para especificar una tercera o cuarta respuesta posible, haga clic en las casillas **Respuesta 3** o **Respuesta 4**, respectivamente.

31. Especifique hasta otras tres respuestas posibles para la pregunta original. Para ello, repita los pasos 28 y 29 para especificar las posibles respuestas y la acción que se debe seguir con cada respuesta. Para especificar una tercera o cuarta respuesta posible, haga clic en las casillas **Respuesta 3** o **Respuesta 4**, respectivamente.

32. Haga clic en **Implementar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>Para usar el shell de administración de Skype empresarial para crear o modificar un flujo de trabajo interactivo

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

3. Recupere el nombre de servicio del servicio Grupo de respuestas y asígnelo a una variable. En la línea de comandos, ejecute:

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. Un flujo de trabajo interactivo requiere dos o más colas y dos o más grupos de agentes. En primer lugar, cree los grupos de agentes. Ejecute:

   ```
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. Cree las colas. Ejecute:

   ```
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. Cree el primer aviso del grupo de respuestas. Ejecute:

   ```
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. A continuación, cree la acción que debe realizarse tras el aviso. Ejecute:

   ```
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. Cree la primera respuesta del grupo de respuestas. Ejecute:

   ```
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. Ahora cree el segundo aviso, y la acción de llamada y la respuesta correspondientes. En primer lugar, cree el aviso. Ejecute:

   ```
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. Cree la segunda acción de llamada. Ejecute:

    ```
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. Cree la segunda respuesta del grupo de respuestas. Ejecute:

    ```
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. Cree el aviso de nivel superior. Ejecute:

    ```
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. Cree la pregunta de nivel superior. Ejecute:

    ```
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. Ahora cree el flujo de trabajo. Ejecute:

    ```
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > A todos los usuarios que se hayan designado como administradores de un grupo de respuesta se les debe asignar el rol CsResponseGroupManager. De lo contrario, no podrán administrar los grupos de respuestas.

## <a name="see-also"></a>Vea también

[Faculta Definir conjuntos de días festivos de grupos de respuesta en Skype empresarial](optional-define-response-group-holiday-sets.md)

[Faculta Definir las horas de trabajo del grupo de respuesta en Skype empresarial](optional-define-response-group-business-hours.md)

[Nuevo: CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[Nuevo: CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)


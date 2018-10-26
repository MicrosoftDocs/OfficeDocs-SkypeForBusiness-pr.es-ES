---
title: "Lync Server 2013: Crear o modificar el flujo de trabajo de un grupo de búsqueda"
TOCTitle: Crear o modificar el flujo de trabajo de un grupo de búsqueda
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48276882
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar el flujo de trabajo de un grupo de búsqueda en Lync Server 2013

 

_**Última modificación del tema:** 2013-09-11_

Use uno de los procedimientos siguientes para crear o modificar un flujo de trabajo de grupo de búsqueda.


> [!NOTE]
> Use el Shell de administración de Lync Server o la Herramienta de configuración de grupo de respuesta para crear o modificar un flujo de trabajo de grupo de búsqueda. Obtenga acceso a la Herramienta de configuración de grupo de respuesta desde Panel de control de Lync Server o abriendo la página web directamente desde un explorador web escribiendo la dirección URL siguiente: <STRONG>https://</STRONG><EM>&lt;webPoolFqdn&gt;</EM><STRONG>/RgsConfig</STRONG>.



## Para usar Herramienta de configuración de grupo de respuesta para crear o modificar un flujo de trabajo de grupo de búsqueda

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y después en **Flujo de trabajo**.

4.  En la página **Flujo de trabajo**, haga clic en **Crear o editar un flujo de trabajo**.

5.  En el campo de búsqueda **Seleccionar un servicio**, escriba la totalidad o parte del nombre del servicio **ApplicationServer** que hospeda el flujo de trabajo que desea crear o cambiar. En la lista de servicios obtenida, haga clic en el servicio que desee y después en **Aceptar**.
    

    > [!NOTE]
    > Se abrirá la Herramienta de configuración de grupo de respuesta. También puede abrir la Herramienta de configuración de grupo de respuesta directamente desde un explorador web escribiendo la dirección URL siguiente: <STRONG>https://</STRONG><EM>&lt;webPoolFqdn&gt;</EM><STRONG>/RgsConfig</STRONG>.



6.  Siga uno de estos pasos:
    
      - En **Crear un nuevo flujo de trabajo**, junto a **Grupo de búsqueda**, haga clic en Crear.
    
      - En **Administrar un flujo de trabajo existente**, localice el flujo de trabajo que desea cambiar y después, en **Acción**, haga clic en **Editar**.

7.  Si está listo para que los usuarios empiecen a llamar al flujo de trabajo, active **Activar el flujo de trabajo**.
    

    > [!NOTE]
    > Si está creando un flujo de trabajo administrado, seleccione <STRONG>Activar el flujo de trabajo</STRONG>. Después de guardar el flujo de trabajo administrado activo, puede modificarlo o desactivarlo.



8.  Para permitir que los usuarios federados puedan llamar al grupo, active la casilla **Habilitar para federación**. Debe tener también una directiva de acceso externo que se aplique a la Aplicación de grupo de respuesta configurada para la federación.
    

    > [!NOTE]
    > La directiva de acceso externo global se aplica a la Aplicación de grupo de respuesta. Configure la directiva global para la federación de grupos de respuesta con el Panel de control de Lync Server o con el cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> para establecer el parámetro EnableOutsideAccess en True. Recuerde que la configuración de la directiva global se aplica a todos los usuarios, a menos que se les haya asignado una directiva de usuario o de sitio. Por lo tanto, antes de cambiar la configuración de los grupos de respuesta, asegúrese de que la configuración de la federación cumpla los requisitos de la organización. Para más información sobre la aplicación de las directivas a los usuarios, vea <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Administrar la directiva de acceso de la organización en Lync Server 2013</A>. Para más información sobre la configuración de federación, vea <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.

    

    > [!NOTE]
    > Los usuarios hospedados en Lync Online no pueden realizar llamadas a grupos de respuesta hospedados en una implementación local. Esto es cierto en implementaciones híbridas y en casos donde una implementación local está federada con una implementación de Lync Online.



9.  Para ocultar la identidad de los agentes durante las llamadas, active la casilla **Habilitar anonimato de agente**.
    

    > [!NOTE]
    > Las llamadas anónimas no pueden empezar con mensajería instantánea (MI) ni un vídeo, aunque el agente o la persona que llame pueda agregar MI o un vídeo después de establecer la llamada. Asimismo, un agente anónimo puede poner llamadas en espera, transferir llamadas (tanto transferencias a otras líneas como consultas), además de estacionar y recuperar llamadas. Las llamadas anónimas no admiten conferencias, uso compartido de aplicaciones ni de escritorio, transferencia de archivos, función de pizarra, colaboración de datos y grabación de llamadas. Los agentes que usen el complemento VDI de Lync pueden recibir llamadas entrantes anónimas, pero no realizar llamadas salientes anónimas.



10. En **Especifique la dirección del grupo que recibirá las llamadas**, escriba la dirección del identificador uniforme de recursos (URI) del SIP primario del grupo que responderá las llamadas al flujo de trabajo.
    

    > [!NOTE]
    > El URI primario para un flujo de trabajo es el modo en que este se identifica y se da a conocer. El URI del SIP que introduzca se creará como objeto de contacto en Servicios de dominio de Active Directory. Para crear el URI, el objeto deberá ser único en Active Directory.



11. En **Nombre para mostrar**, escriba el nombre que desea mostrar para el flujo de trabajo (por ejemplo, Grupo de respuesta de ventas).
    

    > [!NOTE]
    > No incluya los caracteres "&lt;" o "&gt;" en el nombre para mostrar. No use los siguientes nombres para mostrar porque están reservados: <STRONG>Observador de presencia de RGS</STRONG> o <STRONG>Servicio de anuncio</STRONG>.



12. En **Número de teléfono**, especifique el URI de línea para el grupo de respuesta (por ejemplo, +14255550165).

13. En **Número para mostrar**, escriba el número tal como desea que aparezca para el grupo de respuesta (por ejemplo, +1 (425) 555-0165).

14. (Opcional) En **Descripción**, escriba la descripción del flujo de trabajo que desea que aparezca en la tarjeta de contacto del cliente Lync.

15. En **Tipo de flujo de trabajo**, seleccione **Administrado** si este flujo de trabajo va a ser administrado por un administrador de grupos de respuesta. Haga lo siguiente para asignar administradores de Grupo de respuesta al flujo de trabajo:
    
    1.  Escriba el URI del SIP de un administrador para este flujo de trabajo y haga clic en **Agregar**.
    
    2.  Escriba el URI del SIP de otros administradores que desee agregar al flujo de trabajo y haga clic en **Agregar**.
    
    > [!IMPORTANT]  
    > A todos los usuarios designados administradores de un grupo de respuestas se les asigna el rol CsResponseGroupManager. Los usuarios a los que no se haya asignado este rol no pueden administrar grupos de respuesta.
    


16. En **Paso 2 Seleccionar un idioma**, haga clic en el idioma que desea utilizar para reconocimiento de voz y conversión de texto a voz.

17. Si desea definir un mensaje de bienvenida, en el **Paso 3 Configurar un mensaje de bienvenida**, active la casilla **Reproducir un mensaje de bienvenida** y luego lleve a cabo uno de estos procedimientos:
    
      - Para escribir el mensaje de bienvenida como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.
        

        > [!NOTE]
        > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    
      - Para usar una grabación de un archivo de audio de Windows Media (.wma) o WAVE (.wav) para el mensaje de bienvenida, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo de audio y luego haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        

        > [!NOTE]
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para más información sobre los formatos admitidos, vea <A href="lync-server-2013-technical-requirements-for-response-group.md">Requisitos técnicos para grupos de respuesta en Lync Server 2013</A>.



18. En **Paso 4 Especificar horario comercial**, en el cuadro **Su zona horaria**, haga clic en la zona horaria para el flujo de trabajo.
    

    > [!NOTE]
    > La zona horaria es aquella donde residen los autores de las llamadas y los agentes del flujo de trabajo. Se usa para calcular las horas de apertura y de cierre. Por ejemplo, si el flujo de trabajo se configura para usar la zona horaria Hora oriental de América del Norte y el flujo de trabajo se programa para abrirse a las 7:00 horas y cerrarse a las 23:00 horas, se supone que las horas de apertura y de cierre son, respectivamente, 7:00 horas en horario oriental y 23:00 horas en horario oriental. (Debe escribir las horas en el formato de 24 horas).



19. Para seleccionar el tipo de programación de horario comercial que quiere usar, siga uno de los procedimientos siguientes:
    
      - Para usar una programación predefinida de horario comercial, haga clic en **Utilizar una programación preestablecida** y después seleccione el horario que desea utilizar en la lista desplegable.
        

        > [!NOTE]
        > Debe haber definido al menos una programación preestablecida con anterioridad para seleccionar esta opción. Para definir programaciones preestablecidas, se utiliza el cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>. Para más información, vea <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Opcional) Definir horarios laborales de grupos de respuesta en Lync Server 2013</A>.

        

        > [!NOTE]
        > Cuando selecciona una programación preestablecida, <STRONG>Día</STRONG>, <STRONG>Abrir</STRONG> y <STRONG>Cerrar</STRONG> se rellenan automáticamente con los días y las horas en los que el grupo de respuesta se encuentra disponible.

    
      - Para usar una programación personalizada que se aplique solo a este flujo de trabajo, haga clic en **Usar una programación personalizada**.

20. Si está creando una programación personalizada para este flujo de trabajo, haga clic en las casillas correspondientes a los días de la semana durante los que se encuentra disponible el grupo de respuesta.

21. Si está creando una programación personalizada, especifique las horas en **Abrir** y **Cerrar** para cada día de la semana en el que esté disponible el grupo de respuesta.
    

    > [!NOTE]
    > Las horas en <STRONG>Abrir</STRONG> y <STRONG>Cerrar</STRONG> deben mostrarse en formato de 24 horas. Por ejemplo, si en su oficina se trabaja de 9 a 5 y se cierra al mediodía para el almuerzo, el horario comercial se especificará de la siguiente manera: <STRONG>Abrir</STRONG> 9:00, <STRONG>Cerrar</STRONG> 12:00, <STRONG>Abrir</STRONG> 13:00 y <STRONG>Cerrar</STRONG> 17:00.



22. Si desea reproducir un mensaje cuando la oficina no esté abierta, active la casilla **Reproducir un mensaje cuando el grupo de respuesta esté fuera del horario comercial** y después especifique el mensaje que se va a reproducir siguiendo uno de los procedimientos siguientes:
    
      - Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.
        

        > [!NOTE]
        > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    
      - Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        

        > [!NOTE]
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para más información sobre los formatos de audio admitidos, vea <A href="lync-server-2013-technical-requirements-for-response-group.md">Requisitos técnicos para grupos de respuesta en Lync Server 2013</A>.



23. Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):
    
      - Para desconectar la llamada, haga clic en **Desconectar llamada**.
    
      - Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y después escriba la dirección del correo de voz. El formato de la dirección de correo de voz es *\<nombreusuario\>*@*\<nombredominio\>* (por ejemplo, bob@contoso.com).
    
      - Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y después escriba la dirección de un usuario. El formato de la dirección de usuario es *\<nombreusuario\>*@*\<nombredominio\>*.
    
      - Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y después escriba el número de teléfono. El formato del número de teléfono es *\<número\>*@*\<nombredominio\>* (por ejemplo, +14255550121@contoso.com). El nombre de dominio se usa para redirigir a la persona que llama al destino correcto.

24. En **Paso 5 Especificar vacaciones**, haga clic en las casillas para uno o más conjuntos de vacaciones que definan los días en los que el grupo de respuesta no esté laboralmente disponible.
    

    > [!NOTE]
    > Defina las vacaciones y los conjuntos de vacaciones antes de configurar el flujo de trabajo. Para definir vacaciones y conjuntos de vacaciones, use los cmdlets <STRONG>New-CsRgsHoliday</STRONG> y <STRONG>New-CsRgsHolidaySet</STRONG>. Para más información, vea <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Opcional) Definición de conjuntos de días festivos para grupos de respuesta en Lync Server 2013</A>.



25. Si desea reproducir un mensaje durante las vacaciones, active la casilla **Reproducir un mensaje durante las vacaciones** y después especifique el mensaje que se va a reproducir con uno de los siguientes procedimientos:
    
      - Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.
        

        > [!NOTE]
        > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

    
      - Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        

        > [!NOTE]
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para más información sobre los formatos de audio admitidos, vea <A href="lync-server-2013-technical-requirements-for-response-group.md">Requisitos técnicos para grupos de respuesta en Lync Server 2013</A>.



26. Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):
    
      - Para desconectar la llamada, haga clic en **Desconectar llamada**.
    
      - Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y después escriba la dirección del correo de voz. El formato de la dirección de correo de voz es *\<nombreusuario\>*@*\<nombredominio\>* (por ejemplo, bob@contoso.com).
    
      - Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y después escriba la dirección de un usuario. El formato de la dirección de usuario es *\<nombreusuario\>*@*\<nombredominio\>*.
    
      - Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y después escriba el número de teléfono. El formato del número de teléfono es *\<número\>*@*\<nombredominio\>* (por ejemplo, +14255550121@contoso.com). El nombre de dominio se usa para redirigir a la persona que llama al destino correcto.

27. En el **Paso 6 Configurar una cola**, en **Seleccione la cola que recibirá las llamadas**, seleccione la cola donde desea que los autores de las llamadas se mantengan en espera hasta que un agente esté disponible.

28. En el **Paso 7 Configurar música en espera**, elija la música que desea que escuchen los autores de las llamadas mientras esperan a un agente; para ello lleve a cabo uno de procedimientos siguientes:
    
      - Para usar la grabación habitual de música en espera, haga clic en **Usar predeterminado**.
    
      - Para usar una grabación en un archivo de audio para la música en espera, haga clic en **Seleccionar un archivo de música**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **un archivo de música**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea utilizar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        

        > [!NOTE]
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para más información sobre los formatos de audio admitidos, vea <A href="lync-server-2013-technical-requirements-for-response-group.md">Requisitos técnicos para grupos de respuesta en Lync Server 2013</A>.



29. Haga clic en **Implementar**.

## Para usar Windows PowerShell para crear o modificar un flujo de trabajo de grupo de búsqueda

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Cree el mensaje de bienvenida que se reproducirá y guárdelo en una variable. En la línea de comandos, ejecute:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por ejemplo:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    

    > [!NOTE]
    > Para usar un archivo de audio para el mensaje, ejecute el cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para más información, vea <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.



4.  Obtenga la identidad de la cola o la pregunta a la que se dirigirán las llamadas. En la línea de comandos, ejecute:
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    Para más información sobre la creación de la cola, vea [New-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsQueue).

5.  Defina la acción que se ejecutará cuando un flujo de trabajo se abra en horas de trabajo y guárdela en una variable. En la línea de comandos, ejecute:
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    

    > [!NOTE]
    > Para los flujos de trabajo de grupo de búsqueda, la acción habitual será dirigir la llamada a una cola. Este parámetro se usa para los flujos de trabajo activos. No se necesita para los flujos de trabajo inactivos.

    
    Por ejemplo:
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  Para definir horas laborables y vacaciones, créelas antes de crear o modificar el flujo de trabajo. Para más información, vea [(Opcional) Definir horarios laborales de grupos de respuesta en Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) y [(Opcional) Definición de conjuntos de días festivos para grupos de respuesta en Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).

7.  Si desea tener mensajes para las llamadas que se reciben en un horario no laborable o en época de vacaciones, use el cmdlet **New-CsRgsPrompt** para definir el mensaje y el cmdlet **New-CsRgsCallAction** para definir la acción que se ejecutará después del mensaje. Para más información, vea [New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt) y [New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction).

8.  Recupere el nombre del servicio del Servicio de grupo de respuesta de Lync Server y asígnele una variable. En la línea de comandos, ejecute:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  Cree o modifique el flujo de trabajo. Para crear un flujo de trabajo, use **New-CsRgsWorkflow**. Para modificar un flujo de trabajo, use **Set-CsRgsWorkflow**. En la línea de comandos, escriba lo siguiente:
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    Por ejemplo:
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    > [!IMPORTANT]  
    > Todos los usuarios que hayan sido designados administradores de flujos de trabajo deben tener asignado el rol CsResponseGroupManager.
    
    

    > [!NOTE]
    > Para más información sobre los parámetros opcionales adicionales, vea <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> o <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A>



## Vea también

#### Tareas

[(Opcional) Definición de conjuntos de días festivos para grupos de respuesta en Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)  

#### Conceptos

[(Opcional) Definir horarios laborales de grupos de respuesta en Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)  

#### Otros recursos

[New-CsRgsWorkflow](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsWorkflow)  
[Set-CsRgsWorkflow](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsWorkflow)  
[New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction)


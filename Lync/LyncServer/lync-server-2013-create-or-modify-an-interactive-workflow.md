---
title: 'Lync Server 2013: Crear o modificar un flujo de trabajo interactivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec10d1d9c3281485078b2d7823978c429ea1be3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>Crear o modificar un flujo de trabajo interactivo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-11_

Use uno de los procedimientos siguientes para crear o modificar un flujo de trabajo interactivo.

<div>


> [!NOTE]  
> Puede usar el shell de administración de Lync Server o la herramienta de configuración de grupos de respuesta para crear y modificar flujos de trabajo interactivos. Puede obtener acceso a la herramienta de configuración de grupos de respuesta desde el panel de control de Lync Server o abriendo la página web directamente desde un explorador web escribiendo la siguiente dirección URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Para usar la herramienta de configuración de grupos de respuesta para crear o modificar un flujo de trabajo interactivo

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y después en **Flujo de trabajo**.

4.  En la página **Flujo de trabajo**, haga clic en **Crear o editar un flujo de trabajo**.

5.  En el campo de búsqueda **Seleccionar un servicio**, escriba total o parcialmente el nombre del servicio de **ApplicationServer** que hospeda el flujo de trabajo que desea crear o modificar. En la lista de servicios resultante, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Se abrirá la herramienta de configuración de grupos de respuesta. También puede abrir la herramienta de configuración de grupo de respuesta directamente desde un explorador web escribiendo la siguiente URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Siga uno de estos pasos:
    
      - En **Crear un nuevo flujo de trabajo**, junto a **Interactivo**, haga clic en **Crear**.
    
      - En **Administrar un flujo de trabajo existente**, localice el flujo de trabajo que desea cambiar y, a continuación, en **Acción**, haga clic en **Editar**.

7.  Si todavía no está listo para que los usuarios comiencen a llamar al flujo de trabajo, desactive la casilla **Activar el flujo de trabajo**.
    
    <div>
    

    > [!NOTE]  
    > Si está creando un flujo de trabajo administrado, seleccione <STRONG>Activar el flujo de trabajo</STRONG>. Después de guardar el flujo de trabajo administrado activo, puede modificarlo y desactivarlo.

    
    </div>

8.  Para permitir que los usuarios federados puedan llamar al grupo, active la casilla **Habilitar para federación**. También debe tener una directiva de acceso externo que se aplique a la aplicación de grupo de respuesta configurada para la Federación.
    
    <div>
    

    > [!NOTE]  
    > La Directiva de acceso externo global se aplica a la aplicación de grupo de respuesta. Puede configurar la directiva global para la Federación de grupos de respuesta mediante el panel de control de Lync Server o mediante el cmdlet <STRONG>set-CsExternalAccessPolicy</STRONG> para establecer el parámetro EnableOutsideAccess en true. Recuerde que la configuración de la directiva global se aplica a todos los usuarios, a menos que se les haya asignado una directiva de usuario o de sitio. Por lo tanto, antes de cambiar la configuración de los grupos de respuesta, asegúrese de que la configuración de la federación cumpla los requisitos de la organización. Para obtener más información sobre cómo se aplican las directivas a los usuarios, vea <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">administrar la Directiva de acceso externo en Lync Server 2013</A>. Para obtener más información sobre la configuración de Federación, consulte <STRONG>set-CsExternalAccessPolicy</STRONG> en la documentación del shell de administración de Lync Server.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Los usuarios que se hospedan en Lync Online no pueden realizar llamadas a grupos de respuesta hospedados en una implementación local. Esto sucede en ambas implementaciones híbridas y en los casos en los que una implementación local se federa con una implementación de Lync Online.

    
    </div>

9.  Para ocultar la identidad de los agentes durante las llamadas, active la casilla **Habilitar anonimato de agente**.
    
    <div>
    

    > [!NOTE]  
    > Las llamadas anónimas no pueden empezar con mensajería instantánea (MI) ni un vídeo, aunque el agente o la persona que llame pueda agregar MI o un vídeo después de establecer la llamada. Asimismo, un agente anónimo puede poner llamadas en espera, transferir llamadas (tanto transferencias a otras líneas como consultas), además de estacionar y recuperar llamadas. Las llamadas anónimas no admiten conferencias, uso compartido de aplicaciones ni de escritorio, transferencia de archivos, función de pizarra, colaboración de datos y grabación de llamadas. Los agentes que usen el complemento VDI de Lync pueden recibir llamadas entrantes anónimas, pero no realizar llamadas salientes anónimas.

    
    </div>

10. En **Especifique la dirección del grupo que recibirá las llamadas**, escriba la dirección del identificador uniforme de recursos (URI) del SIP primario del grupo que responderá las llamadas al flujo de trabajo.

11. En **Nombre para mostrar**, escriba el nombre que desea mostrar para el flujo de trabajo (por ejemplo, Grupo de respuesta IVR de ventas).
    
    <div>
    

    > [!NOTE]  
    > No incluyas los caracteres&lt;"" o&gt;"" en el nombre para mostrar. No use los siguientes nombres para mostrar porque están reservados: Observador de presencia de RGS o Servicio de anuncio.

    
    </div>

12. En **Número de teléfono**, escriba el URI de línea para el grupo de respuesta (por ejemplo, +14255550165).

13. En **Número para mostrar**, escriba el número tal como desea que aparezca para el grupo de respuesta (por ejemplo, +1 (425) 555-0165).

14. Faculta En **Descripción**, escriba una descripción para el flujo de trabajo que desea que aparezca en la tarjeta de contacto en el cliente de Lync.

15. En **Tipo de flujo de trabajo**, seleccione **Administrado** si este flujo de trabajo va a ser administrado por un administrador de grupos de respuesta. Siga este procedimiento para asignar administradores de grupos de respuesta al flujo de trabajo:
    
    1.  Escriba el URI del SIP de un administrador para este flujo de trabajo y haga clic en **Agregar**.
    
    2.  Escriba el URI del SIP de otros administradores para agregar al flujo de trabajo y haga clic en **Agregar**.
    
    <div>
    

    > [!IMPORTANT]  
    > A todos los usuarios designados como administradores de un grupo de respuestas se les asigna el rol CsResponseGroupManager. Los usuarios a los que no se haya asignado este rol no pueden administrar grupos de respuesta.

    
    </div>

16. En **Paso 2 Seleccionar un idioma**, haga clic en el idioma que se usará para el reconocimiento de voz y texto a voz.

17. Si desea definir un mensaje de bienvenida, en el **Paso 3 Configurar un mensaje de bienvenida**, active la casilla **Reproducir un mensaje de bienvenida** y luego lleve a cabo uno de estos procedimientos:
    
      - Para escribir el mensaje de bienvenida como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.
        
        <div>
        

        > [!NOTE]  
        > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

        
        </div>
    
      - Para usar una grabación de archivos de Wave o Windows Media Audio para el mensaje de bienvenida, haga clic en **Seleccionar una grabación**. Si desea cargar un nuevo archivo de audio, haga clic en el vínculo de **una grabación**. En la nueva ventana de explorador, haga clic en **Examinar**, seleccione el archivo de audio que desea usar y haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        
        <div>
        

        > [!NOTE]  
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener detalles sobre los formatos de archivo admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.

        
        </div>

18. En **Paso 4 Especificar horario comercial**, en el cuadro **Su zona horaria**, haga clic en la zona horaria del flujo de trabajo.
    
    <div>
    

    > [!NOTE]  
    > La zona horaria se refiere a la zona donde residen los autores de llamadas y los agentes del flujo de trabajo. Se usa para calcular las horas de apertura y cierre. Por ejemplo, si el flujo de trabajo está configurado para usar la zona horaria Hora oriental de América del Norte y el flujo de trabajo está programado para abrir a las 7:00 y cerrar a 23:00, se supone que las horas de apertura y cierre son las 7:00 (Hora del este) y las 23:00 (Hora del este) respectivamente. Escriba las horas en la notación de 24 horas.

    
    </div>

19. Para seleccionar el tipo de programación de horario comercial que quiere usar, siga uno de los procedimientos siguientes:
    
      - Para usar una programación predefinida de horario comercial, haga clic en **Usar una programación preestablecida** y después seleccione el horario que desea utilizar en la lista desplegable.
        
        <div>
        

        > [!NOTE]  
        > Debe definir al menos una programación preestablecida previamente para poder seleccionar esta opción. Puede definir programaciones preestablecidas con el cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>. Para obtener más información, consulte <A href="lync-server-2013-optional-define-response-group-business-hours.md">(opcional) definir las horas de trabajo del grupo de respuesta en Lync Server 2013</A>. Cuando selecciona una programación preestablecida, <STRONG>Día</STRONG>, <STRONG>Abrir</STRONG> y <STRONG>Cerrar</STRONG> se rellenan automáticamente con los días y las horas en los que el grupo de respuesta se encuentra disponible.

        
        </div>
    
      - Para usar una programación personalizada que se aplique solo a este flujo de trabajo, haga clic en **Usar una programación personalizada**.

20. Si está creando una programación personalizada para este flujo de trabajo, haga clic en las casillas correspondientes a los días de la semana durante los que se encuentra disponible el grupo de respuesta.

21. Para crear una programación personalizada, escriba las horas de   **Abrir** y **Cerrar** en las que el grupo de respuesta se encuentra disponible.
    
    <div>
    

    > [!NOTE]  
    > Las horas de <STRONG>Abrir</STRONG> y <STRONG>Cerrar</STRONG> deben mostrarse en formato de 24 horas. Por ejemplo, si en su oficina se trabaja de 9 a 5 y se cierra al mediodía para el almuerzo, el horario comercial se especificará de la siguiente manera: <STRONG>Abrir</STRONG> 9:00, <STRONG>Cerrar</STRONG> 12:00, <STRONG>Abrir</STRONG> 13:00 y <STRONG>Cerrar</STRONG> 17:00.

    
    </div>

22. Si desea reproducir un mensaje cuando la oficina no esté abierta, active la casilla **Reproducir un mensaje cuando el grupo de respuesta esté fuera del horario comercial** y después especifique el mensaje que se va a reproducir siguiendo uno de los procedimientos siguientes:
    
      - Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.
        
        <div>
        

        > [!NOTE]  
        > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

        
        </div>
    
      - Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        
        <div>
        

        > [!NOTE]  
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener detalles sobre los formatos de archivo admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.

        
        </div>

23. Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):
    
      - Para desconectar la llamada, haga clic en **Desconectar llamada**.
    
      - Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y escriba la dirección de correo de voz. El formato de la dirección de correo de \<voz\>@\<es\> nombre de usuario nombreDeDominio (por ejemplo, Bob@contoso.com).
    
      - Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y escriba la dirección de usuario. El formato de la dirección de usuario \<es\>@\<nombre\>de usuario nombreDeDominio.
    
      - Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y escriba el número de teléfono. El formato del número de teléfono es \<\>@\<domainname\> (por ejemplo, + 14255550121@contoso.com). El nombre de dominio se usa para redirigir al autor de la llamada al destino correcto.

24. En **Paso 5 Especificar vacaciones**, haga clic en las casillas para uno o más conjuntos de vacaciones que definan los días en los que el grupo de respuesta no esté laboralmente disponible.
    
    <div>
    

    > [!NOTE]  
    > Defina las vacaciones y los conjuntos de vacaciones antes de configurar el flujo de trabajo. Para ello, use los cmdlets <STRONG>New-CsRgsHoliday</STRONG> y <STRONG>New-CsRgsHolidaySet</STRONG>. Para obtener más información, consulte <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(opcional) definir conjuntos de días festivos de grupos de respuesta en Lync Server 2013</A>.

    
    </div>

25. Si desea reproducir un mensaje durante las vacaciones, active la casilla **Reproducir un mensaje durante las vacaciones** y después especifique el mensaje que se va a reproducir con uno de los siguientes procedimientos:
    
      - Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.
        
        <div>
        

        > [!NOTE]  
        > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

        
        </div>
    
      - Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        
        <div>
        

        > [!NOTE]  
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener detalles sobre los formatos de archivo de audio admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.

        
        </div>

26. Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):
    
      - Para desconectar la llamada, haga clic en **Desconectar llamada**.
    
      - Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y escriba la dirección de correo de voz. El formato de la dirección de correo de \<voz\>@\<es\> nombre de usuario nombreDeDominio (por ejemplo, Bob@contoso.com).
    
      - Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y escriba la dirección de usuario. El formato de la dirección de usuario \<es\>@\<nombre\>de usuario nombreDeDominio.
    
      - Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y escriba el número de teléfono. El formato del número de teléfono es \<\>@\<domainname\> (por ejemplo, + 14255550121@contoso.com). El nombre de dominio se usa para redirigir al autor de la llamada al destino correcto.

27. En **Paso 6 Configurar música en espera**, elija lo que desea que escuchen los autores de las llamadas mientras esperan a un agente con uno de los procedimientos siguientes:
    
      - Para usar la grabación de música en espera predeterminada, haga clic en **Predeterminada**.
    
      - Para usar una grabación de archivo de audio para la música en espera, haga clic en **Seleccionar un archivo de música**. Si desea cargar un nuevo archivo de audio, haga clic en el vínculo de   **un archivo de música**. En la nueva ventana de explorador, haga clic en **Examinar**, seleccione el archivo de audio que desea usar y haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        
        <div>
        

        > [!NOTE]  
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener detalles sobre los formatos de archivo admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.

        
        </div>

28. En **Paso 7 Configurar una respuesta interactiva de voz**, en   **El usuario escuchará el siguiente texto o mensaje grabado**, especifique la pregunta que desea formular a los autores de las llamadas, como se indica a continuación:
    
      - Para especificar la pregunta en formato de texto, haga clic en **Usar texto a voz** y escriba la pregunta en el cuadro de texto.
        
        <div>
        

        > [!NOTE]  
        > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > El motor de conversión de texto a voz traduce el símbolo "#" como la palabra "número". Si necesita hacer referencia a la tecla #, debe usar el nombre de tecla, en lugar de el símbolo, en el mensaje de asistencia por voz. Por ejemplo, "Para hablar con el departamento de ventas, presione la tecla almohadilla".

        
        </div>
    
      - Para usar un archivo de audio pregrabado que contiene la pregunta, haga clic en **Seleccionar una grabación** y en el vínculo **una grabación** para cargar el archivo. En la nueva ventana de explorador, haga clic en **Examinar**, seleccione el archivo de audio y haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo y, si lo desea, puede escribir la pregunta en el cuadro de texto (esto permite desviar la pregunta y la respuesta del autor de la llamada al agente de respuesta).
        
        <div>
        

        > [!NOTE]  
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener detalles sobre los formatos de archivo admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.

        
        </div>

29. En **Respuesta 1**, especifique la primera respuesta posible a la pregunta con este procedimiento:
    
    <div>
    

    > [!IMPORTANT]  
    > No use comillas (") en las respuestas de voz porque provocan un error de IVR.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Puede elegir si los autores de la llamada pueden responder con voz, con el teclado alfanumérico o con ambos.

    
    </div>
    
      - Si desea permitir que el autor de la llamada responda con voz, escriba la respuesta en **Especificar una respuesta de voz**.
    
      - Si desea permitir que el autor de la llamada presione una tecla del teclado para responder, en **Dígito**, haga clic en el dígito del teclado.

30. Para especificar si desea redirigir al autor de la llamada a una cola o hacer otra pregunta, haga lo siguiente:
    
      - Para redirigir al autor de la llamada a una cola, haga clic en **Enviar a una cola** y, en **Seleccionar una cola**, haga clic en la cola que desea usar.
    
      - Para hacer otra pregunta, haga clic en **Formular otra pregunta**, en **Usar texto a voz** y escriba la pregunta o haga clic en **Seleccionar una grabación**. Use los grupos de respuesta de esta sección para especificar hasta cuatro respuestas posibles para la pregunta adicional y la cola que se desea usar para cada respuesta. Para especificar una tercera o cuarta respuesta posible, haga clic en las casillas **Respuesta 3** o **Respuesta 4**, respectivamente.

31. Especifique hasta otras tres respuestas posibles para la pregunta original. Para ello, repita los pasos 28 y 29 para especificar las posibles respuestas y la acción que se debe seguir con cada respuesta. Para especificar una tercera o cuarta respuesta posible, haga clic en las casillas **Respuesta 3** o **Respuesta 4**, respectivamente.

32. Haga clic en **Implementar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>Para usar Windows PowerShell para crear o modificar un flujo de trabajo interactivo

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Recupere el nombre de servicio del servicio Grupo de respuestas y asígnelo a una variable. En la línea de comandos, ejecute:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  Un flujo de trabajo interactivo requiere dos o más colas y dos o más grupos de agentes. En primer lugar, cree los grupos de agentes. Ejecute:
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  Cree las colas. Ejecute:
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  Cree el primer aviso del grupo de respuestas. Ejecute:
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  A continuación, cree la acción que debe realizarse tras el aviso. Ejecute:
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  Cree la primera respuesta del grupo de respuestas. Ejecute:
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  Ahora cree el segundo aviso, y la acción de llamada y la respuesta correspondientes. En primer lugar, cree el aviso. Ejecute:
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. Cree la segunda acción de llamada. Ejecute:
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. Cree la segunda respuesta del grupo de respuestas. Ejecute:
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. Cree el aviso de nivel superior. Ejecute:
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. Cree la pregunta de nivel superior. Ejecute:
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. Ahora cree el flujo de trabajo. Ejecute:
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > El rol CsResponseGroupManager debe asignarse a todos los usuarios que se designen como administradores de un grupo de respuesta. De lo contrario, no podrán administrar los grupos de respuestas.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


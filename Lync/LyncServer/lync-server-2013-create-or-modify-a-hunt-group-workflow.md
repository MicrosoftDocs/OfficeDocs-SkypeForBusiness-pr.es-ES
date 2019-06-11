---
title: 'Lync Server 2013: crear o modificar un flujo de trabajo de un grupo de captura'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c927b10107626c1d40c33290b30f331f660e45e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a>Crear o modificar un flujo de trabajo de grupo de captura en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-11_

Use uno de los procedimientos siguientes para crear o modificar un flujo de trabajo de grupo de captura.

<div>


> [!NOTE]  
> Puede usar el shell de administración de Lync Server o la herramienta de configuración de grupos de respuesta para crear y modificar flujos de trabajo de grupos de búsqueda. Puede obtener acceso a la herramienta de configuración de grupos de respuesta desde el panel de control de Lync Server o abriendo la página web directamente desde un explorador web escribiendo la siguiente dirección URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Para usar la herramienta de configuración de grupos de respuesta para crear o modificar un flujo de trabajo de Hunt Group

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y después en **Flujo de trabajo**.

4.  En la página **Flujo de trabajo**, haga clic en **Crear o editar un flujo de trabajo**.

5.  En el campo de búsqueda **Seleccionar un servicio**, escriba la totalidad o parte del nombre del servicio **ApplicationServer** que hospeda el flujo de trabajo que desea crear o cambiar. En la lista de servicios resultante, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Se abrirá la herramienta de configuración de grupos de respuesta. También puede abrir la herramienta de configuración de grupo de respuesta directamente desde un explorador web escribiendo la siguiente URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Siga uno de estos pasos:
    
      - Under **Create a New Workflow**, next to **Hunt Group, click Create**.
    
      - En **Administrar un flujo de trabajo existente**, localice el flujo de trabajo que desea cambiar y, a continuación, en **Acción**, haga clic en **Editar**.

7.  Si está listo para que los usuarios empiecen a llamar al flujo de trabajo, seleccione **Activar el flujo de trabajo**.
    
    <div>
    

    > [!NOTE]  
    > Si está creando un flujo de trabajo administrado, seleccione <STRONG>Activar el flujo de trabajo</STRONG>. Después de guardar el flujo de trabajo administrado activo, puede modificarlo y desactivarlo.

    
    </div>

8.  Para permitir que los usuarios federados puedan llamar al grupo, active la casilla **Habilitar para federación**. También debe tener una directiva de acceso externo que se aplique a la aplicación de grupo de respuesta configurada para la Federación.
    
    <div>
    

    > [!NOTE]  
    > La Directiva de acceso externo global se aplica a la aplicación de grupo de respuesta. Puede configurar la directiva global para la Federación de grupos de respuesta mediante el panel de control de Lync Server o mediante el cmdlet <STRONG>set-CsExternalAccessPolicy</STRONG> para establecer el parámetro EnableOutsideAccess en true. Recuerde que la configuración de la directiva global se aplica a todos los usuarios, a menos que se les haya asignado una directiva de usuario o de sitio. Por lo tanto, antes de cambiar la configuración de los grupos de respuesta, asegúrese de que la configuración de la federación cumpla los requisitos de la organización. Para obtener más información sobre cómo se aplican las directivas a los usuarios, vea <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">administrar la Directiva de acceso externo en Lync Server 2013</A>. Para obtener más información sobre la configuración de Federación, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">set-CsExternalAccessPolicy</A>.

    
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
    
    <div>
    

    > [!NOTE]  
    > El URI principal de un flujo de trabajo es la forma cómo se identifica y se denomina el flujo de trabajo. El URI de SIP que especifique se creará como un objeto de contacto en los servicios de dominio de Active Directory. Para crear el URI, el objeto debe ser único en Active Directory.

    
    </div>

11. En **nombre para mostrar**, escriba el nombre que desea mostrar para el flujo de trabajo (por ejemplo, grupo de respuesta de ventas).
    
    <div>
    

    > [!NOTE]  
    > No incluyas los caracteres&lt;"" o&gt;"" en el nombre para mostrar. No use los siguientes nombres para mostrar porque están reservados: <STRONG>RGS Presence Watcher</STRONG> o <STRONG>Announcement Service</STRONG>.

    
    </div>

12. En **Número de teléfono**, especifique el URI de línea para el grupo de respuesta (por ejemplo, +14255550165).

13. En **Número para mostrar**, escriba el número tal como desea que aparezca para el grupo de respuesta (por ejemplo, +1 (425) 555-0165).

14. Faculta En **Descripción**, escriba una descripción para el flujo de trabajo tal y como desea que aparezca en la tarjeta de contacto en el cliente de Lync.

15. En **Tipo de flujo de trabajo**, seleccione **Administrado** si este flujo de trabajo va a ser administrado por un administrador de grupos de respuesta. Siga este procedimiento para asignar administradores de grupos de respuesta al flujo de trabajo:
    
    1.  Escriba el URI del SIP de un administrador para este flujo de trabajo y haga clic en **Agregar**.
    
    2.  Escriba el URI del SIP de otros administradores que desee agregar al flujo de trabajo y haga clic en **Agregar**.
    
    <div>
    

    > [!IMPORTANT]  
    > A todos los usuarios designados administradores de un grupo de respuestas se les asigna el rol CsResponseGroupManager. Los usuarios a los que no se haya asignado este rol no pueden administrar grupos de respuesta.

    
    </div>

16. En **Paso 2 Seleccionar un idioma**, haga clic en el idioma que desea utilizar para reconocimiento de voz y conversión de texto a voz.

17. Si desea definir un mensaje de bienvenida, en el **Paso 3 Configurar un mensaje de bienvenida**, active la casilla **Reproducir un mensaje de bienvenida** y luego lleve a cabo uno de estos procedimientos:
    
      - Para escribir el mensaje de bienvenida como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.
        
        <div>
        

        > [!NOTE]  
        > No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.

        
        </div>
    
      - Para usar una grabación de un archivo de audio de Windows Media (.wma) o WAVE (.wav) para el mensaje de bienvenida, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo de audio y luego haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        
        <div>
        

        > [!NOTE]  
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener detalles sobre los formatos de archivo admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.

        
        </div>

18. En **Paso 4 Especificar horario comercial**, en el cuadro **Su zona horaria**, haga clic en la zona horaria para el flujo de trabajo.
    
    <div>
    

    > [!NOTE]  
    > La zona horaria es aquella donde residen los autores de las llamadas y los agentes del flujo de trabajo. Se usa para calcular las horas de apertura y de cierre. Por ejemplo, si el flujo de trabajo se configura para usar la zona horaria Hora oriental de América del Norte y el flujo de trabajo se programa para abrirse a las 7:00 horas y cerrarse a las 23:00 horas, se supone que las horas de apertura y de cierre son, respectivamente, 7:00 horas en horario oriental y 23:00 horas en horario oriental. (Debe escribir las horas en el formato de 24 horas).

    
    </div>

19. Para seleccionar el tipo de programación de horario comercial que quiere usar, siga uno de los procedimientos siguientes:
    
      - Para usar una programación predefinida de horario comercial, haga clic en **Usar una programación preestablecida** y después seleccione el horario que desea utilizar en la lista desplegable.
        
        <div>
        

        > [!NOTE]  
        > Debe definir al menos una programación preestablecida previamente para poder seleccionar esta opción. Puede definir programaciones preestablecidas con el cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>. Para obtener más información, consulte <A href="lync-server-2013-optional-define-response-group-business-hours.md">(opcional) definir las horas de trabajo del grupo de respuesta en Lync Server 2013</A>.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > Cuando selecciona una programación preestablecida, <STRONG>Día</STRONG>, <STRONG>Abrir</STRONG> y <STRONG>Cerrar</STRONG> se rellenan automáticamente con los días y las horas en los que el grupo de respuesta se encuentra disponible.

        
        </div>
    
      - Para usar una programación personalizada que se aplique solo a este flujo de trabajo, haga clic en **Usar una programación personalizada**.

20. Si está creando una programación personalizada para este flujo de trabajo, haga clic en las casillas correspondientes a los días de la semana durante los que se encuentra disponible el grupo de respuesta.

21. Si está creando una programación personalizada, especifique las horas en **Abrir** y **Cerrar** para cada día de la semana en el que esté disponible el grupo de respuesta.
    
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
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener detalles sobre los formatos de archivo de audio admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.

        
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

27. En el **Paso 6 Configurar una cola**, en **Seleccione la cola que recibirá las llamadas**, seleccione la cola donde desea que los autores de las llamadas se mantengan en espera hasta que un agente esté disponible.

28. En el **Paso 7 Configurar música en espera**, elija la música que desea que escuchen los autores de las llamadas mientras esperan a un agente; para ello lleve a cabo uno de procedimientos siguientes:
    
      - Para usar la grabación habitual de música en espera, haga clic en **Usar predeterminado**.
    
      - Para usar una grabación de un archivo de audio para la música en espera, haga clic en **Seleccionar un archivo de música**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **un archivo de música**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.
        
        <div>
        

        > [!NOTE]  
        > Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos. Para obtener detalles sobre los formatos de archivo de audio admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.

        
        </div>

29. Haga clic en **Implementar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a>Para usar Windows PowerShell para crear o modificar un flujo de trabajo de grupo de captura

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Cree el mensaje de bienvenida que se reproducirá y guárdelo en una variable. En la línea de comandos, ejecute:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por ejemplo:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > Para usar un archivo de audio para el mensaje, ejecute el cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Obtenga la identidad de la cola o la pregunta a la que se dirigirán las llamadas. En la línea de comandos, ejecute:
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    Para obtener detalles sobre la creación de la cola, vea [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).

5.  Defina la acción que se ejecutará cuando un flujo de trabajo se abra en horas de trabajo y guárdela en una variable. En la línea de comandos, ejecute:
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > Para los flujos de trabajo de grupo de búsqueda, la acción habitual será dirigir la llamada a una cola. Este parámetro se usa para los flujos de trabajo activos. No se necesita para los flujos de trabajo inactivos.

    
    </div>
    
    Por ejemplo:
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  Si desea definir horas laborables y vacaciones, debe crearlas antes de crear o modificar el flujo de trabajo. Para obtener más información, consulte [(opcional) definir las horas de trabajo del grupo de respuesta en Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) y [(opcional) definir conjuntos de días festivos de grupos de respuesta en Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).

7.  Si desea tener mensajes para las llamadas que se reciben en un horario no laborable o en época de vacaciones, use el cmdlet **New-CsRgsPrompt** para definir el mensaje y el cmdlet **New-CsRgsCallAction** para definir la acción que se ejecutará después del mensaje. Para obtener más información, vea [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) y [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).

8.  Recupere el nombre del servicio del grupo de respuesta de Lync Server y asígnelo a una variable. En la línea de comandos, ejecute:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  Cree o modifique el flujo de trabajo. Para crear un flujo de trabajo, use **New-CsRgsWorkflow**. Para modificar un flujo de trabajo, use **Set-CsRgsWorkflow**. En la línea de comandos, escriba lo siguiente:
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    Por ejemplo:
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > Todos los usuarios que hayan sido designados administradores de flujos de trabajo deben tener asignado el rol CsResponseGroupManager.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Para obtener detalles sobre parámetros opcionales adicionales, vea <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> o <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">set-CsRgsWorkflow</A>

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Faculta Definir conjuntos de días festivos de grupos de respuesta en Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[Faculta Definir las horas de trabajo del grupo de respuesta en Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)  


[Nuevo: CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[Nuevo: CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


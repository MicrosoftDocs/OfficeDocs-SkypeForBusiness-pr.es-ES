---
title: 'Lync Server 2013: crear o modificar una cola'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6bc1e5f956b5b975e14f07a3c37f2802d1b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>Crear o modificar una cola en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Use uno de los procedimientos siguientes para crear o modificar una cola.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>Para usar el panel de control de Lync Server para crear o modificar una cola

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
    <div>
    

    > [!NOTE]  
    > Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear o modificar colas de grupo de respuesta y asignarlas a los flujos de trabajo que administre.

    
    </div>

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y luego en **Cola**.

4.  En la página **Cola**, lleve a cabo alguna de estas acciones:
    
      - Para crear una cola nueva, haga clic en **Nuevo**. En **Seleccionar un servicio**, escriba total o parcialmente el nombre del servicio **ApplicationServer** en cuyo campo de búsqueda desea agregar la cola. En la lista de servicios que aparezca, haga clic en el servicio que desea y en **Aceptar**.
    
      - Para modificar una cola actual, escriba total o parcialmente el nombre de la cola en el campo de búsqueda. En la lista de colas que aparezca, haga clic sucesivamente en la cola que desea, **Editar** y **Mostrar detalles**.

5.  En **Nombre**, escriba un nombre de identificación para la cola.

6.  En **Descripción**, escriba la descripción de la cola.

7.  En **Grupos**, especifique los grupos que desea asignar a la cola. Lleve a cabo una de estas acciones:
    
      - Para agregar un grupo a la cola, haga clic en **Seleccionar**. En el campo de búsqueda **Seleccionar grupos**, escriba total o parcialmente el nombre del grupo de agentes que desea asignar a la cola. A continuación, haga clic en el grupo de agentes que desea y en **Aceptar**.
    
      - Para quitar un grupo de la cola, en la lista de grupos de agentes, haga clic en el grupo que desea quitar y en **Aceptar**.
    
      - Para cambiar el orden en el que se buscan los agentes, en la lista de grupos de agentes, haga clic en un grupo y en la flecha arriba o abajo.
        
        <div>
        

        > [!NOTE]  
        > Cuando el servidor busca un agente disponible en la cola, usa el orden de grupo. Es decir, busca primero en el primer grupo de la lista, después en el segundo grupo y así sucesivamente.

        
        </div>

8.  Para especificar un período máximo de tiempo de espera para el autor de una llamada antes de que un agente responda, active la casilla **Habilitar tiempo de espera de cola** y haga lo siguiente:
    
    1.  En **Período de tiempo de espera (segundos)**, especifique el número máximo de segundos que el autor de una llamada debe esperar hasta que un agente responda.
    
    2.  En **Acción de llamada**, seleccione la acción que debe producirse cuando se agote el tiempo de espera de una llamada:
    
    <!-- end list -->
    
      - Para desconectar la llamada una vez transcurrido el tiempo de espera, haga clic en **Desconectar**.
    
      - Para desviar la llamada al correo de voz, haga clic en\>@\< **reenviar al correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una\<dirección de correo de voz con el formato SIP: nombre de usuario nombreDeDominio\> (por ejemplo, SIP: bob@contoso.com).
    
      - Para desviar la llamada a otro número de teléfono, haga clic en\>@\< **reenviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba\<el número de teléfono en el formato SIP: número domainname\> (por ejemplo, sip:+14255550121@contoso.com).
    
      - Para desviar la llamada a otro usuario, haga clic en\>@\< **reenviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI para el\<usuario con\>el formato SIP: nombreusuario nombreDeDominio.
    
      - Para reenviar la llamada a otra cola, haga clic en **Desviar a otra cola** y busque la cola que desea usar.

9.  Para especificar el número máximo de llamadas que se pueden incluir en una cola, active la casilla **Habilitar desbordamiento de cola** y haga lo siguiente:
    
    1.  En **Número máximo de llamadas**, seleccione el número máximo de llamadas que desea incluir en la cola.
    
    2.  En **Desviar la llamada**, seleccione la llamada que desea reenviar cuando la cola está completa: **Llamada más reciente** o **Llamada más antigua**.
    
    3.  En **Acción de llamada**, seleccione la acción que debe producirse cuando se alcance el umbral de desbordamiento conforme a lo siguiente:
    
    <!-- end list -->
    
      - Para desconectar la llamada una vez transcurrido el tiempo de espera, haga clic en **Desconectar**.
    
      - Para desviar la llamada al correo de voz, haga clic en\>@\< **reenviar al correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una\<dirección de correo de voz con el formato SIP: nombre de usuario nombreDeDominio\> (por ejemplo, SIP: bob@contoso.com).
    
      - Para desviar la llamada a otro número de teléfono, haga clic en\>@\< **reenviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba\<el número de teléfono en el formato SIP: número domainname\> (por ejemplo, sip:+14255550121@contoso.com).
    
      - Para desviar la llamada a otro usuario, haga clic en\>@\< **reenviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI para el\<usuario con\>el formato SIP: nombreusuario nombreDeDominio.
    
      - Para reenviar la llamada a otra cola, haga clic en **Desviar a otra cola** y busque la cola que desea usar.

10. Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>Para usar Windows PowerShell para crear o modificar una cola

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
    <div>
    

    > [!NOTE]  
    > Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear colas y grupos de agentes, y asignar estos grupos a las colas.

    
    </div>

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Cree el aviso que debe reproducirse cuando se alcance el umbral de tiempo de espera de la cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por ejemplo:
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Para usar un archivo de audio para el mensaje, ejecute el cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Defina la acción que debe realizarse cuando se alcance el umbral de tiempo de espera de la cola y guárdela en una variable. En la línea de comandos ejecute:
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Para obtener detalles sobre las posibles acciones y su sintaxis, vea <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Por ejemplo:
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  Cree el aviso que debe reproducirse cuando se alcance el umbral de desbordamiento de la cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por ejemplo:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Para usar un archivo de audio para el mensaje, ejecute el cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

6.  Defina la acción que debe realizarse cuando se alcance el umbral de desbordamiento de la cola y guárdela en una variable. En la línea de comandos ejecute:
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Para obtener detalles sobre las posibles acciones y su sintaxis, vea <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Por ejemplo:
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  Recupere el nombre de servicio del servicio Grupo de respuestas y asígnelo a una variable. En la línea de comandos, ejecute:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  Obtenga la identidad del grupo de agentes que debe asignarse a la cola. En la línea de comandos, ejecute:
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre cómo crear el grupo agente, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A>

    
    </div>

9.  Cree la cola. En la línea de comandos, ejecute:
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    Por ejemplo:
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. Confirme que la cola se ha creado. Ejecute:
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Vea también


[Nuevo: CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[Nuevo: CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Importar-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: crear o modificar una cola'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4c85dd6da5ba15a6ce946c4e331e09c8617974
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525827"
---
# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>Crear o modificar una cola en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Use uno de los siguientes procedimientos para crear o modificar una cola.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>Para usar el panel de control de Lync Server para crear o modificar una cola

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
    <div>
    

    > [!NOTE]  
    > Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear o modificar colas de grupo de respuesta y asignarlas a los flujos de trabajo que administre.

    
    </div>

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Cola**.

4.  En la página **cola** , lleve a cabo uno de los procedimientos siguientes:
    
      - Para crear una nueva cola, haga clic en **nuevo**. En **seleccionar un servicio**, escriba la parte o la totalidad del nombre del servicio **ApplicationServer** en el que desea agregar la cola en el campo de búsqueda. En la lista de resultados que aparece, haga clic en el servicio que desea y en **Aceptar**.
    
      - Para modificar una cola existente, escriba todo o parte del nombre de la cola en el campo de búsqueda. En la lista resultante de colas, haga clic en la cola que desee, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **nombre**, escriba un nombre de identificación para la cola.

6.  En **Descripción**, escriba una descripción para la cola.

7.  En **grupos**, especifique los grupos que desea asignar a la cola. Realice una de las siguientes acciones:
    
      - Para agregar un grupo a la cola, haga clic en **seleccionar**. En el campo de búsqueda **seleccionar grupos** , escriba todo o parte del nombre del grupo de agentes que desee asignar a la cola, haga clic en el grupo de agentes que desee y, a continuación, haga clic en **Aceptar**.
    
      - Para quitar un grupo de la cola, en la lista de grupos de agentes, haga clic en el grupo que desea quitar y, a continuación, haga clic en **quitar**.
    
      - Para cambiar el orden en el que se buscan los agentes, en la lista de grupos de agentes, haga clic en un grupo y, a continuación, haga clic en la flecha hacia arriba o hacia abajo.
        
        <div>
        

        > [!NOTE]  
        > Cuando el servidor busca un agente disponible para la cola, utiliza el orden de grupo. Es decir, se busca primero en el primer grupo de la lista, después en el segundo grupo de la lista y así sucesivamente.

        
        </div>

8.  Para especificar un período de tiempo máximo de espera para el autor de una llamada antes de que un agente le atienda, active la casilla **Habilitar tiempo de espera de la cola**.
    
    1.  En **Tiempo de espera (segundos)**, especifique el número máximo de segundos que va a esperar el autor de una llamada para que le atienda un agente.
    
    2.  En **Acción de llamada**, seleccione la acción que va a tener lugar cuando se agota el tiempo de espera de una llamada de la forma siguiente:
    
    <!-- end list -->
    
      - Para desconectar la llamada tras el tiempo de espera, haga clic en **Desconectar**.
    
      - Para reenviar la llamada al correo de voz, haga clic en **desviar a correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una dirección de correo de voz con el formato SIP: \<username\> @ \<domainname\> (por ejemplo, SIP:Bob@contoso.com).
    
      - Para desviar la llamada a otro número de teléfono, haga clic en **desviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba el número de teléfono con el formato SIP: \<number\> @ \<domainname\> (por ejemplo, SIP:+14255550121@contoso.com).
    
      - Para reenviar la llamada a otro usuario, haga clic en **desviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI del usuario con el formato SIP: \<username\> @ \<domainname\> .
    
      - Para desviar la llamada a otra cola, haga clic en **Desviar a otra cola** y, a continuación, vaya a la cola que desee utilizar.

9.  Para especificar un número máximo de llamadas que puede contener la cola, active la casilla **Permitir desbordamiento de cola** y siga este procedimiento:
    
    1.  En **Número máximo de llamadas**, seleccione el número máximo de llamadas que desea que contenga la cola.
    
    2.  En **Desviar la llamada**, seleccione la llamada que se va a desviar cuando la cola esté llena. **Llamada más reciente** o **Llamada más antigua**.
    
    3.  En **acción de llamada**, seleccione la acción que debe producirse cuando se alcance el umbral de desbordamiento de la siguiente manera:
    
    <!-- end list -->
    
      - Para desconectar la llamada tras el tiempo de espera, haga clic en **Desconectar**.
    
      - Para reenviar la llamada al correo de voz, haga clic en **desviar a correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una dirección de correo de voz con el formato SIP: \<username\> @ \<domainname\> (por ejemplo, SIP:Bob@contoso.com).
    
      - Para desviar la llamada a otro número de teléfono, haga clic en **desviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba el número de teléfono con el formato SIP: \<number\> @ \<domainname\> (por ejemplo, SIP:+14255550121@contoso.com).
    
      - Para reenviar la llamada a otro usuario, haga clic en **desviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI del usuario con el formato SIP: \<username\> @ \<domainname\> .
    
      - Para desviar la llamada a otra cola, haga clic en **Desviar a otra cola** y, a continuación, vaya a la cola que desee utilizar.

10. Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>Para usar Windows PowerShell para crear o modificar una cola

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
    <div>
    

    > [!NOTE]  
    > Si es uno de los administradores del grupo de respuesta delegado de un flujo de trabajo administrado, podrá crear colas y grupos de agentes, y asignar grupos de agentes a las colas.

    
    </div>

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Cree el mensaje que se reproducirá cuando se alcance el umbral de tiempo de espera de la cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por ejemplo:
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Para usar un archivo de audio para el mensaje, ejecute el cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Defina la acción que se llevará a cabo cuando se alcance el umbral de tiempo de espera de la cola y guárdela en una variable. En la línea de comandos, ejecute:
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre las posibles acciones y su sintaxis, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Por ejemplo:
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  Cree el mensaje que se reproducirá cuando se alcance el umbral de desbordamiento de la cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por ejemplo:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Para usar un archivo de audio para el mensaje, ejecute el cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

6.  Defina la acción que se llevará a cabo cuando se alcance el umbral de desbordamiento de la cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre las posibles acciones y su sintaxis, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Por ejemplo:
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  Recupere el nombre del servicio para el servicio del grupo de respuesta y asígnelo a una variable. En la línea de comandos, ejecute:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  Obtiene la identidad del grupo de agentes que se va a asignar a la cola. En la línea de comandos, ejecute:
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre cómo crear el grupo de agentes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A>

    
    </div>

9.  Cree la cola. En la línea de comandos, ejecute:
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    Por ejemplo:
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. Confirme que se ha creado la cola. Realizar
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Consulte también


[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


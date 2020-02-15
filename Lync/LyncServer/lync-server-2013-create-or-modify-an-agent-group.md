---
title: 'Lync Server 2013: crear o modificar un grupo de agentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cd385c5310a5b2df01127e870861fa83231d6f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41994185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Crear o modificar un grupo de agentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

Use uno de los siguientes procedimientos para crear o modificar un grupo de agentes.

<div>


> [!NOTE]  
> Un administrador (por ejemplo, CsVoiceAdministrator) debe habilitar a los usuarios para telefonía IP empresarial y Lync Server antes de que los usuarios se puedan asignar a grupos de agentes. Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear grupos de agentes y usar los grupos de agentes en los flujos de trabajo que administre.



</div>

<div>


> [!IMPORTANT]  
> Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de "Observador de presencia de RGS" y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan "Observador de presencia RGS" en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Para usar el panel de control de Lync Server para crear o modificar un grupo de agentes

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
    <div>
    

    > [!NOTE]  
    > Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear grupos y usarlos en los flujos de trabajo que administre.

    
    </div>

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Grupo**.

4.  En la página **Grupo** , realice una de las siguientes acciones:
    
      - Para crear un nuevo grupo de agentes, haga clic en **nuevo**. En el campo de búsqueda **seleccionar un servicio** , escriba todo o parte del nombre del servicio **ApplicationServer** en el que desea agregar el grupo. En la lista de resultados que aparece, haga clic en el servicio que desea y en **Aceptar**.
    
      - Para modificar un grupo de agentes existente, escriba todo o parte del nombre del grupo de agentes en el campo de búsqueda. En la lista resultante, haga clic en el grupo que desee, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **nombre**, escriba un nombre de identificación para el grupo de agentes.

6.  En **Descripción**, escriba una descripción para el grupo.

7.  En **Directiva de participación**, elija uno de estos procedimientos para configurar el comportamiento de conexión al grupo:
    
      - Seleccione **Informal** para especificar que los agentes del grupo no necesitan iniciar y cerrar sesión en el grupo. Los agentes inician sesión automáticamente en el grupo cuando inician sesión en Lync Server 2013.
    
      - Para especificar que los agentes del grupo deben iniciar y cerrar sesión en el grupo, haga clic en **Formal**. Al seleccionar esta opción, los agentes hacen clic en un elemento de menú de Lync para abrir Internet Explorer y mostrar una consola de página web para iniciar y cerrar sesión en el grupo.

8.  En **Tiempo de alerta (segundos)**, especifique los segundos que va a sonar la llamada de un agente antes de ofrecer la llamada al siguiente agente disponible (el valor predeterminado es 20 segundos).
    
    <div>
    

    > [!IMPORTANT]  
    > La configuración del tiempo de alerta del agente no puede superar los 180 segundos. Si el tiempo de la alerta del agente supera los 180 segundos, la aplicación cliente rechaza la llamada porque el temporizador de la transacción SIP alcanza el tiempo de espera máximo.

    
    </div>

9.  En **Método de enrutamiento**, seleccione un método para enrutar las llamadas a los agentes del grupo, según se muestra a continuación:
    
      - Para ofrecer una llamada nueva primero al agente que ha estado más tiempo inactivo (el más largo ha estado **disponible** o **inactivo** en Lync Server), haga clic en tiempo de **inactividad más largo**.
    
      - Para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo, haga clic en **Enrutamiento en paralelo**. La llamada se envía al primer agente que la acepta.
    
      - Para ofrecer una nueva llamada a un agente cada vez, haga clic en **Round robin**.
    
      - Para ofrecer siempre una llamada a los agentes en el orden en que aparecen en la lista **Agente**, haga clic en **Enrutamiento en serie**.
    
      - Para ofrecer una nueva llamada a todos los agentes que hayan iniciado sesión en Lync Server 2013 y la aplicación de grupo de respuesta al mismo tiempo, independientemente de su presencia actual, haga clic en **operador**. Los usuarios del operador de Lync 2010 que están configurados como agentes pueden ver todas las llamadas en espera y responder a las llamadas en espera en cualquier orden. La llamada se envía al primer agente que la acepta, tras lo cual los otros usuarios del operador de Lync 2010 ya no verán la llamada.

10. En la ficha **Agentes**, especifique el modo en que desea crear la lista de agentes:
    
      - Para usar una lista personalizada de agentes, haga clic en **definir un grupo personalizado de agentes**y, a continuación, siga uno de estos procedimientos:
        
          - Para agregar un usuario al grupo de agentes, haga clic en **seleccionar**y, a continuación, en el campo de búsqueda **seleccionar agentes** , escriba todo o parte del nombre del usuario que desea agregar a este grupo y, a continuación, haga clic en **Buscar**. En la lista de agentes resultante, haga clic en el usuario y, a continuación, haga clic en **Aceptar**.
        
          - Para quitar un usuario del grupo de agentes, en la lista de agentes, haga clic en el usuario que desea quitar y, a continuación, haga clic en **quitar**.
        
          - Para cambiar el orden en el que se ofrecen las llamadas a los agentes en los grupos que usan el enrutamiento Round Robin o el enrutamiento en serie, en la lista de agentes, haga clic en un usuario y, a continuación, haga clic en la flecha arriba o abajo.
    
      - Para usar una lista de distribución de Microsoft Exchange Server como grupo de agentes, haga clic en **usar una lista de distribución de correo electrónico existente**y, a continuación, en dirección de la **lista de distribución**, escriba la dirección de correo electrónico de la lista de distribución (por ejemplo, NetworkSupport@contoso.com).
        
        Si usa una lista de distribución de correo electrónico, se aplican las restricciones siguientes:
        
          - No se pueden seleccionar varias listas de distribución para el grupo de agentes. Cada grupo solo admite una lista de distribución única.
        
          - Si la lista de distribución contiene una o varias listas de distribución, los miembros de las listas de distribución anidadas no se agregan a la lista de agentes.
        
          - Si se selecciona el enrutamiento en serie o Round Robin, el servidor ofrece una llamada entrante al agente apropiado de acuerdo con el método de enrutamiento y según el orden en el que los agentes aparecen en la lista de distribución.
        
          - Si la lista de distribución contiene los usuarios para los que Lync Server 2010 está habilitado, pero Enterprise Voice no está habilitado, se agregará al grupo de agentes como agentes disfuncionales. Asegúrese de que todos los miembros de la lista de distribución tienen habilitada la telefonía IP empresarial para sus cuentas de usuario.
        
        <div>
        

        > [!IMPORTANT]  
        > Si usa una lista de distribución de correo electrónico, las pertenencias ocultas o las listas ocultas pueden ser visibles para el administrador del grupo de respuesta o los usuarios.

        
        </div>
        
        Las pertenencias ocultas o las listas ocultas pueden quedar visibles en los casos siguientes:
        
          - Si se ha configurado una lista de distribución para que la pertenencia esté oculta y el administrador del grupo de respuesta asigna la lista de distribución a la lista de agentes, los usuarios pueden llamar al grupo para averiguar quiénes son los miembros.
        
          - Si se ha configurado una lista de distribución para que quede oculta en la lista global de direcciones de Exchange, es posible que el administrador del grupo de respuesta pueda ver la lista de distribución y asignarla a la lista de agentes si el proceso del grupo de respuesta tiene los derechos de usuario adecuados y permisos, incluso si el administrador no dispone de los permisos y derechos de usuario adecuados.

11. Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Para usar Windows PowerShell para crear o modificar un grupo de agentes

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Use **New-CsRgsAgentGroup** para crear un nuevo grupo de agentes. Use **set-CsRgsAgentGroup** para modificar un grupo de agentes existente. En la línea de comandos, ejecute:
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Por ejemplo:
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > La configuración del tiempo de alerta del agente no puede superar los 180 segundos. Si la hora de la alerta del agente es superior a 180 segundos, la aplicación cliente rechaza la llamada porque el temporizador de la transacción SIP alcanza el tiempo de espera máximo.

    
    </div>

4.  Confirme que se ha creado el grupo de agentes. Realizar
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar un grupo de agentes en Lync Server 2013](lync-server-2013-delete-an-agent-group.md)  


[Administración de grupos de agentes de grupo de respuesta en Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


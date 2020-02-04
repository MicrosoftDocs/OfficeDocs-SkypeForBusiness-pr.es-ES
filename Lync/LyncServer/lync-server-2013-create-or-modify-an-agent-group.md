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
ms.openlocfilehash: 99fed5bf80979ef807f45ce7e5ecdc8e8a16329b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Crear o modificar un grupo de agentes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

Use uno de los procedimientos siguientes para crear o modificar un grupo de agentes.

<div>


> [!NOTE]  
> Un administrador, por ejemplo, CsVoiceAdministrator, debe habilitar los usuarios de telefonía IP y voz empresarial para que los usuarios puedan ser asignados a grupos de agentes. Si es uno de los administradores de grupos de respuesta delegada de un flujo de trabajo administrado, puede crear grupos de agentes y usar los grupos de agentes en los flujos de trabajo que administra.



</div>

<div>


> [!IMPORTANT]  
> Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de "Observador de presencia de RGS" y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan "Observador de presencia RGS" en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Para usar el panel de control de Lync Server para crear o modificar un grupo de agentes

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
    <div>
    

    > [!NOTE]  
    > Si es uno de los administradores del grupo de respuesta delegado de un flujo de trabajo administrado, podrá crear grupos y asignarlos a los flujos de trabajo que administre.

    
    </div>

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, haga clic en **Grupo**.

4.  En la página **Grupo**, haga lo siguiente:
    
      - Para crear un grupo de agente nuevo, haga clic en **Nuevo**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre completo o una parte del servicio **ApplicationServer** para el que desea añadir el grupo. En la lista de servicios resultante, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.
    
      - Para modificar un grupo de agentes existentes, en el campo de búsqueda, escriba el nombre completo o una parte del grupo de agentes. En la lista de resultados, haga clic en el grupo que desee modificar, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En **Nombre**, escriba un nombre de identificación para el grupo de agentes.

6.  En **Descripción**, escriba una descripción para el grupo.

7.  En la **Directiva de participación**, seleccione una de las siguientes opciones para configurar el comportamiento de inicio de sesión en el grupo:
    
      - Seleccione **Informal** para especificar que los agentes del grupo no tienen que iniciar ni cerrar sesión en el grupo. Los agentes inician sesión automáticamente en el grupo al iniciar sesión en Lync Server 2013.
    
      - Seleccione **Formal** para especificar que los agentes del grupo deben iniciar y cerrar sesión en el grupo. Al seleccionar esta opción, los agentes deben hacer clic en un elemento de menú de Lync para abrir Internet Explorer y mostrar una consola de página web para iniciar y cerrar sesión en el grupo.

8.  En **Tiempo de alerta (segundos)**, especifique el número de segundos para llamar a un agente antes de ofrecer la llamada al siguiente agente disponible (el valor predeterminado es de 20 segundos).
    
    <div>
    

    > [!IMPORTANT]  
    > La configuración del tiempo de alerta del agente no puede exceder los 180 segundos o la aplicación del cliente rechazará la llamada debido al temporizador de la transacción SIP que alcanza su tiempo de espera máximo. Para evitarlo, defina el valor del tiempo de alerta en menos de 180 segundos.

    
    </div>

9.  En **Método de enrutamiento**, seleccione el método para las llamadas de enrutamiento a los agentes en el grupo tal como se indica a continuación:
    
      - Para ofrecer una nueva llamada primero al agente que haya estado inactivo el más largo ( **disponible** o **inactivo** en Lync Server el más largo), haga clic en **tiempo de inactividad más largo**.
    
      - Para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo, haga clic en **En paralelo**. La llamada se envía al primer agente que la acepte.
    
      - Para ofrecer una nueva llamada a cada agente por turnos, haga clic en **Por turnos**.
    
      - Para ofrecer una nueva llamada a los agentes según el orden en el que aparecen en la lista de **Agente**, haga clic en **En serie**.
    
      - Para ofrecer una nueva llamada a todos los agentes que han iniciado sesión en Lync Server 2013 y la aplicación de grupo de respuesta al mismo tiempo, independientemente de su presencia actual, haga clic en **operador**. El operador de Lync 2010 los usuarios que están configurados como agentes pueden ver todas las llamadas que están esperando y responder llamadas en espera en cualquier orden. La llamada se envía al primer agente que la acepta, después de la cual los otros usuarios del operador de 2010 de Lync ya no verán la llamada.

10. En **Agentes**, especifique cómo desea crear su lista de agentes:
    
      - Para usar una lista personalizada de agentes, haga clic en **Definir un grupo personalizado de agentes** y, a continuación, realice uno de estos procedimientos:
        
          - Para agregar un usuario al grupo de agentes, haga clic en **Seleccionar** y, a continuación, en el campo de búsqueda **Seleccionar agentes**, escriba el nombre completo o una parte del usuario que desea agregar a este grupo y haga clic en **Buscar**. En la lista de resultados, haga clic en el usuario y, a continuación, en **Aceptar**.
        
          - Para quitar a un usuario de un grupo de agentes, en la lista de agentes, seleccione el usuario que desea quitar y haga clic en **Quitar**.
        
          - Para cambiar el orden en el que se ofrecen llamadas a los agentes de los grupos que usan el enrutamiento por turnos (round robin) o en serie, en la lista de agentes, haga clic en un usuario y, a continuación, seleccione la flecha hacia arriba o hacia abajo.
    
      - Para utilizar una lista de distribución de Microsoft Exchange Server, haga clic en **Usar una lista de distribución de correo electrónico existente** y, a continuación, en **Dirección de lista de distribución**, escriba la dirección de correo electrónico de la lista de distribución (por ejemplo, NetworkSupport@contoso.com).
        
        Si usa una lista de distribución de correo electrónico, se aplican las restricciones siguientes:
        
          - No puede seleccionar varias listas de distribución para el grupo de agentes. Cada grupo admite solo una única lista de distribución.
        
          - Si la lista de distribución contiene una o más listas de distribución, los miembros de las listas de distribución anidadas no se agregan a la lista de agentes.
        
          - Si se selecciona un enrutamiento en serie y por turnos o round robin, el servidor ofrece una llamada de entrada al agente apropiado de acuerdo con el método de enrutamiento y de acuerdo con el orden en el que los agentes aparecen en la lista de distribución.
        
          - Si la lista de distribución contiene usuarios para los que Lync Server 2010 está habilitado, pero la telefonía IP empresarial no, se agregarán al grupo de agentes como agentes disfuncionales. Asegúrese de que todos los miembros de la lista de distribución tengan la Telefonía IP empresarial habilitada en sus cuentas de usuario.
        
        <div>
        

        > [!IMPORTANT]  
        > Si usa una lista de distribución de correo electrónico, las suscripciones ocultas o las listas ocultas podrían hacerse visibles para el administrador del grupo de respuesta o los usuarios.

        
        </div>
        
        Los miembros ocultos o las listas ocultas se pueden convertir en visibles de la siguiente manera:
        
          - Si una lista de distribución se configuró de modo que la pertenencia está oculta y el administrador del grupo de respuesta asigna la lista de distribución a la lista de agentes, los usuarios pueden llamar al grupo para averiguar quiénes son los miembros.
        
          - Si se ha configurado una lista de distribución de modo que se oculte en la lista global de direcciones de Exchange, es posible que el administrador del grupo de respuesta pueda ver la lista de distribución y asignarla a la lista de agentes si el proceso de grupo de respuesta tiene los derechos de usuario apropiados y permisos, incluso si el administrador no tiene los derechos de usuario y los permisos apropiados.

11. Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Para usar Windows PowerShell para crear o modificar un grupo de agentes

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Use **New-CsRgsAgentGroup** para crear un grupo de agentes nuevo. Use **Set-CsRgsAgentGroup** para modificar un grupo de agentes existente. En la línea de comandos, ejecute:
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Por ejemplo:
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > La configuración del tiempo de alerta del agente no puede exceder los 180 segundos o la aplicación del cliente rechazará la llamada debido al temporizador de la transacción SIP que alcanza su tiempo de espera máximo.

    
    </div>

4.  Confirme que el grupo de agentes se ha creado. Ejecute:
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar un grupo de agentes en Lync Server 2013](lync-server-2013-delete-an-agent-group.md)  


[Administrar grupos de agentes de grupo de respuesta en Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Nuevo: CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


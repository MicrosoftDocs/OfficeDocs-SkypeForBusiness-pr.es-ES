---
title: 'Lync Server 2013: Crear o modificar un grupo de agentes'
TOCTitle: Crear o modificar un grupo de agentes
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48277139
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar un grupo de agentes en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-07_

Use uno de los procedimientos siguientes para crear o modificar un grupo de agentes.


> [!NOTE]
> Un administrador (por ejemplo, CsVoiceAdministrator) debe habilitar a los usuarios para Telefonía IP empresarial y Lync Server para poder asignar a los usuarios a los grupos de agentes. Si es usted uno de los administradores de grupos de respuesta delegados para un flujo de trabajo administrado, puede crear grupos de agentes y usarlos en los flujos de trabajo que usted administra.



> [!IMPORTANT]  
> Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de &quot;Observador de presencia de RGS&quot; y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan &quot;Observador de presencia RGS&quot; en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados.



## Uso de Panel de control de Lync Server para crear o modificar un grupo de agentes

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    

    > [!NOTE]
    > Si es uno de los administradores del grupo de respuesta delegado de un flujo de trabajo administrado, podrá crear grupos y asignarlos a los flujos de trabajo que administre.



2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, haga clic en **Grupo**.

4.  En la página **Grupo**, haga lo siguiente:
    
      - Para crear un grupo de agente nuevo, haga clic en **Nuevo**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre completo o una parte del servicio **ApplicationServer** para el que desea añadir el grupo. En la lista de servicios resultante, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.
    
      - Para modificar un grupo de agentes existentes, en el campo de búsqueda, escriba el nombre completo o una parte del grupo de agentes. En la lista de resultados, haga clic en el grupo que desee modificar, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En **Nombre**, escriba un nombre de identificación para el grupo de agentes.

6.  En **Descripción**, escriba una descripción para el grupo.

7.  En la **Directiva de participación**, seleccione una de las siguientes opciones para configurar el comportamiento de inicio de sesión en el grupo:
    
      - Seleccione **Informal** para especificar que los agentes del grupo no tienen que iniciar ni cerrar sesión en el grupo. Los agentes inician sesión automáticamente en el grupo cuando inician sesión en Lync Server 2013.
    
      - Seleccione **Formal** para especificar que los agentes del grupo deben iniciar y cerrar sesión en el grupo. Cuando se selecciona esta opción, los agentes hacen clic en un elemento del menú en Lync para abrir Internet Explorer y mostrar una consola de página web para el inicio y el cierre de sesión en el grupo.

8.  En **Tiempo de alerta (segundos)**, especifique el número de segundos para llamar a un agente antes de ofrecer la llamada al siguiente agente disponible (el valor predeterminado es de 20 segundos).
    
    > [!IMPORTANT]  
    > La configuración del tiempo de alerta del agente no puede exceder los 180 segundos o la aplicación del cliente rechazará la llamada debido al temporizador de la transacción SIP que alcanza su tiempo de espera máximo. Para evitarlo, defina el valor del tiempo de alerta en menos de 180 segundos.
    


9.  En **Método de enrutamiento**, seleccione el método para las llamadas de enrutamiento a los agentes en el grupo tal como se indica a continuación:
    
      - Para ofrecer una llamada nueva primero al agente que ha estado inactivo durante más tiempo (ha tenido una presencia de **Disponible** o **Inactivo** en Lync Server durante más tiempo), haga clic en **Máxima inactividad**.
    
      - Para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo, haga clic en **En paralelo**. La llamada se envía al primer agente que la acepte.
    
      - Para ofrecer una nueva llamada a cada agente por turnos, haga clic en **Por turnos**.
    
      - Para ofrecer una nueva llamada a los agentes según el orden en el que aparecen en la lista de **Agentes**, haga clic en **En serie**.
    
      - Para ofrecer una llamada nueva al mismo tiempo a todos los agentes que hayan iniciado sesión en Lync Server 2013 y Aplicación de grupo de respuesta, independientemente de su presencia en esos momentos, haga clic en **Operador**. Los usuarios de Operador de Lync 2010 que están configurados como agentes pueden ver todas las llamadas que están en espera y atenderlas en el orden que deseen. La llamada se envía al primer agente que la acepta, después de lo cual, el resto de usuarios de Operador de Lync 2010 dejarán de ver la llamada.

10. En **Agentes**, especifique cómo desea crear su lista de agentes:
    
      - Para utilizar una lista personalizada de agentes, haga clic en **Definir un grupo personalizado de agentes** y, a continuación, realice uno de estos procedimientos:
        
          - Para agregar un usuario al grupo de agentes, haga clic en **Seleccionar** y, a continuación, en el campo de búsqueda **Seleccionar agentes**, escriba el nombre completo o una parte del usuario que desea agregar a este grupo y haga clic en **Buscar**. En la lista de resultados, haga clic en el usuario y, a continuación, en **Aceptar**.
        
          - Para quitar a un usuario de un grupo de agentes, en la lista de agentes, seleccione el usuario que desea quitar y haga clic en **Quitar**.
        
          - Para cambiar el orden en el que se ofrecen llamadas a los agentes de los grupos que usan el enrutamiento por turnos (round robin) o en serie, en la lista de agentes, haga clic en un usuario y, a continuación, seleccione la flecha hacia arriba o hacia abajo.
    
      - Para utilizar una lista de distribución de Microsoft Exchange Server, haga clic en **Utilizar una lista de distribución de correo electrónico existente** y, a continuación, en **Dirección de lista de distribución**, escriba la dirección de correo electrónico de la lista de distribución (por ejemplo, NetworkSupport@contoso.com).
        
        Si usa una lista de distribución de correo electrónico, se aplican las restricciones siguientes:
        
          - No puede seleccionar varias listas de distribución para el grupo de agentes. Cada grupo admite solo una única lista de distribución.
        
          - Si la lista de distribución contiene una o más listas de distribución, los miembros de las listas de distribución anidadas no se agregan a la lista de agentes.
        
          - Si se selecciona un enrutamiento en serie y por turnos o round robin, el servidor ofrece una llamada de entrada al agente apropiado de acuerdo con el método de enrutamiento y de acuerdo con el orden en el que los agentes aparecen en la lista de distribución.
        
          - Si la lista de distribución contiene usuarios para los que Lync Server 2010 está habilitado, pero la telefonía IP empresarial no, se agregarán al grupo de agentes como agentes disfuncionales. Asegúrese de que todos los miembros de la lista de distribución tengan la Telefonía IP empresarial habilitada en sus cuentas de usuario.
        
        > [!IMPORTANT]  
        > Si utiliza una lista de distribución de correo electrónico, los miembros ocultos o las listas ocultas se convertirán en visibles para el administrador o los usuarios de Grupo de respuesta.
        
        
        Los miembros ocultos o las listas ocultas se pueden convertir en visibles de la siguiente manera:
        
          - Si una lista de distribución se configuró de modo que el miembro quede oculto y el administrador de Grupo de respuesta asigna la lista de distribución a la lista de agentes, los usuarios pueden llamar al grupo para iguar quiénes son los miembros.
        
          - Si se configuró una lista de distribución de modo que quede oculta en la lista de direcciones globales de Exchange, el administrador del Grupo de respuesta puede ver la lista de distribución y asignarla a la lista de agentes si el proceso de Grupo de respuesta tiene los derechos y los permisos de usuario adecuados, incluso si el administrador no dispone de los derechos y los permisos de usuario adecuados.

11. Haga clic en **Confirmar**.

## Uso de Windows PowerShell para crear o modificar un grupo de agentes

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Use **New-CsRgsAgentGroup** para crear un grupo de agentes nuevo. Use **Set-CsRgsAgentGroup** para modificar un grupo de agentes existente. En la línea de comandos, ejecute:
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Por ejemplo:
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    > [!IMPORTANT]  
    > La configuración del tiempo de alerta del agente no puede exceder los 180 segundos o la aplicación del cliente rechazará la llamada debido al temporizador de la transacción SIP que alcanza su tiempo de espera máximo.
    


4.  Confirme que el grupo de agentes se ha creado. Ejecute:
    
        Get-CsRgsAgentGroup -Name "Help Desk"

## Vea también

#### Tareas

[Eliminar un grupo de agentes de Lync Server 2013](lync-server-2013-delete-an-agent-group.md)  

#### Otros recursos

[Administración de grupos de agente de grupos de respuesta en Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)


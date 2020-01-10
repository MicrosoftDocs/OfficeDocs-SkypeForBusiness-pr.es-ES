---
title: Crear o modificar un grupo de agentes en Skype empresarial
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
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Crear o modificar un grupo de agentes en el grupo respuesta de Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: a919c1a25f3f4aa5a2d8648d782ea329f1e70d60
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001690"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Crear o modificar un grupo de agentes en Skype empresarial
 
Crear o modificar un grupo de agentes en el grupo respuesta de Skype empresarial Server Enterprise Voice.
  
Cuando se crea un grupo de agentes, se seleccionan los agentes que se asignan al grupo y se especifica la configuración de grupo adicional, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo. 
  
Un agente que debe iniciar y cerrar sesión en el grupo, lo cual difiere de la sesión o de Skype empresarial, se denomina agente formal. Los agentes formales deben iniciar sesión en el grupo para poder recibir llamadas enrutadas al grupo. Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada. Agentes formales inicie y cierre sesión en sus grupos haciendo clic en un elemento de menú de Skype empresarial para abrir el explorador de Internet de Windows Internet Explorer y mostrar una consola de página web.
  
Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de  agente informal. Los agentes informales inician sesión automáticamente en el grupo cuando inician sesión en Skype empresarial y no pueden cerrar sesión en el grupo.
  
Solo los usuarios locales pueden ser agentes. Si un agente se mueve de local a conectado, las llamadas a grupos de respuesta no se dirigirán a ese agente.
  
Use uno de los procedimientos siguientes para crear o modificar un grupo de agentes.
  
> [!IMPORTANT]
> Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de "Observador de presencia de RGS" y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan "Observador de presencia RGS" en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>Para usar el panel de control de Skype empresarial Server para crear o modificar un grupo de agentes

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
    > [!NOTE]
    > Si es uno de los administradores del grupo de respuesta delegado de un flujo de trabajo administrado, podrá crear grupos y asignarlos a los flujos de trabajo que administre. 
  
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, haga clic en **Grupo**.
    
4. En la página **Grupo**, haga lo siguiente:
    
   - Para crear un grupo de agente nuevo, haga clic en **Nuevo**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre completo o una parte del servicio **ApplicationServer** para el que desea añadir el grupo. En la lista de servicios resultante, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.
    
   - Para modificar un grupo de agentes existentes, en el campo de búsqueda, escriba el nombre completo o una parte del grupo de agentes. En la lista de resultados, haga clic en el grupo que desee modificar, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
5. En **Nombre**, escriba un nombre de identificación para el grupo de agentes.
    
6. En **Descripción**, escriba una descripción para el grupo.
    
7. En la **Directiva de participación**, seleccione una de las siguientes opciones para configurar el comportamiento de inicio de sesión en el grupo:
    
   - Seleccione **Informal** para especificar que los agentes del grupo no tienen que iniciar ni cerrar sesión en el grupo. Los agentes inician sesión automáticamente en el grupo cuando inician sesión en Skype empresarial.
    
   - Seleccione **Formal** para especificar que los agentes del grupo deben iniciar y cerrar sesión en el grupo. Al seleccionar esta opción, los agentes hace clic en un elemento de menú de Skype empresarial para abrir Internet Explorer y mostrar una consola de página web para iniciar y cerrar sesión en el grupo.
    
8. En **Tiempo de alerta (segundos)**, especifique el número de segundos para llamar a un agente antes de ofrecer la llamada al siguiente agente disponible (el valor predeterminado es de 20 segundos).
    
    > [!IMPORTANT]
    > La configuración del tiempo de alerta del agente no puede exceder los 180 segundos o la aplicación del cliente rechazará la llamada debido al temporizador de la transacción SIP que alcanza su tiempo de espera máximo. Para evitarlo, defina el valor del tiempo de alerta en menos de 180 segundos. 
  
9. En **Método de enrutamiento**, seleccione el método para las llamadas de enrutamiento a los agentes en el grupo tal como se indica a continuación:
    
   - Para ofrecer una nueva llamada primero al agente que haya estado inactivo el más largo ( **disponible** o **inactivo** en Skype para empresas), haga clic en **tiempo de inactividad más largo**. 
    
   - Para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo, haga clic en **En paralelo**. La llamada se envía al primer agente que la acepte.
    
   - Para ofrecer una nueva llamada a cada agente por turnos, haga clic en **Por turnos**. 
    
   - Para ofrecer una nueva llamada a los agentes según el orden en el que aparecen en la lista de **Agente**, haga clic en **En serie**. 
    
   - Para ofrecer una nueva llamada a todos los agentes que han iniciado sesión en Skype empresarial y la aplicación de grupo de respuesta al mismo tiempo, independientemente de su presencia actual, haga clic en **operador**. Los usuarios configurados como agentes pueden ver todas las llamadas y responder a las llamadas en espera en cualquier orden. La llamada se envía al primer agente que la acepta, y a partir de ese momento los demás agentes ya no pueden ver la llamada.
    
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
    
    > [!IMPORTANT]
    > Si usa una lista de distribución de correo electrónico, las suscripciones ocultas o las listas ocultas podrían hacerse visibles para el administrador del grupo de respuesta o los usuarios. 
  
    Los miembros ocultos o las listas ocultas se pueden convertir en visibles de la siguiente manera:
    
     - Si una lista de distribución se configuró de modo que la pertenencia está oculta y el administrador del grupo de respuesta asigna la lista de distribución a la lista de agentes, los usuarios pueden llamar al grupo para averiguar quiénes son los miembros. 
    
     - Si se ha configurado una lista de distribución de modo que se oculte en la lista global de direcciones de Exchange, es posible que el administrador del grupo de respuesta pueda ver la lista de distribución y asignarla a la lista de agentes si el proceso de grupo de respuesta tiene los derechos de usuario apropiados y permisos, incluso si el administrador no tiene los derechos de usuario y los permisos apropiados.
    
11. Haga clic en **Confirmar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>Para usar el shell de administración de Skype empresarial para crear o modificar un grupo de agentes

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Use **New-CsRgsAgentGroup** para crear un grupo de agentes nuevo. Use **Set-CsRgsAgentGroup** para modificar un grupo de agentes existente. En la línea de comandos, ejecute:
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Por ejemplo:
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > La configuración del tiempo de alerta del agente no puede exceder los 180 segundos o la aplicación del cliente rechazará la llamada debido al temporizador de la transacción SIP que alcanza su tiempo de espera máximo. 
  
4. Confirme que el grupo de agentes se ha creado. Ejecute:
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Vea también

[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[Nuevo: CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)

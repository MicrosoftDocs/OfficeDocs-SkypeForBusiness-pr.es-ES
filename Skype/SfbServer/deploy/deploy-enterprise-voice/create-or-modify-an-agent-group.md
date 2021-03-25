---
title: Crear o modificar un grupo de agentes en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Cree o modifique un grupo de agentes en grupo de respuesta, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 0c0e7d54008ba6affa2bae5bd3228c93e430a114
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105816"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Crear o modificar un grupo de agentes en Skype Empresarial
 
Cree o modifique un grupo de agentes en grupo de respuesta, en Skype Empresarial Server Telefonía IP empresarial.
  
Cuando se crea un grupo de agentes, se seleccionan los agentes que se asignan al grupo y se especifica la configuración de grupo adicional, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo. 
  
Un agente que debe iniciar y cerrar sesión en el grupo, que es diferente de iniciar o salir de Skype Empresarial, se denomina agente formal. Los agentes formales deben iniciar sesión en el grupo para poder recibir llamadas enrutadas al grupo. Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada. Los agentes formales inician y cierran sesión en sus grupos haciendo clic en un elemento de menú de Skype Empresarial para abrir el explorador de Internet de Windows Internet Explorer y mostrar una consola de página web.
  
Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de agente informal. Los agentes informales inician sesión automáticamente en el grupo cuando inician sesión en Skype Empresarial y no pueden cerrar sesión en el grupo.
  
Solo los usuarios locales pueden ser agentes. Si un agente deja de ser local para estar en línea, las llamadas al grupo de respuesta no se enrutarán a dicho agente.
  
Use uno de los siguientes procedimientos para crear o modificar un grupo de agentes.
  
> [!IMPORTANT]
> Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de "Observador de presencia de RGS" y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan "Observador de presencia RGS" en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>Para usar el Panel de control de Skype Empresarial Server para crear o modificar un grupo de agentes

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
    > [!NOTE]
    > Si es uno de los administradores de grupos de respuesta delegados para un flujo de trabajo administrado, puede crear grupos y usarlos en los flujos de trabajo que administre. 
  
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Grupo**.
    
4. En la **página** Grupo, realice una de las siguientes acciones:
    
   - Para crear un nuevo grupo de agentes, haga clic en **Nuevo**. En el **campo Seleccionar un servicio** de búsqueda, escriba todo o parte del nombre del servicio **ApplicationServer** donde desea agregar el grupo. En la lista de resultados que aparece, haga clic en el servicio que desea y en **Aceptar**.
    
   - Para modificar un grupo de agentes existente, escriba todo o parte del nombre del grupo de agentes en el campo de búsqueda. En la lista resultante, haga clic en el grupo que desee, haga clic **en Editar** y, a continuación, haga clic en **Mostrar detalles.**
    
5. En **Nombre**, escriba un nombre de identificación para el grupo de agentes.
    
6. En **Descripción**, escriba una descripción para el grupo.
    
7. En **Directiva de participación**, elija uno de estos procedimientos para configurar el comportamiento de conexión al grupo:
    
   - Seleccione **Informal** para especificar que los agentes del grupo no necesitan iniciar y cerrar sesión en el grupo. Los agentes inician sesión automáticamente en el grupo cuando inician sesión en Skype Empresarial.
    
   - Para especificar que los agentes del grupo deben iniciar y cerrar sesión en el grupo, haga clic en **Formal**. Al seleccionar esta opción, los agentes hacen clic en un elemento de menú de Skype Empresarial para abrir Internet Explorer y mostrar una consola de página web para iniciar y salir del grupo.
    
8. En **Tiempo de alerta (segundos)**, especifique los segundos que va a sonar la llamada de un agente antes de ofrecer la llamada al siguiente agente disponible (el valor predeterminado es 20 segundos).
    
    > [!IMPORTANT]
    > La configuración de hora de alerta del agente no puede superar los 180 segundos. Si el tiempo de alerta del agente supera los 180 segundos, la aplicación cliente rechaza la llamada porque el temporizador de transacción SIP alcanza su tiempo máximo de espera. 
  
9. En **Método de enrutamiento**, seleccione un método para enrutar las llamadas a los agentes del grupo, según se muestra a continuación:
    
   - Para ofrecer una nueva llamada primero al agente que ha estado inactivo  más tiempo (ha tenido una presencia de **Disponible** o Inactivo en Skype Empresarial el más largo), haga clic en Inactivo **más largo.** 
    
   - Para ofrecer una nueva llamada a todos los agentes disponibles al mismo tiempo, haga clic en **Enrutamiento en paralelo**. La llamada se envía al primer agente que la acepta.
    
   - Para ofrecer una nueva llamada a un agente cada vez, haga clic en **Round robin**. 
    
   - Para ofrecer siempre una llamada a los agentes en el orden en que aparecen en la lista **Agente**, haga clic en **Enrutamiento en serie**. 
    
   - Para ofrecer una nueva llamada a todos los agentes que han iniciado sesión en Skype Empresarial y la aplicación grupo de respuesta al mismo tiempo, independientemente de su presencia actual, haga clic en **Operador**. Los usuarios configurados como agentes pueden ver todas las llamadas que están en espera y responder llamadas en espera en cualquier orden. La llamada se envía al primer agente que la acepta, después de lo cual los demás agentes ya no ven la llamada.
    
10. En la ficha **Agentes**, especifique el modo en que desea crear la lista de agentes:
    
    - Para usar una lista personalizada de agentes, haga clic **en Definir un grupo** personalizado de agentes y realice una de las siguientes acciones:
    
    - Para agregar un usuario al grupo de agentes,  haga clic en **Seleccionar** y, a continuación, en el campo de búsqueda Seleccionar agentes, escriba todo o parte del nombre del usuario que desea agregar a este grupo y, a continuación, haga clic en **Buscar**. En la lista resultante de agentes, haga clic en el usuario y, a continuación, haga clic en **Aceptar**.
    
    - Para quitar un usuario del grupo de agentes, en la lista de agentes, haga clic en el usuario que desea quitar y, a continuación, haga clic en **Quitar**.
    
    - Para cambiar el orden en que se ofrecen llamadas a los agentes en grupos que usan enrutamiento por turnos o enrutamiento en serie, en la lista de agentes, haga clic en un usuario y, a continuación, haga clic en la flecha arriba o abajo. 
    
    - Para usar una lista de distribución Microsoft Exchange Server como grupo de agentes, haga clic en Usar una lista de distribución de correo electrónico existente y, a continuación, en Dirección de lista de **distribución,** escriba la dirección de correo electrónico de la lista de distribución (por ejemplo, NetworkSupport@contoso.com).
    
      Si usa una lista de distribución de correo electrónico, se aplican las restricciones siguientes:
    
      - No se pueden seleccionar varias listas de distribución para el grupo de agentes. Cada grupo solo admite una lista de distribución única.
    
      - Si la lista de distribución contiene una o varias listas de distribución, los miembros de las listas de distribución anidadas no se agregan a la lista de agentes.
    
      - Si se selecciona el enrutamiento por turnos o serie, el servidor ofrece una llamada entrante al agente adecuado de acuerdo con el método de enrutamiento y según el orden en que se enumeran los agentes en la lista de distribución.
    
      - Si la lista de distribución contiene usuarios para los que Lync Server 2010 está habilitado pero Telefonía IP empresarial no está habilitado, se agregarán al grupo de agentes como agentes disfuncionales. Asegúrese de que todos los miembros de la lista de distribución Telefonía IP empresarial habilitados para sus cuentas de usuario.
    
    > [!IMPORTANT]
    > Si usa una lista de distribución de correo electrónico, las pertenencias ocultas o las listas ocultas pueden ser visibles para el administrador o los usuarios del grupo de respuesta. 
  
    Las pertenencias ocultas o las listas ocultas pueden quedar visibles en los casos siguientes:
    
     - Si se configuró una lista de distribución para que la pertenencia esté oculta y el administrador del grupo de respuesta asigne la lista de distribución a la lista de agentes, los usuarios pueden llamar al grupo para averiguar quiénes son los miembros. 
    
     - Si se configuró una lista de distribución para que esté oculta en la lista global de direcciones de Exchange, es posible que el administrador del grupo de respuesta pueda ver la lista de distribución y asignarla a la lista de agentes si el proceso del grupo de respuesta tiene los derechos y permisos de usuario adecuados, incluso si el administrador no tiene los permisos y derechos de usuario adecuados.
    
11. Haga clic en **Confirmar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>Para usar el Shell de administración de Skype Empresarial Server para crear o modificar un grupo de agentes

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
3. Use **New-CsRgsAgentGroup para** crear un nuevo grupo de agentes. Use **Set-CsRgsAgentGroup para** modificar un grupo de agentes existente. En la línea de comandos, ejecute:
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Por ejemplo:
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > La configuración de hora de alerta del agente no puede superar los 180 segundos. Si el tiempo de alerta del agente es superior a 180 segundos, la aplicación cliente rechaza la llamada porque el temporizador de transacción SIP alcanza su tiempo máximo de espera. 
  
4. Confirme que se ha creado el grupo de agentes. Ejecute: 
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Ver también

[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
---
title: Eliminar un grupo de agentes de Lync Server 2013
TOCTitle: Eliminar un grupo de agentes de Lync Server 2013
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182597(v=OCS.15)
ms:contentKeyID: 48276932
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar un grupo de agentes de Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Use uno de los procedimientos siguientes para eliminar un grupo de agentes.

## Siga estos pasos para eliminar un grupo de agentes con Panel de control de Lync Server.

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y después en **Grupo**.

4.  En la página **Grupos de respuesta**, escriba el nombre completo (o parte del nombre) del grupo de agentes que desee eliminar en el campo de búsqueda.

5.  En la lista de resultados de la búsqueda, haga clic en el grupo que desee eliminar, haga clic en **Editar** y después en **Eliminar**.

6.  Haga clic en **Aceptar**.

## Para eliminar un grupo de agentes

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute:
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    Por ejemplo:
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

## Vea también

#### Tareas

[Crear o modificar un grupo de agentes en Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)  

#### Otros recursos

[Remove-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)


---
title: 'Lync Server 2013: abrir las herramientas administrativas de Lync Server'
description: 'Lync Server 2013: abrir las herramientas administrativas de Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01cf0dc0c17686e2b1c7bee17bdc383ab6247909
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544766"
---
# <a name="open-lync-server-2013-administrative-tools"></a>Abrir las herramientas administrativas de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-28_

Puede usar los procedimientos de este tema para abrir las herramientas administrativas para implementar, configurar o solucionar los problemas de la topología de Lync Server 2013.

  - Asistente para implementación

  - Topology Builder

  - Panel de control de Lync Server

  - Shell de administración de Lync Server

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>Asistente para implementación

Use el siguiente procedimiento para iniciar el Asistente para la implementación localmente para agregar o quitar archivos de componentes de Lync Server 2013.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Para iniciar el Asistente para la implementación de Lync Server 2013

1.  Inicie sesión en el equipo en el que el asistente para la implementación de Lync Server esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **Asistente para la implementación de Lync Server**.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>Topology Builder

Use el siguiente procedimiento para abrir el generador de topologías y definir los servidores que desea implementar en su topología de 2013 de Lync Server.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Para abrir el generador de topologías de Lync Server 2013 para diseñar la topología

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para leer, publicar o habilitar una topología, que es necesaria para instalar Lync Server 2013 en un servidor, debe usar una cuenta que sea miembro del grupo administradores de dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control total (es decir, , leer, escribir y modificar) en el recurso compartido de archivos que se va a usar para el almacén de archivos de archivado, de modo que el generador de topologías pueda configurar la lista de control de acceso discrecional (DACL) necesaria o una cuenta con derechos de usuario equivalentes.

    
    </div>

2.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Panel de control de Lync Server 2013

Use uno de los siguientes procedimientos para abrir el panel de control de Lync Server 2013 para administrar la configuración de servidores, usuarios, clientes y dispositivos en su entorno.

<div>


> [!NOTE]  
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el panel de control de Lync Server 2013. Puede usar otros roles para iniciar sesión en el panel de control de Lync Server 2013 para realizar tareas de administración específicas, en función de la tarea que necesite realizar. Por ejemplo, puede usar rol csarchivingadministrator para administrar el archivado en el panel de control de Lync Server 2013. Para obtener más información sobre los roles, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación referente a la planeación. Para obtener información sobre las funciones que puede usar para realizar una tarea específica, consulte la documentación de la tarea.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>Para abrir el panel de control de Lync Server 2013 desde cualquier equipo dentro del firewall de la organización

1.  Desde una cuenta de usuario asignada al rol CsAdministrator o a otro rol que tenga los derechos y permisos de usuario adecuados para la tarea que se va a realizar, inicie sesión en cualquier equipo en la implementación interna con una resolución de pantalla mínima de 1024 x 768.
    
    <div>
    

    > [!IMPORTANT]  
    > Si ha configurado una dirección URL sencilla de administración, puede tener acceso al panel de control de Lync Server 2013 desde un explorador de Internet que se ejecute en cualquier equipo del firewall de la organización. Para obtener más información sobre cómo configurar la dirección URL sencilla de administración, consulte <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync server 2013</A> en la documentación de planeación y <A href="lync-server-2013-edit-or-configure-simple-urls.md">Editar o configurar direcciones URL sencillas en Lync Server 2013</A> en la documentación sobre implementación.

    
    </div>

2.  Abra una ventana del explorador y escriba la dirección URL de administración configurada para la organización.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Para abrir el panel de control de Lync Server 2013 en un equipo que ejecuta Lync Server 2013

1.  Desde una cuenta de usuario que sea miembro de la función CsAdministrator o de otro rol que tenga los derechos y permisos de usuario adecuados para la tarea que se va a realizar, inicie sesión en un equipo en el que tenga instalado Lync Server 2013 o, como mínimo, en las herramientas administrativas de Lync Server 2013. Para configurar las opciones, el equipo debe tener una resolución de pantalla mínima de 1024 x 768.

2.  Inicie el panel de control 2013 de Lync Server: haga clic en **Inicio**, **todos los programas**, **herramientas administrativas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Panel de control de Lync Server 2013**.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Shell de administración de Lync Server 2013

Use el siguiente procedimiento para abrir Shell de administración de Lync Server 2013 para administrar servidores, usuarios, clientes y dispositivos en su entorno mediante la línea de comandos.

<div>


> [!NOTE]  
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el shell de administración de Lync Server 2013. Puede iniciar sesión con otras funciones para realizar tareas específicas de administración, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para ejecutar cmdlets relacionados con las administración de archivado. Para obtener más información sobre los roles, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación referente a la planeación. Para obtener información sobre las funciones que puede usar para ejecutar un cmdlet específico, consulte la documentación del cmdlet.<BR>También puede ejecutar ciertos cmdlets mediante una cuenta de usuario en los grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins, o RTCUniversalReadOnlyAdmins, según el cmdlet.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Para abrir el shell de administración de Lync Server 2013

  - Si abre una ventana de Windows PowerShell en lugar del shell de administración de Lync Server 2013, de forma predeterminada, no podrá ejecutar los cmdlets de Lync Server 2013. Para ejecutar los cmdlets de Lync Server 2013 desde dentro de Windows PowerShell, escriba lo siguiente en el símbolo del sistema de Windows PowerShell:
    
    `Import-Module Lync`

  - Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

</div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Instalación de las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)  


[Herramientas administrativas de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: abrir las herramientas administrativas de Lync Server'
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
ms.openlocfilehash: 3f3c1b2eec210b22bc45a27c9635507c7ad83553
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Abrir las herramientas administrativas de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-28_

Puede usar los procedimientos de este tema para abrir herramientas administrativas para implementar, configurar o solucionar problemas de su topología de Lync Server 2013.

  - Asistente para la implementación

  - Generador de topologías

  - Panel de control de Lync Server

  - Shell de administración de Communications Server

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>Asistente para la implementación

Use el siguiente procedimiento para iniciar el Asistente para la implementación de forma local y agregar o quitar archivos de componentes de Lync Server 2013.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Para iniciar el Asistente para la implementación de Lync Server 2013

1.  Inicie sesión en el equipo donde está instalado el Asistente para la implementación de Lync Server como miembro del grupo administradores de dominio y el grupo RTCUniversalServerAdmins.

2.  Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Asistente de implementación de Lync Server**.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>Generador de topologías

Use el siguiente procedimiento para abrir el generador de topologías y definir los servidores que desea implementar en su topología de Lync Server 2013.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Para abrir el generador de topología de Lync Server 2013 y diseñar la topología

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para leer, publicar o habilitar una topología, lo cual es necesario para instalar Lync Server 2013 en un servidor, debe usar una cuenta que sea miembro del grupo de administradores de dominio y la RTCUniv ersalServerAdmins Group, y que tiene permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que va a usar para el almacén de archivos de almacenamiento para que Topology Builder pueda configurar la lista de control de acceso discrecional (DACL) requerida, o una cuenta con derechos de usuario equivalentes.

    
    </div>

2.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Panel de control de Lync Server 2013

Use uno de los procedimientos siguientes para abrir el panel de control de Lync Server 2013 para administrar la configuración de servidores, usuarios, clientes y dispositivos en su entorno.

<div>


> [!NOTE]  
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el panel de control de Lync Server 2013. Puede usar otros roles para iniciar sesión en el panel de control de Lync Server 2013 para realizar tareas de administración específicas, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para administrar el archivado en el panel de control de Lync Server 2013. Para obtener más información sobre los roles, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación. Para obtener más información sobre los roles que puede usar para realizar una tarea específica, consulte la documentación de la tarea.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>Para abrir el panel de control de Lync Server 2013 desde cualquier equipo del firewall de la organización

1.  Desde una cuenta de usuario que tenga asignada la función CsAdministrator u otro rol que tenga los permisos y permisos de usuario adecuados para la tarea que se va a realizar, inicie sesión en cualquier equipo de la implementación interna con una resolución de pantalla mínima de 1024 x 768.
    
    <div>
    

    > [!IMPORTANT]  
    > Si ha configurado un localizador de recursos uniforme (URL) de administración, puede obtener acceso al panel de control de Lync Server 2013 desde un explorador de Internet que se esté ejecutando en cualquier equipo del firewall de su organización. Para obtener detalles sobre la configuración de la dirección URL simple de administración, consulte <A href="lync-server-2013-planning-for-simple-urls.md">planeamiento de direcciones URL simples en Lync server 2013</A> en la documentación de planeación y <A href="lync-server-2013-edit-or-configure-simple-urls.md">Editar o configurar direcciones URL simples en Lync Server 2013</A> en la documentación de implementación.

    
    </div>

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administrador configurada para su organización.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Para abrir el panel de control de Lync Server 2013 en un equipo con Lync Server 2013

1.  Desde una cuenta de usuario que sea miembro de la función CsAdministrator u otro rol que tenga los derechos de usuario y permisos adecuados para la tarea que se va a realizar, inicie sesión en un equipo en el que tenga instalado Lync Server 2013 o, como mínimo, Lync Server 2013 administración Ive Tools. Para configurar las opciones, el equipo debe tener una resolución de pantalla mínima de 1024 x 768.

2.  Inicie el panel de control de Lync Server 2013: haga clic en **Inicio**, haga clic en **todos los programas**, seleccione **herramientas administrativas**, seleccione **Microsoft Lync Server 2013**y, a continuación, haga clic en **Panel de control de Lync Server 2013**.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Shell de administración de Lync Server 2013

Use el procedimiento siguiente para abrir el shell de administración de Lync Server 2013 para administrar servidores, usuarios, clientes y dispositivos en el entorno mediante la línea de comandos.

<div>


> [!NOTE]  
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el shell de administración de Lync Server 2013. Puede iniciar sesión con otros roles para realizar tareas de administración específicas, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para ejecutar cmdlets relacionados con la administración de archivado. Para obtener más información sobre los roles, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación. Para obtener más información sobre los roles que puede usar para ejecutar un cmdlet específico, consulte la documentación del cmdlet.<BR>También puede ejecutar determinados cmdlets usando una cuenta de usuario en los grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, según el cmdlet.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Para abrir el shell de administración de Lync Server 2013

  - Si abre una ventana de Windows PowerShell en lugar del shell de administración de Lync Server 2013, de forma predeterminada, no podrá ejecutar los cmdlets de la 2013 de Lync Server. Para ejecutar los cmdlets de Lync Server 2013 desde Windows PowerShell, escriba lo siguiente en el símbolo del sistema de Windows PowerShell:
    
    `Import-Module Lync`

  - Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)  


[Herramientas administrativas de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


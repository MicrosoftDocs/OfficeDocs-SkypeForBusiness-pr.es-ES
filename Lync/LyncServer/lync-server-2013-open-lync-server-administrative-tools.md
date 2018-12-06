---
title: Abrir las herramientas administrativas de Lync Server
TOCTitle: Abrir las herramientas administrativas de Lync Server
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48275965
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Abrir las herramientas administrativas de Lync Server

 

_**Última modificación del tema:** 2012-06-28_

Puede usar los procedimientos de este tema para abrir las herramientas administrativas a fin de implementar, configurar o solucionar problemas de su topología de Lync Server 2013.

  - Asistente para implementación

  - Generador de topologías

  - Panel de control de Lync Server 2013

  - Shell de administración de Communications Server

## Asistente para implementación

Use el siguiente procedimiento para iniciar el Asistente para implementación localmente y agregar o eliminar archivos de componentes de Lync Server 2013.

## Para iniciar el Asistente para implementación de Lync Server 2013

1.  Inicie sesión en el equipo donde se encuentre instalado el Asistente para la implementación de Lync Server como miembro del grupo de administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  Haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, a continuación, haga clic en **Asistente para implementación de Lync Server**.

## Generador de topologías

Use el siguiente procedimiento para abrir la Generador de topologías y definir los servidores que desea implementar en su topología de Lync Server 2013.

## Para abrir el Generador de topologías de Lync Server 2013 y diseñar la topología

1.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    

    > [!NOTE]
    > Puede definir una topología usando una cuenta que sea miembro del grupo Usuarios local, pero para leer, publicar o habilitar una topología, necesario para instalar Lync Server 2013 en un servidor, debe usar una cuenta que sea miembro del grupo Admins. de dominio y del grupo RTCUniversalServerAdmins, y que disponga de todos los permisos (es decir, lectura, escritura y modificación) para controlar el uso compartido de los archivos que se van a usar en el almacén de archivos de archivado, de modo que Generador de topologías pueda configurar la lista de control de acceso discrecional (DACL) necesaria, o una cuenta con derechos de usuario equivalentes.



2.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

## Panel de control de Lync Server 2013

Use uno de los siguientes procedimientos para abrir Panel de control de Lync Server 2013 y administrar la configuración de servidores, usuarios, clientes y dispositivos en su entorno.


> [!NOTE]
> Puede usar una cuenta de usuario que esté asignada a la función CsAdministrator para realizar cualquier tarea en Panel de control de Lync Server 2013. Puede usar otras funciones para iniciar sesión en Panel de control de Lync Server 2013 para realizar tareas específicas de administración, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para administrar el archivado en Panel de control de Lync Server 2013. Para más información sobre funciones, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</A> en la documentación sobre planeación. Para obtener información sobre las funciones que puede usar para realizar una tarea específica, consulte la documentación de la tarea.



## Para abrir Panel de control de Lync Server 2013 desde cualquier equipo dentro del firewall de su organización

1.  Desde una cuenta de usuario asignada a la función CsAdministrator o a otra función que tenga los derechos de usuario y permisos apropiados para la tarea que se va a realizar, inicie sesión en un equipo de la implementación interna con una resolución de pantalla mínima de 1024 × 768.
    
    > [!IMPORTANT]  
    > Si configuró un localizador uniforme de recursos (URL) simple de administración, puede obtener acceso a Panel de control de Lync Server 2013 desde un explorador de Internet que se está ejecutando en cualquier equipo dentro del firewall de la organización. Para obtener información sobre la configuración de la URL simple de administración, consulte <a href="lync-server-2013-planning-for-simple-urls.md">Planeación de las direcciones URL simples en Lync Server 2013</a> en la documentación de planeación y <a href="lync-server-2013-edit-or-configure-simple-urls.md">Editar o configurar direcciones URL sencillas en Lync Server 2013</a> en la documentación de implementación.
    


2.  Abra una ventana del explorador y escriba la dirección URL de administración configurada para la organización.

## Para abrir Panel de control de Lync Server 2013 en un equipo que ejecute Lync Server 2013

1.  Desde una cuenta de usuario que sea miembro de la función CsAdministrator u otra función que tenga los permisos y derechos de usuario adecuados para la tarea que se va a realizar, inicie sesión en un equipo en el que Lync Server 2013 esté instalado o, como mínimo, las herramientas administrativas de Lync Server 2013. Para configurar los parámetros, el equipo debe tener una resolución de pantalla mínima de 1024 × 768.

2.  Inicie Panel de control de Lync Server 2013: haga clic en **Inicio**, **Todos los programas**, seleccione **Herramientas administrativas**, **Microsoft Lync Server 2013** y, a continuación, haga clic en **Panel de control de Lync Server 2013**.

## Shell de administración de Lync Server 2013

Use el siguiente procedimiento para abrir Shell de administración de Lync Server 2013 y administrar servidores, usuarios, clientes y dispositivos en su entorno mediante la línea de comandos.


> [!NOTE]
> Puede usar una cuenta de usuario que esté asignada a la función CsAdministrator para realizar cualquier tarea en Shell de administración de Lync Server 2013. Puede iniciar sesión con otras funciones para realizar tareas específicas de administración, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para ejecutar cmdlets relacionados con las administración de archivado. Para obtener información sobre funciones, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</A> en la documentación sobre planeación. Para obtener información sobre las funciones que puede usar para ejecutar un cmdlet específico, consulte la documentación del cmdlet.<BR>También puede ejecutar ciertos cmdlets mediante una cuenta de usuario en los grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, según el cmdlet.



## Para abrir la Shell de administración de Lync Server 2013

  - Si abre una ventana de Windows PowerShell en lugar del Shell de administración de Lync Server 2013, de forma predeterminada no puede ejecutar los cmdlets de Lync Server 2013. Para ejecutar los cmdlets de Lync Server 2013 desde Windows PowerShell, escriba lo siguiente en el símbolo del sistema de Windows PowerShell:
    
    `Import-Module Lync`

  - Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

## Vea también

#### Tareas

[Instalar las herramientas administrativas de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)  

#### Conceptos

[Herramientas administrativas de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)


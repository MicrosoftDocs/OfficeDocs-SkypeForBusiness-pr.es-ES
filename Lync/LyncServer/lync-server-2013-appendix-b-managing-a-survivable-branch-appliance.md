---
title: 'Apéndice B: Administrar una aplicación de sucursal con funciones de supervivencia'
TOCTitle: 'Apéndice B: Administración de una aplicación de sucursal con funciones de supervivencia'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48274809
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Apéndice B: Administración de una aplicación de sucursal con funciones de supervivencia en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-18_

Este tema describe los procedimientos necesarios para administrar una Aplicación de sucursal con funciones de supervivencia: específicamente, el modo de reemplazar una Aplicación de sucursal con funciones de supervivencia y cambiarle el nombre, así como el modo de cambiar el grupo de servidores front-end de Lync Server 2013 al que la Aplicación de sucursal con funciones de supervivencia está asociada.

## Reemplazar una aplicación de sucursal con funciones de supervivencia

1.  Detenga todos los servicios de Lync Server 2013 en la Aplicación de sucursal con funciones de supervivencia. (Consulte la documentación del proveedor de la Aplicación de sucursal con funciones de supervivencia.)

2.  (Recomendado) Quite la Aplicación de sucursal con funciones de supervivencia del dominio.

3.  Elimine el objeto de equipo de la Aplicación de sucursal con funciones de supervivencia en Servicios de dominio de Active Directory realizando los siguientes pasos:
    
      - Inicie sesión en un servidor miembro como miembro del grupo Administradores de organización.
    
      - Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Usuarios y equipos de Active Directory**.
    
      - Haga clic con el botón secundario en el objeto de la Aplicación de sucursal con funciones de supervivencia y haga clic en **Eliminar**.

4.  Vuelva a agregar el objeto de equipo de la Aplicación de sucursal con funciones de supervivencia. Consulte para ello [Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).

5.  Espere a que se produzca la replicación de Active Directory.

6.  Abra el Shell de administración de Lync Server y escriba **Enable-CSTopology**.

7.  Conecte la nueva Aplicación de sucursal con funciones de supervivencia a la red y siga los pasos descritos en [Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) y en [Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013 - Tarea en el sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

## Cambiar el nombre de una aplicación de sucursal con funciones de supervivencia

1.  Mueva los usuarios a un sitio central. Si desea información detallada, vea [Mover usuarios a otro grupo en Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Detenga todos los servicios de Lync Server 2013 en la Aplicación de sucursal con funciones de supervivencia. (Consulte la documentación del proveedor de la Aplicación de sucursal con funciones de supervivencia.)

3.  Quite la Aplicación de sucursal con funciones de supervivencia de la topología realizando los siguientes pasos:
    
      - Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server** y **Generador de topologías de Lync Server**.
    
      - En el árbol de la consola, expanda **Sitios de sucursal**, haga clic en la Aplicación de sucursal con funciones de supervivencia y después haga clic en **Eliminar** en el panel de acciones.

4.  Quite la Aplicación de sucursal con funciones de supervivencia del dominio.

5.  Elimine el objeto de equipo de la Aplicación de sucursal con funciones de supervivencia en Active Directory realizando los siguientes pasos:
    
      - Inicie sesión en un controlador de dominio como miembro del grupo Administradores de organización.
    
      - Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Usuarios y equipos de Active Directory**.
    
      - Haga clic con el botón secundario en el objeto de la Aplicación de sucursal con funciones de supervivencia y haga clic en **Eliminar**.

6.  Restaure Aplicación de sucursal con funciones de supervivencia a los valores de fábrica predeterminados (consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia)

7.  Siga los pasos descritos en [Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central con Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) y en [Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013 - Tarea en el sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Mueva los usuarios a la Aplicación de sucursal con funciones de supervivencia con el nuevo nombre. Para más información, consulte [Mover usuarios a otro grupo en Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

## Cambiar el grupo de servidores front-end de Lync Server al que la aplicación de sucursal con funciones de supervivencia está asociada

1.  Mueva los usuarios de la Aplicación de sucursal con funciones de supervivencia al grupo de servidores front-end de Lync Server en un sitio central. Para más información, consulte [Mover usuarios a otro grupo en Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Detenga todos los servicios de Lync Server en la Aplicación de sucursal con funciones de supervivencia. (Consulte la documentación del proveedor de la Aplicación de sucursal con funciones de supervivencia.)

3.  Actualice el grupo de servidores front-end de Lync Server al que la Aplicación de sucursal con funciones de supervivencia está asociado realizando los siguientes pasos:
    
      - Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server** y **Generador de topologías de Lync Server**.
    
      - Expanda **Sitios de sucursal**.
    
      - Haga clic con el botón secundario en el objeto para modificar Aplicación de sucursal con funciones de supervivencia y, a continuación, haga clic en **Editar propiedades**.
    
      - En Resistencia, seleccione el nuevo Grupo de servidores front-end con el que deba asociarse el Aplicación de sucursal con funciones de supervivencia y, a continuación, haga clic en **Siguiente**.
    
      - En el árbol de la consola, haga clic con el botón secundario en la nueva Aplicación de sucursal con funciones de supervivencia, haga clic en **Topología** y después en **Publicar**.

4.  Reinicie todos los servicios de Lync Server en la Aplicación de sucursal con funciones de supervivencia.

5.  Pruebe la Aplicación de sucursal con funciones de supervivencia. Para información detallada, consulte [Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Mueva los usuarios del grupo de servidores front-end de Lync Server en el sitio central a la Aplicación de sucursal con funciones de supervivencia.


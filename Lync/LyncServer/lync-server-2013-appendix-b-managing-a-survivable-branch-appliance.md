---
title: 'Lync Server 2013: Apéndice B: administración de una aplicación de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df6e2dc473da81177dacb8d53ee673c9a5457c98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Apéndice B: administración de una aplicación de sucursal con funciones de supervivencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

En este tema se describen los procedimientos para administrar una aplicación de sucursal con funciones de supervivencia. En concreto, cómo reemplazar y cambiar el nombre de una aplicación de sucursal con funciones de supervivencia y cómo cambiar el grupo de servidores front-end 2013 de Lync Server con el que está asociada la aplicación de sucursal con funciones de supervivencia.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Reemplazar una aplicación de sucursal con funciones de supervivencia

1.  Detenga todos los servicios de Lync Server 2013 en la aplicación de sucursal con funciones de supervivencia. (Consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia).

2.  Recomenda Quite la aplicación de sucursal con funciones de supervivencia del dominio.

3.  Para eliminar el objeto de equipo de aplicación de sucursal con funciones de supervivencia de servicios de dominio de Active Directory, siga estos pasos:
    
      - Inicie sesión en un servidor miembro como miembro del grupo Administradores de organización.
    
      - Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Usuarios y equipos de Active Directory**.
    
      - Haga clic con el botón derecho en el objeto aplicación de sucursal con funciones de supervivencia y haga clic en **eliminar**.

4.  Vuelva a agregar el objeto de equipo de aplicación de sucursal con funciones de supervivencia. (Consulte [Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)).

5.  Espere a que se produzca la replicación de Active Directory.

6.  Abra el shell de administración de Lync Server y escriba **enable-CSTopology**.

7.  Conecte la nueva aplicación de sucursal con funciones de supervivencia a la red y siga los pasos de [implementación de una aplicación o servidor de sucursal con funciones de supervivencia con las tareas del sitio de Lync server 2013-central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implemente una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Cambiar el nombre de una aplicación de sucursal con funciones de supervivencia

1.  Mueva los usuarios a un sitio central. Para obtener más información, consulte [Move users to a otro pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Detenga todos los servicios de Lync Server 2013 en la aplicación de sucursal con funciones de supervivencia. (Consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia).

3.  Para quitar la aplicación de sucursal con funciones de supervivencia de la topología, siga estos pasos:
    
      - Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server** y **Lync Server Topology Builder**.
    
      - En el árbol de la consola, expanda **sitios de sucursal**, haga clic en la aplicación de sucursal con funciones de supervivencia y, a continuación, haga clic en **eliminar** en el panel de acciones.

4.  Quite la aplicación de sucursal con funciones de supervivencia del dominio.

5.  Para eliminar el objeto de equipo de aplicación de sucursal con funciones de supervivencia de Active Directory, siga estos pasos:
    
      - Inicie sesión en un controlador de dominio como miembro del grupo Administradores de organización.
    
      - Haga clic en **Inicio**, en **Herramientas administrativas** y después en **Usuarios y equipos de Active Directory**.
    
      - Haga clic con el botón derecho en el objeto aplicación de sucursal con funciones de supervivencia y haga clic en **eliminar**.

6.  Restaurar la aplicación de sucursal con funciones de supervivencia a los valores predeterminados de fábrica. (Consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia).

7.  Siga los pasos que se indican en [implementar una aplicación o servidor de sucursal con funciones de supervivencia con las tareas del sitio de Lync server 2013-central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implemente una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013: tarea de sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Mueva a los usuarios a la aplicación de sucursal con el nombre supervivencia. Para obtener más información, consulte [Move users to a otro pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Cambiar el grupo de servidores front-end de Lync Server al que la aplicación de sucursal con funciones de supervivencia está asociada

1.  Mueva los usuarios de la aplicación de sucursal con funciones de supervivencia al grupo de servidores front-end de Lync Server en el sitio central. Para obtener más información, consulte [Move users to a otro pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Detenga todos los servicios de Lync Server en la aplicación de sucursal con funciones de supervivencia. (Consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia).

3.  Siga estos pasos para actualizar el grupo de servidores front-end de Lync Server con el que está asociada la aplicación de sucursal con funciones de supervivencia:
    
      - Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server ** y **Lync Server Topology Builder**.
    
      - Expanda **Sitios de sucursal**.
    
      - Haga clic con el botón secundario en el objeto aplicación de sucursal con funciones de supervivencia que desea modificar y haga clic en **Editar propiedades** .
    
      - En resistencia, seleccione el nuevo grupo de servidores front-end al que se asociará la aplicación de sucursal con funciones de supervivencia y, a continuación, haga clic en **siguiente**.
    
      - En el árbol de la consola, haga clic con el botón secundario en la nueva aplicación de sucursal con funciones de supervivencia, haga clic en **topología**y, a continuación, en **publicar**.

4.  Reinicie todos los servicios de Lync Server en la aplicación de sucursal con funciones de supervivencia.

5.  Pruebe la aplicación de sucursal con funciones de supervivencia. Para obtener más información, consulte [usuarios domésticos en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Mueva a los usuarios del grupo de servidores front-end de Lync Server en el sitio central a la aplicación de sucursal con funciones de supervivencia.

</div>

</div>

<span> </span>

</div>

</div>

</div>


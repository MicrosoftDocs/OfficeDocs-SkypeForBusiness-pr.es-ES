---
title: 'Lync Server 2013: Apéndice B: Administración de una aplicación de sucursal con funciones de supervivencia'
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
ms.openlocfilehash: b16d4c55197785a6df12ad2031dbd2e624501ebd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Apéndice B: Administración de una aplicación de sucursal con funciones de supervivencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

En este tema se describen los procedimientos para administrar una aplicación de rama que sea superviviente. En concreto, cómo reemplazar y cambiar el nombre de un dispositivo de sucursal con la que se puede cambiar el nombre de la aplicación de Skype Server 2013 front end,

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Para reemplazar un dispositivo de sucursal con la supervivencia

1.  Detenga todos los servicios de Lync Server 2013 en el equipo con la sucursal que sea sobreviviente. (Consulte la documentación del proveedor de la aplicación de sucursales supervivientes).

2.  Práctica Quite la aplicación de la rama superviviente del dominio.

3.  Elimine el objeto de equipo de la aplicación de sucursal superviviente en servicios de dominio de Active Directory, siguiendo estos pasos:
    
      - Inicie sesión en un servidor miembro como miembro del grupo administradores de la empresa.
    
      - Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **usuarios y equipos de Active**Directory.
    
      - Haga clic con el botón derecho en el objeto de equipo de rama superviviente y haga clic en **eliminar**.

4.  Vuelva a agregar el objeto de equipo de la aplicación de la aplicación superviviente. (Consulte [Agregar una aplicación de rama superviviente a Active Directory en Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)).

5.  Espere a que se lleve a cabo la replicación de Active Directory.

6.  Abra el shell de administración de Lync Server y escriba **enable-CSTopology**.

7.  Conecte el nuevo dispositivo de sucursal superviviente a la red y siga los pasos que se indican en [implementación de un dispositivo o servidor de rama con la supervivencia con Lync server 2013-tareas de sitio central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implementación de un equipo o servidor de rama con la supervivencia con Lync Server 2013-tarea de sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Para cambiar el nombre de un equipo de sucursal con la supervivencia

1.  Mover usuarios al sitio central. Para obtener más información, vea [mover usuarios a otro grupo en Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Detenga todos los servicios de Lync Server 2013 en el equipo con la sucursal que sea sobreviviente. (Consulte la documentación del proveedor de la aplicación de sucursales supervivientes).

3.  Para quitar la rama superviviente de la topología, siga estos pasos:
    
      - Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server**y, a continuación, haga clic en **generador de topología de Lync Server**.
    
      - En el árbol de consola, expanda **sitios de sucursales**, haga clic en el dispositivo de rama superviviente y, a continuación, haga clic en **eliminar** en el panel de acciones.

4.  Quite la aplicación de la rama superviviente del dominio.

5.  Elimine el objeto de equipo de la aplicación de la aplicación superviviente en Active Directory, siguiendo estos pasos:
    
      - Inicie sesión en un controlador de dominio como miembro del grupo administradores de la empresa.
    
      - Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **usuarios y equipos de Active**Directory.
    
      - Haga clic con el botón derecho en el objeto de equipo de rama superviviente y haga clic en **eliminar**.

6.  Restaura los valores predeterminados de fábrica de la aplicación de rama que es superviviente. (Consulte la documentación del proveedor de la aplicación de sucursales supervivientes).

7.  Siga los pasos que se indican en [implementar un dispositivo o servidor de sucursal que sea reviviente con Lync server 2013-tareas de sitio central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implementar un equipo o servidor de rama con la supervivencia con Lync Server 2013-tarea de sitio de rama](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Mueva a los usuarios al equipo de rama con el nombre cambiado. Para obtener más información, vea [mover usuarios a otro grupo en Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Para cambiar el grupo de servidores front-end de Lync Server al que está asociado el equipo con la rama superviviente

1.  Mueva los usuarios de la aplicación de rama superviviente al grupo de servidores front end de Lync Server en el sitio central. Para obtener más información, vea [mover usuarios a otro grupo en Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Detenga todos los servicios de Lync Server en el equipo con la sucursal que sea sobreviviente. (Consulte la documentación del proveedor de la aplicación de sucursales supervivientes).

3.  Actualice el grupo de servidores front-end de Lync Server al que está asociado el equipo con la rama superviviente, siguiendo estos pasos:
    
      - Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server**y, a continuación, haga clic en **generador de topología de Lync Server**.
    
      - Expanda **sitios de sucursales**.
    
      - Haga clic con el botón derecho en el objeto de dispositivo de rama superviviente que desee modificar y haga clic en **Editar propiedades** .
    
      - En resistencia, seleccione el nuevo grupo de servidores front-end al que se va a asociar el equipo con la rama superviviente y, a continuación, haga clic en **siguiente**.
    
      - En el árbol de consola, haga clic con el botón secundario en el nuevo dispositivo de sucursal con el que se hace clic en **topología**y luego en **publicar**.

4.  Reinicie todos los servicios de Lync Server en el equipo con la sucursal que sea sobreviviente.

5.  Prueba la aplicación de la sucursal con supervivencia. Para obtener más información, consulte [usuarios domésticos en un equipo o servidor de sucursal con la supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Mueva los usuarios del grupo de servidores front-end de Lync Server en el sitio central a la aplicación de rama superviviente.

</div>

</div>

<span> </span>

</div>

</div>

</div>


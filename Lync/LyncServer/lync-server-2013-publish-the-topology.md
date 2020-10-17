---
title: 'Lync Server 2013: publicar la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e94e47536c8af6ef8fd3c22dba245b03c961c575
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512367"
---
# <a name="publish-the-topology-in-lync-server-2013"></a>Publicar la topología en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-01_

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, es necesario haber iniciado sesión como usuario miembro de los grupos Admins del dominio y RTCUniversalServerAdmins. También se pueden delegar los permisos y derechos de administrador adecuados. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Para realizar otros cambios de configuración, solo se requiere pertenecer al grupo RTCUniversalServerAdmins.

Después de definir la topología en el generador de topologías, debe publicar la topología en el almacén de administración central. El almacén de administración central proporciona un almacenamiento sólido y esquematizado de los datos necesarios para definir, configurar, mantener, administrar, describir y usar una implementación de Lync Server 2013. También valida los datos para ayudar a garantizar la coherencia de la configuración. Todos los cambios en estos datos de configuración ocurren en el almacén de administración central, lo que elimina los problemas de "falta de sincronización". Las copias de solo lectura de los datos se replican a todos los servidores de la topología, incluidos los servidores perimetrales.

<div>


> [!NOTE]  
> SQL Server necesita un mínimo de 20 GB de espacio libre en disco para poder publicar correctamente la topología inicial y crear el servidor de administración central.



</div>

<div>


> [!NOTE]  
> Solo para Enterprise Edition: Para publicar la topología, el servidor back-end basado en SQL Server debe estar conectado y ser accesible, y haber especificado excepciones de firewall. Para obtener información detallada sobre cómo especificar las excepciones de firewall, consulte <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding Firewall Requirements for SQL Server with Lync server 2013</A>. Para obtener más información sobre cómo configurar SQL Server, consulte <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configurar SQL Server para Lync Server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>Para publicar una topología

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  Seleccione abrir la topología desde un archivo local. Si se encuentra en el equipo en el que definió la topología, esta estará en la ubicación en la que la guardó en pasos anteriores. Normalmente, será la carpeta de documentos del usuario que configuró la topología.

3.  Haga clic con el botón secundario en el nodo **Lync Server 2013** y, a continuación, haga clic en **publicar topología**.

4.  En la página **Publicar topología**, haga clic en **Siguiente**.

5.  En la página **Crear bases de datos**, seleccione las bases de datos que desea publicar.
    
    <div>
    

    > [!NOTE]  
    > Si no dispone de los derechos adecuados para crear las bases de datos, puede desactivar las casillas situadas junto a dichas bases de datos y, posteriormente, alguien con los derechos adecuados podrá crearlas. Para obtener información detallada, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync Server 2013</A>.

    
    </div>

6.  Opcionalmente, haga clic en **Avanzadas**. Las opciones avanzadas de colocación del archivo de datos de SQL Server permiten seleccionar entre las siguientes opciones:
    
      - **Determinar automáticamente la ubicación del archivo de base de datos**: esta opción determinará el mejor rendimiento operativo a partir de la configuración de disco del servidor basado en SQL Server con la distribución de los archivos de datos y de registro en la mejor ubicación.
    
      - **Usar valores predeterminados de instancia de SQL Server**: esta opción coloca los archivos de datos y de registro en el servidor basado en SQL Server con el uso de la configuración de la instancia. No usa la funcionalidad operativa del servidor basado en SQL Server para determinar las ubicaciones óptimas de registros y datos. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que sean adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.
    
    Haga clic en **Aceptar** y después en **Siguiente**.

7.  En la página **Seleccionar servidor de administración central** , seleccione un grupo de servidores front-end.

8.  Opcionalmente, haga clic en **Avanzadas**. Las opciones avanzadas de ubicación de archivos de datos de SQL Server permiten seleccionar entre las siguientes opciones:
    
      - **Determinar automáticamente la ubicación del archivo de base de datos**: esta opción determinará el mejor rendimiento operativo a partir de la configuración de disco del servidor basado en SQL Server con la distribución de los archivos de datos y de registro en la mejor ubicación.
    
      - **Usar valores predeterminados de instancia de SQL Server**: esta opción coloca los archivos de datos y de registro en el servidor basado en SQL Server con el uso de la configuración de la instancia. No usa la funcionalidad operativa del servidor basado en SQL Server para determinar las ubicaciones óptimas de registros y datos. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que sean adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.
    
    Haga clic en **Aceptar**.

9.  Haga clic en **Siguiente** para completar el proceso de publicación.

10. Una vez completado el proceso de publicación, haga clic en **Finalizar**.
    
    Cuando la topología se haya publicado correctamente, puede empezar a instalar una réplica local del almacén de administración central en cada servidor que ejecute Lync Server 2013 en la topología. Le recomendamos que comience con el primer grupo de servidores front-end.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configuración de servidores front-end y grupos de servidores front-end para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


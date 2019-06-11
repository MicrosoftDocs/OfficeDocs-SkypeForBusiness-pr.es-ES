---
title: 'Lync Server 2013: Publicar la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee3b14776c6cdf6ddd52ada724d3d4a6d6a245a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>Publicar la topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-01_

Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins. También es posible delegar los derechos y permisos de administrador adecuados. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.

Después de definir la topología en el generador de topología, debe publicarla en el almacén de administración central. El almacén central de administración proporciona un sólido almacenamiento schematized de los datos necesarios para definir, configurar, mantener, administrar, describir y utilizar una implementación de Lync Server 2013. También valida los datos para garantizar la coherencia de la configuración. Todos los cambios realizados a esta configuración se producen en el almacén de administración central, excepto los problemas de "sin sincronizar". Las copias de solo lectura de los datos se replican en todos los servidores de la topología, incluidos los servidores perimetrales.

<div>


> [!NOTE]  
> SQL Server necesita un mínimo de 20 GB de espacio libre en el disco para publicar correctamente la topología inicial y crear el servidor de administración central.



</div>

<div>


> [!NOTE]  
> Solo para Enterprise Edition: para publicar la topología, el servidor back-end basado en SQL Server debe estar conectado y ser accesible con las excepciones de firewall en contexto. Para obtener más información sobre cómo especificar excepciones de firewall, consulte <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding Firewall Requirements for SQL Server with Lync server 2013</A>. Para obtener más información sobre cómo configurar SQL Server, consulte <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configurar SQL Server para Lync server 2013</A>.



</div>

<div>

## <a name="to-publish-a-topology"></a>Para publicar una topología

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  Seleccione para abrir la topología desde un archivo local. Si está en el equipo donde definió la topología, esta aparecerá en la ubicación en la que lo guardó en los pasos anteriores. Normalmente, será la carpeta documentos del usuario que configuró la topología.

3.  Haga clic con el botón derecho en el nodo de **2013 de Lync Server** y, después, haga clic en **publicar topología**.

4.  En la página **Publicar la topología**, haga clic en **Siguiente**.

5.  En la página **crear bases de datos** , seleccione las bases de datos que desea publicar.
    
    <div>
    

    > [!NOTE]  
    > Si no dispone de los derechos adecuados para crear las bases de datos, puede desactivar las casillas situadas junto a dichas bases de datos y, posteriormente, alguien con los derechos adecuados podrá crearlas. Para obtener más información, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync Server 2013</A>.

    
    </div>

6.  Opcionalmente, haga clic en **Opciones avanzadas**. Las opciones avanzadas de ubicación de los archivos de datos de SQL Server le permiten seleccionar entre las siguientes opciones:
    
      - **Determinar automáticamente la ubicación del archivo de base** de datos: esta opción determinará el mejor rendimiento operativo en función de la configuración de disco de su servidor basado en SQL Server distribuyendo los archivos de registro y de datos a la mejor ubicación.
    
      - **Usar los valores predeterminados de instancia de SQL Server**: esta opción coloca los archivos de datos y de registro en el servidor basado en SQL Server usando la configuración de la instancia. No usa la función operativa del servidor basado en SQL Server para saber cuáles son las mejores ubicaciones para los archivos de datos y de registro. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que son adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.
    
    Haga clic en **Aceptar** y, luego, en **Siguiente**.

7.  En la página **Seleccionar servidor de administración central** , seleccione un grupo de servidores front-end.

8.  Opcionalmente, haga clic en **Opciones avanzadas**. Las opciones avanzadas de ubicación del archivo de datos de SQL Server le permiten seleccionar entre las siguientes opciones:
    
      - **Determinar automáticamente la ubicación del archivo de base** de datos: esta opción determinará el mejor rendimiento operativo en función de la configuración de disco de su servidor basado en SQL Server distribuyendo los archivos de registro y de datos a la mejor ubicación.
    
      - **Usar los valores predeterminados de instancia de SQL Server**: esta opción coloca los archivos de datos y de registro en el servidor basado en SQL Server usando la configuración de la instancia. No usa la función operativa del servidor basado en SQL Server para saber cuáles son las mejores ubicaciones para los archivos de datos y de registro. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que son adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.
    
    Haga clic en **Aceptar**.

9.  Haga clic en **Siguiente** para completar el proceso de publicación.

10. Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar**.
    
    Cuando la topología se ha publicado correctamente, puede empezar a instalar una réplica local del almacén de administración central en cada servidor que ejecute Lync Server 2013 en su topología. Recomendamos empezar por el primer grupo de servidores front-end.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar servidores front-end y grupos de servidores front-end para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


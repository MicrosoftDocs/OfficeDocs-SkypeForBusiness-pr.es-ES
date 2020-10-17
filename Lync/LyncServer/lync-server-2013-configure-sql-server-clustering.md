---
title: 'Lync Server 2013: configurar la organización en clústeres de SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21fac13a22e2b2acf400ca154551a0705544644f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535217"
---
# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Configurar la organización en clústeres de SQL Server para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-10_

Microsoft Lync Server 2013 admite clústeres para SQL Server 2012 y SQL Server 2008 R2. Para obtener más información sobre lo que se admite, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).

Debe configurar y configurar el clúster de SQL Server antes de instalar e implementar la base de datos back-end y el servidor front-end Enterprise Edition. Para conocer los procedimientos recomendados y las instrucciones de configuración de los clústeres de conmutación por error en SQL Server 2012, consulte <https://technet.microsoft.com/library/hh231721.aspx> . Para clústeres de conmutación por error en SQL Server 2008, consulte <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .

Cuando instale SQL Server, instale también SQL Server Management Studio para administrar las ubicaciones de la base de datos y las ubicaciones de archivo de registro. SQL Server Management Studio se instala como componente adicional al instalar SQL Server.

<div>


> [!IMPORTANT]  
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server, el usuario debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server en el que se vayan a instalar los archivos de base de datos. Si no es miembro del grupo sysadmins de SQL Server, deberá solicitar su incorporación en dicho grupo hasta que los archivos de base de datos se implementen. Si no puede convertirse en miembro del grupo sysadmins, proporcione al administrador de bases de datos SQL Server la secuencia de comandos para configurar e implementar las bases de datos. Para obtener información detallada sobre los permisos y derechos de usuario adecuados para realizar los procedimientos, vea <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>Para configurar clústeres SQL Server

1.  Una vez completada la instalación y la configuración de la agrupación en clústeres de SQL Server, defina el almacén de SQL Server en Topology Builder mediante el nombre del clúster virtual de instancia de SQL Server (como se ha configurado en la configuración de clústeres de SQL Server) y el nombre de instancia de la base de datos de SQL Server. A diferencia de lo que sucede con un solo servidor basado en SQL Server, usará el nombre de dominio completo (FQDN) del nodo virtual para un servidor en clúster basado en SQL Server.
    
    <div>
    

    > [!NOTE]  
    > No es necesario configurar los nodos individuales del clúster de servidores de Windows para el generador de topologías. Únicamente usará el nombre de clúster virtual de SQL Server.

    
    </div>

2.  Si usa el generador de topologías para implementar las bases de datos, debe ser miembro del grupo sysadmin de SQL Server. Si es miembro del grupo sysadmin de SQL Server, pero no tiene privilegios en el dominio (por ejemplo, un rol de administrador de bases de datos de SQL Server), tiene derechos para crear las bases de datos pero no para leer la información necesaria en Lync Server. Para obtener más información sobre los derechos de usuario y los permisos necesarios para implementar Lync Server, vea [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Asegúrese de que los valores predeterminados de la carpeta de base de datos y la carpeta de archivos de registro se asignan correctamente a los discos compartidos en el clúster de SQL Server mediante SQL Server Management Studio. Se trata de un procedimiento necesario si se van a crear bases de datos con Topology Builder.
    
    <div>
    

    > [!NOTE]  
    > Si no instaló SQL Server Management Studio, puede hacerlo ejecutando de nuevo la instalación de SQL Server y seleccionando a continuación la herramienta de administración como una característica agregada para la implementación existente de SQL Server.

    
    </div>

4.  Instale las bases de datos para el servidor basado en SQL Server mediante el generador de topologías o los cmdlets de Windows PowerShell. Para usar el generador de topologías, use el siguiente procedimiento. Para usar los cmdlets de Windows PowerShell, consulte [instalación de bases de datos mediante el shell de administración de Lync Server en Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>Para crear bases de datos con el generador de topologías

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.
    
    <div>
    

    > [!WARNING]  
    > El siguiente procedimiento presupone que ha definido y configurado la topología en el generador de topologías. Para obtener más información sobre cómo definir la topología, consulte<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and Configuring the Topology in Lync Server 2013</A>. Para usar Topology Builder para publicar la topología y configurar la base de datos, debe iniciar sesión como usuario con los derechos de usuario y las pertenencias a grupo correctos. Para obtener más información sobre los derechos obligatorios y las pertenencias a grupos, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync Server 2013</A>.

    
    </div>

2.  En el generador de topologías, cuando publique la topología, en la página **crear bases de datos** , haga clic en **Opciones avanzadas**.

3.  La página **Seleccionar la ubicación del archivo de base de datos** incluye dos opciones que determinan la forma en que se implementarán los archivos de base de datos en el clúster de SQL Server. Seleccione una de las siguientes opciones:
    
      - **Determinar automáticamente la ubicación del archivo de base de datos.** Esta selección usa un algoritmo para determinar las ubicaciones del registro de la base de datos y el archivo de datos en función de la configuración de unidades en el servidor basado en SQL Server. Los archivos se distribuirán de manera que se intente proporcionar un rendimiento óptimo.
    
      - Usar valores predeterminados de instancia de SQL Server. Si selecciona esta opción, los archivos de datos y de registro se instalarán según la configuración de la instancia de SQL Server. Después de la implementación de los archivos de base de datos en SQL Server, es posible que el administrador de bases de datos de SQL Server desee reubicar los archivos para optimizar el rendimiento de los requisitos de configuración de SQL Server en concreto.

4.  Complete la publicación de la topología y confirme que no se produjeron errores durante la operación.

</div>

</div>

<span> </span>

</div>

</div>

</div>


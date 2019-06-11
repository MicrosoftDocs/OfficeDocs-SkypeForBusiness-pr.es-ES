---
title: 'Lync Server 2013: configurar la organización en clústeres de SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279c6581d0a56193c094c3dd7b9638fd74e2e60c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Configurar clústeres de SQL Server para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-10_

Microsoft Lync Server 2013 admite clústeres para SQL Server 2012 y SQL Server 2008 R2. Para obtener más información sobre lo que se admite, vea [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).

Debe configurar y configurar el clúster de SQL Server antes de instalar e implementar el servidor front-end Enterprise Edition y la base de datos back-end. Para ver los procedimientos recomendados y las instrucciones de configuración para el clúster de conmutación por <http://technet.microsoft.com/en-us/library/hh231721.aspx>error en SQL Server 2012, consulte. Para el clúster de conmutación por error en SQL Server <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>2008, consulte.

Al instalar SQL Server, es preciso instalar también SQL Server Management Studio para administrar las ubicaciones de la base de datos y de los archivos de registro. SQL Server Management Studio se instala como un componente opcional al instalar SQL Server.

<div>


> [!IMPORTANT]  
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server, debe ser miembro del grupo sysadmin de SQL Server para el servidor basado en SQL Server en el que va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmin de SQL Server, tendrá que solicitar que lo agregue al grupo hasta que se implementen los archivos de base de datos. Si no puede hacerse miembro del grupo sysadmin, debe proporcionar el administrador de la base de datos de SQL Server con el script para configurar e implementar las bases de datos. Para obtener más información sobre los permisos y los derechos de usuario adecuados que necesita para realizar los procedimientos, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>Para configurar la organización en clústeres de SQL Server

1.  Una vez completada la instalación y la configuración de la organización por clústeres de SQL Server, defina el almacén de SQL Server en el generador de topología con el nombre del clúster virtual de instancias de SQL Server (configurado en la configuración de clústeres de SQL Server) y la instancia. nombre de la base de datos de SQL Server. Es diferente de un único servidor basado en SQL Server, se usa el nombre de dominio completo (FQDN) del nodo virtual para un servidor basado en SQL Server agrupado.
    
    <div>
    

    > [!NOTE]  
    > Los nodos individuales del clúster de servidor de Windows no tienen que estar configurados para el generador de topología. Solo usará el nombre de clúster de SQL Server virtual.

    
    </div>

2.  Si usa la topología Builder para implementar sus bases de datos, debe ser miembro del grupo sysadmin de SQL Server. Si es miembro del grupo sysadmin de SQL Server, pero no tiene privilegios en el dominio (por ejemplo, una función de administrador de base de datos de SQL Server), tendrá los derechos para crear las bases de datos pero no para leer la información necesaria en Lync Server. Para más información sobre los derechos de usuario y los permisos necesarios para implementar Lync Server, consulte [permisos de implementación para SQL Server en Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Asegúrese de que los valores predeterminados de la carpeta base de datos y archivos de registro están asignados correctamente a los discos compartidos en el clúster de SQL Server mediante SQL Server Management Studio. Este es un procedimiento obligatorio si va a crear bases de datos con el generador de topologías.
    
    <div>
    

    > [!NOTE]  
    > Si no instaló SQL Server Management Studio, puede instalarlo si vuelve a ejecutar la instalación de SQL Server y, a continuación, selecciona la herramienta de administración como una característica agregada para la implementación existente de SQL Server.

    
    </div>

4.  Instale las bases de datos para el servidor basado en SQL Server con los cmdlets del generador de topología o de Windows PowerShell. Para usar el generador de topología, use el procedimiento siguiente. Para usar los cmdlets de Windows PowerShell, vea [instalación de bases de datos con el shell de administración de Lync Server en Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>Para crear bases de datos con el generador de topología

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.
    
    <div>
    

    > [!WARNING]  
    > En el procedimiento siguiente se supone que ha definido y configurado su topología en el generador de topología. Para obtener más información sobre cómo definir su topología, consulte<A href="lync-server-2013-defining-and-configuring-the-topology.md">definir y configurar la topología en Lync Server 2013</A>. Para usar el generador de topología para publicar la topología y configurar la base de datos, debe iniciar sesión como usuario con los derechos de usuario y pertenencias a grupos correctos. Para obtener más información sobre los derechos obligatorios y la pertenencia a grupos, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync server 2013</A>.

    
    </div>

2.  En el generador de topologías, a medida que publique la topología, en la página **crear bases de datos** , haga clic en **Opciones avanzadas**.

3.  La página **Seleccionar ubicación de archivo de base de datos** tiene dos opciones que determinan cómo se implementarán los archivos de base de datos en el clúster de SQL Server. Seleccione una de las siguientes opciones:
    
      - **Determinar automáticamente la ubicación del archivo de base de datos.** Esta selección usa un algoritmo para determinar el registro de la base de datos y las ubicaciones del archivo de datos en función de la configuración del servidor basado en SQL Server. Los archivos se distribuirán de manera tal que intenten proporcionar un rendimiento óptimo.
    
      - Use los valores predeterminados de instancia de SQL Server. Al seleccionar esta opción se instalarán los archivos de registro y de datos de acuerdo con la configuración de la instancia de SQL Server. Después de implementar los archivos de base de datos en SQL Server, es posible que el administrador de la base de datos de SQL Server desee reubicar los archivos para optimizar el rendimiento de los requisitos de configuración de SQL Server concretos.

4.  Complete la publicación de la topología y confirme que no hubo errores durante la operación.

</div>

</div>

<span> </span>

</div>

</div>

</div>


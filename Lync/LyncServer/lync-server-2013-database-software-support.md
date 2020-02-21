---
title: Soporte de software de base de datos de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c37644e07fd0dfd192867d7d8372d3630d13fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Compatibilidad con software de base de datos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-01_

Lync Server 2013 admite los siguientes sistemas de administración de bases de datos:

  - **Base de datos back-end de un grupo de servidores front-end, una base de datos de archivado, una base de datos de supervisión, una base de datos de chat persistente y una base de datos para el cumplimiento de chat persistente**
    
      - Software de base de datos Microsoft SQL Server 2008 R2 Enterprise (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2008 R2 Standard (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2012 Enterprise (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2012 Standard (edición de 64 bits) o el último service pack (recomendado)

  - **Bases de datos del servidor Standard Edition y de los servidores front-end**
    
      - Microsoft SQL Server 2012 Express (edición de 64 bits). Además, se recomienda ejecutar el último Service Pack.
        
        Admitimos la revisión y actualización de Microsoft SQL Server en servidores front-end y servidores Standard Edition. Sin embargo, cuando realiza cualquier tipo de actualización o revisión en los servidores front-end, debe tener en cuenta los requisitos de quórum. Para obtener más información, vea [actualizar o actualizar los servidores front-end en Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) y las [topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 instala automáticamente Microsoft SQL Server 2012 Express (edición de 64 bits) en cada servidor Standard Edition y en cada servidor front-end.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 no admite la edición de 32 bits de SQL Server. Emplee la edición de 64 bits.</P>
> <LI>
> <P>SQL Server Web Edition y SQL Server Workgroup Edition no son compatibles. No puede usarlos con Lync Server 2013.</P>
> <LI>
> <P>Lync Server 2013 admite la creación de reflejos de bases de datos nativas.</P>
> <LI>
> <P>Para usar la función de servidor de supervisión, debe instalar SQL Server Reporting Services.</P></LI></UL>



</div>

En un grupo de servidores front-end, la base de datos back-end puede ser un único equipo con SQL Server.

<div>


> [!IMPORTANT]  
> Si combinar las bases de datos de Lync Server con otras bases de datos, es muy recomendable evaluar todos los factores que pueden afectar a la disponibilidad y el rendimiento, así como garantizar que, si se produce un error en un nodo, el nodo restante pueda controlar la carga. Para comprobar las capacidades de conmutación por error, se recomienda probar todos los escenarios de conmutación por error.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Uso de la creación de reflejos de SQL y los clústeres de SQL

Lync Server 2013 admite el uso de la creación de reflejo de SQL o de la organización en clústeres de SQL para cada base de datos de Lync Server. Puede configurar la creación de reflejos de SQL fácilmente con la herramienta Topology Builder en Lync Server 2013. Para los clústeres de conmutación por error de SQL, debe usar SQL Server para la instalación.

Lync Server 2013 admite topologías de creación de reflejos de SQL y de agrupación en clústeres de SQL para todas las implementaciones, incluidas las implementaciones de Greenfield y las organizaciones que han actualizado desde versiones anteriores de Lync Server.

La compatibilidad con clústeres de SQL es para una configuración activa/pasiva. Por motivos de rendimiento, el nodo pasivo no debe compartirse con ninguna otra instancia de SQL.

Se incluye la siguiente compatibilidad:

  - Clústeres de conmutación por error de dos nodos para los siguientes elementos:
    
      - Microsoft SQL Server 2012 Standard (edición de 64 bits). Además, se recomienda ejecutar el último Service Pack.
    
      - Microsoft SQL Server 2008 R2 Standard (edición de 64 bits). Además, se recomienda ejecutar el último Service Pack.

  - Clústeres de conmutación por error de hasta dieciséis nodos para los siguientes elementos:
    
      - Microsoft SQL Server 2012 Enterprise (edición de 64 bits). Además, se recomienda ejecutar el último Service Pack.
    
      - Microsoft SQL Server 2008 R2 Enterprise Database software (edición de 64 bits). Además, se recomienda ejecutar el último Service Pack.

Para obtener más información acerca de la creación de reflejos de SQL, vea [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md). Para obtener más información sobre cómo implementar clústeres de SQL, vea [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

Para obtener más información y procedimientos recomendados para clústeres de conmutación por error en SQL <https://technet.microsoft.com/library/hh231721.aspx>Server 2012, consulte. Para clústeres de conmutación por error en SQL Server <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>2008, consulte.

</div>

</div>

<span> </span>

</div>

</div>

</div>


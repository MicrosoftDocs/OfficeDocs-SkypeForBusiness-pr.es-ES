---
title: 'Lync Server 2013: Compatibilidad con software de base de datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc8daef764ce5b15fd8c8b7e29f7031ebcfbafc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Compatibilidad con software de base de datos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-01_

Lync Server 2013 admite los siguientes sistemas de administración de bases de datos:

  - **Base de datos back-end de un grupo de servidores front-end, una base de datos de archivado, una base de datos de supervisión, una base de datos de chat persistente y una base de datos para el cumplimiento de chat persistente **
    
      - Software de base de datos Microsoft SQL Server 2008 R2 Enterprise (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2008 R2 Standard (edición de 64 bits). Se recomienda ejecutar además el último Service Pack.
    
      - Microsoft SQL Server 2012 Enterprise (64-bit Edition). Se recomienda ejecutar además el último Service Pack.
    
      - Microsoft SQL Server 2012 Standard (edición de 64 bits). Se recomienda ejecutar además el último Service Pack.

  - **Bases de datos del servidor Standard Edition y del servidor front-end**
    
      - Microsoft SQL Server 2012 Express (edición de 64 bits). Se recomienda ejecutar además el último Service Pack.
        
        Admitimos la revisión y actualización de Microsoft SQL Server en servidores front-end y servidores Standard Edition. Sin embargo, cuando realiza cualquier tipo de actualización o revisión en servidores de aplicaciones para el usuario, debe tener en cuenta los requisitos de quórum. Para obtener más información, consulte [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) y [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 instala automáticamente Microsoft SQL Server 2012 Express (64-bit Edition) en cada servidor Standard Edition y cada servidor de servidor front-end.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 no es compatible con la edición de 32 bits de SQL Server. Emplee la edición de 64 bits.</P>
> <LI>
> <P>SQL Server Web Edition y SQL Server Workgroup Edition no son compatibles. No puede usarlos con Lync Server 2013.</P>
> <LI>
> <P>Lync Server 2013 admite el reflejo de base de datos nativa.</P>
> <LI>
> <P>Para usar el rol de servidor supervisión, debe instalar SQL Server Reporting Services.</P></LI></UL>



</div>

En un grupo de servidores front-end, la base de datos back-end puede ser un único equipo SQL Server.

<div>


> [!IMPORTANT]  
> Si Collocate bases de datos de Lync Server con otras bases de datos, recomendamos encarecidamente evaluar todos los factores que pueden afectar a la disponibilidad y el rendimiento, así como garantizar que, si se produce un error en un nodo, el nodo restante puede controlar la carga. Para comprobar las capacidades de conmutación por error, se recomienda probar todos los escenarios de conmutación por error.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Información de uso sobre la creación de espejos y la agrupación en clústeres de SQL

Lync Server 2013 admite el uso de la creación de reflejos SQL o SQL clustering en cada base de datos de Lync Server. Puede configurar el reflejo de SQL fácilmente con la herramienta topología del compilador de Lync Server 2013. Los clústeres de conmutación por error de SQL deben configurarse desde SQL Server.

Lync Server 2013 admite el reflejo SQL y las topologías de clúster SQL para todas las implementaciones, incluidas las implementaciones y organizaciones de Greenfield que han actualizado de versiones anteriores de Lync Server.

La agrupación en clústeres de SQL es compatible con la configuración activa/pasiva. Por motivos de rendimiento, el nodo pasivo no debe compartirse con otras instancias de SQL.

Se ofrecen los supuestos de compatibilidad siguientes:

  - Clústeres de conmutación por error de dos nodos para:
    
      - Microsoft SQL Server 2012 Standard (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2008 R2 Standard (edición de 64 bits) o el último service pack (recomendado)

  - Clústeres de conmutación por error de hasta dieciséis nodos para:
    
      - Microsoft SQL Server 2012 Enterprise (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2008 R2 Enterprise Database software (edición de 64 bits). Se recomienda ejecutar además el último Service Pack.

Para obtener más información sobre la creación de reflejos de SQL, vea la [alta disponibilidad del servidor de back-end en Lync server 2013](lync-server-2013-back-end-server-high-availability.md). Para obtener más información sobre cómo implementar clústeres SQL, consulte [configurar clústeres de SQL Server para Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

Para obtener más información y procedimientos recomendados para el clúster de conmutación por error en SQL <http://technet.microsoft.com/en-us/library/hh231721.aspx>Server 2012, consulte. Para el clúster de conmutación por error en SQL Server <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>2008, consulte.

</div>

</div>

<span> </span>

</div>

</div>

</div>


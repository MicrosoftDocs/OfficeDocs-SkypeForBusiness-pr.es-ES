---
title: 'Lync Server 2013: Compatibilidad con software de base de datos'
TOCTitle: Compatibilidad con software de base de datos
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48276947
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad con software de base de datos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 admite los sistemas de administración de bases de datos siguientes:

  - **Base de datos back-end de un grupo de servidores front-end, una base de datos de archivado, una base de datos de supervisión, una base de datos de chat persistente y una base de datos para el cumplimiento de chat persistente**
    
      - Software de base de datos Microsoft SQL Server 2008 R2 Enterprise (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2008 R2 Standard (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2012 Enterprise (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2012 Standard (edición de 64 bits) o el último service pack (recomendado)

  - **Base de datos de servidor Standard Edition y Servidor front-end bases de datos**
    
      - Microsoft SQL Server 2012 Express (edición de 64 bits) o el último service pack (recomendado).
        
        Apoyamos el parcheado y actualización de Microsoft SQL Server en Servidores front-end y Servidores Standard Edition. Sin embargo, cuando haga algún tipo de actualización o parche en Servidores front-end, debe cumplir con los requisitos del quórum. Para obtener más información, consulte [Actualización o mejora de los servidores front-end en Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) y [Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    

    > [!NOTE]
    > Lync Server 2013 instala automáticamente Microsoft SQL Server 2012 Express (edición de 64 bits) en cada servidor con Standard Edition y en cada servidor Servidor front-end.



> [!IMPORTANT]  
> <ul>
> <li><p>Lync Server 2013 no admite la edición de 32 bits de SQL Server. Emplee la edición de 64 bits.</p></li>
> <li><p>SQL Server Web Edition y SQL Server Workgroup Edition no son compatibles. No puede usarlos con Lync Server 2013.</p></li>
> <li><p>Lync Server 2013 admite la creación de reflejos de bases de datos nativas.</p></li>
> <li><p>Para usar el rol de servidor de supervisión, instale SQL Server Reporting Services.</p></li>
> </ul>


En un grupo de servidores front-end, la base de datos back-end puede ser un único PC de SQL Server.

> [!IMPORTANT]  
> Si combina bases de datos de Lync Server con otras bases de datos, recomendamos encarecidamente evaluar todos los factores que pueden afectar a la disponibilidad y al rendimiento, así como asegurarse de que, si un nodo provoca un error, el otro nodo pueda administrar la carga. Para comprobar las capacidades de conmutación por error, se recomienda probar todos los escenarios de conmutación por error.



## Información de uso sobre la creación de espejos y la agrupación en clústeres de SQL

Lync Server 2013 permite usar la creación de espejos y la agrupación en clústeres de SQL en las distintas bases de datos de Lync Server. Puede configurar fácilmente la creación de reflejos de SQL con la herramientaGenerador de topologías enLync Server 2013. Los clústeres de conmutación por error de SQL deben configurarse desde SQL Server.

Lync Server 2013 permite usar topologías de creación de reflejos de SQL y agrupación en clústeres de SQL en todas las implementaciones, incluidas las realizadas en entornos vírgenes y en organizaciones que han realizado actualizaciones de versiones anteriores deLync Server.

La agrupación en clústeres de SQL es compatible con la configuración activa/pasiva. Por motivos de rendimiento, el nodo pasivo no debe compartirse con otras instancias de SQL.

Se ofrecen los supuestos de compatibilidad siguientes:

  - Clústeres de conmutación por error de dos nodos para:
    
      - Microsoft SQL Server 2012 Standard (edición de 64 bits) o el último service pack (recomendado)
    
      - Microsoft SQL Server 2008 R2 Standard (edición de 64 bits) o el último service pack (recomendado)

  - Clústeres de conmutación por error de hasta dieciséis nodos para:
    
      - Microsoft SQL Server 2012 Enterprise (edición de 64 bits) o el último service pack (recomendado)
    
      - Software de base de datos Microsoft SQL Server 2008 R2 Enterprise (edición de 64 bits) o el último service pack (recomendado)

Para más información sobre la creación de reflejos de SQL, vea [Alta disponibilidad del servidor back-end en Lync Server 2013](lync-server-2013-back-end-server-high-availability.md). Para más información sobre cómo implementar la agrupación en clústeres de SQL, vea[Configurar la agrupación en clústeres de SQL Server en Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

Para más información sobre procedimientos recomendados relacionados con los clústeres de conmutación por error en SQL Server 2012, vea <http://technet.microsoft.com/es-es/library/hh231721.aspx>. Para más información sobre los clústeres de conmutación por error en SQL Server 2008, vea <http://technet.microsoft.com/es-es/library/ms189134(v=sql.105).aspx>.


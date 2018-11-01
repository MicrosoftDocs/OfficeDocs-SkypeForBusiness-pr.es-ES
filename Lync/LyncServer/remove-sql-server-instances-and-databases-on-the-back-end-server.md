---
title: "Suppression des instances et des BD SQL Server sur le serveur principal"
TOCTitle: "Suppression des instances et des BD SQL Server sur le serveur principal"
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49889031
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar instancias y bases de datos SQL Server en el servidor back-end

 

_**Última modificación del tema:** 2012-10-19_

Debe quitar las bases de datos y las instancias de Microsoft SQL Server después de quitar los servidores con Lync Server 2010 que dependen de ellas o después de reconfigurar los servidores con Lync Server 2010 para que utilicen otra base de datos. Debe realizar el procedimiento descrito en este tema al retirar el servidor SQL Server actual o al reconfigurar el servidor actual con Lync Server 2010 de modo que las bases de datos se vuelvan obsoletas o inaccesibles.

Para quitar las bases de datos o instancias del Servidor de archivado o del Servidor de supervisión, primero debe quitar el rol de servidor. De manera similar, para quitar las instancias o bases de datos del Grupo de servidores front-end, primero debe quitar o reconfigurar el rol del servidor dependiente. Estos procedimientos no distinguen entre bases de datos combinadas o instancias independientes de los servidores. Los procedimientos no se ven afectados por la combinación de bases de datos.

## En esta sección

  - [Quitar la base de datos de SQL Server para un grupo de servidores front-end](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Quitar la base de datos SQL Server en un servidor de supervisión](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Quitar la base de datos de SQL Server para un servidor de archivado](remove-the-sql-server-database-for-an-archiving-server.md)


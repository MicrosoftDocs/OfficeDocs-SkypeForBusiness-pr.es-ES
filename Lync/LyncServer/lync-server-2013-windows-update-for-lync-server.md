---
title: 'Lync Server 2013: Windows Update para Lync Server'
TOCTitle: Windows Update para Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn518337(v=OCS.15)
ms:contentKeyID: 60505981
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows Update para Lync Server 2013

 

_**Última modificación del tema:** 2013-12-05_

Utilice el servicio Windows Update para comprobar con frecuencia si hay actualizaciones y actualizaciones de seguridad y aplicarlas. De este modo, contribuirá a evitar vulnerabilidades en otros componentes del sistema que den pie a que atacantes obtengan acceso a los servidores que ejecutan Microsoft Lync Server 2013 con privilegios de administrador y, por lo tanto, pongan en peligro Lync Server 2013.

Las actualizaciones de Microsoft SQL Server 2008 Express (edición de 64 bits) se ejecutan en cada servidor Lync Server 2013 Standard Edition (para la base de datos back-end) y en todos los demás roles de servidor de Lync Server 2013 (para el almacén de configuración local), a menos que haya actualizado estas bases de datos a SQL Server 2008 R2 Express. Debe considerar estas bases de datos como parte del mantenimiento rutinario de las actualizaciones de seguridad, al igual que SQL Server en la base de datos back-end de un grupo de servidores front-end, la base de datos de supervisión y la base de datos de archivado.

## Procedimiento recomendado

  - Mantenga el equipo actualizado a través del servicio Windows Update.


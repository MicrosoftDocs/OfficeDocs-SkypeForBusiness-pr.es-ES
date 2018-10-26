---
title: 'Lync Server 2013: Introducción general a la implementación'
TOCTitle: Introducción general a la implementación
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48276866
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Introducción general a la implementación para Lync Server 2013

 

_**Última modificación del tema:** 2013-03-12_

La principal diferencia entre Lync Server 2013 Enterprise Edition y Lync Server 2013 Standard Edition es que Standard Edition no admite las características de alta disponibilidad de Enterprise Edition. Para alta disponibilidad, se implementan varios Servidores front-end a un grupo de servidores y el servidor basado en SQL Server se puede reflejar. Con el Enterprise Edition puede elegir combinar o definir un Servidor de mediación independiente. El Servidor de supervisión y el Servidor de archivado pueden usar un servidor independiente que ejecute SQL Server o pueden tener instancias de SQL Server ejecutándose en el servidor de base de datos para los Servidores front-end y los grupos.

Los servidores que ejecutan Lync Server 2013Standard Edition están diseñados para las organizaciones más pequeñas y ubicaciones remotas, localizadas geográficamente fuera de la implementación de la organización principal. Dos servidores Servidor Standard Edition emparejados para conmutación por error en caso de desastres pueden dar soporte hasta 5.000 usuarios hospedados. No se pueden agrupar los Servidores Standard Edition al igual que se pueden agrupar Servidores front-end en Enterprise Edition. Además, la base de datos de SQL Server que usa Standard Edition es una versión de SQL Server Express combinada con el tamaño adecuado para las cargas de trabajo de un Servidor Standard Edition. Eso no quiere decir que todos los roles deben residir en un Servidor Standard Edition. Puede tener Servidores de mediación y Servidores perimetrales independientes. La base de datos de SQL Server para el Almacén de administración central y para los fines de Lync Server 2013 debe residir en el Servidor Standard Edition combinado con el servidor que ejecuta SQL Server. El Servidor de supervisión y el Servidor de archivado usan un servidor independiente con la base de datos de SQL Server.


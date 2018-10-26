---
title: "Usar servidores de chat persistente estirado para la recuperación ante desastres"
TOCTitle: Usar un grupo de servidores de chat persistente estirado para la recuperación ante desastres
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48275701
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar un grupo de servidores de chat persistente estirado para la recuperación ante desastres en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

La solución de recuperación ante desastres para el Servidor de chat persistente está construida en un Grupo de servidores de chat persistente extendido. Esto es similar a la resistencia de sitios metropolitanos en Lync Server 2010; sin embargo, no hay ningún requisito para una red de área local virtual (VLAN) extendida. Al extender el Grupo de servidores de chat persistente, esencialmente configura un grupo de la topología lógicamente, pero coloca físicamente los servidores en el grupo en dos centros de datos diferentes. Configure la creación de reflejo de SQL Server para la base de datos de la misma forma e implemente la base de datos y el reflejo en el mismo centro de datos. Es necesario que configure una base de datos de copia de seguridad en el centro de datos secundario (con un reflejo opcional para proporcionar alta disponibilidad durante la recuperación ante desastres). Se trata de la base de datos de copia de seguridad usada para la conmutación por error durante la recuperación ante desastres.

Si desea conocer los pasos necesarios para configurar la creación de reflejo de SQL Server para alta disponibilidad, vea [Crear un reflejo de SQL Server en Lync Server 2013](lync-server-2013-sql-server-mirroring.md). Para más información sobre la conmutación por error de la base de datos para la recuperación ante desastres, vea [Configurar registro de transacciones de SQL Server para base de datos principal del servidor de chat persistente en Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) y [Configuración del envío de registro de SQL Server entre el reflejo principal y la base de datos secundaria de envío de registro en Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).


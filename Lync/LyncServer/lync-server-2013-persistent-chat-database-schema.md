---
title: 'Lync Server 2013: Esquema de la base de datos de chat persistente'
TOCTitle: Esquema de la base de datos de chat persistente
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48275352
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Esquema de la base de datos de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-18_

Documenta el esquema de la base de datos de Chat persistente en Lync Server 2013 software de comunicaciones.

La base de datos de Chat persistente hace referencia a la base de datos correspondiente a los roles **PersistentChatStore** (correspondientes a la base de datos mgc) y **PersistentChatComplianceStore** (correspondiente a la base de datos mgccomp) del servidor back-end de Lync Server 2013. El objetivo de la publicación de este esquema es para permitirle generar consultas y obtener algunas ideas sobre la creación de informes útiles sobre el uso del chat, los salones activos, las personas que publican más, etc.

> [!IMPORTANT]  
> Nos reservamos el derecho a evolucionar este esquema. Microsoft no ofrece ninguna garantía sobre el mantenimiento de la total compatibilidad con este esquema publicado.



Siga estos procedimientos recomendados:

  - No se admite SELECT\* // porque la lista de columnas puede crecer.

  - No se admiten cambios de esquema generados por el usuario.

  - No se admiten operaciones de escritura.

  - Pruebe las consultas que genere sobre bases de datos de tamaño representativo para garantizar que las consultas se pueden realizar a un nivel que satisface sus necesidades.

## En esta sección

  - [Lista de tablas de servidores de chat persistente en Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lista de tablas de cumplimiento del servidor de chat persistente en Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Detalles de la tabla del servidor de chat persistente en Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Consultas de base de datos del chat persistente de ejemplo para Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)


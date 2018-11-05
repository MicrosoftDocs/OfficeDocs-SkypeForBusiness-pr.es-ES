---
title: 'Lync Server 2013: Alta disponibilidad del servidor back-end'
TOCTitle: Alta disponibilidad del servidor back-end
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48276611
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Alta disponibilidad del servidor back-end en Lync Server 2013

 

_**Última modificación del tema:** 2013-08-12_

Para asegurar una disponibilidad alta para sus servidores back-end, puede usar la creación de reflejos o la agrupación en clústeres de SQL. El uso de una de estas soluciones es opcional, pero se recomienda para mantener la continuidad del negocio de su organización. No se admite la creación de reflejos SQL asincrónica para la disponibilidad alta de servidores back-end en Lync Server 2013. En lo que resta de este documento, la creación de reflejos SQL significa la creación de reflejos SQL sincrónica, salvo que se aclare explícitamente lo contrario.

Puede configurar fácilmente la creación de reflejos de SQL con la herramienta Generador de topologías. Los clústeres de conmutación por error de SQL deben configurarse desde SQL Server.

Si utiliza la creación de reflejos o la agrupación en clústeres de SQL en un grupo que está emparejado con otro grupo front-end para la recuperación ante desastres, debe utilizar la misma solución de alta disponibilidad back-end en ambos grupos. No debe emparejar un grupo que usa la creación de reflejos con un grupo que usa la agrupación en clústeres de SQL.

Cuando implementa la creación de reflejos SQL, todas las bases de datos de Lync Server en el grupo de servidores se reflejan, incluso el Almacén de administración central, si se encuentra en este grupo de servidores, así como la base de datos de la aplicación Grupo de respuesta y la base de datos de la aplicación Estacionamiento de llamadas, si esas aplicaciones se están ejecutando en el grupo.

Con la creación de reflejos SQL, no necesita utilizar almacenamiento compartido para los servidores. Cada servidor guarda su copia de la base de datos en un almacenamiento local.

Puede elegir implementar una creación de reflejos SQL con o sin un testigo. Recomendamos utilizar un testigo porque esto permite que la conmutación por error del servidor back-end sea automática. De lo contrario, un administrador debe invocar manualmente la conmutación por error. Tenga en cuenta que incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.

Si utiliza un testigo, puede utilizar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones que utilizan un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end.

Para obtener más información sobre la compatibilidad de la agrupación en clústeres de SQL, vea [Compatibilidad con software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md). Para obtener información detallada sobre cómo implementar la agrupación en clústeres de SQL, vea [Configurar la agrupación en clústeres de SQL Server en Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

## Tiempo de recuperación de conmutación por error automática de servidor back-end con la creación de reflejos de SQL

Para la conmutación por error automática de back-end con la creación de reflejos de SQL, el destino de ingeniería para objetivo de tiempo de recuperación (RTO) es de 5 minutos. Debido a la creación de reflejos SQL sincrónica, no prevemos pérdida de datos durante los errores en el servidor back-end excepto en raras ocasiones, cuando tanto los servidores front-end y los servidores back-end dejan de funcionar simultáneamente mientras se mueven datos entre los servidores. El destino de ingeniería para objetivo de punto de recuperación (RPO) es de 5 minutos.

## Experiencia del usuario durante un error en un servidor back-end con la creación de reflejos de SQL

La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.

Si usa la la creación de reflejos de SQL y tiene un testigo configurado y se produce un error en la entidad principal, la conmutación por error del servidor back-end se produce automática y rápidamente. Los usuarios activos no deberían notar muchas interrupciones en sus sesiones en curso.

Si no hay ningún testigo configurado, tomará algún tiempo que el administrador invoque manualmente la conmutación por error. Durante ese tiempo, los usuarios activos probablemente lo notarán. Continuarán con sus sesiones durante unos minutos y, a continuación, se los cambiará al modo de resistencia, lo que significa que no podrán realizar las tareas que requieran un cambio persistente en Lync Server (tales como agregar un contacto).

Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.


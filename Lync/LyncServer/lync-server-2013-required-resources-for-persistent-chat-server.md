---
title: "Lync Server 2013 : Ressources req. pour le serveur de conversation permanente"
TOCTitle: Recursos requeridos
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48276512
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Recursos requeridos para el servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2016-02-05_

La alta disponibilidad y la recuperación ante desastres para el Servidor de chat persistente requieren recursos adicionales aparte de lo que normalmente se necesita para una operación completa. Antes de configurar el Servidor de chat persistente para alta disponibilidad y recuperación ante desastres, asegúrese de que tiene los siguientes recursos además de lo que se necesita para el funcionamiento estándar del Servidor de chat persistente. Para más información de configuración, consulte [Configurar servidor de chat persistente en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Una instancia de base de datos dedicada ubicada en el mismo centro de datos físico en el que se ubica el front-end principal del servicio de Servidor de chat persistente. Esta base de datos servirá como el reflejo de SQL Server para la base de datos principal de Chat persistente. Opcionalmente, designe un SQL Server para que funcione el testigo de creación de reflejo si desea una conmutación por error automatizada para la base de datos reflejada.

  - Una instancia de base de datos dedicada ubicada en el otro centro de datos físico. Esta base de datos servirá como la base de datos secundaria de trasvase de registros de SQL Server para la base de datos en el centro de datos principal.

  - Una instancia de base de datos dedicada que sirva como el reflejo de SQL Server para la base de datos secundaria. Opcionalmente, designe un SQL Server que sirva como testigo de creación de reflejo. Ambos deben estar ubicados en el mismo centro de datos físico que la base de datos secundaria.

  - Si está habilitado el cumplimiento de Servidor de chat persistente, se necesitan tres instancias de base de datos dedicadas adicionales. Su distribución es la misma que la descrita anteriormente para la base de datos de Chat persistente. Aunque es posible que la base de datos de cumplimiento comparta la misma instancia de SQL Server que la base de datos de Chat persistente, recomendamos usar instancias independientes para la alta disponibilidad y la recuperación ante desastres.

  - Se debe crear y designar un recurso compartido de archivos para los registros de transacciones de trasvase de registros de SQL Server. Todos los servidores SQL Server de ambos centros de datos que ejecuten bases de datos de Chat persistente deben tener acceso de lectura y escritura para este recurso compartido de archivos. Este recurso compartido no está designado como parte del rol FileStore.

  - Una carpeta en el servidor de base de datos secundario que sirva como carpeta de destino para el registro de transacciones de SQL Server que se copia desde el recurso compartido del servidor principal.

Las figuras siguientes proporcionan ejemplos acerca de cómo todo el Grupo de servidores de chat persistente se puede configurar en dos topologías de grupo de servidores estirados.

  - Grupo de servidores de chat persistente donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja

  - Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta

La figura siguiente muestra una topología de Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja.

**Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja**

![Examen de configuración de alto ancho de banda del grupo de servidores de chat persistente](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen de configuración de alto ancho de banda del grupo de servidores de chat persistente")

La figura siguiente muestra una topología de Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta.

**Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta**

![Examen de configuración de bajo ancho de banda de grupo de servidores de chat persistente](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen de configuración de bajo ancho de banda de grupo de servidores de chat persistente")


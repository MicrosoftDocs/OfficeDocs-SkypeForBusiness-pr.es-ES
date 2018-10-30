---
title: 'Lync Server 2013: Información general del archivado'
TOCTitle: Información general del archivado
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48274627
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general del archivado en Lync Server 2013

 

_**Última modificación del tema:** 2013-09-30_

El archivado en Lync Server 2013 permite archivar las comunicaciones que se envían a través de Lync Server 2013.

Puede implementar el archivado como parte de su implementación inicial de Lync Server 2013 o puede agregarlo a una implementación existente. Para utilizar las bases de datos de archivado de Lync Server 2013 (bases de datos de SQL Server) para almacenamiento de datos de archivado, utilice Generador de topologías para agregar las bases de datos a su topología y, a continuación, publique la topología nuevamente. Si todos los usuarios están hospedados en Exchange 2013 y tienen sus buzones de correo en espera in situ, no necesita actualizar su topología, sino que solamente necesitará habilitar la integración de Microsoft Exchange para almacenar los datos archivados en Exchange 2013.

Al implementar el archivado, debe configurarlo para especificar qué se debe archivar. De manera predeterminada, nada se archiva. Configure y administre el archivado con Panel de control de Lync Server 2013. Puede implementar el archivado para las comunicaciones internas, las comunicaciones externas o ambas. Puede configurar las opciones de archivado para la organización completa y, de manera opcional, para sitios específicos, grupos de servidores específicos y usuarios y grupos de usuarios específicos. Para obtener información acerca de la determinación de las opciones adecuadas para su organización, vea [Definir los requisitos para archivado en Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) en la documentación sobre planeación. Para obtener información sobre cómo se implementan las directivas y configuraciones del archivado y detalles sobré qué información se puede archivar, vea [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre planeación, la documentación sobre implementación o la documención de operaciones.


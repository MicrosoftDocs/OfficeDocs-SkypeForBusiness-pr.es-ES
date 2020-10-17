---
title: 'Lync Server 2013: información general sobre el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1bbb6e5a94aad896e977145df56ea196277adf9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522237"
---
# <a name="overview-of-archiving-in-lync-server-2013"></a>Información general sobre el archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-30_

El archivado en Lync Server 2013 proporciona una forma de archivar las comunicaciones que se envían a través de Lync Server 2013.

Puede implementar el archivado como parte de la implementación inicial de Lync Server 2013 o puede agregarlo a una implementación existente. Para usar las bases de datos de archivado de Lync Server 2013 (bases de datos de SQL Server) para el almacenamiento de datos de archivado, use el generador de topologías para agregar las bases de datos a la topología y, a continuación, vuelva a publicar la topología. Si todos los usuarios están hospedados en Exchange 2013 y tienen buzones colocados en In-Place, no es necesario actualizar la topología, pero solo es necesario habilitar la integración de Microsoft Exchange para almacenar datos archivados en Exchange 2013.

Al implementar el archivado, debe configurarlo para especificar qué se debe archivar. De manera predeterminada, nada se archiva. Puede configurar y administrar el archivado mediante el panel de control de Lync Server 2013. Puede implementar el archivado para las comunicaciones internas, las comunicaciones externas o ambas. Puede configurar las opciones de archivado para la organización completa y, de manera opcional, para sitios específicos, grupos de servidores específicos y usuarios y grupos de usuarios específicos. Para obtener información detallada sobre cómo determinar las opciones adecuadas para su organización, consulte definición de los [requisitos para el archivado en Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) en la documentación referente a la planeación. Para obtener más información sobre cómo se implementan las directivas de archivado y las configuraciones, y sobre qué información se puede archivar o no, vea [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.

</div>

<span> </span>

</div>

</div>

</div>


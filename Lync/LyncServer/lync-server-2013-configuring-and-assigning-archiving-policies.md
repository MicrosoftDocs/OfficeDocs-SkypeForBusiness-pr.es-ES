---
title: 'Lync Server 2013: configuración y asignación de directivas de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7db876d03f7322fae5f3a55f88708fe4165a20ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Configuración y asignación de directivas de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

En Lync Server 2013, las directivas se usan para habilitar y deshabilitar el archivado de comunicaciones internas y comunicaciones externas para los usuarios hospedados en Lync Server 2013. Esto incluye las siguientes directivas de archivado:

  - Una directiva global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Directivas opcionales de nivel de sitio y de usuario que puede crear y usar para especificar cómo se implementa el archivado para sitios o usuarios específicos.

Las directivas de archivado se configuran inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar directivas después de la implementación. En el panel de control de Lync Server 2013, puede usar la página **Directiva de archivado** del grupo **archivado y supervisión** para administrar las directivas en el nivel global, en el nivel de sitio y en el nivel de usuario.

<div>


> [!NOTE]  
> Para controlar la implementación del archivado, debe especificar opciones en las configuraciones de archivado, por ejemplo, si se deben archivar las sesiones de MI o de conferencia, el uso del modo crítico y las opciones de depuración. De manera predeterminada, no hay opciones habilitadas en la configuración de archivado global ni ninguna otra configuración de archivado de nivel de grupo. Debe especificar todas las opciones correspondientes en las configuraciones de archivado antes de habilitar el archivado para las comunicaciones internas o externas en las directivas de archivado. Para obtener más información, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">administrar las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos</A> de servidores en la documentación de operaciones.<BR>Si integra el almacenamiento de Lync Server con el almacenamiento de Exchange 2013, las directivas de usuario de Exchange tienen prioridad sobre las directivas de archivado de Lync Server 2013, pero solo para los usuarios hospedados en Exchange 2013 cuyos buzones se han puesto en conservación local.



</div>

Para obtener más información sobre cómo se implementan las directivas, incluida la jerarquía de directivas, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación referente a la planeación, la implementación o las operaciones. Para obtener más información sobre cómo administrar directivas tras la implementación, consulte [Administración del archivado de comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) en la documentación referente a las operaciones.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración de la directiva global para el archivado en Lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Configuración de directivas de sitio para archivado en Lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Configuración de directivas de archivado para usuarios en Lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


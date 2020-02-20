---
title: 'Lync Server 2013: configuración de las opciones de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 873b7775c889f5d866e21f04c1f154a3158ea99d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Configurar las opciones de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

En el panel de control de Lync Server 2013, se usan configuraciones de archivado para especificar cómo se implementa el archivado. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Unas configuraciones en el nivel de sitio y de grupo que se pueden crear y usar para especificar cómo se implementa el archivado en sitios o grupos determinados.

Las configuraciones de archivado se instalan inicialmente al implementar el archivado, pero podrá cambiar, agregar y eliminar las configuraciones después de la implementación. En el panel de control de Lync Server 2013, puede usar la página **configuración de archivado** del grupo **archivado y supervisión** para administrar las configuraciones en el nivel global, el nivel de sitio y el nivel de grupo. Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones. Para obtener más información sobre cómo administrar las configuraciones después de la implementación, consulte [Managing archiving Configurations in Lync Server 2013 for your Organization, Sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) en la documentación de operaciones.

<div>


> [!NOTE]  
> Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado para las comunicaciones internas, para las comunicaciones externas o para los usuarios hospedados en Lync Server 2013. De forma predeterminada, el archivado no está habilitado ni para la comunicación interna ni para la externa. Antes de habilitar el archivado en las directivas, debe especificar la configuración de archivado pertinente para su implementación y, de manera opcional, para sitios y grupos específicos, como se describe en esta sección. Para obtener más información sobre cómo habilitar el archivado, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuración y asignación de directivas de archivado en Lync Server 2013</A> en la documentación sobre implementación.<BR>Si no usa la integración de Microsoft Exchange para todos los usuarios de la implementación, debe configurar las directivas de archivado para especificar si desea habilitar el archivado para las comunicaciones internas, para las comunicaciones externas o para ambas. De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas de archivado de datos al usar las bases de datos de archivado de Lync Server 2013. Antes de habilitar el archivado en ninguna directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, si lo desea, para sitios y grupos de servidores concretos, como se describe en este apartado. Para obtener más información sobre cómo habilitar el archivado para su uso con las bases de datos de archivado de Lync Server 2013, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and Assigning policies in Lync server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar las opciones de archivado en el nivel global en Lync Server 2013](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Configurar las opciones de archivado para un sitio en Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Configuración de opciones de archivado para un grupo de servidores en Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


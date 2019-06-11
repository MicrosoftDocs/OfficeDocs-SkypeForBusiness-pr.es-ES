---
title: 'Lync Server 2013: configuración de las opciones de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98356b53940c6189abac5a4b554769093f84dd2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Configuración de las opciones de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

En el panel de control de Lync Server 2013, se usan configuraciones de archivado para especificar cómo se implementa el archivado. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Configuraciones de nivel de sitio y de grupo opcionales que puede crear y usar para especificar cómo se implementa el archivado para grupos o sitios específicos.

Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación. En el panel de control de Lync Server 2013, puede usar la página **configuración** de archivado del grupo **archivado y supervisión** para administrar las configuraciones a nivel global, nivel de sitio y nivel de grupo. Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación documentación u operación. Para más información sobre cómo administrar las configuraciones después de la implementación, consulte [administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) en la documentación de operaciones.

<div>


> [!NOTE]  
> Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado de las comunicaciones internas, de las comunicaciones externas o de ambos para los usuarios alojados en Lync Server 2013. De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas. Antes de habilitar el archivado en cualquier directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, opcionalmente, para determinados sitios y grupos, tal y como se describe en esta sección. Para obtener más información sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar y asignar directivas de archivado en Lync Server 2013</A> en la documentación de implementación.<BR>Si no usa la integración de Microsoft Exchange para todos los usuarios de su implementación, debe configurar las directivas de archivado para especificar si desea habilitar el archivado de las comunicaciones internas, de las comunicaciones externas o de ambos. De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas para el archivado de datos al usar las bases de datos de archivado de Lync Server 2013. Antes de habilitar el archivado en cualquier directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, opcionalmente, para determinados sitios y grupos, tal y como se describe en esta sección. Para obtener más información sobre cómo habilitar el archivado para su uso con bases de datos de archivado de Lync Server 2013, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuración y asignación de directivas de archivado en Lync server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar las opciones de archivado en el nivel global de Lync Server 2013](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Configuración de las opciones de archivado de un sitio en Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Configuración de las opciones de archivado de un grupo en Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


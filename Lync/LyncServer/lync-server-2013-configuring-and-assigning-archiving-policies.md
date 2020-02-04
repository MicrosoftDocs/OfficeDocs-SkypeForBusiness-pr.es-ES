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
ms.openlocfilehash: 0d8cfb5b446456d99750529d883172ed3cb56e3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Configurar y asignar directivas de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

En Lync Server 2013, se usan directivas para habilitar y deshabilitar el archivado de comunicaciones internas y comunicaciones externas para los usuarios alojados en Lync Server 2013. Esto incluye las siguientes directivas de archivado:

  - Una directiva global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Directivas opcionales a nivel de sitio y de usuario que puede crear y usar para especificar cómo se implementa el archivado para usuarios o sitios específicos.

Inicialmente, debe configurar las directivas de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar directivas después de la implementación. En el panel de control de Lync Server 2013, puede usar la página **Directiva de archivado** del grupo **archivado y supervisión** para administrar directivas a nivel global, nivel de sitio y nivel de usuario.

<div>


> [!NOTE]  
> Para controlar la implementación de archivado, debe especificar las opciones para archivar las configuraciones, por ejemplo, si desea archivar la mensajería instantánea o la Conferencia, el uso del modo crítico y las opciones de depuración. De forma predeterminada, no se habilita ninguna opción en la configuración global de archivado ni en ninguna configuración de archivado de sitios o grupos. Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado. Para obtener más información, vea <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos</A> en la documentación de operaciones.<BR>Si integra el almacenamiento de Lync Server con el almacenamiento de Exchange 2013, las directivas de usuario de Exchange prevalecen sobre las directivas de archivado de Lync Server 2013, pero solo para los usuarios alojados en Exchange 2013 que hayan puesto sus buzones en conservación local.



</div>

Para obtener más información sobre cómo se implementan las directivas, incluida la jerarquía de directivas, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones. Para obtener detalles sobre cómo administrar directivas después de la implementación, vea [administrar el archivado de comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) en la documentación de operaciones.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración de la directiva global para archivar en Lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Configurar directivas de sitio para archivar en Lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Configuración de directivas de archivado para usuarios en Lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


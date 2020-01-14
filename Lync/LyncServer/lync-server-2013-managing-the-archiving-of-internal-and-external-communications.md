---
title: Administrar el archivado de las comunicaciones internas y externas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891318ba677891916af678b74365026d20d69016
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Administrar el archivado de comunicaciones internas y externas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

En Lync Server 2013, se usan directivas de archivado para habilitar y deshabilitar el archivado de comunicaciones internas y comunicaciones externas si no se usa la integración de Microsoft Exchange o si hay usuarios que no están alojados en Exchange 2013 con sus buzones puestos en Conservación local. Esto incluye las siguientes directivas de archivado:

  - Una directiva global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Directivas opcionales a nivel de sitio y de usuario que puede crear y usar para especificar cómo se implementa el archivado para usuarios o sitios específicos.

Inicialmente, debe configurar las directivas de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar directivas después de la implementación. En el panel de control de Lync Server 2013, puede usar la página **Directiva de archivado** del grupo **archivado y supervisión** para administrar directivas a nivel global, nivel de sitio y nivel de usuario. Si integra el almacenamiento de Lync Server con el almacenamiento de Exchange 2013, las directivas de usuario de Exchange tienen prioridad sobre las directivas de archivado de Lync Server 2013.

Para obtener más información sobre cómo se implementan las directivas, incluida la jerarquía de directivas, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.

<div>


> [!NOTE]
> Para controlar la implementación de archivado, debe especificar las opciones para archivar las configuraciones, por ejemplo, si desea archivar la mensajería instantánea o la Conferencia, el uso del modo crítico y las opciones de depuración. De forma predeterminada, no se habilita ninguna opción en la configuración global de archivado ni en ninguna configuración de archivado de sitios o grupos. Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado. Para obtener más información, vea <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos</A> en la documentación de operaciones.<BR>Si habilita la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013 y si sus buzones se colocan en la retención local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Crear una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de las comunicaciones internas o externas para usuarios o sitios específicos](lync-server-2013-create-archiving-policy-sites-users.md)

  - [Cambiar una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de comunicaciones internas o externas para la organización, los sitios o los usuarios](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [Aplicar una directiva de archivado a los usuarios en Lync Server 2013](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Eliminar una directiva de archivado en Lync Server 2013](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


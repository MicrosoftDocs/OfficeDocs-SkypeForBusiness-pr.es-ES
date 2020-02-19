---
title: 'Lync Server 2013: habilitar la Directiva del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8e41342d50a7d056cdb00c328a912bb6dab6378
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Habilitar la Directiva de servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En el panel de control de Lync Server 2013, puede usar la página **Directiva de chat persistente** del grupo **chat persistente** para administrar directivas a nivel global, de grupo, de sitio o de usuario, incluida la configuración de la directiva global predeterminada y la creación de una o varias directivas de usuario y de sitio adicionales para la implementación. Si un usuario está habilitado para el servidor de chat persistente por directiva, el entorno del servidor de chat persistente aparece en el cliente de Lync 2013.

<div>


> [!NOTE]  
> En la topología, las directivas de sitio del servidor de chat persistente se aplican de forma global, por grupo de usuarios o por sitio de usuario o por usuario.



</div>

La directiva global se crea automáticamente al implementar el servidor de chat persistente y se puede configurar, pero no eliminar. Debido a que la política global se aplica a todos los usuarios, no debe configurarse para cada usuario.

Puede crear y configurar varias directivas de sitio y de usuario que, junto con la directiva global, habilitan a los usuarios para el servidor de chat persistente. Las directivas del servidor de chat persistente del sitio y del grupo invalidan la Directiva del servidor de chat persistente global, pero solo para los usuarios de ese sitio. Las directivas de usuario anulan las directivas globales, de grupo y de sitio para los usuarios a los que se asigna la directiva de usuario.

<div>


> [!NOTE]  
> Para configurar y usar el servidor de chat persistente, primero debe usar el generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a la implementación en Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configure la directiva global para chat persistente en Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Crear una directiva de sitio para chat persistente en Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Crear una directiva de usuario para chat persistente en Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Aplicar una directiva de chat persistente a un usuario o a un grupo de usuarios en Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


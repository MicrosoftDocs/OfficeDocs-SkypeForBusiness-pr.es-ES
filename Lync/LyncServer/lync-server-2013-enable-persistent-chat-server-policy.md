---
title: 'Lync Server 2013: Habilitar la directiva de servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58e71cd92182fc9f68d272ba23079677983b399
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Habilitar la directiva de servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

En el panel de control de Lync Server 2013, puede usar la página de la **Directiva de chat** persistente del grupo **chat persistente** para administrar directivas a nivel global, de grupo, de sitio o de usuario, incluida la configuración de la directiva global predeterminada y la creación de una o más directivas de usuario y sitio adicionales para su implementación. Si un usuario está habilitado para el servidor de chat persistente por directiva, el entorno del servidor de chat persistente aparece en el cliente de Lync 2013.

<div>


> [!NOTE]  
> En la topología, se aplican globalmente las directivas del sitio servidor de chat persistentes, por grupo de usuarios o por sitio o por usuario.



</div>

La directiva global se crea automáticamente al implementar un servidor de chat persistente, y puede configurarse, pero no eliminarse. Debido a que la política global se aplica a todos los usuarios, no hay que configurarla para cada usuario.

Puede crear y configurar varias directivas de sitio y de usuario que, junto con la directiva global, permitan a los usuarios usar el servidor de chat persistente. Las directivas del servidor de chat persistente del sitio y del grupo invalidan la Directiva del servidor de chat persistente global, pero solo para los usuarios de ese sitio. Las directivas de usuario reemplazan a las directivas globales, de grupo y de sitio para los usuarios que tengan asignada esa directiva de usuario.

<div>


> [!NOTE]  
> Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología. Para obtener más información, vea <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Agregar un servidor de chat persistente a su implementación en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar la directiva global para chat persistente en Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Crear una directiva de sitio para chat persistente en Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Crear una directiva de usuario para chat persistente en Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Aplicar una directiva de chat persistente a un usuario o grupo de usuarios en Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


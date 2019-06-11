---
title: 'Lync Server 2013: Configurar salones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08b7cb0146f96b151af021a63ef97a485a0a9dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Configurar salones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

La configuración de los salones de chat persistentes la controlan normalmente los usuarios u otros equipos centrales mediante la interfaz de línea de comandos de Windows PowerShell; por lo general, los administradores no administran salones de chat. Sin embargo, si tiene que crear y administrar salones de chat, puede usar la interfaz de línea de comandos de Windows PowerShell o agregarse como miembro a un salón de chat y usar el cliente de Lync 2013.

Para obtener detalles sobre la configuración de salones de chat con la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salas" en [configurar el servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

<div>

## <a name="managing-data-in-chat-rooms"></a>Administración de datos en salones de chat

El servidor de chat persistente permite a los usuarios colaborar mediante la publicación de mensajes en salas de chat persistentes. Los datos se conservan en el servidor y los miembros de la sala pueden tener acceso a los datos, incluidos los datos históricos. Sin embargo, los usuarios con diferentes roles tienen acceso diferente a los datos persistentes, como se describe en la siguiente lista.

  - Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado. O bien, pueden quitar o reemplazar mensajes que se consideren inapropiados para un salón de chat en particular.

  - Los usuarios finales, incluidos los autores de los mensajes, no pueden eliminar contenido de ningún salón de chat.

  - Los administradores de salones de chat pueden deshabilitar salas, pero no pueden eliminar salas. Solo los administradores pueden eliminar un salón de chat una vez que se ha creado.

Cuando se elimina un mensaje, no se puede deshacer la acción. Sin embargo, los mensajes eliminados se pueden restaurar si hay una copia de seguridad. Si un servidor de cumplimiento de chat persistente está habilitado, los mensajes antiguos se conservan en la base de datos de cumplimiento.

<div>


> [!NOTE]  
> Este uso de datos del salón de chat se aplica a Lync Server 2013, aplicación API de servidor de chat persistente, excepto en el caso de que intervenga el rol de administrador. La API del servidor de chat persistente no se puede usar para realizar ninguna de las operaciones del administrador. Debe realizar estas operaciones en el shell de administración de Lync Server.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


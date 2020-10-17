---
title: 'Lync Server 2013: configurar salas'
description: 'Lync Server 2013: configurar salas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9f5b2ece8cf436fe69c000da73871cb92686d82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542776"
---
# <a name="configure-rooms-in-lync-server-2013"></a>Configurar salas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

La configuración de salones de chat persistente suele estar controlada por los usuarios u otros equipos centrales mediante la interfaz de línea de comandos de Windows PowerShell; un administrador no suele administrar los salones de chat. Sin embargo, si tiene que crear y administrar salones de chat, puede usar la interfaz de línea de comandos de Windows PowerShell o agregarse como miembro a un salón de chat y usar el cliente de Lync 2013.

Para obtener más información sobre cómo configurar salones de chat mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salones" en [Configuring persistent chat Server by Using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

<div>

## <a name="managing-data-in-chat-rooms"></a>Administración de datos en salones de chat

El servidor de chat persistente permite que los usuarios colaboren publicando mensajes en salones de chat persistente. Los datos persisten en el servidor, y los miembros del salón pueden obtener acceso a los datos, incluido el historial. No obstante, los usuarios con diferentes roles pueden tener un acceso diferente a los datos de persistencia, como se describe en la lista siguiente.

  - Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado. También pueden quitar o reemplazar mensajes que se consideren inapropiados para un salón de chat específico.

  - Los usuarios finales, incluidos los autores de mensajes, no pueden eliminar contenido de ningún salón de chat.

  - Los administradores de los salones de chat pueden deshabilitar salones, pero no pueden eliminarlos. Solo los administradores pueden eliminar un salón de chat una vez creado.

Si se elimina un mensaje, no se puede deshacer la acción. Sin embargo, los mensajes eliminados pueden restaurarse si hay una copia de seguridad. Si un servidor de cumplimiento de chat persistente está habilitado, los mensajes antiguos se conservan en la base de datos de cumplimiento.

<div>


> [!NOTE]  
> Este uso de datos del salón de chat se aplica a la aplicación de API del servidor de chat persistente de Lync Server 2013, excepto en el caso de que el rol de administrador esté implicado. La API del servidor de chat persistente no se puede usar para realizar ninguna de las operaciones del administrador. Debe realizar estas operaciones en el shell de administración de Lync Server.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


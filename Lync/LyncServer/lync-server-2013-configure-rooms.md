---
title: 'Lync Server 2013: Configurar salones'
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
ms.openlocfilehash: 06fea4fcda27eaedd671d833a4f53ed0ddec67c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="5ff12-102">Configurar salones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ff12-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ff12-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5ff12-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5ff12-104">La configuración de los salones de chat persistentes la controlan normalmente los usuarios u otros equipos centrales mediante la interfaz de línea de comandos de Windows PowerShell; por lo general, los administradores no administran salones de chat.</span><span class="sxs-lookup"><span data-stu-id="5ff12-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="5ff12-105">Sin embargo, si tiene que crear y administrar salones de chat, puede usar la interfaz de línea de comandos de Windows PowerShell o agregarse como miembro a un salón de chat y usar el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5ff12-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="5ff12-106">Para obtener detalles sobre la configuración de salones de chat con la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salas" en [configurar el servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="5ff12-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="5ff12-107">Administración de datos en salones de chat</span><span class="sxs-lookup"><span data-stu-id="5ff12-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="5ff12-108">El servidor de chat persistente permite a los usuarios colaborar mediante la publicación de mensajes en salas de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="5ff12-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="5ff12-109">Los datos se conservan en el servidor y los miembros de la sala pueden tener acceso a los datos, incluidos los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="5ff12-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="5ff12-110">Sin embargo, los usuarios con diferentes roles tienen acceso diferente a los datos persistentes, como se describe en la siguiente lista.</span><span class="sxs-lookup"><span data-stu-id="5ff12-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="5ff12-111">Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado.</span><span class="sxs-lookup"><span data-stu-id="5ff12-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="5ff12-112">O bien, pueden quitar o reemplazar mensajes que se consideren inapropiados para un salón de chat en particular.</span><span class="sxs-lookup"><span data-stu-id="5ff12-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="5ff12-113">Los usuarios finales, incluidos los autores de los mensajes, no pueden eliminar contenido de ningún salón de chat.</span><span class="sxs-lookup"><span data-stu-id="5ff12-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="5ff12-114">Los administradores de salones de chat pueden deshabilitar salas, pero no pueden eliminar salas.</span><span class="sxs-lookup"><span data-stu-id="5ff12-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="5ff12-115">Solo los administradores pueden eliminar un salón de chat una vez que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="5ff12-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="5ff12-116">Cuando se elimina un mensaje, no se puede deshacer la acción.</span><span class="sxs-lookup"><span data-stu-id="5ff12-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="5ff12-117">Sin embargo, los mensajes eliminados se pueden restaurar si hay una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5ff12-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="5ff12-118">Si un servidor de cumplimiento de chat persistente está habilitado, los mensajes antiguos se conservan en la base de datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5ff12-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ff12-119">Este uso de datos del salón de chat se aplica a Lync Server 2013, aplicación API de servidor de chat persistente, excepto en el caso de que intervenga el rol de administrador.</span><span class="sxs-lookup"><span data-stu-id="5ff12-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="5ff12-120">La API del servidor de chat persistente no se puede usar para realizar ninguna de las operaciones del administrador.</span><span class="sxs-lookup"><span data-stu-id="5ff12-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="5ff12-121">Debe realizar estas operaciones en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5ff12-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


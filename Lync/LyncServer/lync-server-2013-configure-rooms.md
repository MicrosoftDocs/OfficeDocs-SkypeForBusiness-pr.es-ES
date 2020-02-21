---
title: 'Lync Server 2013: configurar salas'
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
ms.openlocfilehash: 7e78401d0f72f3b29f50453f49f7d7eb66811715
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="9a6d2-102">Configurar salas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a6d2-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a6d2-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9a6d2-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9a6d2-104">La configuración de salones de chat persistente suele estar controlada por los usuarios u otros equipos centrales mediante la interfaz de línea de comandos de Windows PowerShell; un administrador no suele administrar los salones de chat.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="9a6d2-105">Sin embargo, si tiene que crear y administrar salones de chat, puede usar la interfaz de línea de comandos de Windows PowerShell o agregarse como miembro a un salón de chat y usar el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="9a6d2-106">Para obtener más información sobre cómo configurar salones de chat mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salones" en [Configuring persistent chat Server by Using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="9a6d2-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="9a6d2-107">Administración de datos en salones de chat</span><span class="sxs-lookup"><span data-stu-id="9a6d2-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="9a6d2-108">El servidor de chat persistente permite que los usuarios colaboren publicando mensajes en salones de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="9a6d2-109">Los datos persisten en el servidor, y los miembros del salón pueden obtener acceso a los datos, incluido el historial.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="9a6d2-110">No obstante, los usuarios con diferentes roles pueden tener un acceso diferente a los datos de persistencia, como se describe en la lista siguiente.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="9a6d2-p103">Los administradores pueden eliminar contenido antiguo (por ejemplo, contenido que fue publicado antes de una determinada fecha) de cualquier salón de chat para conservar la base de datos e impedir que crezca demasiado. También pueden quitar o reemplazar mensajes que se consideren inapropiados para un salón de chat específico.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-p103">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large. Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="9a6d2-113">Los usuarios finales, incluidos los autores de mensajes, no pueden eliminar contenido de ningún salón de chat.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="9a6d2-p104">Los administradores de los salones de chat pueden deshabilitar salones, pero no pueden eliminarlos. Solo los administradores pueden eliminar un salón de chat una vez creado.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-p104">Chat room managers can disable rooms, but cannot delete rooms. Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="9a6d2-116">Si se elimina un mensaje, no se puede deshacer la acción.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="9a6d2-117">Sin embargo, los mensajes eliminados pueden restaurarse si hay una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="9a6d2-118">Si un servidor de cumplimiento de chat persistente está habilitado, los mensajes antiguos se conservan en la base de datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a6d2-119">Este uso de datos del salón de chat se aplica a la aplicación de API del servidor de chat persistente de Lync Server 2013, excepto en el caso de que el rol de administrador esté implicado.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="9a6d2-120">La API del servidor de chat persistente no se puede usar para realizar ninguna de las operaciones del administrador.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="9a6d2-121">Debe realizar estas operaciones en el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a6d2-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


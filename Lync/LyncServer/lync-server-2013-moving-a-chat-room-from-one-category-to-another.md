---
title: 'Lync Server 2013: Mover un salón de chat de una categoría a otra'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f9774e53321ff6fe667b3b8c8dcfe0e78bcdaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="4b6f3-102">Mover un salón de chat de una categoría a otra en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b6f3-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b6f3-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4b6f3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4b6f3-104">Le recomendamos que no cambie la categoría de un salón de chat persistente una vez que se haya creado el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="4b6f3-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="4b6f3-105">Sin embargo, si el administrador del salón de chat tiene privilegios de **creador** en otra categoría, puede mover la sala de una categoría a otra.</span><span class="sxs-lookup"><span data-stu-id="4b6f3-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="4b6f3-106">El salón no se elimina y se vuelve a crear.</span><span class="sxs-lookup"><span data-stu-id="4b6f3-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="4b6f3-107">Es un cambio de asociación dentro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4b6f3-107">It is a change of association within the database.</span></span>

<span data-ttu-id="4b6f3-108">El cambio de una categoría de salón de chat debe hacerse casi nunca.</span><span class="sxs-lookup"><span data-stu-id="4b6f3-108">Changing a chat room category should be done rarely.</span></span> <span data-ttu-id="4b6f3-109">Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se purgan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría.</span><span class="sxs-lookup"><span data-stu-id="4b6f3-109">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="4b6f3-110">Por ejemplo, si un usuario era miembro del salón y ya no es un **AllowedMember** de la nueva categoría, se modificará la pertenencia a la sala y el usuario se eliminará del salón.</span><span class="sxs-lookup"><span data-stu-id="4b6f3-110">For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="4b6f3-111">Para obtener detalles sobre cómo mover un salón de chat con la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salas" en [configurar el servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="4b6f3-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="4b6f3-112">Para obtener más información sobre cómo configurar salones de chat, consulte [configurar salas en Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="4b6f3-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


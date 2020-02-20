---
title: 'Lync Server 2013: mover un salón de chat de una categoría a otra'
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
ms.openlocfilehash: 5bde33220c13b5a484f66131ce6090d57d3b9bae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="d0a1e-102">Mover un salón de chat de una categoría a otra en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0a1e-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0a1e-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d0a1e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d0a1e-104">Le recomendamos que no cambie la categoría de un salón de chat persistente una vez que se haya creado el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="d0a1e-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="d0a1e-105">Sin embargo, si el administrador del salón de chat tiene privilegios de **Creador** en otra categoría, puede mover el salón de una categoría a otra.</span><span class="sxs-lookup"><span data-stu-id="d0a1e-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="d0a1e-106">El salón no se eliminará y volverá a crearse.</span><span class="sxs-lookup"><span data-stu-id="d0a1e-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="d0a1e-107">Es un cambio de asociación dentro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d0a1e-107">It is a change of association within the database.</span></span>

<span data-ttu-id="d0a1e-p102">Ocasionalmente podrá realizarse un cambio de categoría del salón de chat. Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se eliminan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría. Por ejemplo, si un usuario era miembro del salón y ya no es un **AllowedMember** en la nueva categoría, la pertenencia del salón se modificará y el usuario se eliminará de el.</span><span class="sxs-lookup"><span data-stu-id="d0a1e-p102">Changing a chat room category should be done rarely. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="d0a1e-111">Para obtener información detallada sobre cómo mover un salón de chat mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salones" en [Configuring persistent chat Server by Using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="d0a1e-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="d0a1e-112">Para obtener más información sobre cómo configurar salones de chat, vea [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d0a1e-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


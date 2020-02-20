---
title: Administrar salones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc3f9e2c680d2812c11c41a551132d580de17f46
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a><span data-ttu-id="1e31a-102">Administrar salones</span><span class="sxs-lookup"><span data-stu-id="1e31a-102">Manage rooms</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e31a-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1e31a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1e31a-104">Para crear un nuevo salón de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="1e31a-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e31a-105">-PersistentChatPoolFqdn no es necesario si se cumple una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1e31a-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1e31a-106">Hay un solo grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1e31a-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="1e31a-107">Proporciona un poolFqdn a la categoría.</span><span class="sxs-lookup"><span data-stu-id="1e31a-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="1e31a-108">Proporciona un poolFqdn para agregar un salón.</span><span class="sxs-lookup"><span data-stu-id="1e31a-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1e31a-109">Para realizar cambios en un salón del servidor de chat persistente existente</span><span class="sxs-lookup"><span data-stu-id="1e31a-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="1e31a-110">Windows PowerShell: los miembros, los administradores y los moderadores se pueden configurar simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="1e31a-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="1e31a-111">Deben estar en el subconjunto de AllowedMembers menos DeniedMembers de la categoría de host.</span><span class="sxs-lookup"><span data-stu-id="1e31a-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="1e31a-112">Un salón que es type=normal no puede incluir moderadores.</span><span class="sxs-lookup"><span data-stu-id="1e31a-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="1e31a-113">Crear, obtener, configurar, borrar o quitar un salón</span><span class="sxs-lookup"><span data-stu-id="1e31a-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="1e31a-114">Para crear un salón nuevo</span><span class="sxs-lookup"><span data-stu-id="1e31a-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="1e31a-115">Para configurar un salón</span><span class="sxs-lookup"><span data-stu-id="1e31a-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="1e31a-116">Para obtener un salón</span><span class="sxs-lookup"><span data-stu-id="1e31a-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="1e31a-117">o</span><span class="sxs-lookup"><span data-stu-id="1e31a-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="1e31a-118">donde el filtro–solo admita el nombre y la descripción y ayude a buscar salones cuyos nombres o descripciones coincidan con la cadena de la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1e31a-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="1e31a-119">PoolFqdn busca en un grupo de servidores de chat persistente determinado.</span><span class="sxs-lookup"><span data-stu-id="1e31a-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="1e31a-120">Para borrar un salón y borrar los mensajes de un salón</span><span class="sxs-lookup"><span data-stu-id="1e31a-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="1e31a-121">o</span><span class="sxs-lookup"><span data-stu-id="1e31a-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="1e31a-122">Para quitar un salón</span><span class="sxs-lookup"><span data-stu-id="1e31a-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="1e31a-123">o</span><span class="sxs-lookup"><span data-stu-id="1e31a-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>


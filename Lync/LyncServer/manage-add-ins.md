---
title: Administrar complementos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55a14e84404d11f4b52bc6438991ae070ca8806a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-add-ins"></a><span data-ttu-id="3031d-102">Administrar complementos</span><span class="sxs-lookup"><span data-stu-id="3031d-102">Manage add-ins</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3031d-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3031d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3031d-104">Para crear un nuevo complemento de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3031d-104">To create a new Persistent Chat Server Add-in</span></span>

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a><span data-ttu-id="3031d-105">Crear, obtener, establecer o quitar un complemento</span><span class="sxs-lookup"><span data-stu-id="3031d-105">Create, Get, Set, or Remove an Add-in</span></span>

<span data-ttu-id="3031d-106">Para crear un nuevo complemento</span><span class="sxs-lookup"><span data-stu-id="3031d-106">To create a new Add-in</span></span>

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3031d-107">La &lt;cadena&gt; PersistentChatPoolFqdn solo se requiere si hay más de un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3031d-107">PersistentChatPoolFqdn &lt;String&gt; is required only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="3031d-108">Para obtener un complemento</span><span class="sxs-lookup"><span data-stu-id="3031d-108">To get an Add-in</span></span>

    Get-CsPersistentChatAddin -Identity <String>]

<span data-ttu-id="3031d-109">o</span><span class="sxs-lookup"><span data-stu-id="3031d-109">or</span></span>

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

<span data-ttu-id="3031d-110">Para establecer un complemento</span><span class="sxs-lookup"><span data-stu-id="3031d-110">To set an Add-in</span></span>

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="3031d-111">o</span><span class="sxs-lookup"><span data-stu-id="3031d-111">or</span></span>

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="3031d-112">Para quitar un complemento</span><span class="sxs-lookup"><span data-stu-id="3031d-112">To remove an Add-in</span></span>

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="3031d-113">o</span><span class="sxs-lookup"><span data-stu-id="3031d-113">or</span></span>

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>


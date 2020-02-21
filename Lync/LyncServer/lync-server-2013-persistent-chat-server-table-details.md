---
title: 'Lync Server 2013: detalles de la tabla del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e103fa03aa747e0c04a680507fe6d57bd6de04d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="9063a-102">Detalles de la tabla del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-102">Persistent Chat Server table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9063a-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="9063a-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="9063a-104">En los temas siguientes se detallan las columnas de cada una de las tablas de esquema de base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9063a-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9063a-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9063a-105">In This Section</span></span>

  - [<span data-ttu-id="9063a-106">tblADCookie en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="9063a-107">tblPrincipalMemberDifference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="9063a-108">tblADUpdates en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="9063a-109">tblPrincipalMembers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="9063a-110">tblPrincipalMeta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="9063a-111">tblSkippedAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="9063a-112">tblPrincipalType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="9063a-113">tblPrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="9063a-114">tblPrincipalAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="9063a-115">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="9063a-116">tblRoleType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="9063a-117">tblScopePrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="9063a-118">tblPrincipalRole en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="9063a-119">tblSiopWhiteList en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="9063a-120">tblEnumAttribute en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="9063a-121">tblEnumValue en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="9063a-122">tblPrincipalInvites en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="9063a-123">tblChat en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="9063a-124">tblLastInviteId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="9063a-125">tblLastChatId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="9063a-126">tblPreference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="9063a-127">tblFileToken en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="9063a-128">Tabla tblserveridentity en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="9063a-129">tblAdminLock en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="9063a-130">tblSystemRevision en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="9063a-131">tblActivePeers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="9063a-132">tblConfig en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="9063a-133">tblComplianceData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="9063a-134">tblComplianceFanout en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="9063a-135">tblComplianceParticipant en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="9063a-136">tblComplianceState en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9063a-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


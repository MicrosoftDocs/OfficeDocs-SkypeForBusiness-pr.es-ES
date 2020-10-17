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
ms.openlocfilehash: cde75ceb141a81af1b6a093742edd23b4adf1716
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524227"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="c42b7-102">Detalles de la tabla del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-102">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c42b7-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="c42b7-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="c42b7-104">En los temas siguientes se detallan las columnas de cada una de las tablas de esquema de base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c42b7-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c42b7-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c42b7-105">In This Section</span></span>

  - [<span data-ttu-id="c42b7-106">tblADCookie en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="c42b7-107">tblPrincipalMemberDifference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="c42b7-108">tblADUpdates en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="c42b7-109">tblPrincipalMembers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="c42b7-110">tblPrincipalMeta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="c42b7-111">tblSkippedAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="c42b7-112">tblPrincipalType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="c42b7-113">tblPrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="c42b7-114">tblPrincipalAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="c42b7-115">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="c42b7-116">tblRoleType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="c42b7-117">tblScopePrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="c42b7-118">tblPrincipalRole en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="c42b7-119">tblSiopWhiteList en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="c42b7-120">tblEnumAttribute en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="c42b7-121">tblEnumValue en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="c42b7-122">tblPrincipalInvites en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="c42b7-123">tblChat en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="c42b7-124">tblLastInviteId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="c42b7-125">tblLastChatId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="c42b7-126">tblPreference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="c42b7-127">tblFileToken en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="c42b7-128">Tabla tblserveridentity en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="c42b7-129">tblAdminLock en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="c42b7-130">tblSystemRevision en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="c42b7-131">tblActivePeers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="c42b7-132">tblConfig en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="c42b7-133">tblComplianceData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="c42b7-134">tblComplianceFanout en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="c42b7-135">tblComplianceParticipant en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="c42b7-136">tblComplianceState en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42b7-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


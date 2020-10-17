---
title: 'Lync Server 2013: detalles de la tabla del servidor de chat persistente'
description: 'Lync Server 2013: detalles de la tabla del servidor de chat persistente.'
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
ms.openlocfilehash: 6a27feaaccf861d537127f06920cf903be5ae000
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545136"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="df7b5-103">Detalles de la tabla del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-103">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df7b5-104">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="df7b5-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="df7b5-105">En los temas siguientes se detallan las columnas de cada una de las tablas de esquema de base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="df7b5-105">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="df7b5-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="df7b5-106">In This Section</span></span>

  - [<span data-ttu-id="df7b5-107">tblADCookie en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-107">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="df7b5-108">tblPrincipalMemberDifference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-108">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="df7b5-109">tblADUpdates en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-109">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="df7b5-110">tblPrincipalMembers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-110">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="df7b5-111">tblPrincipalMeta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-111">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="df7b5-112">tblSkippedAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-112">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="df7b5-113">tblPrincipalType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-113">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="df7b5-114">tblPrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-114">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="df7b5-115">tblPrincipalAffiliations en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-115">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="df7b5-116">tblNode en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-116">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="df7b5-117">tblRoleType en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-117">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="df7b5-118">tblScopePrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-118">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="df7b5-119">tblPrincipalRole en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-119">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="df7b5-120">tblSiopWhiteList en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-120">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="df7b5-121">tblEnumAttribute en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-121">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="df7b5-122">tblEnumValue en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-122">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="df7b5-123">tblPrincipalInvites en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="df7b5-124">tblChat en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="df7b5-125">tblLastInviteId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-125">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="df7b5-126">tblLastChatId en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-126">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="df7b5-127">tblPreference en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-127">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="df7b5-128">tblFileToken en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-128">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="df7b5-129">Tabla tblserveridentity en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-129">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="df7b5-130">tblAdminLock en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-130">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="df7b5-131">tblSystemRevision en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-131">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="df7b5-132">tblActivePeers en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-132">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="df7b5-133">tblConfig en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-133">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="df7b5-134">tblComplianceData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-134">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="df7b5-135">tblComplianceFanout en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-135">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="df7b5-136">tblComplianceParticipant en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-136">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="df7b5-137">tblComplianceState en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df7b5-137">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


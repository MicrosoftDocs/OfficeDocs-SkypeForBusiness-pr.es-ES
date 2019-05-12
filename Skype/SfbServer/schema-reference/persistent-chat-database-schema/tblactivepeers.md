---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones punto a punto actuales entre los servicios de chat.
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929878"
---
# <a name="tblactivepeers"></a><span data-ttu-id="c90d8-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="c90d8-103">tblActivePeers</span></span>
 
<span data-ttu-id="c90d8-104">tblActivePeers contiene las conexiones punto a punto actuales entre los servicios de chat.</span><span class="sxs-lookup"><span data-stu-id="c90d8-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="c90d8-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="c90d8-105">**Columns**</span></span>

|<span data-ttu-id="c90d8-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c90d8-106">**Column**</span></span>|<span data-ttu-id="c90d8-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c90d8-107">**Type**</span></span>|<span data-ttu-id="c90d8-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c90d8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c90d8-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="c90d8-109">aplServerID</span></span>  <br/> |<span data-ttu-id="c90d8-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="c90d8-110">int, not null</span></span>  <br/> |<span data-ttu-id="c90d8-111">Identificador del servidor que publicó la entrada.</span><span class="sxs-lookup"><span data-stu-id="c90d8-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="c90d8-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="c90d8-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="c90d8-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="c90d8-113">int, not null</span></span>  <br/> |<span data-ttu-id="c90d8-114">Identificador del punto al que está conectado el servidor de registro.</span><span class="sxs-lookup"><span data-stu-id="c90d8-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="c90d8-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="c90d8-115">**Keys**</span></span>

|<span data-ttu-id="c90d8-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c90d8-116">**Column**</span></span>|<span data-ttu-id="c90d8-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c90d8-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c90d8-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="c90d8-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="c90d8-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="c90d8-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c90d8-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="c90d8-120">aplServerID</span></span>  <br/> |<span data-ttu-id="c90d8-121">Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="c90d8-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="c90d8-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="c90d8-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="c90d8-123">Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="c90d8-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   


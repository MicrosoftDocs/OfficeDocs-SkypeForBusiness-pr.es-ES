---
title: tblActivePeers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones punto a punto actuales entre los servicios de chat.
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884170"
---
# <a name="tblactivepeers"></a><span data-ttu-id="dc600-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="dc600-103">tblActivePeers</span></span>
 
<span data-ttu-id="dc600-104">tblActivePeers contiene las conexiones punto a punto actuales entre los servicios de chat.</span><span class="sxs-lookup"><span data-stu-id="dc600-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="dc600-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="dc600-105">**Columns**</span></span>

|<span data-ttu-id="dc600-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dc600-106">**Column**</span></span>|<span data-ttu-id="dc600-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dc600-107">**Type**</span></span>|<span data-ttu-id="dc600-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dc600-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dc600-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="dc600-109">aplServerID</span></span>  <br/> |<span data-ttu-id="dc600-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="dc600-110">int, not null</span></span>  <br/> |<span data-ttu-id="dc600-111">Identificador del servidor que publicó la entrada.</span><span class="sxs-lookup"><span data-stu-id="dc600-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="dc600-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="dc600-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="dc600-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="dc600-113">int, not null</span></span>  <br/> |<span data-ttu-id="dc600-114">Identificador del punto al que está conectado el servidor de registro.</span><span class="sxs-lookup"><span data-stu-id="dc600-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="dc600-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="dc600-115">**Keys**</span></span>

|<span data-ttu-id="dc600-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dc600-116">**Column**</span></span>|<span data-ttu-id="dc600-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dc600-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dc600-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="dc600-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="dc600-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="dc600-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="dc600-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="dc600-120">aplServerID</span></span>  <br/> |<span data-ttu-id="dc600-121">Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="dc600-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="dc600-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="dc600-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="dc600-123">Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="dc600-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   


---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las actuales conexiones peer-to-peer entre servicios de charla.
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a><span data-ttu-id="e9615-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="e9615-103">tblActivePeers</span></span>
 
<span data-ttu-id="e9615-104">tblActivePeers contiene las actuales conexiones peer-to-peer entre servicios de charla.</span><span class="sxs-lookup"><span data-stu-id="e9615-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="e9615-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="e9615-105">**Columns**</span></span>

|<span data-ttu-id="e9615-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e9615-106">**Column**</span></span>|<span data-ttu-id="e9615-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e9615-107">**Type**</span></span>|<span data-ttu-id="e9615-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e9615-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9615-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="e9615-109">aplServerID</span></span>  <br/> |<span data-ttu-id="e9615-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="e9615-110">int, not null</span></span>  <br/> |<span data-ttu-id="e9615-111">Id. del servidor que se registró el movimiento.</span><span class="sxs-lookup"><span data-stu-id="e9615-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="e9615-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="e9615-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="e9615-113">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="e9615-113">int, not null</span></span>  <br/> |<span data-ttu-id="e9615-114">Id. del interlocutor que está conectado el servidor de registro.</span><span class="sxs-lookup"><span data-stu-id="e9615-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="e9615-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="e9615-115">**Keys**</span></span>

|<span data-ttu-id="e9615-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e9615-116">**Column**</span></span>|<span data-ttu-id="e9615-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e9615-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9615-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="e9615-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="e9615-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="e9615-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e9615-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="e9615-120">aplServerID</span></span>  <br/> |<span data-ttu-id="e9615-121">Clave externa con la búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="e9615-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="e9615-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="e9615-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="e9615-123">Clave externa con la búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="e9615-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   


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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212680"
---
# <a name="tblactivepeers"></a><span data-ttu-id="04746-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="04746-103">tblActivePeers</span></span>
 
<span data-ttu-id="04746-104">tblActivePeers contiene las conexiones punto a punto actuales entre los servicios de chat.</span><span class="sxs-lookup"><span data-stu-id="04746-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="04746-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="04746-105">**Columns**</span></span>

|<span data-ttu-id="04746-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="04746-106">**Column**</span></span>|<span data-ttu-id="04746-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="04746-107">**Type**</span></span>|<span data-ttu-id="04746-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="04746-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="04746-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="04746-109">aplServerID</span></span>  <br/> |<span data-ttu-id="04746-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="04746-110">int, not null</span></span>  <br/> |<span data-ttu-id="04746-111">Identificador del servidor que publicó la entrada.</span><span class="sxs-lookup"><span data-stu-id="04746-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="04746-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="04746-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="04746-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="04746-113">int, not null</span></span>  <br/> |<span data-ttu-id="04746-114">Identificador del punto al que está conectado el servidor de registro.</span><span class="sxs-lookup"><span data-stu-id="04746-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="04746-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="04746-115">**Keys**</span></span>

|<span data-ttu-id="04746-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="04746-116">**Column**</span></span>|<span data-ttu-id="04746-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="04746-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="04746-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="04746-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="04746-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="04746-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="04746-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="04746-120">aplServerID</span></span>  <br/> |<span data-ttu-id="04746-121">Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="04746-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="04746-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="04746-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="04746-123">Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="04746-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   


---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones punto a punto actuales entre servicios de chat.
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812940"
---
# <a name="tblactivepeers"></a><span data-ttu-id="49af0-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="49af0-103">tblActivePeers</span></span>
 
<span data-ttu-id="49af0-104">tblActivePeers contiene las conexiones punto a punto actuales entre servicios de chat.</span><span class="sxs-lookup"><span data-stu-id="49af0-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="49af0-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="49af0-105">**Columns**</span></span>

|<span data-ttu-id="49af0-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="49af0-106">**Column**</span></span>|<span data-ttu-id="49af0-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="49af0-107">**Type**</span></span>|<span data-ttu-id="49af0-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="49af0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="49af0-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="49af0-109">aplServerID</span></span>  <br/> |<span data-ttu-id="49af0-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="49af0-110">int, not null</span></span>  <br/> |<span data-ttu-id="49af0-111">Identificador del servidor que publicó la entrada.</span><span class="sxs-lookup"><span data-stu-id="49af0-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="49af0-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="49af0-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="49af0-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="49af0-113">int, not null</span></span>  <br/> |<span data-ttu-id="49af0-114">Identificador del sistema del mismo nivel al que está conectado el servidor de publicación.</span><span class="sxs-lookup"><span data-stu-id="49af0-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="49af0-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="49af0-115">**Keys**</span></span>

|<span data-ttu-id="49af0-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="49af0-116">**Column**</span></span>|<span data-ttu-id="49af0-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="49af0-117">**Description**</span></span>|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |<span data-ttu-id="49af0-118">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="49af0-118">Primary key.</span></span>  <br/> |
|<span data-ttu-id="49af0-119">aplServerID</span><span class="sxs-lookup"><span data-stu-id="49af0-119">aplServerID</span></span>  <br/> |<span data-ttu-id="49af0-120">Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="49af0-120">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="49af0-121">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="49af0-121">aplPeerID</span></span>  <br/> |<span data-ttu-id="49af0-122">Clave externa con búsqueda en la tabla tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="49af0-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   


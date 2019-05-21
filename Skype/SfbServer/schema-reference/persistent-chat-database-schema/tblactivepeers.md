---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones de punto a punto actuales entre los servicios de chat.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295548"
---
# <a name="tblactivepeers"></a><span data-ttu-id="d248c-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="d248c-103">tblActivePeers</span></span>
 
<span data-ttu-id="d248c-104">tblActivePeers contiene las conexiones de punto a punto actuales entre los servicios de chat.</span><span class="sxs-lookup"><span data-stu-id="d248c-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="d248c-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="d248c-105">**Columns**</span></span>

|<span data-ttu-id="d248c-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d248c-106">**Column**</span></span>|<span data-ttu-id="d248c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d248c-107">**Type**</span></span>|<span data-ttu-id="d248c-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d248c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d248c-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="d248c-109">aplServerID</span></span>  <br/> |<span data-ttu-id="d248c-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="d248c-110">int, not null</span></span>  <br/> |<span data-ttu-id="d248c-111">IDENTIFICADOR del servidor que ha publicado la entrada.</span><span class="sxs-lookup"><span data-stu-id="d248c-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="d248c-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="d248c-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="d248c-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="d248c-113">int, not null</span></span>  <br/> |<span data-ttu-id="d248c-114">IDENTIFICADOR del elemento del mismo nivel al que está conectado el servidor de publicación.</span><span class="sxs-lookup"><span data-stu-id="d248c-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="d248c-115">**Sus**</span><span class="sxs-lookup"><span data-stu-id="d248c-115">**Keys**</span></span>

|<span data-ttu-id="d248c-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d248c-116">**Column**</span></span>|<span data-ttu-id="d248c-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d248c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d248c-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="d248c-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="d248c-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="d248c-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d248c-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="d248c-120">aplServerID</span></span>  <br/> |<span data-ttu-id="d248c-121">Clave externa con la búsqueda en la tabla tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="d248c-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="d248c-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="d248c-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="d248c-123">Clave externa con la búsqueda en la tabla tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="d248c-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   


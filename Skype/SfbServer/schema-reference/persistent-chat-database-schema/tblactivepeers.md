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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene las conexiones de punto a punto actuales entre los servicios de chat.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814718"
---
# <a name="tblactivepeers"></a><span data-ttu-id="dfd65-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="dfd65-103">tblActivePeers</span></span>
 
<span data-ttu-id="dfd65-104">tblActivePeers contiene las conexiones de punto a punto actuales entre los servicios de chat.</span><span class="sxs-lookup"><span data-stu-id="dfd65-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="dfd65-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="dfd65-105">**Columns**</span></span>

|<span data-ttu-id="dfd65-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dfd65-106">**Column**</span></span>|<span data-ttu-id="dfd65-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dfd65-107">**Type**</span></span>|<span data-ttu-id="dfd65-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dfd65-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dfd65-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="dfd65-109">aplServerID</span></span>  <br/> |<span data-ttu-id="dfd65-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="dfd65-110">int, not null</span></span>  <br/> |<span data-ttu-id="dfd65-111">IDENTIFICADOR del servidor que ha publicado la entrada.</span><span class="sxs-lookup"><span data-stu-id="dfd65-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="dfd65-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="dfd65-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="dfd65-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="dfd65-113">int, not null</span></span>  <br/> |<span data-ttu-id="dfd65-114">IDENTIFICADOR del elemento del mismo nivel al que está conectado el servidor de publicación.</span><span class="sxs-lookup"><span data-stu-id="dfd65-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="dfd65-115">**Sus**</span><span class="sxs-lookup"><span data-stu-id="dfd65-115">**Keys**</span></span>

|<span data-ttu-id="dfd65-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dfd65-116">**Column**</span></span>|<span data-ttu-id="dfd65-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dfd65-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dfd65-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="dfd65-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="dfd65-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="dfd65-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="dfd65-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="dfd65-120">aplServerID</span></span>  <br/> |<span data-ttu-id="dfd65-121">Clave externa con la búsqueda en la tabla tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="dfd65-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="dfd65-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="dfd65-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="dfd65-123">Clave externa con la búsqueda en la tabla tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="dfd65-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   


---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295401"
---
# <a name="tbllastchatid"></a><span data-ttu-id="96f09-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="96f09-103">tblLastChatId</span></span>
 
<span data-ttu-id="96f09-104">tblLastChatId contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="96f09-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="96f09-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="96f09-105">**Columns**</span></span>

|<span data-ttu-id="96f09-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="96f09-106">**Column**</span></span>|<span data-ttu-id="96f09-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="96f09-107">**Type**</span></span>|<span data-ttu-id="96f09-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="96f09-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="96f09-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="96f09-109">nodeID</span></span>  <br/> |<span data-ttu-id="96f09-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="96f09-110">int, not null</span></span>  <br/> |<span data-ttu-id="96f09-111">IDENTIFICADOR de nodo (solo tipo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="96f09-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="96f09-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="96f09-112">lastChatID</span></span>  <br/> |<span data-ttu-id="96f09-113">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="96f09-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="96f09-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="96f09-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="96f09-115">**Sus**</span><span class="sxs-lookup"><span data-stu-id="96f09-115">**Keys**</span></span>

|<span data-ttu-id="96f09-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="96f09-116">**Column**</span></span>|<span data-ttu-id="96f09-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="96f09-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="96f09-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="96f09-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="96f09-119">Clave principal (solo nodeID es suficiente para procesar).</span><span class="sxs-lookup"><span data-stu-id="96f09-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="96f09-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="96f09-120">nodeID</span></span>  <br/> |<span data-ttu-id="96f09-121">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="96f09-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="96f09-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="96f09-122">See also</span></span>

[<span data-ttu-id="96f09-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="96f09-123">tblChat</span></span>](tblchat.md)

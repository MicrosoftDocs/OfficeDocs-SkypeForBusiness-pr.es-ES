---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último id. de chat generado (y usado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816010"
---
# <a name="tbllastchatid"></a><span data-ttu-id="935db-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="935db-103">tblLastChatId</span></span>
 
<span data-ttu-id="935db-104">tblLastChatId contiene el último id. de chat generado (y usado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="935db-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="935db-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="935db-105">**Columns**</span></span>

|<span data-ttu-id="935db-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="935db-106">**Column**</span></span>|<span data-ttu-id="935db-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="935db-107">**Type**</span></span>|<span data-ttu-id="935db-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="935db-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="935db-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="935db-109">nodeID</span></span>  <br/> |<span data-ttu-id="935db-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="935db-110">int, not null</span></span>  <br/> |<span data-ttu-id="935db-111">Identificador de nodo (tipo de salón de chat únicamente).</span><span class="sxs-lookup"><span data-stu-id="935db-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="935db-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="935db-112">lastChatID</span></span>  <br/> |<span data-ttu-id="935db-113">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="935db-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="935db-114">Identificador de chat usado por última vez.</span><span class="sxs-lookup"><span data-stu-id="935db-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="935db-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="935db-115">**Keys**</span></span>

|<span data-ttu-id="935db-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="935db-116">**Column**</span></span>|<span data-ttu-id="935db-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="935db-117">**Description**</span></span>|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |<span data-ttu-id="935db-118">Clave principal (nodeID es suficiente para el procesamiento).</span><span class="sxs-lookup"><span data-stu-id="935db-118">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="935db-119">nodeID</span><span class="sxs-lookup"><span data-stu-id="935db-119">nodeID</span></span>  <br/> |<span data-ttu-id="935db-120">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="935db-120">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="935db-121">Ver también</span><span class="sxs-lookup"><span data-stu-id="935db-121">See also</span></span>

[<span data-ttu-id="935db-122">tblChat</span><span class="sxs-lookup"><span data-stu-id="935db-122">tblChat</span></span>](tblchat.md)

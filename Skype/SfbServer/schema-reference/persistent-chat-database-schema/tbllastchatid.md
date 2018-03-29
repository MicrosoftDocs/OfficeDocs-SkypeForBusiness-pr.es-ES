---
title: tblLastChatId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último ID de charla que se ha generado (y utilizado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a><span data-ttu-id="39926-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="39926-103">tblLastChatId</span></span>
 
<span data-ttu-id="39926-104">tblLastChatId contiene el último ID de charla que se ha generado (y utilizado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="39926-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="39926-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="39926-105">**Columns**</span></span>

|<span data-ttu-id="39926-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="39926-106">**Column**</span></span>|<span data-ttu-id="39926-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="39926-107">**Type**</span></span>|<span data-ttu-id="39926-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="39926-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39926-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="39926-109">nodeID</span></span>  <br/> |<span data-ttu-id="39926-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="39926-110">int, not null</span></span>  <br/> |<span data-ttu-id="39926-111">Identificador de nodo (tipo de salón de chat sólo).</span><span class="sxs-lookup"><span data-stu-id="39926-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="39926-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="39926-112">lastChatID</span></span>  <br/> |<span data-ttu-id="39926-113">bigint, no nulo</span><span class="sxs-lookup"><span data-stu-id="39926-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="39926-114">ID de chat utilizados anterior.</span><span class="sxs-lookup"><span data-stu-id="39926-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="39926-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="39926-115">**Keys**</span></span>

|<span data-ttu-id="39926-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="39926-116">**Column**</span></span>|<span data-ttu-id="39926-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="39926-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39926-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="39926-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="39926-119">Clave principal (sólo nodeID es suficiente para su procesamiento).</span><span class="sxs-lookup"><span data-stu-id="39926-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="39926-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="39926-120">nodeID</span></span>  <br/> |<span data-ttu-id="39926-121">Clave externa con la búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="39926-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="39926-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="39926-122">See also</span></span>

#### 

[<span data-ttu-id="39926-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="39926-123">tblChat</span></span>](tblchat.md)


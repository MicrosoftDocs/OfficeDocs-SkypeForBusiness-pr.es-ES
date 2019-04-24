---
title: tblLastChatId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último identificador de chat generado (y utilizado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212568"
---
# <a name="tbllastchatid"></a><span data-ttu-id="5481e-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="5481e-103">tblLastChatId</span></span>
 
<span data-ttu-id="5481e-104">tblLastChatId contiene el último identificador de chat generado (y utilizado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="5481e-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="5481e-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="5481e-105">**Columns**</span></span>

|<span data-ttu-id="5481e-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5481e-106">**Column**</span></span>|<span data-ttu-id="5481e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5481e-107">**Type**</span></span>|<span data-ttu-id="5481e-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5481e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5481e-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="5481e-109">nodeID</span></span>  <br/> |<span data-ttu-id="5481e-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="5481e-110">int, not null</span></span>  <br/> |<span data-ttu-id="5481e-111">Identificador de nodo (tipo de salón de chat únicamente).</span><span class="sxs-lookup"><span data-stu-id="5481e-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="5481e-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="5481e-112">lastChatID</span></span>  <br/> |<span data-ttu-id="5481e-113">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="5481e-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="5481e-114">Último identificador de chat usado.</span><span class="sxs-lookup"><span data-stu-id="5481e-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="5481e-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="5481e-115">**Keys**</span></span>

|<span data-ttu-id="5481e-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5481e-116">**Column**</span></span>|<span data-ttu-id="5481e-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5481e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5481e-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="5481e-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="5481e-119">Clave principal (nodeID es suficiente para el procesamiento).</span><span class="sxs-lookup"><span data-stu-id="5481e-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="5481e-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="5481e-120">nodeID</span></span>  <br/> |<span data-ttu-id="5481e-121">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="5481e-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5481e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5481e-122">See also</span></span>

[<span data-ttu-id="5481e-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="5481e-123">tblChat</span></span>](tblchat.md)

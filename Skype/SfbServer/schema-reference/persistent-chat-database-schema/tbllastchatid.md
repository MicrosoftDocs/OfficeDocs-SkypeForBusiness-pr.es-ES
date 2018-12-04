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
description: tblLastChatId contiene el último identificador de chat generado (y utilizado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505093"
---
# <a name="tbllastchatid"></a><span data-ttu-id="5247d-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="5247d-103">tblLastChatId</span></span>
 
<span data-ttu-id="5247d-104">tblLastChatId contiene el último identificador de chat generado (y utilizado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="5247d-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="5247d-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="5247d-105">**Columns**</span></span>

|<span data-ttu-id="5247d-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5247d-106">**Column**</span></span>|<span data-ttu-id="5247d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5247d-107">**Type**</span></span>|<span data-ttu-id="5247d-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5247d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5247d-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="5247d-109">nodeID</span></span>  <br/> |<span data-ttu-id="5247d-110">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="5247d-110">int, not null</span></span>  <br/> |<span data-ttu-id="5247d-111">Identificador de nodo (tipo de salón de chat únicamente).</span><span class="sxs-lookup"><span data-stu-id="5247d-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="5247d-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="5247d-112">lastChatID</span></span>  <br/> |<span data-ttu-id="5247d-113">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="5247d-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="5247d-114">Último identificador de chat usado.</span><span class="sxs-lookup"><span data-stu-id="5247d-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="5247d-115">**Claves**</span><span class="sxs-lookup"><span data-stu-id="5247d-115">**Keys**</span></span>

|<span data-ttu-id="5247d-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5247d-116">**Column**</span></span>|<span data-ttu-id="5247d-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5247d-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5247d-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="5247d-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="5247d-119">Clave principal (nodeID es suficiente para el procesamiento).</span><span class="sxs-lookup"><span data-stu-id="5247d-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="5247d-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="5247d-120">nodeID</span></span>  <br/> |<span data-ttu-id="5247d-121">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="5247d-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5247d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5247d-122">See also</span></span>

[<span data-ttu-id="5247d-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="5247d-123">tblChat</span></span>](tblchat.md)
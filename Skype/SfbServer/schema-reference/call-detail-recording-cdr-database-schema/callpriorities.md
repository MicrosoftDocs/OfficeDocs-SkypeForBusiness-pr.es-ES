---
title: Tabla CallPriorities en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: En la tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamada, como 'emergencia', 'urgente' o 'normal'.
ms.openlocfilehash: aac21073e98d7c1ef8d137a736445b62e4fb9878
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901532"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="35465-103">Tabla CallPriorities en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="35465-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="35465-104">En la tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamada, como 'emergencia', 'urgente' o 'normal'.</span><span class="sxs-lookup"><span data-stu-id="35465-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="35465-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="35465-105">**Column**</span></span>|<span data-ttu-id="35465-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="35465-106">**Data Type**</span></span>|<span data-ttu-id="35465-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="35465-107">**Key/Index**</span></span>|<span data-ttu-id="35465-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="35465-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35465-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="35465-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="35465-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="35465-110">tinyint</span></span>  <br/> |<span data-ttu-id="35465-111">Primary</span><span class="sxs-lookup"><span data-stu-id="35465-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="35465-112">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="35465-112">**Priority**</span></span> <br/> |<span data-ttu-id="35465-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="35465-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="35465-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="35465-114">Allowed values:</span></span> <br/>  <span data-ttu-id="35465-115">0 - Unknown (desconocido)</span><span class="sxs-lookup"><span data-stu-id="35465-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="35465-116">1 - no urgente</span><span class="sxs-lookup"><span data-stu-id="35465-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="35465-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="35465-117">2 - Normal</span></span> <br/>  <span data-ttu-id="35465-118">3 - urgente</span><span class="sxs-lookup"><span data-stu-id="35465-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="35465-119">4 - emergencia</span><span class="sxs-lookup"><span data-stu-id="35465-119">4 - Emergency</span></span> <br/> |
   


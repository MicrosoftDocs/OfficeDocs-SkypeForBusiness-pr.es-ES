---
title: Tabla CallPriorities en Skype Empresarial Server 2015
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamada, como "emergencia", "urgente" o "normal".
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813440"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fd398-103">Tabla CallPriorities en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd398-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fd398-104">La tabla CallPriorities es una tabla estática que almacena la lista de posibles prioridades de llamada, como "emergencia", "urgente" o "normal".</span><span class="sxs-lookup"><span data-stu-id="fd398-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="fd398-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fd398-105">**Column**</span></span>|<span data-ttu-id="fd398-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="fd398-106">**Data Type**</span></span>|<span data-ttu-id="fd398-107">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="fd398-107">**Key/Index**</span></span>|<span data-ttu-id="fd398-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="fd398-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd398-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="fd398-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="fd398-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="fd398-110">tinyint</span></span>  <br/> |<span data-ttu-id="fd398-111">Principal</span><span class="sxs-lookup"><span data-stu-id="fd398-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="fd398-112">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="fd398-112">**Priority**</span></span> <br/> |<span data-ttu-id="fd398-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fd398-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="fd398-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="fd398-114">Allowed values:</span></span> <br/>  <span data-ttu-id="fd398-115">0 - Desconocido</span><span class="sxs-lookup"><span data-stu-id="fd398-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="fd398-116">1- No urgente</span><span class="sxs-lookup"><span data-stu-id="fd398-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="fd398-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="fd398-117">2 - Normal</span></span> <br/>  <span data-ttu-id="fd398-118">3 - Urgente</span><span class="sxs-lookup"><span data-stu-id="fd398-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="fd398-119">4 - Emergencia</span><span class="sxs-lookup"><span data-stu-id="fd398-119">4 - Emergency</span></span> <br/> |
   


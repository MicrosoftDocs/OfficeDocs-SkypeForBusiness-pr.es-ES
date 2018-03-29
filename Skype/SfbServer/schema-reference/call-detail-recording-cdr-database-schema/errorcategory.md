---
title: Tabla ErrorCategory en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabla ErrorCategory contiene el nombre descriptivo de cada Skype para clasificación diagnóstico Business Server 2015. De forma predeterminada, Skype para el año 2015 de Business Server utiliza las siguientes clasificaciones:'
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="03467-104">Tabla ErrorCategory en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="03467-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="03467-105">La tabla ErrorCategory contiene el nombre descriptivo de cada Skype para clasificación diagnóstico Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="03467-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="03467-106">De forma predeterminada, Skype para el año 2015 de Business Server utiliza las siguientes clasificaciones:</span><span class="sxs-lookup"><span data-stu-id="03467-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="03467-107">0--correcto</span><span class="sxs-lookup"><span data-stu-id="03467-107">0 -- Success</span></span>
    
- <span data-ttu-id="03467-108">1--error</span><span class="sxs-lookup"><span data-stu-id="03467-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="03467-109">2 - Error inesperado</span><span class="sxs-lookup"><span data-stu-id="03467-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="03467-110">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03467-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="03467-111">**Columna**</span><span class="sxs-lookup"><span data-stu-id="03467-111">**Column**</span></span>|<span data-ttu-id="03467-112">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="03467-112">**Data Type**</span></span>|<span data-ttu-id="03467-113">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="03467-113">**Key/Index**</span></span>|<span data-ttu-id="03467-114">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="03467-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="03467-115">**IdCategoría**</span><span class="sxs-lookup"><span data-stu-id="03467-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="03467-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="03467-116">tinyint</span></span>  <br/> |<span data-ttu-id="03467-117">Primary</span><span class="sxs-lookup"><span data-stu-id="03467-117">Primary</span></span>  <br/> |<span data-ttu-id="03467-118">Identificador único para la clasificación.</span><span class="sxs-lookup"><span data-stu-id="03467-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="03467-119">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="03467-119">**Name**</span></span> <br/> |<span data-ttu-id="03467-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="03467-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="03467-121">Valor y nombre descriptivo asignado a la clasificación.</span><span class="sxs-lookup"><span data-stu-id="03467-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="03467-122">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="03467-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="03467-123">0--correcto</span><span class="sxs-lookup"><span data-stu-id="03467-123">0 -- Success</span></span> <br/>  <span data-ttu-id="03467-124">1--error</span><span class="sxs-lookup"><span data-stu-id="03467-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="03467-125">2 - Error inesperado</span><span class="sxs-lookup"><span data-stu-id="03467-125">2 - Unexpected failure</span></span> <br/> |
   


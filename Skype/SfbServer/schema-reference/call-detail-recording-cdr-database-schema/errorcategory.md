---
title: Tabla de categoría de error de Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'En la tabla de la categoría de error contiene el nombre descriptivo para cada Skype para la clasificación de diagnóstico Business Server 2015. De forma predeterminada, Skype para Business Server 2015 usa las siguientes clasificaciones:'
ms.openlocfilehash: b6226396302353b815138b41b7c19f170a0d6b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901090"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5ac32-104">Tabla de categoría de error de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ac32-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5ac32-105">En la tabla de la categoría de error contiene el nombre descriptivo para cada Skype para la clasificación de diagnóstico Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5ac32-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="5ac32-106">De forma predeterminada, Skype para Business Server 2015 usa las siguientes clasificaciones:</span><span class="sxs-lookup"><span data-stu-id="5ac32-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="5ac32-107">0--correcto</span><span class="sxs-lookup"><span data-stu-id="5ac32-107">0 -- Success</span></span>
    
- <span data-ttu-id="5ac32-108">1--error esperado</span><span class="sxs-lookup"><span data-stu-id="5ac32-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="5ac32-109">2 - Error inesperado</span><span class="sxs-lookup"><span data-stu-id="5ac32-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="5ac32-110">En esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ac32-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5ac32-111">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5ac32-111">**Column**</span></span>|<span data-ttu-id="5ac32-112">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="5ac32-112">**Data Type**</span></span>|<span data-ttu-id="5ac32-113">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="5ac32-113">**Key/Index**</span></span>|<span data-ttu-id="5ac32-114">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="5ac32-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ac32-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="5ac32-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="5ac32-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="5ac32-116">tinyint</span></span>  <br/> |<span data-ttu-id="5ac32-117">Primary</span><span class="sxs-lookup"><span data-stu-id="5ac32-117">Primary</span></span>  <br/> |<span data-ttu-id="5ac32-118">Identificador único para la clasificación.</span><span class="sxs-lookup"><span data-stu-id="5ac32-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="5ac32-119">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="5ac32-119">**Name**</span></span> <br/> |<span data-ttu-id="5ac32-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5ac32-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="5ac32-121">Valor y nombre descriptivo asignado a la clasificación.</span><span class="sxs-lookup"><span data-stu-id="5ac32-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="5ac32-122">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="5ac32-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="5ac32-123">0--correcto</span><span class="sxs-lookup"><span data-stu-id="5ac32-123">0 -- Success</span></span> <br/>  <span data-ttu-id="5ac32-124">1--error esperado</span><span class="sxs-lookup"><span data-stu-id="5ac32-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="5ac32-125">2 - Error inesperado</span><span class="sxs-lookup"><span data-stu-id="5ac32-125">2 - Unexpected failure</span></span> <br/> |
   


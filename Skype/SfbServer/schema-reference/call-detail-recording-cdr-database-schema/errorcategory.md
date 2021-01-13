---
title: Tabla ErrorCategory en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabla ErrorCategory contiene el nombre descriptivo de cada clasificación de diagnóstico de Skype Empresarial Server 2015. De forma predeterminada, Skype Empresarial Server 2015 usa las siguientes clasificaciones:'
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813150"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cf258-104">Tabla ErrorCategory en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="cf258-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cf258-105">La tabla ErrorCategory contiene el nombre descriptivo de cada clasificación de diagnóstico de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cf258-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="cf258-106">De forma predeterminada, Skype Empresarial Server 2015 usa las siguientes clasificaciones:</span><span class="sxs-lookup"><span data-stu-id="cf258-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="cf258-107">0 -- Éxito</span><span class="sxs-lookup"><span data-stu-id="cf258-107">0 -- Success</span></span>
    
- <span data-ttu-id="cf258-108">1-- Error esperado</span><span class="sxs-lookup"><span data-stu-id="cf258-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="cf258-109">2- Error inesperado</span><span class="sxs-lookup"><span data-stu-id="cf258-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="cf258-110">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf258-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cf258-111">**Columna**</span><span class="sxs-lookup"><span data-stu-id="cf258-111">**Column**</span></span>|<span data-ttu-id="cf258-112">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="cf258-112">**Data Type**</span></span>|<span data-ttu-id="cf258-113">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="cf258-113">**Key/Index**</span></span>|<span data-ttu-id="cf258-114">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="cf258-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf258-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="cf258-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="cf258-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="cf258-116">tinyint</span></span>  <br/> |<span data-ttu-id="cf258-117">Principal</span><span class="sxs-lookup"><span data-stu-id="cf258-117">Primary</span></span>  <br/> |<span data-ttu-id="cf258-118">Identificador único de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="cf258-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="cf258-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cf258-119">**Name**</span></span> <br/> |<span data-ttu-id="cf258-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cf258-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="cf258-p103">Valor y nombre descriptivo asignados a la clasificación. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="cf258-p103">Value and friendly name assigned to the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="cf258-123">0 -- Éxito</span><span class="sxs-lookup"><span data-stu-id="cf258-123">0 -- Success</span></span> <br/>  <span data-ttu-id="cf258-124">1-- Error esperado</span><span class="sxs-lookup"><span data-stu-id="cf258-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="cf258-125">2- Error inesperado</span><span class="sxs-lookup"><span data-stu-id="cf258-125">2 - Unexpected failure</span></span> <br/> |
   


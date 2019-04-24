---
title: Tabla DeRegisterType en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de posible usuario desaprovisionamiento registra tipos, como 'iniciado por cliente', 'registro expirado' o 'cliente interrumpida'.
ms.openlocfilehash: be6fd10388c9f85315554605fd491aafa9d3a0d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213196"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="72f26-103">Tabla DeRegisterType en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="72f26-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="72f26-104">La tabla DeRegisterType es una tabla estática que almacena la lista de posible usuario desaprovisionamiento registra tipos, como 'iniciado por cliente', 'registro expirado' o 'cliente interrumpida'.</span><span class="sxs-lookup"><span data-stu-id="72f26-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="72f26-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="72f26-105">**Column**</span></span>|<span data-ttu-id="72f26-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="72f26-106">**Data Type**</span></span>|<span data-ttu-id="72f26-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="72f26-107">**Key/Index**</span></span>|<span data-ttu-id="72f26-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="72f26-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="72f26-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="72f26-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="72f26-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="72f26-110">tinyint</span></span>  <br/> |<span data-ttu-id="72f26-111">Primary</span><span class="sxs-lookup"><span data-stu-id="72f26-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="72f26-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="72f26-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="72f26-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="72f26-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="72f26-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="72f26-114">Allowed values:</span></span> <br/>  <span data-ttu-id="72f26-115">0--Unknown (desconocido)</span><span class="sxs-lookup"><span data-stu-id="72f26-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="72f26-116">1--anulación del registro iniciada por el cliente</span><span class="sxs-lookup"><span data-stu-id="72f26-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="72f26-117">2--registro expirado</span><span class="sxs-lookup"><span data-stu-id="72f26-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="72f26-118">3 - cliente bloqueado</span><span class="sxs-lookup"><span data-stu-id="72f26-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="72f26-119">4--atributos de usuario ha cambiado</span><span class="sxs-lookup"><span data-stu-id="72f26-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="72f26-120">5 - registrador preferido modificado</span><span class="sxs-lookup"><span data-stu-id="72f26-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="72f26-121">6--El cliente heredado en modo de supervivencia</span><span class="sxs-lookup"><span data-stu-id="72f26-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   


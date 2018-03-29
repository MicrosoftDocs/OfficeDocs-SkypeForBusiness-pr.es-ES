---
title: Tabla DeRegisterType en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de usuario posible anular registra tipos como 'cliente inicia', 'registro ha caducado' o 'cliente dejado de responder'.
ms.openlocfilehash: 97b342a8d0175da0517aa36e0fea477e32df4dd9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3f5cb-103">Tabla DeRegisterType en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3f5cb-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3f5cb-104">La tabla DeRegisterType es una tabla estática que almacena la lista de usuario posible anular registra tipos como 'cliente inicia', 'registro ha caducado' o 'cliente dejado de responder'.</span><span class="sxs-lookup"><span data-stu-id="3f5cb-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="3f5cb-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3f5cb-105">**Column**</span></span>|<span data-ttu-id="3f5cb-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3f5cb-106">**Data Type**</span></span>|<span data-ttu-id="3f5cb-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="3f5cb-107">**Key/Index**</span></span>|<span data-ttu-id="3f5cb-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3f5cb-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f5cb-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="3f5cb-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="3f5cb-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="3f5cb-110">tinyint</span></span>  <br/> |<span data-ttu-id="3f5cb-111">Primary</span><span class="sxs-lookup"><span data-stu-id="3f5cb-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="3f5cb-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="3f5cb-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="3f5cb-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3f5cb-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="3f5cb-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="3f5cb-114">Allowed values:</span></span> <br/>  <span data-ttu-id="3f5cb-115">0--desconocido</span><span class="sxs-lookup"><span data-stu-id="3f5cb-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="3f5cb-116">1: el cliente inicia la anulación de registro</span><span class="sxs-lookup"><span data-stu-id="3f5cb-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="3f5cb-117">2--registro caducado</span><span class="sxs-lookup"><span data-stu-id="3f5cb-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="3f5cb-118">3 - cliente bloqueado</span><span class="sxs-lookup"><span data-stu-id="3f5cb-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="3f5cb-119">4--atributos de usuario cambiados</span><span class="sxs-lookup"><span data-stu-id="3f5cb-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="3f5cb-120">5 - preferido registrador cambiado</span><span class="sxs-lookup"><span data-stu-id="3f5cb-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="3f5cb-121">6--Cliente heredado en modo de supervivencia</span><span class="sxs-lookup"><span data-stu-id="3f5cb-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   


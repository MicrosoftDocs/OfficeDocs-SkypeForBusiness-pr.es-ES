---
title: Tabla DeRegisterType en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296353"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="90540-103">Tabla DeRegisterType en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="90540-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="90540-104">La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.</span><span class="sxs-lookup"><span data-stu-id="90540-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="90540-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="90540-105">**Column**</span></span>|<span data-ttu-id="90540-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="90540-106">**Data Type**</span></span>|<span data-ttu-id="90540-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="90540-107">**Key/Index**</span></span>|<span data-ttu-id="90540-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="90540-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90540-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="90540-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="90540-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="90540-110">tinyint</span></span>  <br/> |<span data-ttu-id="90540-111">Primary</span><span class="sxs-lookup"><span data-stu-id="90540-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="90540-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="90540-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="90540-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="90540-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="90540-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="90540-114">Allowed values:</span></span> <br/>  <span data-ttu-id="90540-115">0--desconocido</span><span class="sxs-lookup"><span data-stu-id="90540-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="90540-116">1: deregistro Iniciado por el cliente</span><span class="sxs-lookup"><span data-stu-id="90540-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="90540-117">2--registro expirado</span><span class="sxs-lookup"><span data-stu-id="90540-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="90540-118">3-cliente bloqueado</span><span class="sxs-lookup"><span data-stu-id="90540-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="90540-119">4: atributos de usuario modificados</span><span class="sxs-lookup"><span data-stu-id="90540-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="90540-120">5: el registrador preferido ha cambiado</span><span class="sxs-lookup"><span data-stu-id="90540-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="90540-121">6--cliente heredado en modo de supervivencia</span><span class="sxs-lookup"><span data-stu-id="90540-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   


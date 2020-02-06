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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815298"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7a605-103">Tabla DeRegisterType en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7a605-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7a605-104">La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de registros de usuario, como ' cliente iniciado ', ' registro expirado ' o ' cliente ha dejado de responder '.</span><span class="sxs-lookup"><span data-stu-id="7a605-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="7a605-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7a605-105">**Column**</span></span>|<span data-ttu-id="7a605-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="7a605-106">**Data Type**</span></span>|<span data-ttu-id="7a605-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="7a605-107">**Key/Index**</span></span>|<span data-ttu-id="7a605-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="7a605-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a605-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="7a605-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="7a605-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7a605-110">tinyint</span></span>  <br/> |<span data-ttu-id="7a605-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7a605-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="7a605-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="7a605-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="7a605-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7a605-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="7a605-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="7a605-114">Allowed values:</span></span> <br/>  <span data-ttu-id="7a605-115">0--desconocido</span><span class="sxs-lookup"><span data-stu-id="7a605-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="7a605-116">1: deregistro Iniciado por el cliente</span><span class="sxs-lookup"><span data-stu-id="7a605-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="7a605-117">2--registro expirado</span><span class="sxs-lookup"><span data-stu-id="7a605-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="7a605-118">3-cliente bloqueado</span><span class="sxs-lookup"><span data-stu-id="7a605-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="7a605-119">4: atributos de usuario modificados</span><span class="sxs-lookup"><span data-stu-id="7a605-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="7a605-120">5: el registrador preferido ha cambiado</span><span class="sxs-lookup"><span data-stu-id="7a605-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="7a605-121">6--cliente heredado en modo de supervivencia</span><span class="sxs-lookup"><span data-stu-id="7a605-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   


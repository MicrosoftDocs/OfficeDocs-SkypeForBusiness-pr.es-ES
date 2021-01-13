---
title: Tabla DeRegisterType en Skype Empresarial Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de anulación de registros de usuario, como "iniciado por el cliente", "el registro expiró" o "el cliente dejó de responder".
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816080"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ef26e-103">Tabla DeRegisterType en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="ef26e-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ef26e-104">La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de anulación de registros de usuario, como "iniciado por el cliente", "el registro expiró" o "el cliente dejó de responder".</span><span class="sxs-lookup"><span data-stu-id="ef26e-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="ef26e-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ef26e-105">**Column**</span></span>|<span data-ttu-id="ef26e-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ef26e-106">**Data Type**</span></span>|<span data-ttu-id="ef26e-107">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="ef26e-107">**Key/Index**</span></span>|<span data-ttu-id="ef26e-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ef26e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ef26e-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="ef26e-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="ef26e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ef26e-110">tinyint</span></span>  <br/> |<span data-ttu-id="ef26e-111">Principal</span><span class="sxs-lookup"><span data-stu-id="ef26e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ef26e-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="ef26e-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="ef26e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ef26e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ef26e-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="ef26e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ef26e-115">0 -- Desconocido</span><span class="sxs-lookup"><span data-stu-id="ef26e-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="ef26e-116">1 -- Anulación del registro iniciada por el cliente</span><span class="sxs-lookup"><span data-stu-id="ef26e-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="ef26e-117">2 -- Registro expirado</span><span class="sxs-lookup"><span data-stu-id="ef26e-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="ef26e-118">3- Cliente con bloqueo</span><span class="sxs-lookup"><span data-stu-id="ef26e-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="ef26e-119">4 -- Atributos de usuario modificados</span><span class="sxs-lookup"><span data-stu-id="ef26e-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="ef26e-120">5- Registrador preferido cambiado</span><span class="sxs-lookup"><span data-stu-id="ef26e-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="ef26e-121">6 -- Cliente heredado en modo de supervivencia</span><span class="sxs-lookup"><span data-stu-id="ef26e-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   


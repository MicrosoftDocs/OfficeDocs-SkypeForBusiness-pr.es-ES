---
title: Tabla Pool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabla Pool es una tabla de apoyo donde se almacena información sobre los distintos grupos de servidores front-end. Cada registro de la tabla representa un grupo.
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815820"
---
# <a name="pool-table"></a><span data-ttu-id="57110-104">Tabla Pool</span><span class="sxs-lookup"><span data-stu-id="57110-104">Pool table</span></span>
 
<span data-ttu-id="57110-p102">La tabla Pool es una tabla de apoyo donde se almacena información sobre los distintos grupos de servidores front-end. Cada registro de la tabla representa un grupo.</span><span class="sxs-lookup"><span data-stu-id="57110-p102">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="57110-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="57110-107">**Column**</span></span>|<span data-ttu-id="57110-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="57110-108">**Data Type**</span></span>|<span data-ttu-id="57110-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="57110-109">**Key/Index**</span></span>|<span data-ttu-id="57110-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="57110-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="57110-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="57110-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="57110-112">entero</span><span class="sxs-lookup"><span data-stu-id="57110-112">int</span></span>  <br/> |<span data-ttu-id="57110-113">Principal</span><span class="sxs-lookup"><span data-stu-id="57110-113">Primary</span></span>  <br/> |<span data-ttu-id="57110-114">Número único con el que se identifica a este grupo.</span><span class="sxs-lookup"><span data-stu-id="57110-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="57110-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="57110-115">**PoolName**</span></span> <br/> |<span data-ttu-id="57110-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="57110-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="57110-117">Única</span><span class="sxs-lookup"><span data-stu-id="57110-117">Unique</span></span>  <br/> |<span data-ttu-id="57110-118">FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="57110-118">Pool FQDN.</span></span>  <br/> |
   


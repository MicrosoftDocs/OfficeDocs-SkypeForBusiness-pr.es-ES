---
title: Tabla Pool
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabla de grupo es una tabla de soporte que almacena información acerca de los diversos grupos de Front-End. Cada registro de la tabla representa un grupo de servidores.
ms.openlocfilehash: 8ce54d4b0a20fa405f34bb14b3eecb9ad395884e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="pool-table"></a><span data-ttu-id="2c39f-104">Tabla Pool</span><span class="sxs-lookup"><span data-stu-id="2c39f-104">Pool table</span></span>
 
<span data-ttu-id="2c39f-105">La tabla de grupo es una tabla de soporte que almacena información acerca de los diversos grupos de Front-End.</span><span class="sxs-lookup"><span data-stu-id="2c39f-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="2c39f-106">Cada registro de la tabla representa un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="2c39f-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="2c39f-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2c39f-107">**Column**</span></span>|<span data-ttu-id="2c39f-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="2c39f-108">**Data Type**</span></span>|<span data-ttu-id="2c39f-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="2c39f-109">**Key/Index**</span></span>|<span data-ttu-id="2c39f-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="2c39f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c39f-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="2c39f-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="2c39f-112">int</span><span class="sxs-lookup"><span data-stu-id="2c39f-112">int</span></span>  <br/> |<span data-ttu-id="2c39f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2c39f-113">Primary</span></span>  <br/> |<span data-ttu-id="2c39f-114">Número único que identifica este grupo.</span><span class="sxs-lookup"><span data-stu-id="2c39f-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="2c39f-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="2c39f-115">**PoolName**</span></span> <br/> |<span data-ttu-id="2c39f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2c39f-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2c39f-117">Único</span><span class="sxs-lookup"><span data-stu-id="2c39f-117">Unique</span></span>  <br/> |<span data-ttu-id="2c39f-118">FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="2c39f-118">Pool FQDN.</span></span>  <br/> |
   


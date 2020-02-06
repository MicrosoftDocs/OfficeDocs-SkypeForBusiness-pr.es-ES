---
title: Tabla Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabla Pool es una tabla de soporte que almacena información sobre los distintos grupos de aplicaciones para el usuario. Cada registro de la tabla representa un grupo.
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807408"
---
# <a name="pool-table"></a><span data-ttu-id="5b5d3-104">Tabla Pool</span><span class="sxs-lookup"><span data-stu-id="5b5d3-104">Pool table</span></span>
 
<span data-ttu-id="5b5d3-105">La tabla Pool es una tabla de soporte que almacena información sobre los distintos grupos de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5b5d3-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="5b5d3-106">Cada registro de la tabla representa un grupo.</span><span class="sxs-lookup"><span data-stu-id="5b5d3-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="5b5d3-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5b5d3-107">**Column**</span></span>|<span data-ttu-id="5b5d3-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="5b5d3-108">**Data Type**</span></span>|<span data-ttu-id="5b5d3-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="5b5d3-109">**Key/Index**</span></span>|<span data-ttu-id="5b5d3-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="5b5d3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b5d3-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="5b5d3-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="5b5d3-112">int</span><span class="sxs-lookup"><span data-stu-id="5b5d3-112">int</span></span>  <br/> |<span data-ttu-id="5b5d3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5b5d3-113">Primary</span></span>  <br/> |<span data-ttu-id="5b5d3-114">Número único que identifica este grupo.</span><span class="sxs-lookup"><span data-stu-id="5b5d3-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="5b5d3-115">**Nombredegrupo**</span><span class="sxs-lookup"><span data-stu-id="5b5d3-115">**PoolName**</span></span> <br/> |<span data-ttu-id="5b5d3-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5b5d3-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5b5d3-117">Solo</span><span class="sxs-lookup"><span data-stu-id="5b5d3-117">Unique</span></span>  <br/> |<span data-ttu-id="5b5d3-118">FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="5b5d3-118">Pool FQDN.</span></span>  <br/> |
   


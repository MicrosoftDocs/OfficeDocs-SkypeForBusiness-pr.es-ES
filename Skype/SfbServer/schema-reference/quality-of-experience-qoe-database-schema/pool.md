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
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabla Pool es una tabla de soporte que almacena información sobre los distintos grupos de aplicaciones para el usuario. Cada registro de la tabla representa un grupo.
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294806"
---
# <a name="pool-table"></a><span data-ttu-id="9fe97-104">Tabla Pool</span><span class="sxs-lookup"><span data-stu-id="9fe97-104">Pool table</span></span>
 
<span data-ttu-id="9fe97-105">La tabla Pool es una tabla de soporte que almacena información sobre los distintos grupos de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="9fe97-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="9fe97-106">Cada registro de la tabla representa un grupo.</span><span class="sxs-lookup"><span data-stu-id="9fe97-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="9fe97-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9fe97-107">**Column**</span></span>|<span data-ttu-id="9fe97-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9fe97-108">**Data Type**</span></span>|<span data-ttu-id="9fe97-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="9fe97-109">**Key/Index**</span></span>|<span data-ttu-id="9fe97-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="9fe97-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fe97-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="9fe97-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="9fe97-112">int</span><span class="sxs-lookup"><span data-stu-id="9fe97-112">int</span></span>  <br/> |<span data-ttu-id="9fe97-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9fe97-113">Primary</span></span>  <br/> |<span data-ttu-id="9fe97-114">Número único que identifica este grupo.</span><span class="sxs-lookup"><span data-stu-id="9fe97-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="9fe97-115">**Nombredegrupo**</span><span class="sxs-lookup"><span data-stu-id="9fe97-115">**PoolName**</span></span> <br/> |<span data-ttu-id="9fe97-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9fe97-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9fe97-117">Solo</span><span class="sxs-lookup"><span data-stu-id="9fe97-117">Unique</span></span>  <br/> |<span data-ttu-id="9fe97-118">FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="9fe97-118">Pool FQDN.</span></span>  <br/> |
   


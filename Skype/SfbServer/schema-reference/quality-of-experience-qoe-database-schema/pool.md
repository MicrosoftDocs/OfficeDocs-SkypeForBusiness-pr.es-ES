---
title: Tabla Pool
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: En la tabla de grupo de servidores es una tabla de apoyo que almacena información acerca de los distintos grupos de Front-End. Cada registro de la tabla representa un grupo de servidores.
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874021"
---
# <a name="pool-table"></a><span data-ttu-id="7c26a-104">Tabla Pool</span><span class="sxs-lookup"><span data-stu-id="7c26a-104">Pool table</span></span>
 
<span data-ttu-id="7c26a-105">En la tabla de grupo de servidores es una tabla de apoyo que almacena información acerca de los distintos grupos de Front-End.</span><span class="sxs-lookup"><span data-stu-id="7c26a-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="7c26a-106">Cada registro de la tabla representa un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7c26a-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="7c26a-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7c26a-107">**Column**</span></span>|<span data-ttu-id="7c26a-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="7c26a-108">**Data Type**</span></span>|<span data-ttu-id="7c26a-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="7c26a-109">**Key/Index**</span></span>|<span data-ttu-id="7c26a-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="7c26a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7c26a-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="7c26a-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="7c26a-112">int</span><span class="sxs-lookup"><span data-stu-id="7c26a-112">int</span></span>  <br/> |<span data-ttu-id="7c26a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7c26a-113">Primary</span></span>  <br/> |<span data-ttu-id="7c26a-114">Número único que identifica a este grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7c26a-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="7c26a-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="7c26a-115">**PoolName**</span></span> <br/> |<span data-ttu-id="7c26a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7c26a-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7c26a-117">Único</span><span class="sxs-lookup"><span data-stu-id="7c26a-117">Unique</span></span>  <br/> |<span data-ttu-id="7c26a-118">FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="7c26a-118">Pool FQDN.</span></span>  <br/> |
   


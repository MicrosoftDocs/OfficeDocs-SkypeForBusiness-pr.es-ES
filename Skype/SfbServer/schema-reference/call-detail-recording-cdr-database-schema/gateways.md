---
title: Tabla de puertas de enlace de Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabla de puertas de enlace es una tabla de soporte. Cada registro almacena información sobre una puerta de enlace que interviene en las llamadas (RTC) de la red telefónica pública conmutada que tengan registros en la base de datos.
ms.openlocfilehash: e9592b227e8ccff6829748230abd3e8ddb8edb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4a2fe-104">Tabla de puertas de enlace de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4a2fe-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4a2fe-105">La tabla de puertas de enlace es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="4a2fe-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="4a2fe-106">Cada registro almacena información sobre una puerta de enlace que interviene en las llamadas (RTC) de la red telefónica pública conmutada que tengan registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a2fe-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="4a2fe-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4a2fe-107">**Column**</span></span>|<span data-ttu-id="4a2fe-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="4a2fe-108">**Data Type**</span></span>|<span data-ttu-id="4a2fe-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="4a2fe-109">**Key/Index**</span></span>|<span data-ttu-id="4a2fe-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="4a2fe-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4a2fe-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="4a2fe-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="4a2fe-112">int</span><span class="sxs-lookup"><span data-stu-id="4a2fe-112">int</span></span>  <br/> |<span data-ttu-id="4a2fe-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4a2fe-113">Primary</span></span>  <br/> |<span data-ttu-id="4a2fe-114">Número único que identifica esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="4a2fe-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="4a2fe-115">**Puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="4a2fe-115">**Gateway**</span></span> <br/> |<span data-ttu-id="4a2fe-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4a2fe-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="4a2fe-117">Nombre de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="4a2fe-117">Gateway name.</span></span>  <br/> |
   


---
title: Tabla de puertas de enlace de Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: En la tabla de puertas de enlace es una tabla de apoyo. Cada registro almacena información acerca de una puerta de enlace que está implicado en las llamadas de telefónica conmutada (RTC) de red que tienen registros en la base de datos.
ms.openlocfilehash: 16860e924fb69f1dfe337e05c13d54fb66a8ed81
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899084"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="58261-104">Tabla de puertas de enlace de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="58261-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="58261-105">En la tabla de puertas de enlace es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="58261-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="58261-106">Cada registro almacena información acerca de una puerta de enlace que está implicado en las llamadas de telefónica conmutada (RTC) de red que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="58261-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="58261-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="58261-107">**Column**</span></span>|<span data-ttu-id="58261-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="58261-108">**Data Type**</span></span>|<span data-ttu-id="58261-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="58261-109">**Key/Index**</span></span>|<span data-ttu-id="58261-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="58261-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58261-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="58261-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="58261-112">int</span><span class="sxs-lookup"><span data-stu-id="58261-112">int</span></span>  <br/> |<span data-ttu-id="58261-113">Primary</span><span class="sxs-lookup"><span data-stu-id="58261-113">Primary</span></span>  <br/> |<span data-ttu-id="58261-114">Número único que identifica esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="58261-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="58261-115">**Puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="58261-115">**Gateway**</span></span> <br/> |<span data-ttu-id="58261-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="58261-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="58261-117">Nombre de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="58261-117">Gateway name.</span></span>  <br/> |
   


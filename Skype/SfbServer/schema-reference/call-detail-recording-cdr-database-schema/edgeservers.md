---
title: Tabla EdgeServers en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: La tabla EdgeServers es un auxiliar. Cada registro almacena información sobre un servidor perimetral que está implicado en las llamadas que tengan registros en la base de datos.
ms.openlocfilehash: 581dfcb6bbd3b5088af2bbc27a580d791b9ef8f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="10980-104">Tabla EdgeServers en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="10980-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="10980-105">La tabla EdgeServers es un auxiliar.</span><span class="sxs-lookup"><span data-stu-id="10980-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="10980-106">Cada registro almacena información sobre un servidor perimetral que está implicado en las llamadas que tengan registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="10980-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="10980-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="10980-107">**Column**</span></span>|<span data-ttu-id="10980-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10980-108">**Data Type**</span></span>|<span data-ttu-id="10980-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="10980-109">**Key/Index**</span></span>|<span data-ttu-id="10980-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="10980-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10980-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="10980-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="10980-112">int</span><span class="sxs-lookup"><span data-stu-id="10980-112">int</span></span>  <br/> |<span data-ttu-id="10980-113">Primary</span><span class="sxs-lookup"><span data-stu-id="10980-113">Primary</span></span>  <br/> |<span data-ttu-id="10980-114">Número único que identifica este servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="10980-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="10980-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="10980-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="10980-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="10980-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="10980-117">Nombre del servidor de borde.</span><span class="sxs-lookup"><span data-stu-id="10980-117">Edge Server name.</span></span>  <br/> |
   


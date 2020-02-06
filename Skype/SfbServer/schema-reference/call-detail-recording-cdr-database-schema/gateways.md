---
title: Tabla de puertas de enlace en Skype empresarial Server 2015
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabla puertas de enlace es una tabla de soporte. Cada registro almacena información acerca de una puerta de enlace que está implicada en llamadas públicas de red telefónica conmutada (RTC) que tienen registros en la base de datos.
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815168"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c78ea-104">Tabla de puertas de enlace en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="c78ea-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c78ea-105">La tabla puertas de enlace es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="c78ea-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="c78ea-106">Cada registro almacena información acerca de una puerta de enlace que está implicada en llamadas públicas de red telefónica conmutada (RTC) que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c78ea-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="c78ea-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c78ea-107">**Column**</span></span>|<span data-ttu-id="c78ea-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c78ea-108">**Data Type**</span></span>|<span data-ttu-id="c78ea-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="c78ea-109">**Key/Index**</span></span>|<span data-ttu-id="c78ea-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c78ea-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c78ea-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="c78ea-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="c78ea-112">int</span><span class="sxs-lookup"><span data-stu-id="c78ea-112">int</span></span>  <br/> |<span data-ttu-id="c78ea-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c78ea-113">Primary</span></span>  <br/> |<span data-ttu-id="c78ea-114">Número único que identifica esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="c78ea-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="c78ea-115">**Puerta**</span><span class="sxs-lookup"><span data-stu-id="c78ea-115">**Gateway**</span></span> <br/> |<span data-ttu-id="c78ea-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c78ea-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="c78ea-117">Nombre de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="c78ea-117">Gateway name.</span></span>  <br/> |
   


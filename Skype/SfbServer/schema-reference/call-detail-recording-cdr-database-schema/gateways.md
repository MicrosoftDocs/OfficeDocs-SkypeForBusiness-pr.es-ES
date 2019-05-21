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
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabla puertas de enlace es una tabla de soporte. Cada registro almacena información acerca de una puerta de enlace que está implicada en llamadas públicas de red telefónica conmutada (RTC) que tienen registros en la base de datos.
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296185"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="276f9-104">Tabla de puertas de enlace en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="276f9-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="276f9-105">La tabla puertas de enlace es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="276f9-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="276f9-106">Cada registro almacena información acerca de una puerta de enlace que está implicada en llamadas públicas de red telefónica conmutada (RTC) que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="276f9-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="276f9-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="276f9-107">**Column**</span></span>|<span data-ttu-id="276f9-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="276f9-108">**Data Type**</span></span>|<span data-ttu-id="276f9-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="276f9-109">**Key/Index**</span></span>|<span data-ttu-id="276f9-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="276f9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="276f9-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="276f9-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="276f9-112">int</span><span class="sxs-lookup"><span data-stu-id="276f9-112">int</span></span>  <br/> |<span data-ttu-id="276f9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="276f9-113">Primary</span></span>  <br/> |<span data-ttu-id="276f9-114">Número único que identifica esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="276f9-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="276f9-115">**Puerta**</span><span class="sxs-lookup"><span data-stu-id="276f9-115">**Gateway**</span></span> <br/> |<span data-ttu-id="276f9-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="276f9-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="276f9-117">Nombre de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="276f9-117">Gateway name.</span></span>  <br/> |
   


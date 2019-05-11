---
title: Tabla de puertas de enlace de Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: En la tabla de puertas de enlace es una tabla de apoyo. Cada registro almacena información acerca de una puerta de enlace que está implicado en las llamadas de telefónica conmutada (RTC) de red que tienen registros en la base de datos.
ms.openlocfilehash: 2a3429b45a63c0c7765f4e9da0ea2baf3f0d11b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901041"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="116df-104">Tabla de puertas de enlace de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="116df-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="116df-105">En la tabla de puertas de enlace es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="116df-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="116df-106">Cada registro almacena información acerca de una puerta de enlace que está implicado en las llamadas de telefónica conmutada (RTC) de red que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="116df-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="116df-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="116df-107">**Column**</span></span>|<span data-ttu-id="116df-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="116df-108">**Data Type**</span></span>|<span data-ttu-id="116df-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="116df-109">**Key/Index**</span></span>|<span data-ttu-id="116df-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="116df-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="116df-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="116df-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="116df-112">int</span><span class="sxs-lookup"><span data-stu-id="116df-112">int</span></span>  <br/> |<span data-ttu-id="116df-113">Primary</span><span class="sxs-lookup"><span data-stu-id="116df-113">Primary</span></span>  <br/> |<span data-ttu-id="116df-114">Número único que identifica esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="116df-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="116df-115">**Puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="116df-115">**Gateway**</span></span> <br/> |<span data-ttu-id="116df-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="116df-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="116df-117">Nombre de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="116df-117">Gateway name.</span></span>  <br/> |
   


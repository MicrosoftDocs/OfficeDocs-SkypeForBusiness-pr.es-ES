---
title: Tabla Gateways en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La tabla Puertas de enlace es una tabla compatible. Cada registro almacena información acerca de una puerta de enlace que participa en llamadas de red telefónica conmutada (RTC) que tienen registros en la base de datos.
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821590"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2a21c-104">Tabla Gateways en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="2a21c-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2a21c-105">La tabla Puertas de enlace es una tabla compatible.</span><span class="sxs-lookup"><span data-stu-id="2a21c-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="2a21c-106">Cada registro almacena información acerca de una puerta de enlace que participa en llamadas de red telefónica conmutada (RTC) que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2a21c-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="2a21c-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2a21c-107">**Column**</span></span>|<span data-ttu-id="2a21c-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="2a21c-108">**Data Type**</span></span>|<span data-ttu-id="2a21c-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="2a21c-109">**Key/Index**</span></span>|<span data-ttu-id="2a21c-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="2a21c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a21c-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="2a21c-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="2a21c-112">entero</span><span class="sxs-lookup"><span data-stu-id="2a21c-112">int</span></span>  <br/> |<span data-ttu-id="2a21c-113">Principal</span><span class="sxs-lookup"><span data-stu-id="2a21c-113">Primary</span></span>  <br/> |<span data-ttu-id="2a21c-114">Número único que identifica esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="2a21c-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="2a21c-115">**Puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="2a21c-115">**Gateway**</span></span> <br/> |<span data-ttu-id="2a21c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2a21c-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="2a21c-117">Nombre de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="2a21c-117">Gateway name.</span></span>  <br/> |
   


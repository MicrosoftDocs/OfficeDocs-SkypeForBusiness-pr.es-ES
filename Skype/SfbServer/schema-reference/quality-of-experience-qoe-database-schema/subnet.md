---
title: Tabla Subnet
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: En la tabla de subred es una tabla de apoyo. Cada registro representa una subred definida en la configuración de configuración de red.
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212091"
---
# <a name="subnet-table"></a><span data-ttu-id="ff90e-104">Tabla Subnet</span><span class="sxs-lookup"><span data-stu-id="ff90e-104">Subnet table</span></span>
 
<span data-ttu-id="ff90e-105">En la tabla de subred es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="ff90e-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="ff90e-106">Cada registro representa una subred definida en la configuración de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="ff90e-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="ff90e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ff90e-107">**Column**</span></span>|<span data-ttu-id="ff90e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ff90e-108">**Data Type**</span></span>|<span data-ttu-id="ff90e-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="ff90e-109">**Key/Index**</span></span>|<span data-ttu-id="ff90e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ff90e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ff90e-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="ff90e-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="ff90e-112">int</span><span class="sxs-lookup"><span data-stu-id="ff90e-112">int</span></span>  <br/> |<span data-ttu-id="ff90e-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="ff90e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ff90e-114">Representación de enteros para la dirección IP de la subred.</span><span class="sxs-lookup"><span data-stu-id="ff90e-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="ff90e-115">**Máscara de subred**</span><span class="sxs-lookup"><span data-stu-id="ff90e-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="ff90e-116">int</span><span class="sxs-lookup"><span data-stu-id="ff90e-116">int</span></span>  <br/> ||<span data-ttu-id="ff90e-117">Máscara de la subred.</span><span class="sxs-lookup"><span data-stu-id="ff90e-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="ff90e-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="ff90e-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="ff90e-119">int</span><span class="sxs-lookup"><span data-stu-id="ff90e-119">int</span></span>  <br/> |<span data-ttu-id="ff90e-120">Externa</span><span class="sxs-lookup"><span data-stu-id="ff90e-120">Foreign</span></span>  <br/> |<span data-ttu-id="ff90e-121">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="ff90e-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="ff90e-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="ff90e-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="ff90e-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="ff90e-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="ff90e-124">La descripción de la subred.</span><span class="sxs-lookup"><span data-stu-id="ff90e-124">The description for the subnet.</span></span>  <br/> |
   


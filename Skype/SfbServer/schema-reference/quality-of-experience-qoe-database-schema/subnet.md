---
title: Tabla Subnet
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831340"
---
# <a name="subnet-table"></a><span data-ttu-id="d3861-104">Tabla Subnet</span><span class="sxs-lookup"><span data-stu-id="d3861-104">Subnet table</span></span>
 
<span data-ttu-id="d3861-p102">La tabla Subnet es una tabla de apoyo. Cada registro representa una subred definida en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="d3861-p102">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="d3861-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d3861-107">**Column**</span></span>|<span data-ttu-id="d3861-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d3861-108">**Data Type**</span></span>|<span data-ttu-id="d3861-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="d3861-109">**Key/Index**</span></span>|<span data-ttu-id="d3861-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d3861-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d3861-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="d3861-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="d3861-112">entero</span><span class="sxs-lookup"><span data-stu-id="d3861-112">int</span></span>  <br/> |<span data-ttu-id="d3861-113">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="d3861-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d3861-114">Representación en número entero de la IP de la subred.</span><span class="sxs-lookup"><span data-stu-id="d3861-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="d3861-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="d3861-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="d3861-116">entero</span><span class="sxs-lookup"><span data-stu-id="d3861-116">int</span></span>  <br/> ||<span data-ttu-id="d3861-117">Máscara de la subred.</span><span class="sxs-lookup"><span data-stu-id="d3861-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="d3861-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="d3861-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="d3861-119">entero</span><span class="sxs-lookup"><span data-stu-id="d3861-119">int</span></span>  <br/> |<span data-ttu-id="d3861-120">Externo</span><span class="sxs-lookup"><span data-stu-id="d3861-120">Foreign</span></span>  <br/> |<span data-ttu-id="d3861-121">Se hace referencia a la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="d3861-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="d3861-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="d3861-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="d3861-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="d3861-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="d3861-124">Descripción de la subred.</span><span class="sxs-lookup"><span data-stu-id="d3861-124">The description for the subnet.</span></span>  <br/> |
   


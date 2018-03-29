---
title: Tabla Subnet
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla de subred es una tabla de soporte. Cada registro representa una subred definida en configuración de red.
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a><span data-ttu-id="397a7-104">Tabla Subnet</span><span class="sxs-lookup"><span data-stu-id="397a7-104">Subnet table</span></span>
 
<span data-ttu-id="397a7-105">La tabla de subred es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="397a7-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="397a7-106">Cada registro representa una subred definida en configuración de red.</span><span class="sxs-lookup"><span data-stu-id="397a7-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="397a7-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="397a7-107">**Column**</span></span>|<span data-ttu-id="397a7-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="397a7-108">**Data Type**</span></span>|<span data-ttu-id="397a7-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="397a7-109">**Key/Index**</span></span>|<span data-ttu-id="397a7-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="397a7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="397a7-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="397a7-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="397a7-112">int</span><span class="sxs-lookup"><span data-stu-id="397a7-112">int</span></span>  <br/> |<span data-ttu-id="397a7-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="397a7-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="397a7-114">Representación de entero de la dirección IP de la subred.</span><span class="sxs-lookup"><span data-stu-id="397a7-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="397a7-115">**Máscara de subred**</span><span class="sxs-lookup"><span data-stu-id="397a7-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="397a7-116">int</span><span class="sxs-lookup"><span data-stu-id="397a7-116">int</span></span>  <br/> ||<span data-ttu-id="397a7-117">Máscara de la subred.</span><span class="sxs-lookup"><span data-stu-id="397a7-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="397a7-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="397a7-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="397a7-119">int</span><span class="sxs-lookup"><span data-stu-id="397a7-119">int</span></span>  <br/> |<span data-ttu-id="397a7-120">Externa</span><span class="sxs-lookup"><span data-stu-id="397a7-120">Foreign</span></span>  <br/> |<span data-ttu-id="397a7-121">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="397a7-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="397a7-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="397a7-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="397a7-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="397a7-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="397a7-124">Descripción de la subred.</span><span class="sxs-lookup"><span data-stu-id="397a7-124">The description for the subnet.</span></span>  <br/> |
   


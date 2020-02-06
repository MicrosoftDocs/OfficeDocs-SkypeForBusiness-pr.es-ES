---
title: Tabla Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla de subred es una tabla de soporte técnico. Cada registro representa una subred definida en la opción de configuración de red.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805208"
---
# <a name="subnet-table"></a><span data-ttu-id="a5c3f-104">Tabla Subnet</span><span class="sxs-lookup"><span data-stu-id="a5c3f-104">Subnet table</span></span>
 
<span data-ttu-id="a5c3f-105">La tabla de subred es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="a5c3f-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="a5c3f-106">Cada registro representa una subred definida en la opción de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="a5c3f-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="a5c3f-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a5c3f-107">**Column**</span></span>|<span data-ttu-id="a5c3f-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="a5c3f-108">**Data Type**</span></span>|<span data-ttu-id="a5c3f-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="a5c3f-109">**Key/Index**</span></span>|<span data-ttu-id="a5c3f-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="a5c3f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5c3f-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="a5c3f-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="a5c3f-112">int</span><span class="sxs-lookup"><span data-stu-id="a5c3f-112">int</span></span>  <br/> |<span data-ttu-id="a5c3f-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="a5c3f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a5c3f-114">Representación de enteros de la IP de subred.</span><span class="sxs-lookup"><span data-stu-id="a5c3f-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="a5c3f-115">**Máscaradesubred**</span><span class="sxs-lookup"><span data-stu-id="a5c3f-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="a5c3f-116">int</span><span class="sxs-lookup"><span data-stu-id="a5c3f-116">int</span></span>  <br/> ||<span data-ttu-id="a5c3f-117">Máscara de la subred.</span><span class="sxs-lookup"><span data-stu-id="a5c3f-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="a5c3f-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="a5c3f-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="a5c3f-119">int</span><span class="sxs-lookup"><span data-stu-id="a5c3f-119">int</span></span>  <br/> |<span data-ttu-id="a5c3f-120">Extranjero</span><span class="sxs-lookup"><span data-stu-id="a5c3f-120">Foreign</span></span>  <br/> |<span data-ttu-id="a5c3f-121">Se hace referencia a ella desde la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="a5c3f-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="a5c3f-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="a5c3f-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="a5c3f-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="a5c3f-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="a5c3f-124">La descripción de la subred.</span><span class="sxs-lookup"><span data-stu-id="a5c3f-124">The description for the subnet.</span></span>  <br/> |
   


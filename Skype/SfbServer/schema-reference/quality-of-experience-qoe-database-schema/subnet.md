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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabla de subred es una tabla de soporte técnico. Cada registro representa una subred definida en la opción de configuración de red.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294638"
---
# <a name="subnet-table"></a><span data-ttu-id="fd753-104">Tabla Subnet</span><span class="sxs-lookup"><span data-stu-id="fd753-104">Subnet table</span></span>
 
<span data-ttu-id="fd753-105">La tabla de subred es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fd753-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="fd753-106">Cada registro representa una subred definida en la opción de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="fd753-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="fd753-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fd753-107">**Column**</span></span>|<span data-ttu-id="fd753-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="fd753-108">**Data Type**</span></span>|<span data-ttu-id="fd753-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="fd753-109">**Key/Index**</span></span>|<span data-ttu-id="fd753-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="fd753-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd753-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="fd753-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="fd753-112">int</span><span class="sxs-lookup"><span data-stu-id="fd753-112">int</span></span>  <br/> |<span data-ttu-id="fd753-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="fd753-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fd753-114">Representación de enteros de la IP de subred.</span><span class="sxs-lookup"><span data-stu-id="fd753-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="fd753-115">**Máscaradesubred**</span><span class="sxs-lookup"><span data-stu-id="fd753-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="fd753-116">int</span><span class="sxs-lookup"><span data-stu-id="fd753-116">int</span></span>  <br/> ||<span data-ttu-id="fd753-117">Máscara de la subred.</span><span class="sxs-lookup"><span data-stu-id="fd753-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="fd753-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="fd753-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="fd753-119">int</span><span class="sxs-lookup"><span data-stu-id="fd753-119">int</span></span>  <br/> |<span data-ttu-id="fd753-120">Extranjero</span><span class="sxs-lookup"><span data-stu-id="fd753-120">Foreign</span></span>  <br/> |<span data-ttu-id="fd753-121">Se hace referencia a ella desde la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="fd753-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="fd753-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="fd753-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="fd753-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="fd753-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="fd753-124">La descripción de la subred.</span><span class="sxs-lookup"><span data-stu-id="fd753-124">The description for the subnet.</span></span>  <br/> |
   


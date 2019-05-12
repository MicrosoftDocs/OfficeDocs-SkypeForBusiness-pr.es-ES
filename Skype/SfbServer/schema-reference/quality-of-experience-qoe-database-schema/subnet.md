---
title: Tabla Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: En la tabla de subred es una tabla de apoyo. Cada registro representa una subred definida en la configuración de configuración de red.
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907069"
---
# <a name="subnet-table"></a><span data-ttu-id="ced41-104">Tabla Subnet</span><span class="sxs-lookup"><span data-stu-id="ced41-104">Subnet table</span></span>
 
<span data-ttu-id="ced41-105">En la tabla de subred es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="ced41-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="ced41-106">Cada registro representa una subred definida en la configuración de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="ced41-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="ced41-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ced41-107">**Column**</span></span>|<span data-ttu-id="ced41-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ced41-108">**Data Type**</span></span>|<span data-ttu-id="ced41-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="ced41-109">**Key/Index**</span></span>|<span data-ttu-id="ced41-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ced41-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ced41-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="ced41-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="ced41-112">int</span><span class="sxs-lookup"><span data-stu-id="ced41-112">int</span></span>  <br/> |<span data-ttu-id="ced41-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="ced41-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ced41-114">Representación de enteros para la dirección IP de la subred.</span><span class="sxs-lookup"><span data-stu-id="ced41-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="ced41-115">**Máscara de subred**</span><span class="sxs-lookup"><span data-stu-id="ced41-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="ced41-116">int</span><span class="sxs-lookup"><span data-stu-id="ced41-116">int</span></span>  <br/> ||<span data-ttu-id="ced41-117">Máscara de la subred.</span><span class="sxs-lookup"><span data-stu-id="ced41-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="ced41-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="ced41-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="ced41-119">int</span><span class="sxs-lookup"><span data-stu-id="ced41-119">int</span></span>  <br/> |<span data-ttu-id="ced41-120">Externa</span><span class="sxs-lookup"><span data-stu-id="ced41-120">Foreign</span></span>  <br/> |<span data-ttu-id="ced41-121">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="ced41-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="ced41-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="ced41-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="ced41-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="ced41-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="ced41-124">La descripción de la subred.</span><span class="sxs-lookup"><span data-stu-id="ced41-124">The description for the subnet.</span></span>  <br/> |
   


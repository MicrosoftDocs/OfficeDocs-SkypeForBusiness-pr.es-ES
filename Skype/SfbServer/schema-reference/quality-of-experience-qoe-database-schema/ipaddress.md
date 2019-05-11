---
title: Tabla IPAddress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: En la tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en la base de datos de calidad de la experiencia. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: d7d3b5f9192c2385836f42f9c430da5b99752892
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920036"
---
# <a name="ipaddress-table"></a><span data-ttu-id="3d5a8-104">Tabla IPAddress</span><span class="sxs-lookup"><span data-stu-id="3d5a8-104">IPAddress table</span></span>
 
<span data-ttu-id="3d5a8-105">En la tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="3d5a8-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3d5a8-106">En esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d5a8-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3d5a8-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-107">**Column**</span></span>|<span data-ttu-id="3d5a8-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-108">**Data Type**</span></span>|<span data-ttu-id="3d5a8-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-109">**Key/Index**</span></span>|<span data-ttu-id="3d5a8-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3d5a8-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="3d5a8-112">int</span><span class="sxs-lookup"><span data-stu-id="3d5a8-112">int</span></span>  <br/> |<span data-ttu-id="3d5a8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3d5a8-113">Primary</span></span>  <br/> |<span data-ttu-id="3d5a8-114">Identificador único de la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="3d5a8-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="3d5a8-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="3d5a8-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="3d5a8-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="3d5a8-117">Único</span><span class="sxs-lookup"><span data-stu-id="3d5a8-117">Unique</span></span>  <br/> |<span data-ttu-id="3d5a8-118">Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a la IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="3d5a8-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="3d5a8-119">Esto puede resultar una IPv4 o una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="3d5a8-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   


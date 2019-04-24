---
title: Tabla IPAddress
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: En la tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en la base de datos de calidad de la experiencia. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212210"
---
# <a name="ipaddress-table"></a><span data-ttu-id="dd87a-104">Tabla IPAddress</span><span class="sxs-lookup"><span data-stu-id="dd87a-104">IPAddress table</span></span>
 
<span data-ttu-id="dd87a-105">En la tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="dd87a-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="dd87a-106">En esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd87a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="dd87a-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dd87a-107">**Column**</span></span>|<span data-ttu-id="dd87a-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="dd87a-108">**Data Type**</span></span>|<span data-ttu-id="dd87a-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="dd87a-109">**Key/Index**</span></span>|<span data-ttu-id="dd87a-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="dd87a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dd87a-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="dd87a-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="dd87a-112">int</span><span class="sxs-lookup"><span data-stu-id="dd87a-112">int</span></span>  <br/> |<span data-ttu-id="dd87a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="dd87a-113">Primary</span></span>  <br/> |<span data-ttu-id="dd87a-114">Identificador único de la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="dd87a-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="dd87a-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="dd87a-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="dd87a-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="dd87a-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="dd87a-117">Único</span><span class="sxs-lookup"><span data-stu-id="dd87a-117">Unique</span></span>  <br/> |<span data-ttu-id="dd87a-118">Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a la IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="dd87a-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="dd87a-119">Esto puede resultar una IPv4 o una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="dd87a-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   


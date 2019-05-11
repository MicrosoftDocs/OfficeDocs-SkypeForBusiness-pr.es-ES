---
title: Tabla Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: En la tabla de teléfonos es una tabla de apoyo. Cada registro en la tabla almacena información acerca de un número de teléfono que participan en llamadas VoIP que tienen registros en la base de datos.
ms.openlocfilehash: ba13a059e043cf2a18c41c28dce1a2a54e694b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930619"
---
# <a name="phones-table"></a><span data-ttu-id="22d87-104">Tabla Phones</span><span class="sxs-lookup"><span data-stu-id="22d87-104">Phones table</span></span>
 
<span data-ttu-id="22d87-105">En la tabla de teléfonos es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="22d87-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="22d87-106">Cada registro en la tabla almacena información acerca de un número de teléfono que participan en llamadas VoIP que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="22d87-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="22d87-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="22d87-107">**Column**</span></span>|<span data-ttu-id="22d87-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22d87-108">**Data Type**</span></span>|<span data-ttu-id="22d87-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="22d87-109">**Key/Index**</span></span>|<span data-ttu-id="22d87-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="22d87-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22d87-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="22d87-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="22d87-112">int</span><span class="sxs-lookup"><span data-stu-id="22d87-112">int</span></span>  <br/> |<span data-ttu-id="22d87-113">Primary</span><span class="sxs-lookup"><span data-stu-id="22d87-113">Primary</span></span>  <br/> |<span data-ttu-id="22d87-114">Número único que identifica este teléfono.</span><span class="sxs-lookup"><span data-stu-id="22d87-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="22d87-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="22d87-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="22d87-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="22d87-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="22d87-117">Número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="22d87-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="22d87-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="22d87-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="22d87-119">fecha y hora</span><span class="sxs-lookup"><span data-stu-id="22d87-119">dateTime</span></span>  <br/> ||<span data-ttu-id="22d87-120">Marca de tiempo (sólo para uso interno).</span><span class="sxs-lookup"><span data-stu-id="22d87-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="22d87-121">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22d87-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   


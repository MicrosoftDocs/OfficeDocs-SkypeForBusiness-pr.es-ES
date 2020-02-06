---
title: Tabla Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabla teléfonos es una tabla de soporte técnico. Cada registro de la tabla almacena información acerca de un número de teléfono implicado en llamadas VoIP que tienen registros en la base de datos.
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815008"
---
# <a name="phones-table"></a><span data-ttu-id="08ad8-104">Tabla Phones</span><span class="sxs-lookup"><span data-stu-id="08ad8-104">Phones table</span></span>
 
<span data-ttu-id="08ad8-105">La tabla teléfonos es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="08ad8-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="08ad8-106">Cada registro de la tabla almacena información acerca de un número de teléfono implicado en llamadas VoIP que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="08ad8-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="08ad8-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="08ad8-107">**Column**</span></span>|<span data-ttu-id="08ad8-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="08ad8-108">**Data Type**</span></span>|<span data-ttu-id="08ad8-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="08ad8-109">**Key/Index**</span></span>|<span data-ttu-id="08ad8-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="08ad8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08ad8-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="08ad8-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="08ad8-112">int</span><span class="sxs-lookup"><span data-stu-id="08ad8-112">int</span></span>  <br/> |<span data-ttu-id="08ad8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="08ad8-113">Primary</span></span>  <br/> |<span data-ttu-id="08ad8-114">Número único que identifica este teléfono.</span><span class="sxs-lookup"><span data-stu-id="08ad8-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="08ad8-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="08ad8-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="08ad8-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="08ad8-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="08ad8-117">Número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="08ad8-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="08ad8-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="08ad8-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="08ad8-119">Fechas</span><span class="sxs-lookup"><span data-stu-id="08ad8-119">dateTime</span></span>  <br/> ||<span data-ttu-id="08ad8-120">Marca de tiempo (solo para uso interno).</span><span class="sxs-lookup"><span data-stu-id="08ad8-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="08ad8-121">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08ad8-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   


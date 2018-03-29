---
title: Tabla Phones
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabla de teléfonos es un auxiliar. Cada registro de la tabla almacena información sobre un número de teléfono en llamadas VoIP que tengan registros en la base de datos.
ms.openlocfilehash: 8ec2095b857ba474a92bf0766d86119500919f51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="phones-table"></a><span data-ttu-id="1cf0a-104">Tabla Phones</span><span class="sxs-lookup"><span data-stu-id="1cf0a-104">Phones table</span></span>
 
<span data-ttu-id="1cf0a-105">La tabla de teléfonos es un auxiliar.</span><span class="sxs-lookup"><span data-stu-id="1cf0a-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="1cf0a-106">Cada registro de la tabla almacena información sobre un número de teléfono en llamadas VoIP que tengan registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1cf0a-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="1cf0a-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-107">**Column**</span></span>|<span data-ttu-id="1cf0a-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-108">**Data Type**</span></span>|<span data-ttu-id="1cf0a-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-109">**Key/Index**</span></span>|<span data-ttu-id="1cf0a-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1cf0a-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="1cf0a-112">int</span><span class="sxs-lookup"><span data-stu-id="1cf0a-112">int</span></span>  <br/> |<span data-ttu-id="1cf0a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1cf0a-113">Primary</span></span>  <br/> |<span data-ttu-id="1cf0a-114">Número único que identifica este teléfono.</span><span class="sxs-lookup"><span data-stu-id="1cf0a-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="1cf0a-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="1cf0a-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="1cf0a-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="1cf0a-117">Número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="1cf0a-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="1cf0a-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="1cf0a-119">fecha y hora</span><span class="sxs-lookup"><span data-stu-id="1cf0a-119">dateTime</span></span>  <br/> ||<span data-ttu-id="1cf0a-120">Marca de hora (sólo para uso interno).</span><span class="sxs-lookup"><span data-stu-id="1cf0a-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="1cf0a-121">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cf0a-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   


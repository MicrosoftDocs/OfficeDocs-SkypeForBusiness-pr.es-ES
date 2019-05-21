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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabla teléfonos es una tabla de soporte técnico. Cada registro de la tabla almacena información acerca de un número de teléfono implicado en llamadas VoIP que tienen registros en la base de datos.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295947"
---
# <a name="phones-table"></a><span data-ttu-id="c590f-104">Tabla Phones</span><span class="sxs-lookup"><span data-stu-id="c590f-104">Phones table</span></span>
 
<span data-ttu-id="c590f-105">La tabla teléfonos es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="c590f-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="c590f-106">Cada registro de la tabla almacena información acerca de un número de teléfono implicado en llamadas VoIP que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c590f-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="c590f-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c590f-107">**Column**</span></span>|<span data-ttu-id="c590f-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c590f-108">**Data Type**</span></span>|<span data-ttu-id="c590f-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="c590f-109">**Key/Index**</span></span>|<span data-ttu-id="c590f-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c590f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c590f-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="c590f-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="c590f-112">int</span><span class="sxs-lookup"><span data-stu-id="c590f-112">int</span></span>  <br/> |<span data-ttu-id="c590f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c590f-113">Primary</span></span>  <br/> |<span data-ttu-id="c590f-114">Número único que identifica este teléfono.</span><span class="sxs-lookup"><span data-stu-id="c590f-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="c590f-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="c590f-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="c590f-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c590f-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="c590f-117">Número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="c590f-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="c590f-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="c590f-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="c590f-119">Fechas</span><span class="sxs-lookup"><span data-stu-id="c590f-119">dateTime</span></span>  <br/> ||<span data-ttu-id="c590f-120">Marca de tiempo (solo para uso interno).</span><span class="sxs-lookup"><span data-stu-id="c590f-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="c590f-121">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c590f-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   


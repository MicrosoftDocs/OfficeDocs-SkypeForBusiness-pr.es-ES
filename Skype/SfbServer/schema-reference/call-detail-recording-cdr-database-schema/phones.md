---
title: Tabla Teléfonos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabla Teléfonos es una tabla de apoyo. Cada registro de la tabla almacena información sobre un número de teléfono implicado en las llamadas VoIP que tienen registros en la base de datos.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823270"
---
# <a name="phones-table"></a><span data-ttu-id="f311d-104">Tabla Teléfonos</span><span class="sxs-lookup"><span data-stu-id="f311d-104">Phones table</span></span>
 
<span data-ttu-id="f311d-105">La tabla Teléfonos es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="f311d-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="f311d-106">Cada registro de la tabla almacena información sobre un número de teléfono implicado en las llamadas VoIP que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f311d-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="f311d-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f311d-107">**Column**</span></span>|<span data-ttu-id="f311d-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f311d-108">**Data Type**</span></span>|<span data-ttu-id="f311d-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="f311d-109">**Key/Index**</span></span>|<span data-ttu-id="f311d-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="f311d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f311d-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="f311d-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="f311d-112">entero</span><span class="sxs-lookup"><span data-stu-id="f311d-112">int</span></span>  <br/> |<span data-ttu-id="f311d-113">Principal</span><span class="sxs-lookup"><span data-stu-id="f311d-113">Primary</span></span>  <br/> |<span data-ttu-id="f311d-114">Número único que identifica este teléfono.</span><span class="sxs-lookup"><span data-stu-id="f311d-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="f311d-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="f311d-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="f311d-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="f311d-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="f311d-117">Número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f311d-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="f311d-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="f311d-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="f311d-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="f311d-119">dateTime</span></span>  <br/> ||<span data-ttu-id="f311d-120">Marca de tiempo (solo para uso interno).</span><span class="sxs-lookup"><span data-stu-id="f311d-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="f311d-121">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f311d-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   


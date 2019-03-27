---
title: Tabla Tenants
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: En la tabla de inquilinos es una tabla de apoyo que almacena una lista de los inquilinos distintos. Cada registro de la tabla representa a un inquilino.
ms.openlocfilehash: cf7d0271c9cacfd76079a80a7e5db63d669a8dfb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873993"
---
# <a name="tenants-table"></a><span data-ttu-id="5af51-104">Tabla Tenants</span><span class="sxs-lookup"><span data-stu-id="5af51-104">Tenants table</span></span>
 
<span data-ttu-id="5af51-105">En la tabla de inquilinos es una tabla de apoyo que almacena una lista de los inquilinos distintos.</span><span class="sxs-lookup"><span data-stu-id="5af51-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="5af51-106">Cada registro de la tabla representa a un inquilino.</span><span class="sxs-lookup"><span data-stu-id="5af51-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5af51-107">En la implementación local, CDR usa el identificador de inquilino de compilación para indicar distintos tipos de autenticación, como la conectividad de mensajería instantánea pública, federada y anónima.</span><span class="sxs-lookup"><span data-stu-id="5af51-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="5af51-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5af51-108">**Column**</span></span>|<span data-ttu-id="5af51-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="5af51-109">**Data Type**</span></span>|<span data-ttu-id="5af51-110">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="5af51-110">**Key/Index**</span></span>|<span data-ttu-id="5af51-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="5af51-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5af51-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="5af51-112">**TenantId**</span></span> <br/> |<span data-ttu-id="5af51-113">int</span><span class="sxs-lookup"><span data-stu-id="5af51-113">int</span></span>  <br/> |<span data-ttu-id="5af51-114">Primary</span><span class="sxs-lookup"><span data-stu-id="5af51-114">Primary</span></span>  <br/> |<span data-ttu-id="5af51-115">Número único que identifica este identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="5af51-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="5af51-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="5af51-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="5af51-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5af51-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="5af51-118">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="5af51-118">Allowed values:</span></span> <br/>  <span data-ttu-id="5af51-119">00000000-0000-0000-0000-000000000000-Enterprise</span><span class="sxs-lookup"><span data-stu-id="5af51-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="5af51-120">00000000-0000-0000-0000-000000000001-federado</span><span class="sxs-lookup"><span data-stu-id="5af51-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="5af51-121">00000000-0000-0000-0000-000000000002 - anónimo</span><span class="sxs-lookup"><span data-stu-id="5af51-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="5af51-122">00000000-0000-0000-0000-000000000003-conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="5af51-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   


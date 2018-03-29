---
title: Tabla Tenants
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabla de los inquilinos es una tabla de soporte que almacena una lista de los varios inquilinos. Cada registro de la tabla representa a un arrendatario.
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a><span data-ttu-id="be07b-104">Tabla Tenants</span><span class="sxs-lookup"><span data-stu-id="be07b-104">Tenants table</span></span>
 
<span data-ttu-id="be07b-105">La tabla de los inquilinos es una tabla de soporte que almacena una lista de los varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="be07b-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="be07b-106">Cada registro de la tabla representa a un arrendatario.</span><span class="sxs-lookup"><span data-stu-id="be07b-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="be07b-107">En la implementación local, CDR utiliza el identificador de inquilinos de compilación para indicar el tipo de autenticación diferentes, como la conectividad con IM pública, federados y anónimos.</span><span class="sxs-lookup"><span data-stu-id="be07b-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="be07b-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="be07b-108">**Column**</span></span>|<span data-ttu-id="be07b-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="be07b-109">**Data Type**</span></span>|<span data-ttu-id="be07b-110">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="be07b-110">**Key/Index**</span></span>|<span data-ttu-id="be07b-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="be07b-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be07b-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="be07b-112">**TenantId**</span></span> <br/> |<span data-ttu-id="be07b-113">int</span><span class="sxs-lookup"><span data-stu-id="be07b-113">int</span></span>  <br/> |<span data-ttu-id="be07b-114">Primary</span><span class="sxs-lookup"><span data-stu-id="be07b-114">Primary</span></span>  <br/> |<span data-ttu-id="be07b-115">Número único que identifica este ID de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="be07b-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="be07b-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="be07b-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="be07b-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="be07b-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="be07b-118">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="be07b-118">Allowed values:</span></span> <br/>  <span data-ttu-id="be07b-119">00000000-0000-0000-0000-000000000000-corporativo</span><span class="sxs-lookup"><span data-stu-id="be07b-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="be07b-120">00000000-0000-0000-0000-000000000001-federado</span><span class="sxs-lookup"><span data-stu-id="be07b-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="be07b-121">00000000-0000-0000-0000-000000000002 - anónimo</span><span class="sxs-lookup"><span data-stu-id="be07b-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="be07b-122">00000000-0000-0000-0000-000000000003-conectividad con IM pública</span><span class="sxs-lookup"><span data-stu-id="be07b-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   


---
title: Tabla Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabla de inquilinos es una tabla de soporte que almacena una lista de los distintos inquilinos. Cada registro de la tabla representa un inquilino.
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295772"
---
# <a name="tenants-table"></a><span data-ttu-id="e534e-104">Tabla Tenants</span><span class="sxs-lookup"><span data-stu-id="e534e-104">Tenants table</span></span>
 
<span data-ttu-id="e534e-105">La tabla de inquilinos es una tabla de soporte que almacena una lista de los distintos inquilinos.</span><span class="sxs-lookup"><span data-stu-id="e534e-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="e534e-106">Cada registro de la tabla representa un inquilino.</span><span class="sxs-lookup"><span data-stu-id="e534e-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e534e-107">En la implementación local, CDR usa el identificador de inquilino de la compilación para indicar un tipo de autenticación diferente, como la conectividad de mensajería instantánea pública, federada y anónima.</span><span class="sxs-lookup"><span data-stu-id="e534e-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="e534e-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e534e-108">**Column**</span></span>|<span data-ttu-id="e534e-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e534e-109">**Data Type**</span></span>|<span data-ttu-id="e534e-110">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="e534e-110">**Key/Index**</span></span>|<span data-ttu-id="e534e-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="e534e-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e534e-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="e534e-112">**TenantId**</span></span> <br/> |<span data-ttu-id="e534e-113">int</span><span class="sxs-lookup"><span data-stu-id="e534e-113">int</span></span>  <br/> |<span data-ttu-id="e534e-114">Primary</span><span class="sxs-lookup"><span data-stu-id="e534e-114">Primary</span></span>  <br/> |<span data-ttu-id="e534e-115">Número único que identifica este ID de inquilino.</span><span class="sxs-lookup"><span data-stu-id="e534e-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="e534e-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="e534e-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="e534e-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e534e-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e534e-118">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="e534e-118">Allowed values:</span></span> <br/>  <span data-ttu-id="e534e-119">00000000-0000-0000-0000-000000000000-empresa</span><span class="sxs-lookup"><span data-stu-id="e534e-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="e534e-120">00000000-0000-0000-0000-000000000001-federado</span><span class="sxs-lookup"><span data-stu-id="e534e-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="e534e-121">00000000-0000-0000-0000-000000000002-anónimo</span><span class="sxs-lookup"><span data-stu-id="e534e-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="e534e-122">00000000-0000-0000-0000-000000000003-conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="e534e-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   


---
title: Tabla Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabla Inquilinos es una tabla auxiliar que almacena una lista de los diversos inquilinos. Cada registro de la tabla representa a un inquilino.
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831720"
---
# <a name="tenants-table"></a><span data-ttu-id="2b712-104">Tabla Tenants</span><span class="sxs-lookup"><span data-stu-id="2b712-104">Tenants table</span></span>
 
<span data-ttu-id="2b712-p102">La tabla Inquilinos es una tabla auxiliar que almacena una lista de los diversos inquilinos. Cada registro de la tabla representa a un inquilino.</span><span class="sxs-lookup"><span data-stu-id="2b712-p102">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b712-107">En una instalación local, el CDR usa el identificador de inquilino integrado para indicar distintos tipos de autenticación, como la de conectividad de mensajería instantánea pública, federada y anónima.</span><span class="sxs-lookup"><span data-stu-id="2b712-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="2b712-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2b712-108">**Column**</span></span>|<span data-ttu-id="2b712-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="2b712-109">**Data Type**</span></span>|<span data-ttu-id="2b712-110">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="2b712-110">**Key/Index**</span></span>|<span data-ttu-id="2b712-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="2b712-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b712-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="2b712-112">**TenantId**</span></span> <br/> |<span data-ttu-id="2b712-113">entero</span><span class="sxs-lookup"><span data-stu-id="2b712-113">int</span></span>  <br/> |<span data-ttu-id="2b712-114">Principal</span><span class="sxs-lookup"><span data-stu-id="2b712-114">Primary</span></span>  <br/> |<span data-ttu-id="2b712-115">Número único que identifica este identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="2b712-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="2b712-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="2b712-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="2b712-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b712-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="2b712-118">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="2b712-118">Allowed values:</span></span> <br/>  <span data-ttu-id="2b712-119">00000000-0000-0000-0000-000000000000 - Enterprise</span><span class="sxs-lookup"><span data-stu-id="2b712-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="2b712-120">00000000-0000-0000-0000-000000000001 - Federado</span><span class="sxs-lookup"><span data-stu-id="2b712-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="2b712-121">00000000-0000-0000-0000-000000000002 - Anónimo</span><span class="sxs-lookup"><span data-stu-id="2b712-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="2b712-122">00000000-0000-0000-0000-000000000003- Conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="2b712-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   


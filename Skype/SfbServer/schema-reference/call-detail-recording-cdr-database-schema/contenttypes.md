---
title: Tabla ContentTypes en Skype empresarial Server 2015
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabla ContentTypes es una tabla de soporte que almacena una lista de los tipos de contenido que se usan en sesiones de punto a punto y en sesiones de conferencia. Cada registro de la tabla representa un tipo de contenido.
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815308"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="37310-104">Tabla ContentTypes en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="37310-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="37310-105">La tabla ContentTypes es una tabla de soporte que almacena una lista de los tipos de contenido que se usan en sesiones de punto a punto y en sesiones de conferencia.</span><span class="sxs-lookup"><span data-stu-id="37310-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="37310-106">Cada registro de la tabla representa un tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="37310-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="37310-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="37310-107">**Column**</span></span>|<span data-ttu-id="37310-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="37310-108">**Data Type**</span></span>|<span data-ttu-id="37310-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="37310-109">**Key/Index**</span></span>|<span data-ttu-id="37310-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="37310-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="37310-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="37310-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="37310-112">int</span><span class="sxs-lookup"><span data-stu-id="37310-112">int</span></span>  <br/> |<span data-ttu-id="37310-113">Primary</span><span class="sxs-lookup"><span data-stu-id="37310-113">Primary</span></span>  <br/> |<span data-ttu-id="37310-114">Número único que identifica el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="37310-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="37310-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="37310-115">**ContentType**</span></span> <br/> |<span data-ttu-id="37310-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="37310-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="37310-117">Nombre del tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="37310-117">Content type name.</span></span>  <br/> |
   


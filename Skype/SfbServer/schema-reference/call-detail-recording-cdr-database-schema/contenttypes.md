---
title: Tabla de tipos de contenido en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabla de tipos de contenido es una tabla de soporte que almacena una lista de los tipos de contenido usados en sesiones de peer-to-peer y sesiones de la conferencia. Cada registro de la tabla representa un tipo de contenido.
ms.openlocfilehash: 207e2a4e6ba605950181c437c236205fc8b2778f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="58813-104">Tabla de tipos de contenido en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="58813-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="58813-105">La tabla de tipos de contenido es una tabla de soporte que almacena una lista de los tipos de contenido usados en sesiones de peer-to-peer y sesiones de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="58813-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="58813-106">Cada registro de la tabla representa un tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="58813-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="58813-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="58813-107">**Column**</span></span>|<span data-ttu-id="58813-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="58813-108">**Data Type**</span></span>|<span data-ttu-id="58813-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="58813-109">**Key/Index**</span></span>|<span data-ttu-id="58813-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="58813-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58813-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="58813-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="58813-112">int</span><span class="sxs-lookup"><span data-stu-id="58813-112">int</span></span>  <br/> |<span data-ttu-id="58813-113">Primary</span><span class="sxs-lookup"><span data-stu-id="58813-113">Primary</span></span>  <br/> |<span data-ttu-id="58813-114">Número único que identifica el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="58813-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="58813-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="58813-115">**ContentType**</span></span> <br/> |<span data-ttu-id="58813-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="58813-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="58813-117">Nombre de tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="58813-117">Content type name.</span></span>  <br/> |
   


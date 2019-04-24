---
title: Tabla ContentTypes de Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: En la tabla ContentTypes es una tabla de apoyo que almacena una lista de los tipos de contenido que se utiliza en las sesiones de punto a punto y las sesiones de conferencia. Cada registro de la tabla representa un tipo de contenido.
ms.openlocfilehash: 77bbe375a5870d11c7e4a17a0f32392fe14975a0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213252"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="59e69-104">Tabla ContentTypes de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="59e69-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="59e69-105">En la tabla ContentTypes es una tabla de apoyo que almacena una lista de los tipos de contenido que se utiliza en las sesiones de punto a punto y las sesiones de conferencia.</span><span class="sxs-lookup"><span data-stu-id="59e69-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="59e69-106">Cada registro de la tabla representa un tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="59e69-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="59e69-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="59e69-107">**Column**</span></span>|<span data-ttu-id="59e69-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="59e69-108">**Data Type**</span></span>|<span data-ttu-id="59e69-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="59e69-109">**Key/Index**</span></span>|<span data-ttu-id="59e69-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="59e69-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="59e69-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="59e69-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="59e69-112">int</span><span class="sxs-lookup"><span data-stu-id="59e69-112">int</span></span>  <br/> |<span data-ttu-id="59e69-113">Primary</span><span class="sxs-lookup"><span data-stu-id="59e69-113">Primary</span></span>  <br/> |<span data-ttu-id="59e69-114">Número único que identifica el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="59e69-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="59e69-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="59e69-115">**ContentType**</span></span> <br/> |<span data-ttu-id="59e69-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="59e69-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="59e69-117">Nombre de tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="59e69-117">Content type name.</span></span>  <br/> |
   


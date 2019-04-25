---
title: Obtener elementos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumen: Obtenga información acerca de la operación obtener elementos, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: ad4be2c09de9d71499cd7592989334ccf4cf17c9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235733"
---
# <a name="get-items"></a><span data-ttu-id="768e4-105">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="768e4-105">Get Items</span></span>
 
<span data-ttu-id="768e4-106">**Resumen:** Obtenga información acerca de la operación obtener elementos, que es parte del servicio de elemento.</span><span class="sxs-lookup"><span data-stu-id="768e4-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="768e4-107">El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="768e4-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="768e4-108">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="768e4-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="768e4-109">La operación obtener elementos es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="768e4-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="768e4-110">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="768e4-110">Get Items</span></span>

<span data-ttu-id="768e4-111">Obtener elementos devuelve todos los elementos en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="768e4-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="768e4-112">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="768e4-112">**Method**</span></span>|<span data-ttu-id="768e4-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="768e4-113">**Request URI**</span></span>|<span data-ttu-id="768e4-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="768e4-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="768e4-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="768e4-115">GET</span></span>  <br/> |<span data-ttu-id="768e4-116">https://\<portal\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="768e4-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="768e4-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="768e4-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="768e4-118">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="768e4-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="768e4-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="768e4-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="768e4-120">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="768e4-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="768e4-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="768e4-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="768e4-122">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="768e4-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="768e4-123">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="768e4-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="768e4-124">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="768e4-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="768e4-125">Se devuelve una matriz de objetos de elemento.</span><span class="sxs-lookup"><span data-stu-id="768e4-125">An array of Item objects is returned.</span></span> <span data-ttu-id="768e4-126">Para obtener información detallada sobre el objeto de elemento, vea obtener elemento.</span><span class="sxs-lookup"><span data-stu-id="768e4-126">For details about Item object, see Get Item.</span></span> 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```

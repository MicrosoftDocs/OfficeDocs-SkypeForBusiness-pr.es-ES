---
title: Obtener configuración de usuario
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumen: obtenga información sobre la operación Obtener configuración de usuario, que forma parte del Servicio de configuración de usuario. El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832490"
---
# <a name="get-user-setting"></a><span data-ttu-id="a9fbf-105">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="a9fbf-105">Get User Setting</span></span>
 
<span data-ttu-id="a9fbf-106">**Resumen:** Obtenga información sobre la operación Obtener configuración de usuario, que forma parte del Servicio de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="a9fbf-107">El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a9fbf-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a9fbf-109">La operación Obtener configuración de usuario forma parte del Servicio de configuración de usuario en la API de repositorio para el Panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="a9fbf-110">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="a9fbf-110">Get User Setting</span></span>

<span data-ttu-id="a9fbf-111">Obtener configuración de usuario devuelve una configuración de usuario único.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="a9fbf-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="a9fbf-112">**Method**</span></span>|<span data-ttu-id="a9fbf-113">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="a9fbf-113">**Request URI**</span></span>|<span data-ttu-id="a9fbf-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="a9fbf-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a9fbf-115">GET</span><span class="sxs-lookup"><span data-stu-id="a9fbf-115">GET</span></span>  <br/> |<span data-ttu-id="a9fbf-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="a9fbf-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="a9fbf-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a9fbf-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a9fbf-118">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a9fbf-119">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a9fbf-120">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a9fbf-121">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a9fbf-122">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="a9fbf-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="a9fbf-123">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a9fbf-124">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="a9fbf-125">*userId:*  id. del usuario.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="a9fbf-126">*clave:*  clave de la configuración.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="a9fbf-127">*valor:*  valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="a9fbf-127">*value*  - Value of the setting.</span></span>
  


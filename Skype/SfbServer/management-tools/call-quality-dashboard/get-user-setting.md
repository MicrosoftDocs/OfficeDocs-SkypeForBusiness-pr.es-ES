---
title: Obtener configuración de usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumen: Obtenga información sobre la operación obtener configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 295e12405eb6a7ebbf45b87e3a06f3a745b90bad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274656"
---
# <a name="get-user-setting"></a><span data-ttu-id="c6580-105">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="c6580-105">Get User Setting</span></span>
 
<span data-ttu-id="c6580-106">**Resumen:** Obtenga más información sobre la operación obtener configuración de usuario, que es parte del servicio de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="c6580-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="c6580-107">El servicio de configuración de usuario es parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c6580-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c6580-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c6580-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c6580-109">La operación obtener configuración del usuario es parte del servicio de configuración de usuario en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c6580-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="c6580-110">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="c6580-110">Get User Setting</span></span>

<span data-ttu-id="c6580-111">Obtener configuración de usuario devuelve la configuración de un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="c6580-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="c6580-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="c6580-112">**Method**</span></span>|<span data-ttu-id="c6580-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="c6580-113">**Request URI**</span></span>|<span data-ttu-id="c6580-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="c6580-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6580-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="c6580-115">GET</span></span>  <br/> |<span data-ttu-id="c6580-116">https://\<portal\>/QoERepositoryService/Repository/User/{userId}/Setting/{Key}</span><span class="sxs-lookup"><span data-stu-id="c6580-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="c6580-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c6580-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c6580-118">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="c6580-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c6580-119">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="c6580-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c6580-120">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="c6580-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c6580-121">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c6580-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c6580-122">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="c6580-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="c6580-123">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="c6580-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c6580-124">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="c6580-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="c6580-125">\*\* ID. de usuario.</span><span class="sxs-lookup"><span data-stu-id="c6580-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="c6580-126">clave *clave* de la configuración.</span><span class="sxs-lookup"><span data-stu-id="c6580-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="c6580-127">*valor* : valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="c6580-127">*value*  - Value of the setting.</span></span>
  


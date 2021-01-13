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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumen: obtenga información sobre la operación Obtener configuración de usuario, que forma parte del Servicio de configuración de usuario. El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832480"
---
# <a name="get-user-settings"></a><span data-ttu-id="dc37e-105">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="dc37e-105">Get User Settings</span></span>
 
<span data-ttu-id="dc37e-106">**Resumen:** Obtenga información sobre la operación Obtener configuración de usuario, que forma parte del Servicio de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="dc37e-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="dc37e-107">El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="dc37e-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="dc37e-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="dc37e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="dc37e-109">La operación Obtener configuración de usuario forma parte del Servicio de configuración de usuario en la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="dc37e-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="dc37e-110">Obtener configuración de usuario</span><span class="sxs-lookup"><span data-stu-id="dc37e-110">Get User Settings</span></span>

<span data-ttu-id="dc37e-111">Obtener configuración de usuario devuelve una lista de configuraciones para un usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="dc37e-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="dc37e-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="dc37e-112">**Method**</span></span>|<span data-ttu-id="dc37e-113">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="dc37e-113">**Request URI**</span></span>|<span data-ttu-id="dc37e-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="dc37e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dc37e-115">GET</span><span class="sxs-lookup"><span data-stu-id="dc37e-115">GET</span></span>  <br/> |<span data-ttu-id="dc37e-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="dc37e-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="dc37e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="dc37e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="dc37e-118">**Parámetros de URI**</span><span class="sxs-lookup"><span data-stu-id="dc37e-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="dc37e-119">*efectivo:*  opcional.</span><span class="sxs-lookup"><span data-stu-id="dc37e-119">*effective*  - Optional.</span></span> <span data-ttu-id="dc37e-120">Este parámetro solo se aplica cuando se usa el identificador de usuario especial predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dc37e-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="dc37e-121">En otros casos, se omitirá.</span><span class="sxs-lookup"><span data-stu-id="dc37e-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="dc37e-122">`True` devuelve una configuración de usuario efectiva `false` y devuelve solo la configuración de usuario (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="dc37e-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="dc37e-123">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="dc37e-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="dc37e-124">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="dc37e-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="dc37e-125">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc37e-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="dc37e-126">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="dc37e-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="dc37e-127">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="dc37e-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="dc37e-128">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="dc37e-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```

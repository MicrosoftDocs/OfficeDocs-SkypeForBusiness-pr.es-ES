---
title: Obtener usuarios
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumen: obtenga información sobre la operación Obtener usuarios, que forma parte del servicio de usuario. El servicio de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832430"
---
# <a name="get-users"></a><span data-ttu-id="97541-105">Obtener usuarios</span><span class="sxs-lookup"><span data-stu-id="97541-105">Get Users</span></span>
 
<span data-ttu-id="97541-106">**Resumen:** Obtenga información sobre la operación Obtener usuarios, que forma parte del servicio de usuario.</span><span class="sxs-lookup"><span data-stu-id="97541-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="97541-107">El servicio de usuario forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="97541-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="97541-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="97541-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="97541-109">La operación Obtener usuarios forma parte del servicio de usuario en la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="97541-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="97541-110">Obtener usuarios</span><span class="sxs-lookup"><span data-stu-id="97541-110">Get Users</span></span>

<span data-ttu-id="97541-111">Obtener usuarios devuelve una lista de usuarios en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="97541-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="97541-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="97541-112">**Method**</span></span>|<span data-ttu-id="97541-113">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="97541-113">**Request URI**</span></span>|<span data-ttu-id="97541-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="97541-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="97541-115">GET</span><span class="sxs-lookup"><span data-stu-id="97541-115">GET</span></span>  <br/> |<span data-ttu-id="97541-116">https:// \<portal\> /QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="97541-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="97541-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="97541-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="97541-118">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="97541-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="97541-119">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="97541-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="97541-120">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="97541-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="97541-121">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="97541-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="97541-122">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="97541-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="97541-123">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="97541-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="97541-124">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="97541-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97541-125">Se devuelve una matriz de objetos User.</span><span class="sxs-lookup"><span data-stu-id="97541-125">An array of User objects is returned.</span></span> <span data-ttu-id="97541-126">Para obtener más información sobre el objeto User, vea Obtener usuario.</span><span class="sxs-lookup"><span data-stu-id="97541-126">For details about the User object, see Get User.</span></span> 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```



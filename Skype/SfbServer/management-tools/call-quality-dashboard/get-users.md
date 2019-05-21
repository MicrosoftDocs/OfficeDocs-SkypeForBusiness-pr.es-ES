---
title: Obtener usuarios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumen: Obtenga información sobre la operación obtener usuarios, que forma parte del servicio de usuario. El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 22223c37dad39f171afc27eb9e0520b8b32335c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274649"
---
# <a name="get-users"></a><span data-ttu-id="0b27b-105">Obtener usuarios</span><span class="sxs-lookup"><span data-stu-id="0b27b-105">Get Users</span></span>
 
<span data-ttu-id="0b27b-106">**Resumen:** Obtenga más información sobre la operación obtener usuarios, que es parte del servicio de usuario.</span><span class="sxs-lookup"><span data-stu-id="0b27b-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="0b27b-107">El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0b27b-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0b27b-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0b27b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0b27b-109">La operación obtener usuarios forma parte del servicio de usuario en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0b27b-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="0b27b-110">Obtener usuarios</span><span class="sxs-lookup"><span data-stu-id="0b27b-110">Get Users</span></span>

<span data-ttu-id="0b27b-111">Obtener usuarios devuelve una lista de usuarios del repositorio.</span><span class="sxs-lookup"><span data-stu-id="0b27b-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="0b27b-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="0b27b-112">**Method**</span></span>|<span data-ttu-id="0b27b-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="0b27b-113">**Request URI**</span></span>|<span data-ttu-id="0b27b-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="0b27b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0b27b-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="0b27b-115">GET</span></span>  <br/> |<span data-ttu-id="0b27b-116">https://\<portal\>/QoERepositoryService/Repository/User</span><span class="sxs-lookup"><span data-stu-id="0b27b-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="0b27b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0b27b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0b27b-118">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="0b27b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0b27b-119">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="0b27b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0b27b-120">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="0b27b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0b27b-121">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0b27b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0b27b-122">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="0b27b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0b27b-123">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="0b27b-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0b27b-124">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="0b27b-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b27b-125">Se devuelve una matriz de objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="0b27b-125">An array of User objects is returned.</span></span> <span data-ttu-id="0b27b-126">Para obtener más información sobre el objeto de usuario, vea obtener usuario.</span><span class="sxs-lookup"><span data-stu-id="0b27b-126">For details about the User object, see Get User.</span></span> 
  
```
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



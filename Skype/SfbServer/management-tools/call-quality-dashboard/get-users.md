---
title: Conseguir que los usuarios
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumen: Conozca la operación obtener usuarios, que forma parte del servicio de usuario de. El servicio de usuario forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: ed26614c0fd4b443e9c5d698d1db9467291ca3d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-users"></a><span data-ttu-id="39f98-105">Conseguir que los usuarios</span><span class="sxs-lookup"><span data-stu-id="39f98-105">Get Users</span></span>
 
<span data-ttu-id="39f98-106">**Resumen:** Obtener información sobre la operación de obtener usuarios, que forma parte del servicio de usuario de.</span><span class="sxs-lookup"><span data-stu-id="39f98-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="39f98-107">El servicio de usuario forma parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="39f98-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="39f98-108">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="39f98-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="39f98-109">La operación de obtener usuarios forma parte del servicio de usuario de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="39f98-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="39f98-110">Conseguir que los usuarios</span><span class="sxs-lookup"><span data-stu-id="39f98-110">Get Users</span></span>

<span data-ttu-id="39f98-111">Obtener una rentabilidad de los usuarios una lista de usuarios en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="39f98-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="39f98-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="39f98-112">**Method**</span></span>|<span data-ttu-id="39f98-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="39f98-113">**Request URI**</span></span>|<span data-ttu-id="39f98-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="39f98-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39f98-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="39f98-115">GET</span></span>  <br/> |<span data-ttu-id="39f98-116">https://\<portal\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="39f98-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="39f98-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="39f98-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="39f98-118">**URI parámetros** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="39f98-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="39f98-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="39f98-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="39f98-120">**Cuerpo de la solicitud** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="39f98-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="39f98-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="39f98-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="39f98-122">**Código de estado** - una operación correcta devuelve el código de estado 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="39f98-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="39f98-123">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="39f98-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="39f98-124">**Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="39f98-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39f98-125">Se devuelve una matriz de objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="39f98-125">An array of User objects is returned.</span></span> <span data-ttu-id="39f98-126">Para obtener más información acerca del objeto de usuario, consulte obtener el usuario.</span><span class="sxs-lookup"><span data-stu-id="39f98-126">For details about the User object, see Get User.</span></span> 
  
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



---
title: Obtener usuario
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumen: obtenga información sobre la operación Obtener usuario, que forma parte del servicio de usuario. El servicio de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832420"
---
# <a name="get-user"></a><span data-ttu-id="fda3c-105">Obtener usuario</span><span class="sxs-lookup"><span data-stu-id="fda3c-105">Get User</span></span>
 
<span data-ttu-id="fda3c-106">**Resumen:** Obtenga información sobre la operación Obtener usuario, que forma parte del servicio de usuario.</span><span class="sxs-lookup"><span data-stu-id="fda3c-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="fda3c-107">El servicio de usuario forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fda3c-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="fda3c-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fda3c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="fda3c-109">La operación Obtener usuarios forma parte del servicio de usuario en la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fda3c-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="fda3c-110">Obtener usuario</span><span class="sxs-lookup"><span data-stu-id="fda3c-110">Get User</span></span>

<span data-ttu-id="fda3c-111">Get User devuelve un registro de usuario del repositorio.</span><span class="sxs-lookup"><span data-stu-id="fda3c-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="fda3c-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="fda3c-112">**Method**</span></span>|<span data-ttu-id="fda3c-113">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="fda3c-113">**Request URI**</span></span>|<span data-ttu-id="fda3c-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="fda3c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fda3c-115">GET</span><span class="sxs-lookup"><span data-stu-id="fda3c-115">GET</span></span>  <br/> |<span data-ttu-id="fda3c-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="fda3c-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="fda3c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="fda3c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="fda3c-118">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="fda3c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="fda3c-119">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="fda3c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="fda3c-120">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="fda3c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="fda3c-121">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="fda3c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="fda3c-122">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="fda3c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="fda3c-123">Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (No encontrado).</span><span class="sxs-lookup"><span data-stu-id="fda3c-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="fda3c-124">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="fda3c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="fda3c-125">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="fda3c-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="fda3c-126">*userId:*  id. del usuario.</span><span class="sxs-lookup"><span data-stu-id="fda3c-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="fda3c-127">*loginName:*  identificación de usuario externo para usuarios normales.</span><span class="sxs-lookup"><span data-stu-id="fda3c-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="fda3c-128">Si se usa la autenticación de Windows para autenticar usuarios, puede ser un FQDN del usuario.</span><span class="sxs-lookup"><span data-stu-id="fda3c-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="fda3c-129">*defaultItemId:*  identificador del elemento predeterminado para este usuario.</span><span class="sxs-lookup"><span data-stu-id="fda3c-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="fda3c-130">El elemento predeterminado es el elemento de nivel superior asociado al usuario.</span><span class="sxs-lookup"><span data-stu-id="fda3c-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="fda3c-131">Todos los demás elementos que posee este usuario se pueden navegar desde el elemento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fda3c-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fda3c-132">Proporcione el  `defaultItemId` valor de la operación Obtener elemento para recuperar los detalles del elemento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fda3c-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  


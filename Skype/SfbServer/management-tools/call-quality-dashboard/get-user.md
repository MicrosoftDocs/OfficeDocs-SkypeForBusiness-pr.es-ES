---
title: Obtener el usuario
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumen: Obtenga información acerca de la operación obtener usuario, que es parte del servicio de usuario. El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 3508336eda934cf317f857d7ad7e903cb7298e00
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035592"
---
# <a name="get-user"></a><span data-ttu-id="f6da9-105">Obtener el usuario</span><span class="sxs-lookup"><span data-stu-id="f6da9-105">Get User</span></span>
 
<span data-ttu-id="f6da9-106">**Resumen:** Obtenga información acerca de la operación obtener usuario, que es parte del servicio de usuario.</span><span class="sxs-lookup"><span data-stu-id="f6da9-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="f6da9-107">El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="f6da9-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="f6da9-108">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6da9-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f6da9-109">La operación de obtener los usuarios es parte del servicio de usuario de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="f6da9-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="f6da9-110">Obtener el usuario</span><span class="sxs-lookup"><span data-stu-id="f6da9-110">Get User</span></span>

<span data-ttu-id="f6da9-111">Obtener devuelve de usuario en un registro de usuario desde el repositorio.</span><span class="sxs-lookup"><span data-stu-id="f6da9-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="f6da9-112">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="f6da9-112">**Method**</span></span>|<span data-ttu-id="f6da9-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="f6da9-113">**Request URI**</span></span>|<span data-ttu-id="f6da9-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="f6da9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6da9-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="f6da9-115">GET</span></span>  <br/> |<span data-ttu-id="f6da9-116">https://\<portal\>/QoERepositoryService/repository/usuario / {userId}</span><span class="sxs-lookup"><span data-stu-id="f6da9-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="f6da9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="f6da9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f6da9-118">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="f6da9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f6da9-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="f6da9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f6da9-120">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="f6da9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f6da9-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f6da9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f6da9-122">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="f6da9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="f6da9-123">Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).</span><span class="sxs-lookup"><span data-stu-id="f6da9-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="f6da9-124">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="f6da9-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f6da9-125">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="f6da9-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="f6da9-126">*userId* : identificador del usuario.</span><span class="sxs-lookup"><span data-stu-id="f6da9-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="f6da9-127">*loginName* - identificación de usuarios externos para los usuarios normales.</span><span class="sxs-lookup"><span data-stu-id="f6da9-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="f6da9-128">Si se usa la autenticación de Windows para autenticar a los usuarios, esto puede resultar un FQDN del usuario.</span><span class="sxs-lookup"><span data-stu-id="f6da9-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="f6da9-129">*defaultItemId* - ID del elemento predeterminado para este usuario.</span><span class="sxs-lookup"><span data-stu-id="f6da9-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="f6da9-130">El valor predeterminado de elemento es el elemento de nivel superior que está asociado al usuario.</span><span class="sxs-lookup"><span data-stu-id="f6da9-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="f6da9-131">Todos los demás elementos que posee este usuario se pueden navegar desde el elemento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f6da9-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6da9-132">Proporcionar la `defaultItemId` valor de la operación de obtener elemento para recuperar los detalles del elemento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f6da9-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  


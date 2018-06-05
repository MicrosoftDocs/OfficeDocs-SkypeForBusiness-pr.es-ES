---
title: Restauración CcCredentials
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: El cmdlet Restore Cc-credenciales restaura todas las credenciales de la actual Skype para la implementación de Business Edition de conector en la nube.
ms.openlocfilehash: bb74444c5f63b792abf6c12c317c1a824298426c
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569736"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="06e7b-103">Restauración CcCredentials</span><span class="sxs-lookup"><span data-stu-id="06e7b-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="06e7b-104">El cmdlet Restore Cc-credenciales restaura todas las credenciales de la actual Skype para la implementación de Business Edition de conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="06e7b-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="06e7b-105">Este cmdlet se aplica a Skype para conector Edition 2.1 de negocio en la nube.</span><span class="sxs-lookup"><span data-stu-id="06e7b-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="06e7b-106">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="06e7b-106">Detailed Description</span></span>

<span data-ttu-id="06e7b-107">El cmdlet Restore-CcCredentials limpia todas las credenciales y le pregunta si desea volver a escribir todas las credenciales usadas para el actual Skype para la implementación de nube de Business Connector.</span><span class="sxs-lookup"><span data-stu-id="06e7b-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="06e7b-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06e7b-108">Parameters</span></span>

<span data-ttu-id="06e7b-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="06e7b-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="06e7b-110">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="06e7b-110">Input Types</span></span>

<span data-ttu-id="06e7b-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="06e7b-111">None.</span></span> <span data-ttu-id="06e7b-112">El cmdlet Restore-CcCredentials no acepta entradas transferidas.</span><span class="sxs-lookup"><span data-stu-id="06e7b-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="06e7b-113">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="06e7b-113">Return Types</span></span>

<span data-ttu-id="06e7b-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="06e7b-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="06e7b-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06e7b-115">Example</span></span>

<span data-ttu-id="06e7b-116">En el ejemplo siguiente se restaura todas las credenciales de la implementación actual de conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="06e7b-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="06e7b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="06e7b-117">See also</span></span>

[<span data-ttu-id="06e7b-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="06e7b-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="06e7b-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="06e7b-119">Set-CcCredential</span></span>](set-cccredential.md)
  


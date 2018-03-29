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
description: El cmdlet Restore Cc-credenciales restaura todas las credenciales de la actual Skype para la implementación del conector de nube Business Edition.
ms.openlocfilehash: 045d7f651408b1cbdbd508966da3272ac61d7c04
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="restore-cccredentials"></a><span data-ttu-id="cc790-103">Restauración CcCredentials</span><span class="sxs-lookup"><span data-stu-id="cc790-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="cc790-104">El cmdlet Restore Cc-credenciales restaura todas las credenciales de la actual Skype para la implementación del conector de nube Business Edition.</span><span class="sxs-lookup"><span data-stu-id="cc790-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="cc790-105">Este cmdlet se aplica a Skype para negocios nube conector Edition 2.1.</span><span class="sxs-lookup"><span data-stu-id="cc790-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```

Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="cc790-106">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="cc790-106">Detailed Description</span></span>

<span data-ttu-id="cc790-107">El cmdlet Restore-CcCredentials limpia todas las credenciales y se le pregunta si desea volver a escribir todas las credenciales usadas para el actual Skype para implementación de nube de Business Connector.</span><span class="sxs-lookup"><span data-stu-id="cc790-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="cc790-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc790-108">Parameters</span></span>

<span data-ttu-id="cc790-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cc790-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="cc790-110">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="cc790-110">Input Types</span></span>

<span data-ttu-id="cc790-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cc790-111">None.</span></span> <span data-ttu-id="cc790-112">El cmdlet Restore-CcCredentials no acepta entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="cc790-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cc790-113">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="cc790-113">Return Types</span></span>

<span data-ttu-id="cc790-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cc790-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="cc790-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc790-115">Example</span></span>

<span data-ttu-id="cc790-116">En el ejemplo siguiente se restaura todas las credenciales de la implementación de nube conector actual:</span><span class="sxs-lookup"><span data-stu-id="cc790-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="cc790-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc790-117">See also</span></span>

[<span data-ttu-id="cc790-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="cc790-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="cc790-119">Conjunto de CcCredential</span><span class="sxs-lookup"><span data-stu-id="cc790-119">Set-CcCredential</span></span>](set-cccredential.md)
  


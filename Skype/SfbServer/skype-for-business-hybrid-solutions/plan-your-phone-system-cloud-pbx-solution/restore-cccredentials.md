---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: El cmdlet restore CC-Credentials restaura todas las credenciales de la implementación actual de Skype empresarial Cloud Connector Edition.
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003250"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="b26c2-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="b26c2-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="b26c2-104">El cmdlet restore CC-Credentials restaura todas las credenciales de la implementación actual de Skype empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="b26c2-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="b26c2-105">Este cmdlet se aplica a Skype empresarial Cloud Connector Edition 2,1.</span><span class="sxs-lookup"><span data-stu-id="b26c2-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="b26c2-106">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="b26c2-106">Detailed Description</span></span>

<span data-ttu-id="b26c2-107">El cmdlet restore-CcCredentials limpia todas las credenciales y le pide que vuelva a escribir todas las credenciales utilizadas para la implementación actual de Skype empresarial Connector.</span><span class="sxs-lookup"><span data-stu-id="b26c2-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b26c2-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b26c2-108">Parameters</span></span>

<span data-ttu-id="b26c2-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b26c2-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b26c2-110">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="b26c2-110">Input Types</span></span>

<span data-ttu-id="b26c2-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b26c2-111">None.</span></span> <span data-ttu-id="b26c2-112">El cmdlet restore-CcCredentials no acepta la entrada canalizada.</span><span class="sxs-lookup"><span data-stu-id="b26c2-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b26c2-113">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="b26c2-113">Return Types</span></span>

<span data-ttu-id="b26c2-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b26c2-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="b26c2-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b26c2-115">Example</span></span>

<span data-ttu-id="b26c2-116">En el siguiente ejemplo se restauran todas las credenciales de la implementación del conector de nube actual:</span><span class="sxs-lookup"><span data-stu-id="b26c2-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="b26c2-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b26c2-117">See also</span></span>

[<span data-ttu-id="b26c2-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="b26c2-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="b26c2-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="b26c2-119">Set-CcCredential</span></span>](set-cccredential.md)
  


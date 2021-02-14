---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad del servicio de entidad de certificación en la carpeta ca en el directorio de recursos compartidos del sitio para Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824296"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="f1e24-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="f1e24-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="f1e24-104">El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad del servicio de entidad de certificación " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" en la carpeta ca en el directorio de recursos compartidos del sitio para Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="f1e24-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="f1e24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1e24-105">Parameters</span></span>

<span data-ttu-id="f1e24-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="f1e24-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f1e24-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f1e24-107">Examples</span></span>
<span data-ttu-id="f1e24-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f1e24-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f1e24-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f1e24-109">Example 1</span></span>

<span data-ttu-id="f1e24-110">En el siguiente ejemplo se quita el archivo de copia de seguridad del servicio de entidad de certificación " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" en la carpeta ca en el directorio de recurso compartido de sitios:</span><span class="sxs-lookup"><span data-stu-id="f1e24-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="f1e24-111">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f1e24-111">Input Types</span></span>
<span data-ttu-id="f1e24-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f1e24-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="f1e24-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f1e24-113">None.</span></span> <span data-ttu-id="f1e24-114">El Remove-CcCertificationAuthorityFile no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="f1e24-114">The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f1e24-115">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="f1e24-115">Return Types</span></span>
<span data-ttu-id="f1e24-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f1e24-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f1e24-117">Ninguno</span><span class="sxs-lookup"><span data-stu-id="f1e24-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f1e24-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1e24-118">See also</span></span>
<span data-ttu-id="f1e24-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f1e24-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="f1e24-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="f1e24-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  


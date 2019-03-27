---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad del servicio de entidad de certificación en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido del sitio de Skype para Business Edition de conector en la nube.
ms.openlocfilehash: 52f3dc8642b9f3177b215b9cd102bbd50cd22fea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899627"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="17acb-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="17acb-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="17acb-104">El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad del servicio de autoridad de certificación "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido del sitio de Skype para la nube de Business Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="17acb-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="17acb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17acb-105">Parameters</span></span>

<span data-ttu-id="17acb-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="17acb-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="17acb-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="17acb-107">Examples</span></span>
<span data-ttu-id="17acb-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="17acb-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="17acb-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="17acb-109">Example 1</span></span>

<span data-ttu-id="17acb-110">En el ejemplo siguiente se quita el archivo de copia de seguridad del servicio de autoridad de certificación "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" en la carpeta de la entidad emisora de certificados en el directorio de recurso compartido de sitio:</span><span class="sxs-lookup"><span data-stu-id="17acb-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="17acb-111">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="17acb-111">Input Types</span></span>
<span data-ttu-id="17acb-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17acb-112"></span></span>

<span data-ttu-id="17acb-p101">Ninguno. El cmdlet Remove-CcCertificationAuthorityFile no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="17acb-p101">None. The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="17acb-115">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="17acb-115">Return Types</span></span>
<span data-ttu-id="17acb-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17acb-116"></span></span>

<span data-ttu-id="17acb-117">Ninguno</span><span class="sxs-lookup"><span data-stu-id="17acb-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="17acb-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17acb-118">See also</span></span>
<span data-ttu-id="17acb-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17acb-119"></span></span>

[<span data-ttu-id="17acb-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="17acb-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  


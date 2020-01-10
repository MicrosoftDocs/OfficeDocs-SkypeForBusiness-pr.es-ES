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
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad servicio de entidad de certificación en la carpeta CA del directorio compartido del sitio de la edición Cloud Connector de Skype empresarial.
ms.openlocfilehash: d7036633eaf092130fc6e4acaebda39d04ff17df
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003300"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="41eaa-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="41eaa-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="41eaa-104">El cmdlet Remove-CcCertificationAuthorityFile quita el archivo de copia de seguridad servicio&lt;de&gt;entidad emisora de certificados "SiteRootDirectory \CA\SfB CCE root. p12" en la carpeta CA, en el directorio compartido del sitio de la edición Cloud Connector de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="41eaa-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="41eaa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41eaa-105">Parameters</span></span>

<span data-ttu-id="41eaa-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="41eaa-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="41eaa-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="41eaa-107">Examples</span></span>
<span data-ttu-id="41eaa-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="41eaa-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="41eaa-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="41eaa-109">Example 1</span></span>

<span data-ttu-id="41eaa-110">En el ejemplo siguiente se quita el archivo de copia de&lt;seguridad&gt;servicio de entidad emisora de certificados "SiteRootDirectory \CA\SfB CCE root. p12" en la carpeta CA en el directorio compartido del sitio:</span><span class="sxs-lookup"><span data-stu-id="41eaa-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="41eaa-111">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="41eaa-111">Input Types</span></span>
<span data-ttu-id="41eaa-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="41eaa-112"></span></span>

<span data-ttu-id="41eaa-p101">Ninguno. El cmdlet Remove-CcCertificationAuthorityFile no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="41eaa-p101">None. The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="41eaa-115">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="41eaa-115">Return Types</span></span>
<span data-ttu-id="41eaa-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="41eaa-116"></span></span>

<span data-ttu-id="41eaa-117">Ninguno</span><span class="sxs-lookup"><span data-stu-id="41eaa-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41eaa-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41eaa-118">See also</span></span>
<span data-ttu-id="41eaa-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="41eaa-119"></span></span>

[<span data-ttu-id="41eaa-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="41eaa-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  


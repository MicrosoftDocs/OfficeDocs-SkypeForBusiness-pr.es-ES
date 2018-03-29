---
title: Copia de seguridad CcCertificationAuthority
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: El cmdlet Backup-CcCertificationAuthority crea una copia de seguridad del servicio de la entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.
ms.openlocfilehash: b3cb566dc72b3966eaa1480f3e17e4d6b46c06a2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="3432a-103">Copia de seguridad CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="3432a-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="3432a-104">El cmdlet Backup-CcCertificationAuthority crea una copia de seguridad del servicio de la entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.</span><span class="sxs-lookup"><span data-stu-id="3432a-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="3432a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3432a-105">Parameters</span></span>

<span data-ttu-id="3432a-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="3432a-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3432a-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3432a-107">Examples</span></span>
<span data-ttu-id="3432a-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3432a-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="3432a-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="3432a-109">Example 1</span></span>

<span data-ttu-id="3432a-110">En el siguiente ejemplo se crea una copia de seguridad del servicio de la entidad de certificación en un archivo y se guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio:</span><span class="sxs-lookup"><span data-stu-id="3432a-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="3432a-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="3432a-111">Detailed Description</span></span>
<span data-ttu-id="3432a-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3432a-112"></span></span>

<span data-ttu-id="3432a-113">Copia de seguridad de entidad emisora de certificados puede resultar útil si piensa volver a implementar un dispositivo conector de nube con el mismo certificado en caso de desastre, o si desea mover el dispositivo al nuevo hardware.</span><span class="sxs-lookup"><span data-stu-id="3432a-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="3432a-114">El comando guarda la copia del servicio entidad emisora de certificación de nube de conector desde el servidor de anuncios a "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span><span class="sxs-lookup"><span data-stu-id="3432a-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="3432a-115">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="3432a-115">Input Types</span></span>
<span data-ttu-id="3432a-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3432a-116"></span></span>

<span data-ttu-id="3432a-p102">Ninguno. El cmdlet Backup-CcCertificationAuthority no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="3432a-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3432a-119">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="3432a-119">Return Types</span></span>
<span data-ttu-id="3432a-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3432a-120"></span></span>

<span data-ttu-id="3432a-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="3432a-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3432a-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3432a-122">See also</span></span>
<span data-ttu-id="3432a-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3432a-123"></span></span>

[<span data-ttu-id="3432a-124">Quitar CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="3432a-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  


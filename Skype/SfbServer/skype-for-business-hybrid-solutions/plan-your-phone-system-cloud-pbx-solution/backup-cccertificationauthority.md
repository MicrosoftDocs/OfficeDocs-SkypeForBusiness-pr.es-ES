---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: El cmdlet Backup-CcCertificationAuthority crea una copia de seguridad del servicio de la entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003030"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="35a22-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="35a22-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="35a22-104">El cmdlet Backup-CcCertificationAuthority crea una copia de seguridad del servicio de la entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.</span><span class="sxs-lookup"><span data-stu-id="35a22-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="35a22-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35a22-105">Parameters</span></span>

<span data-ttu-id="35a22-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="35a22-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="35a22-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="35a22-107">Examples</span></span>
<span data-ttu-id="35a22-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="35a22-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="35a22-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="35a22-109">Example 1</span></span>

<span data-ttu-id="35a22-110">En el siguiente ejemplo se crea una copia de seguridad del servicio de la entidad de certificación en un archivo y se guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio:</span><span class="sxs-lookup"><span data-stu-id="35a22-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="35a22-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="35a22-111">Detailed Description</span></span>
<span data-ttu-id="35a22-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="35a22-112"></span></span>

<span data-ttu-id="35a22-113">La copia de seguridad de la entidad emisora de certificados puede ser útil si tiene previsto volver a implementar un dispositivo de conector de nube con el mismo certificado en caso de que se produzca un desastre o si desea mover el dispositivo a nuevo hardware.</span><span class="sxs-lookup"><span data-stu-id="35a22-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="35a22-114">El comando guarda la copia del servicio de autoridad de certificación del conector de nube desde el servidor\<de\>ad en "SiteRootDirectory \CA\SfB CCE root. p12".</span><span class="sxs-lookup"><span data-stu-id="35a22-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="35a22-115">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="35a22-115">Input Types</span></span>
<span data-ttu-id="35a22-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="35a22-116"></span></span>

<span data-ttu-id="35a22-p102">Ninguno. El cmdlet Backup-CcCertificationAuthority no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="35a22-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="35a22-119">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="35a22-119">Return Types</span></span>
<span data-ttu-id="35a22-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="35a22-120"></span></span>

<span data-ttu-id="35a22-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="35a22-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35a22-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35a22-122">See also</span></span>
<span data-ttu-id="35a22-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="35a22-123"></span></span>

[<span data-ttu-id="35a22-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="35a22-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  


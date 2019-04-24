---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
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
ms.openlocfilehash: 2f85a4da58a586852b3331f1f8e482ee17e29e02
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234554"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="2bba7-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="2bba7-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="2bba7-104">El cmdlet Backup-CcCertificationAuthority crea una copia de seguridad del servicio de la entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio.</span><span class="sxs-lookup"><span data-stu-id="2bba7-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="2bba7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bba7-105">Parameters</span></span>

<span data-ttu-id="2bba7-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="2bba7-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2bba7-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2bba7-107">Examples</span></span>
<span data-ttu-id="2bba7-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2bba7-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="2bba7-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="2bba7-109">Example 1</span></span>

<span data-ttu-id="2bba7-110">En el siguiente ejemplo se crea una copia de seguridad del servicio de la entidad de certificación en un archivo y se guarda en la carpeta de la entidad de certificación en el directorio de recursos compartidos del sitio:</span><span class="sxs-lookup"><span data-stu-id="2bba7-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="2bba7-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="2bba7-111">Detailed Description</span></span>
<span data-ttu-id="2bba7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2bba7-112"></span></span>

<span data-ttu-id="2bba7-113">Copia de seguridad de entidad de certificación puede ser útil si tiene previsto volver a implementar un dispositivo de conector en la nube con el mismo certificado en el caso de un desastre, o si desea mover el dispositivo a un nuevo hardware.</span><span class="sxs-lookup"><span data-stu-id="2bba7-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="2bba7-114">El comando guarda la copia del servicio de autoridad de certificación de conector en la nube desde el servidor de AD para "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span><span class="sxs-lookup"><span data-stu-id="2bba7-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2bba7-115">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2bba7-115">Input Types</span></span>
<span data-ttu-id="2bba7-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2bba7-116"></span></span>

<span data-ttu-id="2bba7-p102">Ninguno. El cmdlet Backup-CcCertificationAuthority no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="2bba7-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2bba7-119">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="2bba7-119">Return Types</span></span>
<span data-ttu-id="2bba7-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2bba7-120"></span></span>

<span data-ttu-id="2bba7-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="2bba7-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2bba7-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2bba7-122">See also</span></span>
<span data-ttu-id="2bba7-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2bba7-123"></span></span>

[<span data-ttu-id="2bba7-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="2bba7-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  


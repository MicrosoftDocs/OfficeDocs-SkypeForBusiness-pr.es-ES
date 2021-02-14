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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: El cmdlet Backup-CcCertificationAuthority copia de seguridad del servicio de entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta ca en el directorio del recurso compartido de sitios.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803810"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="faf20-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="faf20-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="faf20-104">El cmdlet Backup-CcCertificationAuthority copia de seguridad del servicio de entidad de certificación de Skype Empresarial Cloud Connector Edition en un archivo y lo guarda en la carpeta ca en el directorio del recurso compartido de sitios.</span><span class="sxs-lookup"><span data-stu-id="faf20-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="faf20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="faf20-105">Parameters</span></span>

<span data-ttu-id="faf20-106">Ninguno</span><span class="sxs-lookup"><span data-stu-id="faf20-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="faf20-107">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="faf20-107">Examples</span></span>
<span data-ttu-id="faf20-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="faf20-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="faf20-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="faf20-109">Example 1</span></span>

<span data-ttu-id="faf20-110">En el siguiente ejemplo se hace una copia de seguridad del servicio de entidad de certificación en un archivo y se guarda en la carpeta ca del directorio de recurso compartido de sitios:</span><span class="sxs-lookup"><span data-stu-id="faf20-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="faf20-111">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="faf20-111">Detailed Description</span></span>
<span data-ttu-id="faf20-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="faf20-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="faf20-113">La copia de seguridad de la entidad de certificación puede ser útil si tiene previsto volver a implementar un dispositivo de Cloud Connector con el mismo certificado en caso de desastre o si desea mover el dispositivo a un nuevo hardware.</span><span class="sxs-lookup"><span data-stu-id="faf20-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="faf20-114">El comando guarda la copia del servicio de entidad de certificación de Cloud Connector del servidor de AD en \< "SiteRootDirectory \> \CA\SfB CCE Root.p12".</span><span class="sxs-lookup"><span data-stu-id="faf20-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="faf20-115">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="faf20-115">Input Types</span></span>
<span data-ttu-id="faf20-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="faf20-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="faf20-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="faf20-117">None.</span></span> <span data-ttu-id="faf20-118">El Backup-CcCertificationAuthority no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="faf20-118">The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="faf20-119">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="faf20-119">Return Types</span></span>
<span data-ttu-id="faf20-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="faf20-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="faf20-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="faf20-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="faf20-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="faf20-122">See also</span></span>
<span data-ttu-id="faf20-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="faf20-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="faf20-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="faf20-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  


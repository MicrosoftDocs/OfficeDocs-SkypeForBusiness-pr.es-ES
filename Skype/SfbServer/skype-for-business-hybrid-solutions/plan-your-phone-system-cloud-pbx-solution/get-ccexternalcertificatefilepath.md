---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: El cmdlet Get-CcExternalCertificateFilePath devuelve la ruta de acceso del archivo de certificados externos de la implementación de Skype Empresarial Cloud Connector Edition. El usuario debe preparar este certificado.
ms.openlocfilehash: 997b5d7a39decf11a19c307f4e7a7b439069441f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882589"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="0ef18-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0ef18-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="0ef18-p102">El cmdlet Get-CcExternalCertificateFilePath devuelve la ruta de acceso del archivo de certificados externos de la implementación de Skype Empresarial Cloud Connector Edition. El usuario debe preparar este certificado.</span><span class="sxs-lookup"><span data-stu-id="0ef18-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="0ef18-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="0ef18-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="0ef18-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0ef18-108">Examples</span></span>
<span data-ttu-id="0ef18-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0ef18-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="0ef18-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="0ef18-110">Example 1</span></span>

<span data-ttu-id="0ef18-111">En el siguiente ejemplo se muestra la ruta de acceso del certificado del servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="0ef18-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="0ef18-112">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="0ef18-112">Example 2</span></span>

<span data-ttu-id="0ef18-113">En el siguiente ejemplo se muestra el certificado establecido para el servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="0ef18-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="0ef18-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="0ef18-114">Detailed Description</span></span>
<span data-ttu-id="0ef18-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0ef18-115"></span></span>

<span data-ttu-id="0ef18-p103">Durante la implementación o al modificar la topología, deberá especificar la ruta del certificado del servidor perimetral y, opcionalmente, la del servidor de mediación. El certificado del servidor de mediación se requiere si TLS se usa entre las puertas de enlace y el servidor de mediación. Para cambiar la ruta de acceso, use el cmdlet Set-CcExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="0ef18-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0ef18-119">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ef18-119">Parameters</span></span>
<span data-ttu-id="0ef18-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0ef18-120"></span></span>

|<span data-ttu-id="0ef18-121">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="0ef18-121">**Parameter**</span></span>|<span data-ttu-id="0ef18-122">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="0ef18-122">**Required**</span></span>|<span data-ttu-id="0ef18-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0ef18-123">**Type**</span></span>|<span data-ttu-id="0ef18-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0ef18-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0ef18-125">Destino </span><span class="sxs-lookup"><span data-stu-id="0ef18-125">Target</span></span>  <br/> |<span data-ttu-id="0ef18-126">Opcional</span><span class="sxs-lookup"><span data-stu-id="0ef18-126">Optional</span></span>  <br/> | <span data-ttu-id="0ef18-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0ef18-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="0ef18-p104">El tipo de ruta de archivo que se ha solicitado. Los tipos incluyen:</span><span class="sxs-lookup"><span data-stu-id="0ef18-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="0ef18-130">EdgeServer (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="0ef18-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="0ef18-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="0ef18-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0ef18-132">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="0ef18-132">Input Types</span></span>
<span data-ttu-id="0ef18-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0ef18-133"></span></span>

<span data-ttu-id="0ef18-134">El cmdlet Get-CcExternalCertificateFilePath no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="0ef18-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0ef18-135">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="0ef18-135">Return Types</span></span>
<span data-ttu-id="0ef18-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0ef18-136"></span></span>

<span data-ttu-id="0ef18-137">El comando devuelve una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="0ef18-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0ef18-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ef18-138">See also</span></span>
<span data-ttu-id="0ef18-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0ef18-139"></span></span>

[<span data-ttu-id="0ef18-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0ef18-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  


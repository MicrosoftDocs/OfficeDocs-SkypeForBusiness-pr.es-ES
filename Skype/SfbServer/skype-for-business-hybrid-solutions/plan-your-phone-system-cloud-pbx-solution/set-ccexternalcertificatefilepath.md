---
title: Set-CcExternalCertificateFilePath
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
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: El Set-CcExternalCertificateFilePath especifica la ruta de acceso donde se almacena el certificado para el servidor de mediación o el servidor perimetral.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824204"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="0f74b-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0f74b-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="0f74b-104">El Set-CcExternalCertificateFilePath especifica la ruta de acceso donde se almacena el certificado para el servidor de mediación o el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0f74b-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="0f74b-105">Este certificado es necesario durante la implementación o al agregar nuevos dispositivos de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0f74b-105">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="0f74b-106">El comando también permite importar un nuevo certificado para el servidor de mediación después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="0f74b-106">The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="0f74b-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="0f74b-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="0f74b-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0f74b-108">Examples</span></span>
<span data-ttu-id="0f74b-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0f74b-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0f74b-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="0f74b-110">Example 1</span></span>

<span data-ttu-id="0f74b-111">En el siguiente ejemplo se establece la ruta de acceso del certificado para el servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="0f74b-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="0f74b-112">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="0f74b-112">Example 2</span></span>

<span data-ttu-id="0f74b-113">En el siguiente ejemplo se establece la ruta de acceso del certificado para el servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="0f74b-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="0f74b-114">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="0f74b-114">Example 3</span></span>

<span data-ttu-id="0f74b-115">En el siguiente ejemplo se actualiza el certificado para el servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="0f74b-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="0f74b-116">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="0f74b-116">Detailed Description</span></span>
<span data-ttu-id="0f74b-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0f74b-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="0f74b-118">Durante la implementación, o al modificar la topología, debe especificar la ruta de acceso para el certificado del servidor perimetral y, opcionalmente, para el certificado del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0f74b-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="0f74b-119">El certificado para el servidor de mediación es necesario si se usará TLS entre las puertas de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0f74b-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="0f74b-120">Cuando implementa un dispositivo de Cloud Connector y desea implementar TLS, solo puede especificar la ruta de acceso al certificado que se implementará en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0f74b-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="0f74b-121">Sin embargo, si desea actualizar el certificado de mediación en un dispositivo ya implementado, debe especificar la ruta de acceso y el parámetro -Import.</span><span class="sxs-lookup"><span data-stu-id="0f74b-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="0f74b-122">Para ver la ruta de acceso, use Get-CCExternalCertificateFilePath cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0f74b-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0f74b-123">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f74b-123">Parameters</span></span>
<span data-ttu-id="0f74b-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0f74b-124"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="0f74b-125">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="0f74b-125">**Parameter**</span></span>|<span data-ttu-id="0f74b-126">**Required**</span><span class="sxs-lookup"><span data-stu-id="0f74b-126">**Required**</span></span>|<span data-ttu-id="0f74b-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0f74b-127">**Type**</span></span>|<span data-ttu-id="0f74b-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0f74b-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0f74b-129">Target</span><span class="sxs-lookup"><span data-stu-id="0f74b-129">Target</span></span> <br/> | <span data-ttu-id="0f74b-130">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="0f74b-130">Required</span></span> <br/> |<span data-ttu-id="0f74b-131">System.String</span><span class="sxs-lookup"><span data-stu-id="0f74b-131">System.String</span></span>  <br/> |<span data-ttu-id="0f74b-132">Tipo de ruta de acceso de archivo solicitada.</span><span class="sxs-lookup"><span data-stu-id="0f74b-132">Type of file path requested.</span></span> <span data-ttu-id="0f74b-133">Entre los tipos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="0f74b-133">Types include:</span></span>  <br/> <span data-ttu-id="0f74b-134">EdgeServer (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="0f74b-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="0f74b-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="0f74b-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="0f74b-136">Importar</span><span class="sxs-lookup"><span data-stu-id="0f74b-136">Import</span></span>  <br/> |<span data-ttu-id="0f74b-137">Opcional</span><span class="sxs-lookup"><span data-stu-id="0f74b-137">Optional</span></span>  <br/> |<span data-ttu-id="0f74b-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0f74b-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0f74b-139">Indica que el certificado debe importarse al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0f74b-139">Indicates that the certificate must be imported to the Mediation Server.</span></span> <span data-ttu-id="0f74b-140">Este parámetro no es necesario si implementa un dispositivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="0f74b-140">This parameter is not needed if you deploy an appliance for first time.</span></span> <span data-ttu-id="0f74b-141">El parámetro es necesario si desea cambiar el certificado existente en una versión ya implementada.</span><span class="sxs-lookup"><span data-stu-id="0f74b-141">The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0f74b-142">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="0f74b-142">Input Types</span></span>
<span data-ttu-id="0f74b-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0f74b-143"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0f74b-144">El Set-CcExternalCertificateFilePath no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="0f74b-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0f74b-145">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="0f74b-145">Return Types</span></span>
<span data-ttu-id="0f74b-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0f74b-146"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0f74b-147">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0f74b-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0f74b-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f74b-148">See also</span></span>
<span data-ttu-id="0f74b-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0f74b-149"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="0f74b-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0f74b-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  


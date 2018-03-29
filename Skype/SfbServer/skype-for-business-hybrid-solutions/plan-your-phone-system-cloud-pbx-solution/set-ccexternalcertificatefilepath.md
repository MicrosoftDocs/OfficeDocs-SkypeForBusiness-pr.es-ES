---
title: Conjunto de CcExternalCertificateFilePath
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: El cmdlet Set-CcExternalCertificateFilePath especifica la ruta de acceso en la que se almacena el certificado del servidor de mediación o del servidor perimetral.
ms.openlocfilehash: 89216fb2b56130dd76b711a483c6279ac1073392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="57bb5-103">Conjunto de CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="57bb5-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="57bb5-104">El cmdlet Set-CcExternalCertificateFilePath especifica la ruta de acceso en la que se almacena el certificado del servidor de mediación o del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="57bb5-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="57bb5-p101">Este certificado es necesario durante la implementación o al agregar nuevos dispositivos de Skype Empresarial Cloud Connector Edition. El comando también permite la importación de un nuevo certificado para el servidor de mediación después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="57bb5-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="57bb5-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="57bb5-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="57bb5-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="57bb5-108">Examples</span></span>
<span data-ttu-id="57bb5-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="57bb5-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="57bb5-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="57bb5-110">Example 1</span></span>

<span data-ttu-id="57bb5-111">En el siguiente ejemplo se establece la ruta de acceso del certificado del servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="57bb5-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="57bb5-112">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="57bb5-112">Example 2</span></span>

<span data-ttu-id="57bb5-113">En el siguiente ejemplo se establece la ruta de acceso del certificado del servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="57bb5-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="57bb5-114">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="57bb5-114">Example 3</span></span>

<span data-ttu-id="57bb5-115">En el siguiente ejemplo se actualiza el certificado del servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="57bb5-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="57bb5-116">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="57bb5-116">Detailed Description</span></span>
<span data-ttu-id="57bb5-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="57bb5-117"></span></span>

<span data-ttu-id="57bb5-118">Durante la implementación, o al modificar la topología, deberá especificar la ruta del certificado del servidor perimetral y, opcionalmente, la del certificado del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="57bb5-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="57bb5-119">El certificado del servidor de mediación es necesario si se usa TLS entre las puertas de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="57bb5-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="57bb5-120">Al implementar un dispositivo conector de nube y desea implementar TLS, sólo puede especificar la ruta de acceso al certificado que se va a implementar en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="57bb5-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="57bb5-121">Sin embargo, si desea actualizar el certificado del servidor de mediación en un dispositivo que ya se ha implementado, deberá especificar la ruta y el parámetro -Import.</span><span class="sxs-lookup"><span data-stu-id="57bb5-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="57bb5-122">Para ver la ruta, use el cmdlet Get-CCExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="57bb5-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="57bb5-123">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57bb5-123">Parameters</span></span>
<span data-ttu-id="57bb5-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="57bb5-124"></span></span>

|<span data-ttu-id="57bb5-125">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="57bb5-125">**Parameter**</span></span>|<span data-ttu-id="57bb5-126">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="57bb5-126">**Required**</span></span>|<span data-ttu-id="57bb5-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="57bb5-127">**Type**</span></span>|<span data-ttu-id="57bb5-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="57bb5-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="57bb5-129">Target</span><span class="sxs-lookup"><span data-stu-id="57bb5-129">Target</span></span> <br/> | <span data-ttu-id="57bb5-130">Requerido</span><span class="sxs-lookup"><span data-stu-id="57bb5-130">Required</span></span> <br/> |<span data-ttu-id="57bb5-131">System.String</span><span class="sxs-lookup"><span data-stu-id="57bb5-131">System.String</span></span>  <br/> |<span data-ttu-id="57bb5-p103">El tipo de ruta de archivo que se ha solicitado. Los tipos incluyen:</span><span class="sxs-lookup"><span data-stu-id="57bb5-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="57bb5-134">EdgeServer (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="57bb5-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="57bb5-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="57bb5-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="57bb5-136">Import</span><span class="sxs-lookup"><span data-stu-id="57bb5-136">Import</span></span>  <br/> |<span data-ttu-id="57bb5-137">Opcional</span><span class="sxs-lookup"><span data-stu-id="57bb5-137">Optional</span></span>  <br/> |<span data-ttu-id="57bb5-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="57bb5-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="57bb5-p104">Indica que el certificado se debe importar al servidor de mediación. Este parámetro no se necesita si se implementa un dispositivo por primera vez. El parámetro es necesario si desea cambiar el certificado existente en una versión que ya se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="57bb5-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="57bb5-142">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="57bb5-142">Input Types</span></span>
<span data-ttu-id="57bb5-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="57bb5-143"></span></span>

<span data-ttu-id="57bb5-144">El cmdlet Set-CcExternalCertificateFilePath no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="57bb5-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="57bb5-145">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="57bb5-145">Return Types</span></span>
<span data-ttu-id="57bb5-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="57bb5-146"></span></span>

<span data-ttu-id="57bb5-147">Ninguno</span><span class="sxs-lookup"><span data-stu-id="57bb5-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="57bb5-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57bb5-148">See also</span></span>
<span data-ttu-id="57bb5-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="57bb5-149"></span></span>

[<span data-ttu-id="57bb5-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="57bb5-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  


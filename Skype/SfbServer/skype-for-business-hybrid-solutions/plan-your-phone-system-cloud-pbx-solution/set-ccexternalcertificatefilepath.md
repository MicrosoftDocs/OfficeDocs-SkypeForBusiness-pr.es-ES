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
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: El cmdlet Set-CcExternalCertificateFilePath especifica la ruta de acceso en la que se almacena el certificado del servidor de mediación o del servidor perimetral.
ms.openlocfilehash: bc22771c20277d9de99660551864d600f06b3acc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286988"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="70207-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="70207-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="70207-104">El cmdlet Set-CcExternalCertificateFilePath especifica la ruta de acceso en la que se almacena el certificado del servidor de mediación o del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="70207-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="70207-p101">Este certificado es necesario durante la implementación o al agregar nuevos dispositivos de Skype Empresarial Cloud Connector Edition. El comando también permite la importación de un nuevo certificado para el servidor de mediación después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="70207-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="70207-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="70207-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="70207-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="70207-108">Examples</span></span>
<span data-ttu-id="70207-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="70207-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="70207-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="70207-110">Example 1</span></span>

<span data-ttu-id="70207-111">En el siguiente ejemplo se establece la ruta de acceso del certificado del servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="70207-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="70207-112">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="70207-112">Example 2</span></span>

<span data-ttu-id="70207-113">En el siguiente ejemplo se establece la ruta de acceso del certificado del servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="70207-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="70207-114">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="70207-114">Example 3</span></span>

<span data-ttu-id="70207-115">En el siguiente ejemplo se actualiza el certificado del servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="70207-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="70207-116">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="70207-116">Detailed Description</span></span>
<span data-ttu-id="70207-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="70207-117"></span></span>

<span data-ttu-id="70207-118">Durante la implementación, o al modificar la topología, deberá especificar la ruta del certificado del servidor perimetral y, opcionalmente, la del certificado del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="70207-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="70207-119">El certificado del servidor de mediación es necesario si se usa TLS entre las puertas de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="70207-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="70207-120">Al implementar un dispositivo de conector de nube y desea implementar TLS, solo puede especificar la ruta de acceso al certificado que se implementará en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="70207-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="70207-121">Sin embargo, si desea actualizar el certificado del servidor de mediación en un dispositivo que ya se ha implementado, deberá especificar la ruta y el parámetro -Import.</span><span class="sxs-lookup"><span data-stu-id="70207-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="70207-122">Para ver la ruta, use el cmdlet Get-CCExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="70207-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="70207-123">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70207-123">Parameters</span></span>
<span data-ttu-id="70207-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="70207-124"></span></span>

|<span data-ttu-id="70207-125">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="70207-125">**Parameter**</span></span>|<span data-ttu-id="70207-126">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="70207-126">**Required**</span></span>|<span data-ttu-id="70207-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="70207-127">**Type**</span></span>|<span data-ttu-id="70207-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="70207-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="70207-129">Target</span><span class="sxs-lookup"><span data-stu-id="70207-129">Target</span></span> <br/> | <span data-ttu-id="70207-130">Requerido</span><span class="sxs-lookup"><span data-stu-id="70207-130">Required</span></span> <br/> |<span data-ttu-id="70207-131">System.String</span><span class="sxs-lookup"><span data-stu-id="70207-131">System.String</span></span>  <br/> |<span data-ttu-id="70207-p103">El tipo de ruta de archivo que se ha solicitado. Los tipos incluyen:</span><span class="sxs-lookup"><span data-stu-id="70207-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="70207-134">EdgeServer (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="70207-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="70207-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="70207-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="70207-136">Import</span><span class="sxs-lookup"><span data-stu-id="70207-136">Import</span></span>  <br/> |<span data-ttu-id="70207-137">Opcional</span><span class="sxs-lookup"><span data-stu-id="70207-137">Optional</span></span>  <br/> |<span data-ttu-id="70207-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="70207-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="70207-p104">Indica que el certificado se debe importar al servidor de mediación. Este parámetro no se necesita si se implementa un dispositivo por primera vez. El parámetro es necesario si desea cambiar el certificado existente en una versión que ya se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="70207-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="70207-142">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="70207-142">Input Types</span></span>
<span data-ttu-id="70207-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="70207-143"></span></span>

<span data-ttu-id="70207-144">El cmdlet Set-CcExternalCertificateFilePath no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="70207-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="70207-145">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="70207-145">Return Types</span></span>
<span data-ttu-id="70207-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="70207-146"></span></span>

<span data-ttu-id="70207-147">Ninguno</span><span class="sxs-lookup"><span data-stu-id="70207-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="70207-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70207-148">See also</span></span>
<span data-ttu-id="70207-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="70207-149"></span></span>

[<span data-ttu-id="70207-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="70207-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  


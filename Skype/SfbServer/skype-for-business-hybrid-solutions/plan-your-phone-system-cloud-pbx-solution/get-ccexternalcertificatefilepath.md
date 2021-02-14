---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: El cmdlet Get-CcExternalCertificateFilePath devuelve la ruta de acceso del archivo de certificado externo para la implementación de Skype Empresarial Cloud Connector Edition. El usuario prepara este certificado.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799910"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="2fac2-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="2fac2-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="2fac2-105">El cmdlet Get-CcExternalCertificateFilePath devuelve la ruta de acceso del archivo de certificado externo para la implementación de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="2fac2-105">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="2fac2-106">El usuario prepara este certificado.</span><span class="sxs-lookup"><span data-stu-id="2fac2-106">The user prepares this certificate.</span></span>
  
<span data-ttu-id="2fac2-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2fac2-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="2fac2-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2fac2-108">Examples</span></span>
<span data-ttu-id="2fac2-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2fac2-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2fac2-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="2fac2-110">Example 1</span></span>

<span data-ttu-id="2fac2-111">En el siguiente ejemplo se muestra la ruta de acceso del certificado para el servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="2fac2-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="2fac2-112">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="2fac2-112">Example 2</span></span>

<span data-ttu-id="2fac2-113">En el siguiente ejemplo se muestra el conjunto de certificados para el servidor de mediación:</span><span class="sxs-lookup"><span data-stu-id="2fac2-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="2fac2-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="2fac2-114">Detailed Description</span></span>
<span data-ttu-id="2fac2-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2fac2-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2fac2-116">Durante la implementación o al modificar la topología, debe especificar la ruta de acceso para el certificado del servidor perimetral y, opcionalmente, para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="2fac2-116">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server.</span></span> <span data-ttu-id="2fac2-117">El certificado para el servidor de mediación es necesario si se usará TLS entre las puertas de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="2fac2-117">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="2fac2-118">Para cambiar la ruta de acceso, use Set-CcExternalCertificateFilePath cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2fac2-118">To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2fac2-119">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2fac2-119">Parameters</span></span>
<span data-ttu-id="2fac2-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2fac2-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="2fac2-121">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="2fac2-121">**Parameter**</span></span>|<span data-ttu-id="2fac2-122">**Required**</span><span class="sxs-lookup"><span data-stu-id="2fac2-122">**Required**</span></span>|<span data-ttu-id="2fac2-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2fac2-123">**Type**</span></span>|<span data-ttu-id="2fac2-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2fac2-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2fac2-125">Target</span><span class="sxs-lookup"><span data-stu-id="2fac2-125">Target</span></span>  <br/> |<span data-ttu-id="2fac2-126">Opcional</span><span class="sxs-lookup"><span data-stu-id="2fac2-126">Optional</span></span>  <br/> | <span data-ttu-id="2fac2-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2fac2-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="2fac2-128">Tipo de ruta de acceso de archivo solicitada.</span><span class="sxs-lookup"><span data-stu-id="2fac2-128">Type of file path requested.</span></span> <span data-ttu-id="2fac2-129">Entre los tipos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="2fac2-129">Types include:</span></span>  <br/> <span data-ttu-id="2fac2-130">EdgeServer (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="2fac2-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="2fac2-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="2fac2-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2fac2-132">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2fac2-132">Input Types</span></span>
<span data-ttu-id="2fac2-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2fac2-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2fac2-134">El Get-CcExternalCertificateFilePath no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="2fac2-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2fac2-135">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="2fac2-135">Return Types</span></span>
<span data-ttu-id="2fac2-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2fac2-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2fac2-137">El comando devuelve una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="2fac2-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2fac2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fac2-138">See also</span></span>
<span data-ttu-id="2fac2-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2fac2-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="2fac2-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="2fac2-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  


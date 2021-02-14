---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: El cmdlet Get-CcCredential devuelve la credencial de la implementación actual de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: c4e2d47ffc31eb7afef76c710fc93024ce2c593e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800400"
---
# <a name="get-cccredential"></a><span data-ttu-id="fb45c-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="fb45c-103">Get-CcCredential</span></span>
 
<span data-ttu-id="fb45c-104">El cmdlet Get-CcCredential devuelve la credencial de la implementación actual de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fb45c-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="fb45c-105">Con la versión 2.0 y versiones posteriores, también puede usar el parámetro -DisplayPassword para mostrar las contraseñas de TenantAdmin, DomainAdmin y VMAdmin.</span><span class="sxs-lookup"><span data-stu-id="fb45c-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="fb45c-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fb45c-106">Examples</span></span>
<span data-ttu-id="fb45c-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fb45c-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="fb45c-108">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="fb45c-108">Example 1</span></span>

<span data-ttu-id="fb45c-109">En el siguiente ejemplo se devuelve la credencial del administrador de dominio del dominio de la máquina virtual de Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="fb45c-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="fb45c-110">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="fb45c-110">Detailed Description</span></span>
<span data-ttu-id="fb45c-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fb45c-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="fb45c-112">El Get-CcCredential cmdlet devuelve la información de credenciales sobre el tipo de cuenta especificado.</span><span class="sxs-lookup"><span data-stu-id="fb45c-112">The Get-CcCredential cmdlet returns the credential information about the specified account type.</span></span> <span data-ttu-id="fb45c-113">Estas credenciales las especifica el administrador que ejecuta los cmdlets Register-CcAppliance y Install-CcAppliance al implementar el dispositivo actual.</span><span class="sxs-lookup"><span data-stu-id="fb45c-113">These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="fb45c-114">El Get-CcCredential cmdlet devuelve una instancia del objeto System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="fb45c-114">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span> <span data-ttu-id="fb45c-115">La propiedad password del objeto devuelto es System.Security.SecureString.</span><span class="sxs-lookup"><span data-stu-id="fb45c-115">The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="fb45c-116">Si desea obtener el texto sin formato de la contraseña del administrador de dominio, asegúrese de que la contraseña la introduzca la cuenta de inicio de sesión actual en el servidor host y, a continuación, abra una consola de PowerShell como administrador y ejecute el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="fb45c-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="fb45c-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb45c-117">Parameters</span></span>
<span data-ttu-id="fb45c-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fb45c-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="fb45c-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="fb45c-119">**Parameter**</span></span>|<span data-ttu-id="fb45c-120">**Required**</span><span class="sxs-lookup"><span data-stu-id="fb45c-120">**Required**</span></span>|<span data-ttu-id="fb45c-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fb45c-121">**Type**</span></span>|<span data-ttu-id="fb45c-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fb45c-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="fb45c-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="fb45c-123">AccountType</span></span> <br/> |<span data-ttu-id="fb45c-124">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="fb45c-124">Required</span></span>  <br/> | <span data-ttu-id="fb45c-125">System.String</span><span class="sxs-lookup"><span data-stu-id="fb45c-125">System.String</span></span> <br/> | <span data-ttu-id="fb45c-126">El valor accountType puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fb45c-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="fb45c-127">VmAdmin: el administrador local de máquinas virtuales de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fb45c-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="fb45c-128">DomainAdmin: administrador de dominio del dominio de la máquina virtual de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fb45c-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="fb45c-129">SafeModeAdmin: SafeModeAdmin del controlador de dominio de la máquina virtual de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fb45c-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="fb45c-130">ExternalCert: cuenta del certificado externo instalado en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="fb45c-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="fb45c-131">TenantAdmin: administrador del inquilino de O365.</span><span class="sxs-lookup"><span data-stu-id="fb45c-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="fb45c-132">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="fb45c-132">Input Types</span></span>
<span data-ttu-id="fb45c-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fb45c-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="fb45c-134">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fb45c-134">None.</span></span> <span data-ttu-id="fb45c-135">El Get-CcCredential no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="fb45c-135">The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fb45c-136">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="fb45c-136">Return Types</span></span>
<span data-ttu-id="fb45c-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fb45c-137"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="fb45c-138">El Get-CcCredential cmdlet devuelve una instancia del objeto System.Management.Automation.PSCredential.</span><span class="sxs-lookup"><span data-stu-id="fb45c-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fb45c-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb45c-139">See also</span></span>
<span data-ttu-id="fb45c-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fb45c-140"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="fb45c-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="fb45c-141">Set-CcCredential</span></span>](set-cccredential.md)
  


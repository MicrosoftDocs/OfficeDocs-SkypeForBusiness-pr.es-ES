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
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: 'The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment. '
ms.openlocfilehash: 46c51783361ad6613d1e2971600969b324f0f350
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003390"
---
# <a name="get-cccredential"></a><span data-ttu-id="e419c-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="e419c-103">Get-CcCredential</span></span>
 
<span data-ttu-id="e419c-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment. </span><span class="sxs-lookup"><span data-stu-id="e419c-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="e419c-105">Con la versión 2,0 y posteriores, también puede usar el parámetro-DisplayPassword para mostrar las contraseñas de TenantAdmin, esusuario y VMAdmin.</span><span class="sxs-lookup"><span data-stu-id="e419c-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="e419c-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e419c-106">Examples</span></span>
<span data-ttu-id="e419c-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e419c-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="e419c-108">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e419c-108">Example 1</span></span>

<span data-ttu-id="e419c-109">El siguiente ejemplo devuelve las credenciales del administrador de dominio del dominio de la máquina virtual de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e419c-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="e419c-110">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="e419c-110">Detailed Description</span></span>
<span data-ttu-id="e419c-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e419c-111"></span></span>

<span data-ttu-id="e419c-p101">El cmdlet Get-CcCredential devuelve información de las credenciales sobre el tipo de cuenta especificada. Estas credenciales las especifica el administrador que ejecuta los cmdlets Register-CcAppliance e Install-CcAppliance al implementar el dispositivo actual. </span><span class="sxs-lookup"><span data-stu-id="e419c-p101">The Get-CcCredential cmdlet returns the credential information about the specified account type. These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="e419c-p102">El cmdlet Get-CcCredential devuelve una instancia del objeto System.Management.Automation.PSCredential. La propiedad de contraseña del objeto devuelto es System.Security.SecureString.</span><span class="sxs-lookup"><span data-stu-id="e419c-p102">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object. The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="e419c-116">Si desea obtener el texto claro de la contraseña del administrador de dominio, asegúrese la cuenta que haya iniciado la sesión introduzca la contraseña en el servidor host. Después abra una consola de PowerShell como administrador y ejecute el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="e419c-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="e419c-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e419c-117">Parameters</span></span>
<span data-ttu-id="e419c-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e419c-118"></span></span>

|<span data-ttu-id="e419c-119">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="e419c-119">**Parameter**</span></span>|<span data-ttu-id="e419c-120">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="e419c-120">**Required**</span></span>|<span data-ttu-id="e419c-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e419c-121">**Type**</span></span>|<span data-ttu-id="e419c-122">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e419c-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e419c-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="e419c-123">AccountType</span></span> <br/> |<span data-ttu-id="e419c-124">Requerido</span><span class="sxs-lookup"><span data-stu-id="e419c-124">Required</span></span>  <br/> | <span data-ttu-id="e419c-125">System.String</span><span class="sxs-lookup"><span data-stu-id="e419c-125">System.String</span></span> <br/> | <span data-ttu-id="e419c-126">AccountType value can be one of the following:</span><span class="sxs-lookup"><span data-stu-id="e419c-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="e419c-127">VmAdmin: el administrador local de máquinas virtuales del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="e419c-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="e419c-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span><span class="sxs-lookup"><span data-stu-id="e419c-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="e419c-129">SafeModeAdmin: SafeModeAdmin del controlador de dominio de la máquina virtual de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="e419c-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="e419c-130">ExternalCert: cuenta del certificado interno instalado en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="e419c-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="e419c-131">TenantAdmin: administrador del inquilino de O365.</span><span class="sxs-lookup"><span data-stu-id="e419c-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="e419c-132">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e419c-132">Input Types</span></span>
<span data-ttu-id="e419c-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e419c-133"></span></span>

<span data-ttu-id="e419c-p103">Ninguno. El cmdlet Get-CcCredential no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="e419c-p103">None. The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e419c-136">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e419c-136">Return Types</span></span>
<span data-ttu-id="e419c-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e419c-137"></span></span>

<span data-ttu-id="e419c-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span><span class="sxs-lookup"><span data-stu-id="e419c-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e419c-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e419c-139">See also</span></span>
<span data-ttu-id="e419c-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e419c-140"></span></span>

[<span data-ttu-id="e419c-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="e419c-141">Set-CcCredential</span></span>](set-cccredential.md)
  


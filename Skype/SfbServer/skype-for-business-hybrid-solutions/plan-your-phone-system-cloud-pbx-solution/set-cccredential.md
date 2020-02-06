---
title: Set-CcCredential
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
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'El cmdlet Set-CcCredential establece las credenciales de la implementación actual de Skype Empresarial Cloud Connector Edition. '
ms.openlocfilehash: b7620a6d76415e4e2a49ea9bd628d1e1cba7f4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824214"
---
# <a name="set-cccredential"></a><span data-ttu-id="9eb9c-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="9eb9c-103">Set-CcCredential</span></span>
 
<span data-ttu-id="9eb9c-104">El cmdlet Set-CcCredential establece las credenciales de la implementación actual de Skype Empresarial Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="9eb9c-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="9eb9c-105">Con el conector de la nube versión 2,0 y posteriores, este cmdlet también puede establecer la información de la cuenta para el administrador de la máquina virtual y para el administrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="9eb9c-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9eb9c-106">Examples</span></span>
<span data-ttu-id="9eb9c-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9eb9c-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="9eb9c-108">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="9eb9c-108">Example 1</span></span>

<span data-ttu-id="9eb9c-109">En el siguiente ejemplo se especifica el nombre y la contraseña de la cuenta para el administrador de inquilinos:</span><span class="sxs-lookup"><span data-stu-id="9eb9c-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="9eb9c-110">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="9eb9c-110">Detailed Description</span></span>
<span data-ttu-id="9eb9c-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9eb9c-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="9eb9c-112">El cmdlet Set-CcCredential establece el nombre y la contraseña de la cuenta para el administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="9eb9c-113">Para las versiones anteriores a 2.0, este administrador tiene que ser un administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="9eb9c-114">El conector para la nube usa esta cuenta para obtener información de configuración, establecer parámetros de configuración y actualizar el estado del dispositivo a la configuración de inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="9eb9c-115">Con la versión 2,0 y posteriores, también puede usar este cmdlet para actualizar las contraseñas de las cuentas de VmAdmin y de.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9eb9c-116">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9eb9c-116">Parameters</span></span>
<span data-ttu-id="9eb9c-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9eb9c-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="9eb9c-118">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="9eb9c-118">**Parameter**</span></span>|<span data-ttu-id="9eb9c-119">**Requerida.**</span><span class="sxs-lookup"><span data-stu-id="9eb9c-119">**Required**</span></span>|<span data-ttu-id="9eb9c-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9eb9c-120">**Type**</span></span>|<span data-ttu-id="9eb9c-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9eb9c-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9eb9c-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="9eb9c-122">AccountType</span></span> <br/> | <span data-ttu-id="9eb9c-123">Requerido</span><span class="sxs-lookup"><span data-stu-id="9eb9c-123">Required</span></span> <br/> |<span data-ttu-id="9eb9c-124">System.String</span><span class="sxs-lookup"><span data-stu-id="9eb9c-124">System.String</span></span>  <br/> | <span data-ttu-id="9eb9c-125"> El valor del parámetro debe ser "TenantAdmin", "VmAdmin" o "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="9eb9c-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9eb9c-126">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="9eb9c-126">Input Types</span></span>
<span data-ttu-id="9eb9c-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9eb9c-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="9eb9c-p102">Ninguno. El cmdlet Set-CcCredential no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="9eb9c-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9eb9c-130">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="9eb9c-130">Return Types</span></span>
<span data-ttu-id="9eb9c-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9eb9c-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="9eb9c-132">Ninguno</span><span class="sxs-lookup"><span data-stu-id="9eb9c-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9eb9c-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9eb9c-133">See also</span></span>
<span data-ttu-id="9eb9c-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9eb9c-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="9eb9c-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="9eb9c-135">Get-CcCredential</span></span>](get-cccredential.md)
  


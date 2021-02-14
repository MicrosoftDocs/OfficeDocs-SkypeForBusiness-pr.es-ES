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
description: El Set-CcCredential establece la credencial de la implementación actual de Skype Empresarial Cloud Connector Edition.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221574"
---
# <a name="set-cccredential"></a><span data-ttu-id="a7f19-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="a7f19-103">Set-CcCredential</span></span>
 
<span data-ttu-id="a7f19-104">El Set-CcCredential establece la credencial de la implementación actual de Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="a7f19-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="a7f19-105">Con Cloud Connector versión 2.0 y versiones posteriores, este cmdlet también puede establecer la información de la cuenta para el administrador de la máquina virtual y para el administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="a7f19-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="a7f19-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a7f19-106">Examples</span></span>
<span data-ttu-id="a7f19-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a7f19-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a7f19-108">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a7f19-108">Example 1</span></span>

<span data-ttu-id="a7f19-109">En el siguiente ejemplo se especifica el nombre de cuenta y la contraseña del administrador de inquilinos:</span><span class="sxs-lookup"><span data-stu-id="a7f19-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="a7f19-110">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="a7f19-110">Detailed Description</span></span>
<span data-ttu-id="a7f19-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a7f19-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a7f19-112">El Set-CcCredential establece el nombre de cuenta y la contraseña del administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="a7f19-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="a7f19-113">Para las versiones anteriores a 2.0, este administrador debe ser un administrador global.</span><span class="sxs-lookup"><span data-stu-id="a7f19-113">For releases prior to 2.0, this administrator must be a Global Administrator.</span></span> <span data-ttu-id="a7f19-114">Cloud Connector usa esta cuenta para obtener información de configuración, establecer parámetros de configuración y actualizar el estado del dispositivo a la configuración de la organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7f19-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="a7f19-115">Con la versión 2.0 y versiones posteriores, también puede usar este cmdlet para actualizar las contraseñas de las cuentas VmAdmin y DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="a7f19-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a7f19-116">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7f19-116">Parameters</span></span>
<span data-ttu-id="a7f19-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a7f19-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="a7f19-118">**Parámetro**</span><span class="sxs-lookup"><span data-stu-id="a7f19-118">**Parameter**</span></span>|<span data-ttu-id="a7f19-119">**Required**</span><span class="sxs-lookup"><span data-stu-id="a7f19-119">**Required**</span></span>|<span data-ttu-id="a7f19-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a7f19-120">**Type**</span></span>|<span data-ttu-id="a7f19-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a7f19-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a7f19-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="a7f19-122">AccountType</span></span> <br/> | <span data-ttu-id="a7f19-123">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="a7f19-123">Required</span></span> <br/> |<span data-ttu-id="a7f19-124">System.String</span><span class="sxs-lookup"><span data-stu-id="a7f19-124">System.String</span></span>  <br/> | <span data-ttu-id="a7f19-125">El valor del parámetro debe ser "TenantAdmin", "VmAdmin" o "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="a7f19-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a7f19-126">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="a7f19-126">Input Types</span></span>
<span data-ttu-id="a7f19-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a7f19-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a7f19-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a7f19-128">None.</span></span> <span data-ttu-id="a7f19-129">El Set-CcCredential no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="a7f19-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a7f19-130">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="a7f19-130">Return Types</span></span>
<span data-ttu-id="a7f19-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a7f19-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a7f19-132">Ninguno</span><span class="sxs-lookup"><span data-stu-id="a7f19-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7f19-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7f19-133">See also</span></span>
<span data-ttu-id="a7f19-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a7f19-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="a7f19-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="a7f19-135">Get-CcCredential</span></span>](get-cccredential.md)
  


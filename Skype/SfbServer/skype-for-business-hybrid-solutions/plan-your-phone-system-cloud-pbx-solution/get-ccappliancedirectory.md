---
title: Get-CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'El cmdlet Get-CcApplianceDirectory recupera el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio. '
ms.openlocfilehash: c5c445e6017d8af81b681b70bbabcf2ba8bedd78
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="32b8a-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="32b8a-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="32b8a-p102">El cmdlet Get-CcApplianceDirectory recupera el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio. </span><span class="sxs-lookup"><span data-stu-id="32b8a-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="32b8a-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="32b8a-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="32b8a-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32b8a-108">Parameters</span></span>

<span data-ttu-id="32b8a-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="32b8a-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="32b8a-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="32b8a-110">Examples</span></span>
<span data-ttu-id="32b8a-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="32b8a-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="32b8a-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="32b8a-112">Example 1</span></span>

<span data-ttu-id="32b8a-113">En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los archivos de configuración y la máquina virtual de componentes del conector de la nube:</span><span class="sxs-lookup"><span data-stu-id="32b8a-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="32b8a-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="32b8a-114">Detailed Description</span></span>
<span data-ttu-id="32b8a-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="32b8a-115"></span></span>

<span data-ttu-id="32b8a-116">La muestra del cmdlet Get-CcApplianceDirectory donde se almacenan todos los archivos de configuración y la máquina virtual, registros y certificados externos para el dispositivo conector de nube.</span><span class="sxs-lookup"><span data-stu-id="32b8a-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="32b8a-117">Cada dispositivo conector de nube tiene cuatro componentes: un controlador de dominio, servidor perimetral, almacén de Administración Central y servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="32b8a-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="32b8a-118">La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="32b8a-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="32b8a-119">Puede cambiar esta carpeta usando el cmdlet Set-CCApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="32b8a-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="32b8a-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="32b8a-120">Input Types</span></span>
<span data-ttu-id="32b8a-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="32b8a-121"></span></span>

<span data-ttu-id="32b8a-p104">Ninguno. El cmdlet Get-CCApplianceDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="32b8a-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="32b8a-124">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="32b8a-124">Return Types</span></span>
<span data-ttu-id="32b8a-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="32b8a-125"></span></span>

<span data-ttu-id="32b8a-126">El comando devuelve una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="32b8a-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="32b8a-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32b8a-127">See also</span></span>
<span data-ttu-id="32b8a-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="32b8a-128"></span></span>

[<span data-ttu-id="32b8a-129">Conjunto de CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="32b8a-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  


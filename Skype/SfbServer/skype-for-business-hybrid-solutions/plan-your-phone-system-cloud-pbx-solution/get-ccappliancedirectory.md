---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'El cmdlet Get-CcApplianceDirectory recupera el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio. '
ms.openlocfilehash: 77064676062411c3417e554e422b0ffaae461191
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003410"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="d92b1-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="d92b1-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="d92b1-p102">El cmdlet Get-CcApplianceDirectory recupera el directorio de trabajo del servidor host de Skype Empresarial Cloud Connector Edition. Todos los archivos de implementación se almacenan en este directorio. </span><span class="sxs-lookup"><span data-stu-id="d92b1-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="d92b1-107">Este cmdlet se aplica a Skype Empresarial Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="d92b1-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="d92b1-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d92b1-108">Parameters</span></span>

<span data-ttu-id="d92b1-109">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d92b1-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d92b1-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d92b1-110">Examples</span></span>
<span data-ttu-id="d92b1-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d92b1-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="d92b1-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="d92b1-112">Example 1</span></span>

<span data-ttu-id="d92b1-113">En el ejemplo siguiente se muestra la carpeta actual donde se almacenan los archivos de configuración y de máquina virtual de los componentes del conector en la nube:</span><span class="sxs-lookup"><span data-stu-id="d92b1-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="d92b1-114">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="d92b1-114">Detailed Description</span></span>
<span data-ttu-id="d92b1-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d92b1-115"></span></span>

<span data-ttu-id="d92b1-116">El cmdlet Get-CcApplianceDirectory muestra dónde se almacenan toda la configuración y los archivos de la máquina virtual, los registros y los certificados externos para el dispositivo de conector de nube.</span><span class="sxs-lookup"><span data-stu-id="d92b1-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="d92b1-117">Cada equipo conector de nube tiene cuatro componentes: servidor de mediación, almacén central de administración, servidor perimetral y un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="d92b1-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="d92b1-118">La carpeta predeterminada es C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="d92b1-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="d92b1-119">Puede cambiar esta carpeta usando el cmdlet Set-CCApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="d92b1-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="d92b1-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="d92b1-120">Input Types</span></span>
<span data-ttu-id="d92b1-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d92b1-121"></span></span>

<span data-ttu-id="d92b1-p104">Ninguno. El cmdlet Get-CCApplianceDirectory no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="d92b1-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d92b1-124">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="d92b1-124">Return Types</span></span>
<span data-ttu-id="d92b1-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d92b1-125"></span></span>

<span data-ttu-id="d92b1-126">El comando devuelve una ruta de archivo.</span><span class="sxs-lookup"><span data-stu-id="d92b1-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d92b1-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d92b1-127">See also</span></span>
<span data-ttu-id="d92b1-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d92b1-128"></span></span>

[<span data-ttu-id="d92b1-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="d92b1-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  


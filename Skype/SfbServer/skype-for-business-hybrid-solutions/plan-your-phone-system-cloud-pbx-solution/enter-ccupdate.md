---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: El cmdlet Enter-CcUpdate prepara el servidor host de la edición Cloud Connector de Skype empresarial para el proceso de actualización al ponerlo en el modo de mantenimiento. El dispositivo detiene inmediatamente todos los servicios, finaliza cualquier llamada en curso y rechaza cualquier otra llamada.
ms.openlocfilehash: 3ff4c1543e3e882a7ccbaf0b9a216ce902a77c5f
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "34740061"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="0de12-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="0de12-104">Enter-CcUpdate</span></span>

<span data-ttu-id="0de12-105">El cmdlet Enter-CcUpdate prepara el servidor host de la edición Cloud Connector de Skype empresarial para el proceso de actualización al ponerlo en el modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="0de12-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="0de12-106">El dispositivo detiene inmediatamente todos los servicios, finaliza cualquier llamada en curso y rechaza cualquier otra llamada.</span><span class="sxs-lookup"><span data-stu-id="0de12-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="0de12-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0de12-107">Parameters</span></span>

<span data-ttu-id="0de12-108">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0de12-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="0de12-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0de12-109">Examples</span></span>
<span data-ttu-id="0de12-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0de12-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="0de12-111">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="0de12-111">Example 1</span></span>

<span data-ttu-id="0de12-112">En el siguiente ejemplo se prepara el dispositivo para el proceso de actualización mediante la entrada en el modo de mantenimiento:</span><span class="sxs-lookup"><span data-stu-id="0de12-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="0de12-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="0de12-113">Detailed Description</span></span>
<span data-ttu-id="0de12-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0de12-114"></span></span>

<span data-ttu-id="0de12-115">El cmdlet Enter-CcUpdate detendrá inmediatamente todos los servicios que finalizan cualquier llamada en curso y el dispositivo rechazará las llamadas nuevas, que se transfieren a otros dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="0de12-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="0de12-116">Debes asegurarte de que el resto de los dispositivos de producción tengan capacidad suficiente para manejar las llamadas desde el dispositivo que estás preparando para actualizar.</span><span class="sxs-lookup"><span data-stu-id="0de12-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="0de12-p104">El modo de mantenimiento es útil si, por ejemplo, el dispositivo tiene habilitada la actualización automática y Microsoft publica una revisión crítica. El modo de mantenimiento también es útil si decide desactivar las actualizaciones automáticas, pero realiza actualizaciones manuales con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="0de12-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="0de12-119">Después de instalar las actualizaciones, el dispositivo puede volver al modo de producción ejecutando el cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="0de12-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0de12-120">Si decide actualizar manualmente un dispositivo de conector de nube, tendrá que actualizarlo dentro de 60 días después de que Microsoft publique la versión siguiente.</span><span class="sxs-lookup"><span data-stu-id="0de12-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="0de12-121">Microsoft admite la versión publicada anteriormente del conector en la nube para 60 días después de que se publique la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="0de12-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="0de12-122">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="0de12-122">Input Types</span></span>
<span data-ttu-id="0de12-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0de12-123"></span></span>

<span data-ttu-id="0de12-p106">Ninguno. El cmdlet Enter-CCUpdate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="0de12-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0de12-126">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="0de12-126">Return Types</span></span>
<span data-ttu-id="0de12-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0de12-127"></span></span>

<span data-ttu-id="0de12-128">Ninguno</span><span class="sxs-lookup"><span data-stu-id="0de12-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0de12-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0de12-129">See also</span></span>
<span data-ttu-id="0de12-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0de12-130"></span></span>

[<span data-ttu-id="0de12-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="0de12-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  


---
title: Escriba-CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: El cmdlet Enter-CcUpdate prepara el servidor host de Skype Empresarial Cloud Connector Edition para el proceso de actualización poniéndolo en modo de mantenimiento. El isdrained del dispositivo, es decir, todas las llamadas existentes se completarán, pero las nuevas llamadas se rechazan.
ms.openlocfilehash: ed9f3f614829cd5b6bc2cd5499c6889258d67531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enter-ccupdate"></a><span data-ttu-id="3b4ba-104">Escriba-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="3b4ba-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="3b4ba-105">El cmdlet Enter-CcUpdate prepara el servidor host de Skype Empresarial Cloud Connector Edition para el proceso de actualización poniéndolo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="3b4ba-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="3b4ba-106">El dispositivo se "vacía", es decir, todas las llamadas existentes se completarán, pero las nuevas llamadas se rechazan.</span><span class="sxs-lookup"><span data-stu-id="3b4ba-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="3b4ba-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b4ba-107">Parameters</span></span>

<span data-ttu-id="3b4ba-108">Ninguno</span><span class="sxs-lookup"><span data-stu-id="3b4ba-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3b4ba-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3b4ba-109">Examples</span></span>
<span data-ttu-id="3b4ba-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3b4ba-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="3b4ba-111">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="3b4ba-111">Example 1</span></span>

<span data-ttu-id="3b4ba-112">En el siguiente ejemplo se prepara el dispositivo para el proceso de actualización mediante la entrada en el modo de mantenimiento:</span><span class="sxs-lookup"><span data-stu-id="3b4ba-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="3b4ba-113">Descripción detallada</span><span class="sxs-lookup"><span data-stu-id="3b4ba-113">Detailed Description</span></span>
<span data-ttu-id="3b4ba-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3b4ba-114"></span></span>

<span data-ttu-id="3b4ba-115">El cmdlet ENTRAR CcUpdate garantizará que todas las llamadas de ejecución en un dispositivo conector de nube se completará, pero el dispositivo rechazará las nuevas llamadas, que son transferidas a otros dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="3b4ba-115">The Enter-CcUpdate cmdlet will ensure that all running calls on a Cloud Connector appliance will complete, but the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="3b4ba-116">Este cmdlet le permite actualizar un dispositivo sin afectar a las llamadas de los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="3b4ba-116">This cmdlet enables you to update an appliance without affecting end users calls.</span></span> <span data-ttu-id="3b4ba-117">Deberá asegurarse de que los dispositivos de producción restantes tengan la suficiente capacidad para gestionar las llamadas del dispositivo en el que está preparando la actualización.</span><span class="sxs-lookup"><span data-stu-id="3b4ba-117">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="3b4ba-p104">El modo de mantenimiento es útil si, por ejemplo, el dispositivo tiene habilitada la actualización automática y Microsoft publica una revisión crítica. El modo de mantenimiento también es útil si decide desactivar las actualizaciones automáticas, pero realiza actualizaciones manuales con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="3b4ba-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="3b4ba-120">Después de instalar las actualizaciones, el dispositivo puede regresar al modo de producción con el cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="3b4ba-120">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b4ba-121">Si decide actualizar manualmente un dispositivo conector de nube, necesitará actualizarla dentro de 60 días después de que Microsoft lance la versión siguiente.</span><span class="sxs-lookup"><span data-stu-id="3b4ba-121">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="3b4ba-122">Microsoft admite la versión publicado previamente de nube conector durante 60 días después de que se publique la nueva versión</span><span class="sxs-lookup"><span data-stu-id="3b4ba-122">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="3b4ba-123">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="3b4ba-123">Input Types</span></span>
<span data-ttu-id="3b4ba-124"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3b4ba-124"></span></span>

<span data-ttu-id="3b4ba-p106">Ninguno. El cmdlet Enter-CCUpdate no acepta entradas canalizadas.</span><span class="sxs-lookup"><span data-stu-id="3b4ba-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3b4ba-127">Tipos de valores devueltos</span><span class="sxs-lookup"><span data-stu-id="3b4ba-127">Return Types</span></span>
<span data-ttu-id="3b4ba-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3b4ba-128"></span></span>

<span data-ttu-id="3b4ba-129">Ninguno</span><span class="sxs-lookup"><span data-stu-id="3b4ba-129">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3b4ba-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b4ba-130">See also</span></span>
<span data-ttu-id="3b4ba-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3b4ba-131"></span></span>

[<span data-ttu-id="3b4ba-132">Salir CcUpdate</span><span class="sxs-lookup"><span data-stu-id="3b4ba-132">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  


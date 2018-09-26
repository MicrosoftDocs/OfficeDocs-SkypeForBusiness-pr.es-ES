---
title: Comprobar la configuración
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede validar la replicación de la información de configuración para el servidor perimetral mediante la ejecución de la Skype para cmdlet Business Server 2019 Get-CsManagementStoreReplicationStatus en el equipo interno en que se encuentra el almacén de Administración Central, o en cualquier equipo en el que está instalado Skype para 2019 principales componentes (OcsCore.msi) de Business Server unido a un dominio.
ms.openlocfilehash: 23a5b4c3af8ac02ebfd620d3bbc46ddcba5bea11
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027812"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="d8f63-103">Comprobar la configuración</span><span class="sxs-lookup"><span data-stu-id="d8f63-103">Verify configuration settings</span></span>

<span data-ttu-id="d8f63-104">Puede validar la replicación de la información de configuración para el servidor perimetral mediante la ejecución de la Skype para el cmdlet **Get-CsManagementStoreReplicationStatus** de Business Server 2019 en el equipo interno en el que se encuentra, el almacén de Administración Central o en cualquier equipo unido a un dominio en el que está instalado Skype para Business Server 2019 principales componentes (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="d8f63-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="d8f63-105">Resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación.</span><span class="sxs-lookup"><span data-stu-id="d8f63-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="d8f63-106">Si es así, ejecute el cmdlet **Invoke-CsManagementStoreReplication** y permita que la replicación se complete antes de ejecutar de nuevo el **Get-CsManagementStoreReplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="d8f63-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  


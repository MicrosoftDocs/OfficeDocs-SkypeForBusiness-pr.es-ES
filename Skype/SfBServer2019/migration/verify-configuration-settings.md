---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet Get-CsManagementStoreReplicationStatus de Skype Empresarial Server 2019 en el equipo interno en el que se encuentra el almacén de administración central, o en cualquier equipo unido a un dominio en el que esté instalado Skype Empresarial Server 2019 Core Components (OcsCore.msi).
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752152"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="bba4b-103">Comprobación de los parámetros de configuración</span><span class="sxs-lookup"><span data-stu-id="bba4b-103">Verify configuration settings</span></span>

<span data-ttu-id="bba4b-104">Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet **Get-CsManagementStoreReplicationStatus** de Skype Empresarial Server 2019 en el equipo interno en el que se encuentra el almacén de administración central o en cualquier equipo unido a un dominio en el que esté instalado Skype Empresarial Server 2019 Core Components (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="bba4b-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="bba4b-105">Los resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación.</span><span class="sxs-lookup"><span data-stu-id="bba4b-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="bba4b-106">Si es así, ejecute el cmdlet del **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="bba4b-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  


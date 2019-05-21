---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet Get-CsManagementStoreReplicationStatus de Skype empresarial Server 2019 en el equipo interno en el que se encuentra el almacén central de administración o en cualquier equipo unido al dominio en el que está instalado el componente principal de Skype empresarial Server 2019 (OcsCore. msi).
ms.openlocfilehash: 0ea966652972a97dac3e807cef42ddeaa5136322
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307038"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="c79c3-103">Comprobación de los parámetros de configuración</span><span class="sxs-lookup"><span data-stu-id="c79c3-103">Verify configuration settings</span></span>

<span data-ttu-id="c79c3-104">Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet **Get-CsManagementStoreReplicationStatus** de Skype empresarial Server 2019 en el equipo interno en el que se encuentra el almacén central de administración, o bien en cualquier equipo unido a un dominio en el que estén instalados los componentes básicos de Skype empresarial Server 2019 (OcsCore. msi).</span><span class="sxs-lookup"><span data-stu-id="c79c3-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="c79c3-105">Los resultados iniciales pueden indicar que el estado es "false" en lugar de "true" para la replicación.</span><span class="sxs-lookup"><span data-stu-id="c79c3-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="c79c3-106">En ese caso, ejecuta el cmdlet **Invoke-CsManagementStoreReplication** y deja tiempo para que se complete la replicación antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="c79c3-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  


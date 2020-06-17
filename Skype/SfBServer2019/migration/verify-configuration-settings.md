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
description: Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet Get-CsManagementStoreReplicationStatus de Skype empresarial Server 2019 en el equipo interno en el que está ubicado el almacén de administración central, o en cualquier equipo unido al dominio en el que estén instalados los componentes básicos de Skype empresarial Server 2019 (OcsCore.msi).
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752152"
---
# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

Para validar la replicación de la información de configuración en el servidor perimetral, ejecute el cmdlet **Get-CsManagementStoreReplicationStatus** de Skype empresarial Server 2019 en el equipo interno en el que está ubicado el almacén de administración central o en cualquier equipo unido a un dominio en el que estén instalados los componentes básicos de Skype empresarial Server 2019 (OcsCore.msi). 
  
Los resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación. Si es así, ejecute el cmdlet del **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**. 
  


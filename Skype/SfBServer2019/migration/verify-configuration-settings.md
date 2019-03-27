---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede validar la replicación de la información de configuración para el servidor perimetral mediante la ejecución de la Skype para cmdlet Business Server 2019 Get-CsManagementStoreReplicationStatus en el equipo interno en que se encuentra el almacén de Administración Central, o en cualquier equipo en el que está instalado Skype para 2019 principales componentes (OcsCore.msi) de Business Server unido a un dominio.
ms.openlocfilehash: 1b64569ffbdce3d7f41e7f6c54815d051848cfd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889679"
---
# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

Puede validar la replicación de la información de configuración para el servidor perimetral mediante la ejecución de la Skype para el cmdlet **Get-CsManagementStoreReplicationStatus** de Business Server 2019 en el equipo interno en el que se encuentra, el almacén de Administración Central o en cualquier equipo unido a un dominio en el que está instalado Skype para Business Server 2019 principales componentes (OcsCore.msi). 
  
Resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación. Si es así, ejecute el cmdlet **Invoke-CsManagementStoreReplication** y permita que la replicación se complete antes de ejecutar de nuevo el **Get-CsManagementStoreReplicationStatus** . 
  


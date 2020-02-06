---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet Get-CsManagementStoreReplicationStatus de Skype empresarial Server 2019 en el equipo interno en el que se encuentra el almacén central de administración o en cualquier equipo unido al dominio en el que está instalado el componente principal de Skype empresarial Server 2019 (OcsCore. msi).
ms.openlocfilehash: 141bb640193834316ca65f9a42db611010896034
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812758"
---
# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

Para validar la replicación de la información de configuración en el servidor perimetral, ejecute el cmdlet **Get-CsManagementStoreReplicationStatus** de Skype empresarial Server 2019 en el equipo interno en el que se encuentra el almacén de administración central o en cualquier equipo unido al dominio en el que estén instalados los componentes básicos de Skype empresarial Server 2019 (OcsCore. msi). 
  
Los resultados iniciales pueden indicar que el estado es "false" en lugar de "true" para la replicación. En ese caso, ejecuta el cmdlet **Invoke-CsManagementStoreReplication** y deja tiempo para que se complete la replicación antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus** . 
  


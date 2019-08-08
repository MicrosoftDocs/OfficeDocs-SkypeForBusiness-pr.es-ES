---
title: Comprobación de los parámetros de configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet Get-CsManagementStoreReplicationStatus de Skype empresarial Server 2019 en el equipo interno en el que se encuentra el almacén central de administración o en cualquier equipo unido al dominio en el que está instalado el componente principal de Skype empresarial Server 2019 (OcsCore. msi).
ms.openlocfilehash: 5beb3c80bbc4c2f9a73fe68b9d99d7752598c680
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240941"
---
# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

Puede validar la replicación de la información de configuración en el servidor perimetral ejecutando el cmdlet **Get-CsManagementStoreReplicationStatus** de Skype empresarial Server 2019 en el equipo interno en el que se encuentra el almacén central de administración, o bien en cualquier equipo unido a un dominio en el que estén instalados los componentes básicos de Skype empresarial Server 2019 (OcsCore. msi). 
  
Los resultados iniciales pueden indicar que el estado es "false" en lugar de "true" para la replicación. En ese caso, ejecuta el cmdlet **Invoke-CsManagementStoreReplication** y deja tiempo para que se complete la replicación antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus** . 
  


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
description: Puede validar la replicación de información de configuración en el servidor perimetral ejecutando el cmdlet Skype Empresarial Server 2019 Get-CsManagementStoreReplicationStatus en el equipo interno en el que se encuentra el almacén de administración central o en cualquier equipo unido al dominio en el que esté instalado Skype Empresarial Server Componentes principales (OcsCore.msi) de 2019.
ms.openlocfilehash: e681781598af876f722094b0191aa784da2c533adc509a9f9fc4fad96fa4db4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335750"
---
# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

Para validar la replicación de información de configuración en el servidor perimetral, ejecute el cmdlet **Get-CsManagementStoreReplicationStatus** de Skype Empresarial Server 2019 en el equipo interno en el que se encuentra el almacén de administración central o en cualquier equipo unido al dominio en el que esté instalado Skype Empresarial Server componentes principales (OcsCore.msi) de 2019. 
  
Los resultados iniciales pueden indicar un estado "False" en lugar de "True" para la replicación. Si es así, ejecute el cmdlet del **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**. 
  


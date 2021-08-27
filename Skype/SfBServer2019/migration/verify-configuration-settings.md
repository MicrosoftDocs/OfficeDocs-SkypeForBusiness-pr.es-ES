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
ms.localizationpriority: medium
description: Puede validar la replicación de información de configuración en el servidor perimetral ejecutando el cmdlet Skype Empresarial Server 2019 Get-CsManagementStoreReplicationStatus en el equipo interno en el que se encuentra el almacén de administración central o en cualquier equipo unido al dominio en el que esté instalado Skype Empresarial Server Componentes principales (OcsCore.msi) de 2019.
ms.openlocfilehash: ff46dbad696ac4bf200bb669de768a28d0815e1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594268"
---
# <a name="verify-configuration-settings"></a>Comprobación de los parámetros de configuración

Para validar la replicación de información de configuración en el servidor perimetral, ejecute el cmdlet **Get-CsManagementStoreReplicationStatus** de Skype Empresarial Server 2019 en el equipo interno en el que se encuentra el almacén de administración central o en cualquier equipo unido al dominio en el que esté instalado Skype Empresarial Server componentes principales (OcsCore.msi) de 2019. 
  
Los resultados iniciales pueden indicar un estado "False" en lugar de "True" para la replicación. Si es así, ejecute el cmdlet del **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**. 
  


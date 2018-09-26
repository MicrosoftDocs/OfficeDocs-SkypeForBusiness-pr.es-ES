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
# <a name="verify-configuration-settings"></a>Comprobar la configuración

Puede validar la replicación de la información de configuración para el servidor perimetral mediante la ejecución de la Skype para el cmdlet **Get-CsManagementStoreReplicationStatus** de Business Server 2019 en el equipo interno en el que se encuentra, el almacén de Administración Central o en cualquier equipo unido a un dominio en el que está instalado Skype para Business Server 2019 principales componentes (OcsCore.msi). 
  
Resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación. Si es así, ejecute el cmdlet **Invoke-CsManagementStoreReplication** y permita que la replicación se complete antes de ejecutar de nuevo el **Get-CsManagementStoreReplicationStatus** . 
  


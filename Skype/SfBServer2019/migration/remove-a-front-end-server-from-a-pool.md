---
title: Quitar un servidor front-end de un grupo de servidores
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
description: El servidor front-end no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si hay un solo equipo en el grupo.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752322"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Quitar un servidor front-end de un grupo de servidores

El servidor front-end no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si hay un solo equipo en el grupo.
  
Este tema le guiará por el proceso de eliminación de un servidor front-end individual de un grupo de servidores front-end existente. Si el servidor front-end es el último servidor del grupo o si va a quitar completamente el grupo de servidores, consulte [quitar un grupo de servidores front-end o un servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md). No es necesario quitar los servidores front-end individuales antes de quitar el grupo de servidores front-end. Al quitar el grupo de servidores, se quitan todos los servidores front-end.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para quitar un servidor front-end de un grupo

1. En el servidor front-end de Skype empresarial Server 2019, abra el generador de topologías.
    
2. Navegue hasta el nodo instalación heredada.
    
3. Expanda grupos de servidores Front **-End Enterprise Edition**, expanda el grupo de servidores front-end con el servidor front-end que desea quitar, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.
    


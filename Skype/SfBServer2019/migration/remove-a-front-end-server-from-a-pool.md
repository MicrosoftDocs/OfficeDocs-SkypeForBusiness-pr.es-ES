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
ms.localizationpriority: medium
description: El servidor front-end no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si solo hay un solo equipo en el grupo.
ms.openlocfilehash: b52954421034d83191e479e59d1efeeda8972868
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595004"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Quitar un servidor front-end de un grupo de servidores

El servidor front-end no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si solo hay un solo equipo en el grupo.
  
En este tema se explica el proceso de eliminación de un servidor front-end individual de un grupo de servidores front-end existente. Si el servidor front-end es el último servidor del grupo o si está quitando el grupo por completo, consulte [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md). No es necesario quitar los servidores front-end individuales antes de quitar el grupo de servidores front-end. Al quitar el grupo de servidores, quita cada servidor front-end.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para quitar un servidor front-end de un grupo

1. En el Skype Empresarial Server front-end de 2019, abra el Generador de topologías.
    
2. Vaya al nodo de instalación heredado.
    
3. Expanda **Enterprise Edition** grupos de servidores front-end, expanda el grupo de servidores front-end con el servidor front-end que desea quitar, haga clic con el botón secundario en el servidor front-end que desea quitar y, a continuación, haga clic en **Eliminar**.
    


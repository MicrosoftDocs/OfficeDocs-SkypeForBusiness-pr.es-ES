---
title: Quitar un servidor front-end de un grupo de servidores
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
description: El servidor front-end no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si solo hay un equipo en el grupo.
ms.openlocfilehash: 93df9e293f7a1876d4a8b1f172472f708556f67f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813038"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Quitar un servidor front-end de un grupo de servidores

El servidor front-end no puede existir como un equipo independiente. Debe definirse como un grupo de servidores front-end, incluso si solo hay un equipo en el grupo.
  
Este tema le guiará a través del proceso de eliminación de un servidor de front-end individual de un grupo de servidores front-end existente. Si el servidor front-end es el último servidor del grupo o si va a quitar el grupo por completo, consulte [quitar grupo de servidores front-end o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md). No es necesario quitar los servidores front-end individuales antes de quitar el grupo de servidores front-end. Al quitar el grupo, se quita cada uno de los servidores front-end.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Para quitar un servidor front-end de un grupo

1. En el servidor front-end de Skype empresarial Server 2019, abra Topology Builder.
    
2. Vaya al nodo instalación heredada.
    
3. Expanda **agrupaciones front end de Enterprise Edition**, expanda el grupo de aplicaciones para el usuario con el servidor front-end que desee quitar, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.
    


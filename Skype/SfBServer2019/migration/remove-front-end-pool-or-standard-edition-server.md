---
title: Quitar un grupo de servidores front-end o un servidor Standard Edition
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
description: En este tema se guía por el proceso de eliminación de un grupo de servidores front-end o Standard Edition servidor front-end. Al quitar un grupo de servidores front-end, se quitan todos los servidores front-end que pertenecen al grupo como parte del proceso de eliminación del grupo. Al quitar un servidor Standard Edition front-end, debe quitar la definición SQL Store del Generador de topologías.
ms.openlocfilehash: 97407c05afc6055c02b7b54343bbd551c88e6a04236528a74da91f326bf9e25c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304732"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Quitar un grupo de servidores front-end o un servidor Standard Edition

En este artículo se guía por el proceso de eliminación de un grupo de servidores front-end o Standard Edition servidor front-end. Al quitar un grupo de servidores front-end, se quitan todos los servidores front-end que pertenecen al grupo como parte del proceso de eliminación del grupo. Al quitar un servidor Standard Edition front-end, debe quitar la definición SQL Store del Generador de topologías.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para quitar un grupo de servidores front-end

1. Abra el Generador de topologías.
    
2. Vaya al nodo heredado.
    
3. Expanda Enterprise Edition grupos de servidores **front-end,** expanda el grupo de servidores front-end, haga clic con el botón secundario en el grupo de servidores front-end que desea quitar y, a continuación, haga clic en **Eliminar**.
    
4. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación heredada según sea necesario. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para quitar un servidor front-end Standard Edition

1. Abra el Generador de topologías.
    
2. Vaya al nodo de instalación heredada.
    
3. Expanda **Standard Edition servidores front-end,** haga clic con el botón secundario en el servidor front-end que desea quitar y, a continuación, haga clic en **Eliminar**.
    
4. Expanda **SQL,** haga clic con el botón secundario en la base de datos de SQL Server asociada con el servidor front-end Standard Edition y, a continuación, haga clic en **Eliminar**.
    
    > [!IMPORTANT]
    > Debe quitar la definición de las bases SQL Server de datos Standard Edition servidor front-end. 
  
5. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para implementación según sea necesario. 
    


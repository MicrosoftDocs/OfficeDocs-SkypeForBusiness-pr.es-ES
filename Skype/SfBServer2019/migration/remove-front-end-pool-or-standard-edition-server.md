---
title: Quitar un grupo de servidores front-end o servidor Standard Edition
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
description: Este tema le guiará por el proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition. Al quitar un grupo de servidores front-end, se quitan todos los servidores front-end que pertenecen al grupo como parte del proceso de eliminación del grupo. Al quitar un servidor front-end Standard Edition, debe quitar la definición del almacén de SQL del generador de topologías.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752282"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Quitar un grupo de servidores front-end o servidor Standard Edition

Este artículo le guiará por el proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition. Al quitar un grupo de servidores front-end, se quitan todos los servidores front-end que pertenecen al grupo como parte del proceso de eliminación del grupo. Al quitar un servidor front-end Standard Edition, debe quitar la definición del almacén de SQL del generador de topologías.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para quitar un grupo de servidores front-end

1. Abra el Generador de topologías.
    
2. Desplácese hasta el nodo heredado.
    
3. Expanda grupos de servidores Front **-End Enterprise Edition**, expanda el grupo de servidores front-end, haga clic con el botón secundario en el grupo de servidores front-end que desee quitar y, a continuación, haga clic en **eliminar**.
    
4. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación heredada según sea necesario. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para quitar un servidor front-end Standard Edition

1. Abra el Generador de topologías.
    
2. Navegue hasta el nodo instalaciones heredadas.
    
3. Expanda **servidores front-end Standard Edition**, haga clic con el botón secundario en el servidor front-end que desea quitar y, a continuación, haga clic en **eliminar**.
    
4. Expanda **almacenes SQL**, haga clic con el botón secundario en la base de datos de SQL Server asociada con el servidor front-end Standard Edition y, a continuación, haga clic en **eliminar**.
    
    > [!IMPORTANT]
    > Debe quitar la definición de las bases de datos de SQL Server combinados del servidor front-end Standard Edition. 
  
5. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación según sea necesario. 
    


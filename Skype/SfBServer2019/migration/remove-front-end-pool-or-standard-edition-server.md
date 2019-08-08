---
title: Quitar un grupo de servidores front-end o servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tema le guiará a través del proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition. Al quitar un grupo de servidores front-end, se quita cada servidor front-end que pertenece al grupo como parte del proceso de eliminación de la agrupación. Al quitar un servidor front-end Standard Edition, debe quitar la definición de la tienda SQL del generador de topología.
ms.openlocfilehash: 57679fb248c9281b79c12be98b7fd5246c9afd38
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244270"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Quitar un grupo de servidores front-end o servidor Standard Edition

Este artículo le guiará a través del proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition. Al quitar un grupo de servidores front-end, se quita cada servidor front-end que pertenece al grupo como parte del proceso de eliminación de la agrupación. Al quitar un servidor front-end Standard Edition, debe quitar la definición de la tienda SQL del generador de topología.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para quitar un grupo de servidores front-end

1. Abra el generador de topologías.
    
2. Vaya al nodo heredado.
    
3. Expanda agrupaciones **front end de Enterprise Edition**, expanda el grupo de servidores front-end, haga clic con el botón secundario en el grupo de servidores front-end que desee quitar y, a continuación, haga clic en **eliminar**.
    
4. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación heredada según sea necesario. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para quitar un servidor front-end Standard Edition

1. Abra el generador de topologías.
    
2. Vaya al nodo instalaciones heredadas.
    
3. Expanda **servidores front-end Standard Edition**, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.
    
4. Expanda **almacenes SQL**, haga clic con el botón secundario en la base de datos de SQL Server asociada al servidor front-end Standard Edition y, después, haga clic en **eliminar**.
    
    > [!IMPORTANT]
    > Debe quitar la definición de las bases de datos de SQL Server en el servidor front-end Standard Edition. 
  
5. Publique la topología, compruebe el estado de la replicación y, a continuación, ejecute el Asistente para la implementación según sea necesario. 
    


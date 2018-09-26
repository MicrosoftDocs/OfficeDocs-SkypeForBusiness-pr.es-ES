---
title: Quitar el servidor Standard Edition o grupo de servidores Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este tema le guiará en el proceso de eliminación de un grupo de servidores Front-End o un servidor estándar de edición de Front-End. Al quitar un grupo de servidores Front-End, quite cada servidor Front-End que pertenece al grupo de servidores como parte del proceso de eliminación de grupo de servidores. Cuando se quita una edición Standard servidor Front-End, debe quitar la definición de almacén SQL del generador.
ms.openlocfilehash: 7e56f2e9ff57536d1f065452f299a9af33a46aee
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028890"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Quitar el servidor Standard Edition o grupo de servidores Front-End

En este artículo le guiará por el proceso de eliminación de un grupo de servidores Front-End o un servidor estándar de edición de Front-End. Al quitar un grupo de servidores Front-End, quite cada servidor Front-End que pertenece al grupo de servidores como parte del proceso de eliminación de grupo de servidores. Cuando se quita una edición Standard servidor Front-End, debe quitar la definición de almacén SQL del generador.
  
## <a name="to-remove-a-front-end-server-pool"></a>Para quitar un grupo de servidor Front-End

1. Abra el generador de topología.
    
2. Vaya al nodo heredado.
    
3. Expanda **grupos de servidores Front-End de Enterprise Edition**, expanda el grupo de servidores Front-End, haga clic en el grupo de servidores Front-End que desea quitar y, a continuación, haga clic en **Eliminar**.
    
4. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute al Asistente para la implementación heredada según sea necesario. 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>Para quitar un servidor Front-End de Standard Edition

1. Abra el generador de topología.
    
2. Desplácese hasta el nodo de instalaciones heredadas.
    
3. Expanda **servidores Front-End de Standard Edition**, haga clic en el servidor Front-End que desea quitar y, a continuación, haga clic en **Eliminar**.
    
4. Expanda **almacenes SQL**, haga clic en la base de datos de SQL Server que está asociada con la edición Standard servidor Front-End y, a continuación, haga clic en **Eliminar**.
    
    > [!IMPORTANT]
    > Debe quitar la definición de las bases de datos de SQL Server instaladas de la edición Standard servidor Front-End. 
  
5. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute al Asistente para la implementación según sea necesario. 
    


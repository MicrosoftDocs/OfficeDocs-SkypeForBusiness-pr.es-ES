---
title: Quitar un grupo de servidores front-end o servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este tema le guiará en el proceso de eliminación de un grupo de servidores Front-End o un servidor estándar de edición de Front-End. Al quitar un grupo de servidores Front-End, quite cada servidor Front-End que pertenece al grupo de servidores como parte del proceso de eliminación de grupo de servidores. Cuando se quita una edición Standard servidor Front-End, debe quitar la definición de almacén SQL del generador.
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872720"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Quitar un grupo de servidores front-end o servidor Standard Edition

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
    


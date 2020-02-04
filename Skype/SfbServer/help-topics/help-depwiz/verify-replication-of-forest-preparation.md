---
title: Comprobar replicación de la preparación del bosque
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Para confirmar que la replicación del catálogo global y la creación de objetos durante la preparación del bosque se han realizado correctamente, haga lo siguiente:'
ms.openlocfilehash: 4f17b62fd0756019bab105df323215571557dce2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700655"
---
# <a name="verify-replication-of-forest-preparation"></a>Comprobar replicación de la preparación del bosque
 
Para confirmar que la replicación del catálogo global y la creación de objetos durante la preparación del bosque se han realizado correctamente, haga lo siguiente:
  
1. En un controlador de dominio (preferentemente en un sitio remoto desde otros controladores de dominio) en el bosque donde se ejecutó la preparación del bosque, abra **Usuarios y equipos de Active Directory**.
    
2. En **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.
    
3. Haga clic en el contenedor **usuarios** en el panel de la izquierda y busque el grupo universal CsAdministrator en el panel de la derecha. Si CsAdministrator (entre otros ocho grupos universales nuevos que comienzan por CS) está presente, la replicación de la preparación del bosque se ha realizado correctamente.
    
4. Si los grupos aún no están presentes, puede forzar la replicación o esperar 15 minutos y actualizar el panel de la derecha. Cuando los grupos están presentes, la replicación se ha completado.
    
> [!TIP]
> Si desea revisar los archivos de registro creados por el Asistente para la implementación de Skype empresarial Server, puede encontrarlos en el equipo en el que se ejecutó el Asistente para la implementación, en el directorio usuarios del usuario de los servicios de dominio de Active Directory que ejecutó el paso. Por ejemplo, si el usuario ha iniciado sesión como administrador del dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  


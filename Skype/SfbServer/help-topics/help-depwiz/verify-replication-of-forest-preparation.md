---
title: Comprobar la replicación de la preparación del bosque
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Para confirmar que la replicación del catálogo Global y la creación de objetos durante la preparación del bosque ha sido correcta, haga lo siguiente:'
ms.openlocfilehash: cfb993a9a80bf4b37e76712a58aa6c1fb0c270c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-forest-preparation"></a>Comprobar la replicación de la preparación del bosque
 
Para confirmar que la replicación del catálogo Global y la creación de objetos durante la preparación del bosque ha sido correcta, haga lo siguiente:
  
1. En un controlador de dominio (preferentemente en un sitio remoto desde otros controladores de dominio) en el bosque donde se ejecutó la preparación del bosque, abra **Usuarios y equipos de Active Directory**.
    
2. En **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.
    
3. Haga clic en el contenedor **usuarios** en el panel de la izquierda y busque el grupo Universal CsAdministrator en el panel de la derecha. Si está presente CsAdministrator (entre ocho otros nuevos grupos universales que comienzan con Cs), la replicación de la preparación del bosque ha tenido éxito.
    
4. Si el grupo aún no está presente, puede forzar la replicación o espere 15 minutos y actualizar el panel de la derecha. Cuando los grupos están presentes, la replicación se ha completado.
    
> [!TIP]
> Si desea revisar los archivos de registro creados por el Skype para el Asistente para implementación de Business Server, puede encontrarlas en el equipo donde se ejecuta el Asistente de implementación, en el directorio de usuarios de usuario de servicios de dominio de Active Directory que ejecutó el paso. Por ejemplo, si el usuario ha iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  


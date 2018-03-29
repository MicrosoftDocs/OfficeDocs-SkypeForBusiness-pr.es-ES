---
title: Preparar dominio actual
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Para preparar un dominio para servidores host ejecutando Skype para Business Server 2015 o Skype para los usuarios de Business Server, debe completar el paso 5: Preparar dominio actual, como se describe en el tema mediante el programa de instalación para ejecutar la preparación del dominio. Para completar el paso debe ser iniciado como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de organización del bosque que pertenece al dominio. Para preparar el dominio:'
ms.openlocfilehash: e34498dd44d7518300b0e7d4df6a5135b8e51a2d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-current-domain"></a>Preparar dominio actual
 
Para preparar un dominio para servidores host ejecutando Skype para Business Server 2015 o Skype para los usuarios de Business Server, debe completar **paso 5: Preparar dominio actual**, como se describe en el tema [Utilizando el programa de instalación para ejecutar la preparación del dominio](http://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Para completar el paso debe ser iniciado como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de organización del bosque que pertenece al dominio. Para preparar el dominio:
  
1. De Skype para la carpeta de instalación de Business Server 2015 o media, ejecute Setup.exe para iniciar el Skype para el Asistente para implementación de Business Server.
    
2. Haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.
    
3. En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.
    
4. En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.
    
5. En la columna **acción** , expanda **Preparar el dominio**, busque un ** \<éxito\> ** resultado de ejecución al final de cada tarea para comprobar que finalizó correctamente la preparación de dominio, cierre el registro y, a continuación, haga clic en **Finalizar**.
    
> [!TIP]
> Si necesita revisar los archivos de registro creados por el Skype para el Asistente para implementación de Business Server, puede encontrarlas en el equipo donde se ejecutó el Asistente para implementación en el directorio de usuarios de usuario de servicios de dominio de Active Directory que ejecutó el paso. Por ejemplo, si el usuario ha iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  


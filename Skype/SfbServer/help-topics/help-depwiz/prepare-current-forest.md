---
title: Preparar bosque actual
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Para preparar el bosque de servicios de dominio de Active Directory, correctamente debe extender el esquema, como se describe en el tema preparación del esquema de ejecución y asegúrese de que el esquema se ha replicado.
ms.openlocfilehash: 80218036b6eaee5abb0156ca6a13678f9b9f2238
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-current-forest"></a>Preparar bosque actual
 
Para preparar el bosque de servicios de dominio de Active Directory, correctamente debe extender el esquema, como se describe en el tema [Preparación del esquema de ejecución](http://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)y asegúrese de que el esquema se ha replicado.
  
Una vez completados los requisitos previos, puede empezar el **Paso 3: Preparar el bosque actual**. Para preparar el bosque, inicie sesión en un equipo de la raíz del bosque como miembro del grupo Admins. del dominio en la raíz del bosque, o bien como miembro del grupo Administradores de organización del bosque que se prepara.
  
1. En el Asistente para la implementación, en el **Paso 3: Preparar bosque actual**, haga clic en **Ejecutar**.
    
2. En la página **Preparar el bosque**, haga clic en **Siguiente**.
    
    > [!NOTE]
    > Preparación del bosque permite elegir dónde desea colocar los grupos universales para Skype para Business Server 2015. Elija una ubicación que respete los requisitos de su organización. 
  
3. En la página **Ejecución de comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**. Asegúrese de que no haya errores. Examine las advertencias para saber si son las previstas y son habituales en la infraestructura.
    
4. En la columna en el registro de **acción** , expanda **Preparar el bosque**, busque un ** \<éxito\> ** resultado de ejecución al final de cada tarea para comprobar que finalizó correctamente la preparación del bosque, cierre el registro y, a continuación, haga clic en **Finalizar **.
    
5. Espere a completar la replicación de los servicios de dominio de Active Directory o fuerce la replicación en todos los controladores de dominio enumerados en el complemento **servicios y sitios de Active Directory** para el controlador de dominio raíz de bosque, antes de ejecutar la preparación del dominio. Forzar la replicación entre los controladores de dominio en todos los sitios de Active Directory para hacer que la replicación dentro de los sitios que se produzcan en minutos.
    
    > [!TIP]
    > Si necesita revisar los archivos de registro creados por el Skype para el Asistente para implementación de Business Server, puede encontrarlas en el equipo donde se ejecuta el Asistente de implementación, en el directorio de usuarios de usuario de servicios de dominio de Active Directory que ejecutó el paso. Por ejemplo, si el usuario ha iniciado sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  


---
title: Preparar dominio actual
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Para preparar un dominio para hospedar servidores que ejecuten usuarios de Skype Empresarial Server 2015 o Skype Empresarial Server, debe completar el paso 5: Preparar dominio actual, tal como se describe en el tema Using Setup to Run Domain Preparation. Para completar el paso, debe haber iniciado sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo administradores de Enterprise del bosque al que pertenece el dominio. Para preparar el dominio:'
---

# <a name="prepare-current-domain"></a>Preparar dominio actual

Para preparar un dominio para hospedar servidores que ejecuten usuarios de Skype Empresarial Server 2015 o Skype Empresarial Server, debe completar el paso **5: Preparar** dominio actual, tal como se describe en el tema [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation). Para completar el paso, debe haber iniciado sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo administradores de Enterprise del bosque al que pertenece el dominio. Para preparar el dominio:

1. Desde la Skype Empresarial Server o medios de instalación de 2015, ejecute Setup.exe para iniciar el Asistente para Skype Empresarial Server implementación.

2. Haga clic en **Preparar Active Directory** y espere a que se determine el estado de implementación.

3. En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.

4. En la página **Ejecutando comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**.

5. En la **columna** Acción, expanda Preparación del **dominio, busque** un resultado de ejecución al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a **\<Success\>** continuación, haga clic en **Finalizar**.

> [!TIP]
> Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para implementación en el directorio Usuarios del usuario de Servicios de dominio de Active Directory que ejecutó el paso. Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp.
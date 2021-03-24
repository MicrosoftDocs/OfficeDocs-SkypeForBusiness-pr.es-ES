---
title: Preparar dominio actual
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para preparar un dominio para hospedar servidores que ejecutan usuarios de Skype Empresarial Server o Skype Empresarial Server, debe completar el paso 5: Preparar el dominio actual, tal como se describe en el tema Using Setup to Run Domain Preparation. Para completar el paso, debe haber iniciado sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de empresa del bosque al que pertenece el dominio. Para preparar el dominio:'
ms.openlocfilehash: a71e50b0f3d55709c3c22709177b41e541f7075f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097346"
---
# <a name="prepare-current-domain"></a>Preparar dominio actual

Para preparar un dominio para hospedar servidores que ejecutan usuarios de Skype Empresarial Server o Skype Empresarial Server, debe completar el paso **5: Preparar** dominio actual , tal como se describe en el tema [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation). Para completar el paso, debe haber iniciado sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de empresa del bosque al que pertenece el dominio. Para preparar el dominio:

1. Desde la carpeta o medios de instalación de Skype Empresarial Server, ejecute Setup.exe para iniciar el Asistente para la implementación de Skype Empresarial Server.

2. Haga clic en **Preparar Active Directory** y espere a que se determine el estado de implementación.

3. En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.

4. En la página **Ejecutando comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**.

5. En la **columna** Acción, expanda **Preparación** del dominio , busque un resultado de ejecución al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **\<Success\>** **Finalizar**.

> [!TIP]
> Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para implementación en el directorio Usuarios del usuario de Servicios de dominio de Active Directory que ejecutó el paso. Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp.
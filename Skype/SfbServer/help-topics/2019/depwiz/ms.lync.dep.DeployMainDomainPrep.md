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
description: 'Para preparar un dominio para hospedar servidores que ejecuten usuarios de Skype Empresarial Server o Skype Empresarial Server, debe completar el paso 5: Preparar el dominio actual, tal como se describe en el tema Using Setup to Run Domain Preparation. Para completar el paso, debe iniciar sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de organización del bosque al que pertenece el dominio. Para preparar el dominio:'
ms.openlocfilehash: d6e2efb774d7cad653c0a95e0e2863b97efe55ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824940"
---
# <a name="prepare-current-domain"></a>Preparar dominio actual

Para preparar un dominio para hospedar servidores que ejecuten usuarios de Skype Empresarial Server o Skype Empresarial Server, debe completar el paso **5:** Preparar el dominio actual, tal como se describe en el tema Using [Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Para completar el paso, debe iniciar sesión como miembro del grupo Administradores de dominio en el dominio que está preparando o como miembro del grupo Administradores de organización del bosque al que pertenece el dominio. Para preparar el dominio:

1. Desde la carpeta o los medios de instalación de Skype Empresarial Server, ejecute Setup.exe para iniciar el Asistente para la implementación de Skype Empresarial Server.

2. Haga clic en **Preparar Active Directory** y espere a que se determine el estado de implementación.

3. En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.

4. En la página **Ejecutando comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**.

5. En la **columna** Acción, expanda Preparación del dominio **,** busque un resultado de ejecución al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **\<Success\>** **Finalizar**.

> [!TIP]
> Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype Empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para la implementación en el directorio de usuarios del usuario de Servicios de dominio de Active Directory que realizó el paso. Por ejemplo, si el usuario inició sesión como administrador de dominio en el dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp.



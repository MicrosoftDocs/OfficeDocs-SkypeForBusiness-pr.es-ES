---
title: Preparar dominio actual
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Para preparar un dominio de modo que aloje servidores que ejecuten Skype empresarial Server 2015 o usuarios de Skype empresarial Server, debe completar el paso 5: preparar el dominio actual, como se describe en el tema usar el programa de instalación para ejecutar la preparación del dominio. Para completar este paso, debe haber iniciado sesión como miembro del grupo de administradores del dominio en el dominio que está preparando o como miembro del grupo administradores de empresa del bosque al que pertenece el dominio. Para preparar el dominio:'
ms.openlocfilehash: 58ff8ff515d171f7d0d1b0c2fb7d653e25c3ad31
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687413"
---
# <a name="prepare-current-domain"></a>Preparar dominio actual

Para preparar un dominio de modo que aloje servidores que ejecuten Skype empresarial Server 2015 o usuarios de Skype empresarial Server, debe completar el **paso 5: preparar el dominio actual**, como se describe en el tema [usar el programa de instalación para ejecutar la preparación del dominio](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Para completar este paso, debe haber iniciado sesión como miembro del grupo de administradores del dominio en el dominio que está preparando o como miembro del grupo administradores de empresa del bosque al que pertenece el dominio. Para preparar el dominio:

1. Desde la carpeta o los medios de instalación de Skype empresarial Server 2015, ejecute setup. exe para iniciar el Asistente para la implementación de Skype empresarial Server.

2. Haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.

3. En **Paso 5: Preparar dominio actual**, haga clic en **Ejecutar**.

4. En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.

5. En la columna **acción** , expanda **preparar el dominio**, busque un ** \<\> ** resultado de ejecución correcta al final de cada tarea para comprobar que la preparación del dominio se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.

> [!TIP]
> Si necesita revisar los archivos de registro creados por el Asistente para la implementación de Skype empresarial Server, puede encontrarlos en el equipo donde se ejecutó el Asistente para la implementación en el directorio de usuarios del usuario de los servicios de dominio de Active Directory que ejecutó el paso. Por ejemplo, si el usuario ha iniciado sesión como administrador del dominio Contoso.net, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp.



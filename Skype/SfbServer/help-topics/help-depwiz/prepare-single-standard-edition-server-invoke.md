---
title: Preparar un servidor único de Standard Edition (invocar)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: En la página comandos en ejecución, las tareas de instalación de SQL Server Express y la configuración para actuar como almacén de administración central se pueden ver en el panel de tareas. De forma predeterminada, se crea una instancia de una base de datos basada en SQL Server llamada RTC. También se crean reglas de Firewall para permitir el acceso entrante y saliente a los servidores y clientes para que se comuniquen con la base de datos y la instancia. Una vez completada la tarea, puede seleccionar el archivo de registro en la lista desplegable. El archivo de registro se denomina bootstrap local Machine. Después de seleccionar el archivo de registro, haga clic en Ver registro. Revise el archivo de registro en busca de errores y advertencias. Cuando esté listo para continuar, haga clic en finalizar. Ahora debe definir su topología con Topology Builder si todavía no lo ha hecho.
ms.openlocfilehash: 16cc6ada75ae90da4da2cb269aed26adbf472a33
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823444"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparar un servidor único de Standard Edition (invocar)
 
En la página **comandos en ejecución** , las tareas de instalación de SQL Server Express y la configuración para actuar como almacén de administración central se pueden ver en el panel de tareas. De forma predeterminada, se crea una instancia de una base de datos basada en SQL Server llamada RTC. También se crean reglas de Firewall para permitir el acceso entrante y saliente a los servidores y clientes para que se comuniquen con la base de datos y la instancia. Una vez completada la tarea, puede seleccionar el archivo de registro en la lista desplegable. El archivo de registro se denomina **bootstrap local Machine**. Después de seleccionar el archivo de registro, haga clic en **Ver registro**. Revise el archivo de registro en busca de errores y advertencias. Cuando esté listo para continuar, haga clic en **Finalizar.** Ahora debe definir su topología con Topology Builder si todavía no lo ha hecho.
  
> [!IMPORTANT]
> La instalación de SQL Server Express puede tardar algún tiempo en completarse. Durante la instalación, no se muestra ningún progreso en la pantalla o en el panel de tareas. Para supervisar la instalación, debe usar el administrador de tareas de Windows y buscar los procesos de MSIExec y los archivos de instalación de SQL Server. De esta manera, puede ver el estado de la instalación y asegurarse de que la instalación se está realizando. En función de los factores ajenos al ámbito de este tema de ayuda, puede demorar hasta 15 minutos o más para que se complete la instalación de la instancia de SQL Server. 
  


---
title: Preparar el servidor Standard Edition único (Invoke)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: En la página de comandos Executing, pueden verse las tareas de instalación de la versión de SQL Server Express y configuración para actuar como almacén de Administración Central en el panel de tareas. De forma predeterminada, se crea una instancia de una base de datos basada en SQL Server denominada RTC. También se crean las reglas de Firewall para permitir el acceso entrante y saliente para servidores y clientes para comunicarse con la base de datos y la instancia. Una vez completada la tarea, puede seleccionar el archivo de registro de la lista desplegable. El archivo de registro se denomina Bootstrap máquina local. Después de seleccionar el archivo de registro, haga clic en Ver registro. Revise el archivo de registro de los errores y advertencias. Cuando esté listo para continuar, haga clic en Finalizar. Ahora debe definir la topología con el generador de topología si aún no lo ha hecho.
ms.openlocfilehash: d900c383d0f434176ff18b3f310c41042df75b2e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparar el servidor Standard Edition único (Invoke)
 
En la página de **comandos de ejecución** , pueden verse las tareas de instalación de la versión de SQL Server Express y configuración para actuar como almacén de Administración Central en el panel de tareas. De forma predeterminada, se crea una instancia de una base de datos basada en SQL Server denominada RTC. También se crean las reglas de Firewall para permitir el acceso entrante y saliente para servidores y clientes para comunicarse con la base de datos y la instancia. Una vez completada la tarea, puede seleccionar el archivo de registro de la lista desplegable. El archivo de registro se denomina **Bootstrap máquina local**. Después de seleccionar el archivo de registro, haga clic en **Ver registro**. Revise el archivo de registro de los errores y advertencias. Cuando esté listo para continuar, haga clic en **Finalizar.** Ahora debe definir la topología con el generador de topología si aún no lo ha hecho.
  
> [!IMPORTANT]
> La instalación de SQL Server Express puede tardar algún tiempo en completarse. Durante la instalación, no hay ningún progreso visible en la pantalla o el panel de tareas. Para supervisar la instalación, debe utilizar el Administrador de tareas de Windows y busque los procesos de MSIExec y los archivos de instalación de SQL Server. De esta forma, puede ver el estado de la instalación y asegúrese de que la instalación se está realizando. Dependiendo de factores fuera del alcance de este tema de ayuda, puede tardar hasta 15 minutos o más para la instalación de la SQL Server instancia para completar. 
  


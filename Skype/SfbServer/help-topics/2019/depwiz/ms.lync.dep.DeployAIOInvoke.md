---
title: Preparar un servidor único de Standard Edition (invocar)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: En la página Ejecutar comandos, las tareas de instalación de SQL Server Express y configuración para que actúen como almacén de administración central se pueden ver en el panel de tareas. De forma predeterminada, se crea una instancia SQL Server base de datos basada en rtc. También se crean reglas de firewall para que los servidores y clientes tengan acceso de entrada y salida con el fin de comunicarse con la base de datos y la instancia. Cuando la tarea está finalizada, se puede seleccionar el archivo de registro en la lista desplegable. El archivo de registro se denomina Equipo local de arranque. Después de seleccionar el archivo de registro, haga clic en Ver registro. Compruebe si el archivo de registro contiene errores y advertencias. Cuando desee continuar, haga clic en Finalizar. Ahora debe definir la topología con el Generador de topologías si aún no lo ha hecho.
ms.openlocfilehash: c3e6e01f7aed0471d8f1eed0ad79f8ef6320f86a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820620"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparar un servidor único de Standard Edition (invocar)
 
En la **página Ejecución** de comandos, las tareas de instalación de SQL Server Express y configuración para que actúen como almacén de administración central se pueden ver en el panel de tareas. De forma predeterminada, se crea una instancia SQL Server base de datos basada en rtc. También se crean reglas de firewall para que los servidores y clientes tengan acceso de entrada y salida con el fin de comunicarse con la base de datos y la instancia. Cuando la tarea está finalizada, se puede seleccionar el archivo de registro en la lista desplegable. El archivo de registro se denomina **Equipo local de arranque**. Después de seleccionar el archivo de registro, haga clic en **Ver registro**. Compruebe si el archivo de registro contiene errores y advertencias. Cuando desee continuar, haga clic en **Finalizar**. Ahora debe definir la topología con el Generador de topologías si aún no lo ha hecho.
  
> [!IMPORTANT]
> La instalación de SQL Server Express puede tardar algún tiempo en completarse. Durante el proceso de instalación no aparece ninguna información sobre el progreso en la pantalla ni el panel de tareas. Para supervisar la instalación, debes usar el Administrador de tareas de Windows y buscar los procesos MSIExec y los archivos de instalación para SQL Server. De esta forma, puede comprobar el estado de la instalación y saber si el proceso continúa o no. Según los factores que no se den en este tema de ayuda, la instalación de la instancia de SQL Server puede tardar hasta 15 minutos o más en completarse. 
  


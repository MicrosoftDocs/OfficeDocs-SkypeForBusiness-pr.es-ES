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
description: En la página Ejecutar comandos, las tareas de instalación del SQL Server Express y la configuración para que actúen como el almacén de administración central se pueden ver en el panel de tareas. De forma predeterminada, se crea una instancia de una base de SQL Server base de datos basada en archivos denominada RTC. También se crean reglas de firewall para que los servidores y clientes tengan acceso de entrada y salida con el fin de comunicarse con la base de datos y la instancia. Cuando la tarea está finalizada, se puede seleccionar el archivo de registro en la lista desplegable. El archivo de registro se denomina Equipo local de arranque. Después de seleccionar el archivo de registro, haga clic en Ver registro. Compruebe si el archivo de registro contiene errores y advertencias. Cuando desee continuar, haga clic en Finalizar. Ahora debe definir la topología con el Generador de topologías si aún no lo ha hecho.
ms.openlocfilehash: b218fe92f46fb930dda7ffdc3c52dc986447ad7ef14f1f6ff93c70837e21aa3d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292148"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparar un servidor único de Standard Edition (invocar)
 
En la **página Ejecutar** comandos, las tareas de instalación del SQL Server Express y la configuración para que actúen como almacén de administración central se pueden ver en el panel de tareas. De forma predeterminada, se crea una instancia de una base de SQL Server base de datos basada en archivos denominada RTC. También se crean reglas de firewall para que los servidores y clientes tengan acceso de entrada y salida con el fin de comunicarse con la base de datos y la instancia. Cuando la tarea está finalizada, se puede seleccionar el archivo de registro en la lista desplegable. El archivo de registro se denomina **Equipo local de arranque**. Después de seleccionar el archivo de registro, haga clic en **Ver registro**. Compruebe si el archivo de registro contiene errores y advertencias. Cuando desee continuar, haga clic en **Finalizar**. Ahora debe definir la topología con el Generador de topologías si aún no lo ha hecho.
  
> [!IMPORTANT]
> La instalación del SQL Server Express puede tardar algún tiempo en completarse. Durante el proceso de instalación no aparece ninguna información sobre el progreso en la pantalla ni el panel de tareas. Para supervisar la instalación, debe usar Windows de tareas y buscar los procesos MSIExec y los archivos de instalación para SQL Server. De esta forma, puede comprobar el estado de la instalación y saber si el proceso continúa o no. Dependiendo de los factores que están fuera del ámbito de este tema de ayuda, la instalación de la instancia SQL Server puede tardar hasta 15 minutos en completarse. 
  


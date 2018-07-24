---
title: Preparar el servidor Standard Edition (invocar)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: En la página de comandos de ejecución, se pueden ver las tareas de instalación de SQL Server Express y configuración para actuar como el almacén de Administración Central en el panel de tareas. De forma predeterminada, se crea una instancia de una base de datos basada en SQL Server denominada RTC. También se crean las reglas de Firewall para permitir el acceso de entrada y salido para servidores y clientes para comunicarse con la base de datos y la instancia. Una vez finalizada la tarea, puede seleccionar el archivo de registro de la lista desplegable. El archivo de registro se denomina secuencia de inicio del equipo local. Después de seleccionar el archivo de registro, haga clic en Ver registro. Revise el archivo de registro para los errores y advertencias. Cuando esté listo para continuar, haga clic en Finalizar. Ahora debe definir la topología con Topology Builder si aún no lo ha hecho.
ms.openlocfilehash: 44fae0f1349b9252f207248fa99b714b0a8550ce
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987514"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>Preparar el servidor Standard Edition (invocar)
 
En la página **ejecutar comandos** , se pueden ver las tareas de instalación de SQL Server Express y configuración para actuar como el almacén de Administración Central en el panel de tareas. De forma predeterminada, se crea una instancia de una base de datos basada en SQL Server denominada RTC. También se crean las reglas de Firewall para permitir el acceso de entrada y salido para servidores y clientes para comunicarse con la base de datos y la instancia. Una vez finalizada la tarea, puede seleccionar el archivo de registro de la lista desplegable. El archivo de registro se denomina **secuencia de inicio del equipo local**. Después de seleccionar el archivo de registro, haga clic en **Ver registro**. Revise el archivo de registro para los errores y advertencias. Cuando esté listo para continuar, haga clic en **Finalizar.** Ahora debe definir la topología con Topology Builder si aún no lo ha hecho.
  
> [!IMPORTANT]
> La instalación de SQL Server Express puede tardar algún tiempo en completarse. Durante la instalación, no hay ningún progreso visible en la pantalla o el panel de tareas. Para supervisar la instalación, debe usar el Administrador de tareas de Windows y busque los procesos MSIExec y los archivos del programa de instalación para SQL Server. De este modo, puede ver el estado de la instalación y asegúrese de que se está realizando la instalación. Dependiendo de los factores más allá del alcance de este tema de ayuda, puede tardar hasta 15 minutos o más para la instalación del servidor SQL Server instancia para completar. 
  


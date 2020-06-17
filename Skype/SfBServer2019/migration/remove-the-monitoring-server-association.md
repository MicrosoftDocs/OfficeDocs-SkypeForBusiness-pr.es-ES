---
title: Quitar la asociación del servidor de supervisión
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Edite las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para eliminar la dependencia. Una vez que borre la dependencia y elimine el servidor en el generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en Topology Builder.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753422"
---
# <a name="remove-the-monitoring-server-association"></a>Quitar la asociación del servidor de supervisión

Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Edite las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para eliminar la dependencia. Una vez que borre la dependencia y elimine el servidor en el generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en Topology Builder.
  
### <a name="to-remove-the-monitoring-server-association"></a>Para quitar la asociación del Servidor de supervisión:

1. En el servidor front-end de Skype empresarial Server 2019, abra el generador de topologías.
    
2. Navegue hasta el nodo instalaciones heredadas.
    
3. En el generador de topologías, expanda grupos de servidores **front-end Enterprise Edition**, **servidores front-end Standard Edition**o **sitios de sucursal**, dependiendo de dónde se haya definido el servidor de supervisión.
    
4. Si tiene asociado un servidor de sucursal con funciones de supervivencia, expanda **sitios de sucursal**, expanda el nombre del sitio de sucursal y, a continuación, expanda aplicaciones de sucursal con funciones de **supervivencia**.
    
    > [!NOTE]
    > Las **aplicaciones de sucursal** con funciones de supervivencia de la interfaz de usuario se aplican a un servidor de sucursal con funciones de supervivencia y una aplicación de sucursal con funciones de supervivencia. 
  
5. Haga clic con el botón secundario en el grupo de servidores, servidor o dispositivo asociado con el servidor de supervisión y, a continuación, haga clic en **Editar propiedades**.
    
6. En **Editar propiedades**, en **General**  >  **asociaciones**generales, desactive la casilla **asociar servidor de supervisión** y, a continuación, haga clic en **Aceptar**.
    
7. Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de supervisión.
    
8. Haga clic con el botón secundario en el servidor de supervisión y haga clic en **eliminar**. 
    
9. En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.
    
10. Publique la topología, compruebe el estado de la replicación y ejecute el Asistente para la implementación de Skype empresarial Server según sea necesario. 
    


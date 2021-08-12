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
description: Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia del grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Puede editar las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el Generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en el Generador de topologías.
ms.openlocfilehash: 8e4c4b08c6126f6ac2c03d66e9ddcfe921b79850e704c54c65d6951c1449aa9f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280405"
---
# <a name="remove-the-monitoring-server-association"></a>Quitar la asociación del servidor de supervisión

Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia del grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Puede editar las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el Generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en el Generador de topologías.
  
### <a name="to-remove-the-monitoring-server-association"></a>Para quitar la asociación del Servidor de supervisión:

1. En el Skype Empresarial Server front-end de 2019, abra el Generador de topologías.
    
2. Vaya al nodo de instalación heredada.
    
3. En el Generador de topologías, expanda Enterprise Edition grupos de servidores **front-end**, Standard Edition **servidores front-end** o sitios **de** sucursal, en función de dónde se defina el servidor de supervisión.
    
4. Si tiene asociado el servidor de sucursal con funciones de supervivencia, expanda **Sitios** de sucursal, expanda el nombre del sitio de sucursal y, a continuación, expanda **Aplicaciones de sucursal con funciones de supervivencia.**
    
    > [!NOTE]
    > **Los dispositivos de sucursal con funciones** de supervivencia en la interfaz de usuario se aplican tanto al servidor de sucursal con funciones de supervivencia como a la aplicación de sucursal con funciones de supervivencia. 
  
5. Haga clic con el botón secundario en el grupo, servidor o dispositivo asociado al servidor de supervisión y, a continuación, haga clic **en Editar propiedades**.
    
6. En **Editar propiedades**, en Asociaciones **generales**, desactive la casilla Asociar servidor de supervisión  >  y, a continuación, haga clic en **Aceptar**. 
    
7. Repita el paso anterior para cualquier otro grupo, servidor o dispositivo asociado con el servidor de supervisión.
    
8. Haga clic con el botón secundario en el servidor de supervisión y, a continuación, haga clic **en Eliminar**. 
    
9. En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.
    
10. Publique la topología, compruebe el estado de replicación y ejecute el Asistente Skype Empresarial Server implementación según sea necesario. 
    


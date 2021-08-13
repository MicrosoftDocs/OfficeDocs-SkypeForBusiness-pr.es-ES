---
title: Quitar la asociación del servidor de archivado
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
description: Para quitar un servidor de archivado, debe cambiar o borrar la dependencia del grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Puede editar las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el Generador de topologías, se le notificará que también se eliminará el objeto de almacén de bases de datos asociado en el Generador de topologías.
ms.openlocfilehash: 6265642a45b891180e53d3b00d39a9053b663a434aaa1a4a26e92b619dfba257
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340336"
---
# <a name="remove-the-archiving-server-association"></a>Quitar la asociación del servidor de archivado

Para quitar un servidor de archivado, debe cambiar o borrar la dependencia del grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Puede editar las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el Generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en el Generador de topologías.
  
### <a name="to-remove-the-archiving-server-association"></a>Para quitar la asociación del servidor de archivado

1. En el servidor front-end de Skype Empresarial Server 2019, abra el Generador de topologías.
    
2. Vaya al nodo de instalación heredado.
    
3. En el Generador de topologías, expanda Grupos de servidores **front-end Enterprise Edition,** **Servidores front-end Standard Edition** o Sitios **de** sucursal, en función de dónde se defina el servidor de archivado.
    
4. Si tiene asociado el servidor de sucursal con funciones de supervivencia, expanda **Sitios** de sucursal, expanda el nombre del sitio de sucursal y, a continuación, expanda **Aplicaciones de sucursal con funciones de supervivencia.**
    
    > [!NOTE]
    > **Los dispositivos de sucursal con funciones** de supervivencia en la interfaz de usuario se aplican tanto al servidor de sucursal con funciones de supervivencia como a la aplicación de sucursal con funciones de supervivencia. 
  
5. Haga clic con el botón secundario en el grupo, servidor o dispositivo asociado al servidor de archivado y, a continuación, haga clic **en Editar propiedades**.
    
6. En **Editar propiedades**, en Asociaciones **generales,** desactive la casilla Asociar servidor de  >   **archivado** y, a continuación, haga clic en **Aceptar**.
    
7. Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de archivado que desee quitar.
    
8. Haga clic con el botón secundario en el servidor de archivado y, a continuación, haga clic **en Eliminar**.
    
9. En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.
    
10. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Skype Empresarial Server según sea necesario. 
    


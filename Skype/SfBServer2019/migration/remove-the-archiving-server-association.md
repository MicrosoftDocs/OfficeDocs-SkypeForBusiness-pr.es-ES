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
description: Para quitar un servidor de archivado, debe cambiar o borrar la dependencia del grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Puede editar las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el Generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en topology Builder.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752142"
---
# <a name="remove-the-archiving-server-association"></a>Quitar la asociación del servidor de archivado

Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Puede editar las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el Generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en topology Builder.
  
### <a name="to-remove-the-archiving-server-association"></a>Para quitar la asociación del servidor de archivado

1. En el servidor front-end de Skype Empresarial Server 2019, abra el Generador de topologías.
    
2. Navegue al nodo de instalación heredado.
    
3. En Topology Builder, expanda grupos de servidores **front-end Enterprise Edition,** servidores **front-end Standard Edition** o sitios de sucursal, en función de dónde esté definido el servidor de archivado. 
    
4. Si tiene asociado un servidor de sucursal con funciones de supervivencia, expanda **Sitios de** sucursal, expanda el nombre del sitio de sucursal y, a continuación, expanda Aplicaciones de sucursal con funciones **de supervivencia.**
    
    > [!NOTE]
    > **Las aplicaciones de sucursal con funciones** de supervivencia de la interfaz de usuario se aplican tanto al servidor de sucursal con funciones de supervivencia como a la aplicación de sucursal con funciones de supervivencia. 
  
5. Haga clic con el botón secundario en el grupo, servidor o dispositivo asociado con el servidor de archivado y, a continuación, haga clic **en Editar propiedades.**
    
6. En **Editar propiedades**, en Asociaciones **generales,** desactive la casilla Asociar servidor de archivado y, a continuación, haga clic en  >   **Aceptar.** 
    
7. Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de archivado que desee quitar.
    
8. Haga clic con el botón secundario en el servidor de archivado y, a continuación, haga clic **en Eliminar**.
    
9. En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.
    
10. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Skype Empresarial Server según sea necesario. 
    


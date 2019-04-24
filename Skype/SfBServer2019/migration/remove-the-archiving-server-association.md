---
title: Quitar la asociación del servidor de archivado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo de Front-End asociado, servidor Front-End, aplicación de sucursal con funciones de supervivencia y un servidor de sucursal con funciones de supervivencia. Para editar las propiedades del grupo de servidores Front-End, servidor Front-End, aplicación de sucursal con funciones de supervivencia y un servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de desactivar la dependencia y eliminar el servidor en el generador, que se le notifique que también se eliminará el objeto de almacén de base de datos asociada en el generador de topología.
ms.openlocfilehash: 15e6b33decb11ce7ed4550b0d84cc346a0baf073
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231418"
---
# <a name="remove-the-archiving-server-association"></a>Quitar la asociación del servidor de archivado

Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo de servidores, servidor Front-End, aplicación de sucursal con funciones de supervivencia y un servidor de sucursal con funciones de supervivencia de Front-End asociado. Editar las propiedades del grupo de servidores Front-End, servidor Front-End, aplicación de sucursal con funciones de supervivencia y un servidor de sucursal con funciones de supervivencia para quitar la dependencia. Después de desactivar la dependencia y eliminar el servidor en el generador, que se le notifique que también se eliminará el objeto de almacén de base de datos asociada en el generador de topología.
  
### <a name="to-remove-the-archiving-server-association"></a>Para quitar la asociación del servidor de archivado

1. En Skype para profesionales de 2019 Front-End Server, abra el generador de topología.
    
2. Navegue hasta el nodo instalar heredado.
    
3. En el generador de topologías, expanda **grupos de servidores Front-End de Enterprise Edition**, **Standard Edition servidor front-end**o **sitios de sucursal**, dependiendo de dónde se haya definido el servidor de archivado.
    
4. Si tiene un servidor de sucursal con funciones de supervivencia asociado, expanda **sitios de sucursal**, expanda el nombre del sitio de sucursal y, a continuación, expanda **Aplicaciones de sucursal con funciones de supervivencia**.
    
    > [!NOTE]
    > **Aplicaciones de sucursal con funciones de supervivencia** en la interfaz de usuario se aplica a un servidor de sucursal con funciones de supervivencia y aplicación de sucursal con funciones de supervivencia. 
  
5. Haga clic en el grupo de servidores, servidor o dispositivo que está asociada con el servidor de archivado y, a continuación, haga clic en **Editar propiedades**.
    
6. En **Editar propiedades**, en **General** > **asociaciones**, desactive la casilla de verificación de **Asociar el servidor de archivado** y, a continuación, haga clic en **Aceptar**.
    
7. Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de archivado que desea quitar.
    
8. Haga clic en el servidor de archivado y, a continuación, haga clic en **Eliminar**.
    
9. En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.
    
10. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Skype para el Asistente para la implementación de Business Server según sea necesario. 
    


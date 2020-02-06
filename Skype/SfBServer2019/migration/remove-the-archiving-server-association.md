---
title: Quitar la asociación del servidor de archivado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo frontal, el servidor front-end, el equipo de la sucursal y el servidor de la sucursal que siguen funcionando. Edite las propiedades del grupo de servidores front-end, el servidor front-end, el equipo de sucursales con la supervivencia y el servidor de sucursal con la supervivencia para quitar la dependencia. Después de borrar la dependencia y de eliminar el servidor en el generador de topología, se le notificará que el objeto de almacén de base de datos asociado en el generador de topología también se eliminará.
ms.openlocfilehash: 7b6e35131005866feed04a4e9b68c43558b6c1e1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812978"
---
# <a name="remove-the-archiving-server-association"></a>Quitar la asociación del servidor de archivado

Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo frontal de aplicaciones, el servidor front-end, el equipo de la sucursal que puede mantenerse y el servidor de sucursal con la supervivencia. Edite las propiedades del grupo de servidores front-end, el servidor front-end, el equipo de sucursales con la supervivencia y el servidor de sucursal con la supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el generador de topología, se le notificará que el objeto de almacén de base de datos asociado en el generador de topología también se eliminará.
  
### <a name="to-remove-the-archiving-server-association"></a>Para quitar la Asociación del servidor de archivado

1. En el servidor front-end de Skype empresarial Server 2019, abra Topology Builder.
    
2. Vaya al nodo instalación heredada.
    
3. En el generador de topología, expanda las **agrupaciones front end de Enterprise Edition**, **los servidores de aplicaciones para el usuario Standard Edition**o los **sitios de sucursales**, según dónde esté definido el servidor de archivado.
    
4. Si tiene asociado un servidor de sucursal, expanda **sitios de sucursales**, expanda el nombre del sitio de la sucursal y, a continuación, expanda **aplicaciones de sucursales**reutilizables.
    
    > [!NOTE]
    > Los **dispositivos** de la interfaz de usuario que son supervivientes se aplican a los servidores de sucursal con supervivencia y con la aplicación de rama superviviente. 
  
5. Haga clic con el botón secundario en el grupo, servidor o dispositivo asociado al servidor de archivado y, a continuación, haga clic en **Editar propiedades**.
    
6. En **propiedades de edición**, en**asociaciones** **generales** > , desactive la casilla **asociar servidor de archivado** y, a continuación, haga clic en **Aceptar**.
    
7. Repita el paso anterior para cualquier otro grupo, servidor o dispositivo asociado al servidor de archivado que desee quitar.
    
8. Haga clic con el botón secundario en el servidor de archivado y luego haga clic en **eliminar**.
    
9. En **eliminar almacenes dependientes**, haga clic en **Aceptar**.
    
10. Publique la topología, compruebe el estado de la replicación y, a continuación, ejecute el Asistente para la implementación de Skype empresarial Server según sea necesario. 
    


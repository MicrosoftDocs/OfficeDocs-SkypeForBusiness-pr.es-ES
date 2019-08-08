---
title: Quitar la asociación del servidor de supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo front-end, el servidor front-end, el equipo de la sucursal y el servidor de la sucursal supervivientes relacionados. Edite las propiedades del grupo de servidores front-end, el servidor front-end, el equipo de sucursales con la supervivencia y el servidor de sucursal con la supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el generador de topología, se le notificará que el objeto de almacén de base de datos asociado en el generador de topología también se eliminará.
ms.openlocfilehash: ecad0a447bacacf2a894bdb735b97b3a8593b1c8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244126"
---
# <a name="remove-the-monitoring-server-association"></a>Quitar la asociación del servidor de supervisión

Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo front-end, el servidor front-end, el dispositivo de la sucursal que puede ser superviviente y el servidor de sucursal con la supervivencia. Edite las propiedades del grupo de servidores front-end, el servidor front-end, el equipo de sucursales con la supervivencia y el servidor de sucursal con la supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el generador de topología, se le notificará que el objeto de almacén de base de datos asociado en el generador de topología también se eliminará.
  
### <a name="to-remove-the-monitoring-server-association"></a>Para quitar la Asociación de servidor de supervisión

1. En el servidor front-end de Skype empresarial Server 2019, abra Topology Builder.
    
2. Vaya al nodo instalaciones heredadas.
    
3. En el generador de topología, expanda las **agrupaciones front end de Enterprise Edition**, **los servidores de aplicaciones para el usuario Standard Edition**o los **sitios de sucursales**, según dónde se defina el servidor de supervisión.
    
4. Si tiene asociado un servidor de sucursal, expanda **sitios de sucursales**, expanda el nombre del sitio de la sucursal y, a continuación, expanda **aplicaciones de sucursales**reutilizables.
    
    > [!NOTE]
    > Los **dispositivos** de la interfaz de usuario que son supervivientes se aplican a los servidores de sucursal con supervivencia y con la aplicación de rama superviviente. 
  
5. Haga clic con el botón secundario en el grupo, servidor o dispositivo asociado al servidor de supervisión y, a continuación, haga clic en **Editar propiedades**.
    
6. En **Editar propiedades**, en **** > **asociaciones**generales, desactive la casilla **asociar servidor de supervisión** y, a continuación, haga clic en **Aceptar**.
    
7. Repita el paso anterior para cualquier otro grupo, servidor o dispositivo asociado al servidor de supervisión.
    
8. Haga clic con el botón secundario en el servidor de supervisión y luego haga clic en **eliminar**. 
    
9. En **eliminar almacenes**dependientes, haga clic en **Aceptar**.
    
10. Publique la topología, compruebe el estado de la replicación y ejecute el Asistente para la implementación de Skype empresarial Server según sea necesario. 
    


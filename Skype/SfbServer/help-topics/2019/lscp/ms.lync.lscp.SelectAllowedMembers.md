---
title: Seleccionar los miembros permitidos
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Creación y administración de salas de Chat persistente es mucho más sencillo con el uso correcto de las categorías. Un administrador de Chat persistente puede definir AllowedMembers y Creators para cada categoría y también se puede definir la configuración predeterminada de salón de chat y comportamientos que se aplicará a todos los salones de chat creados en la categoría. Los administradores de charla persistente crear y administrar las categorías mediante el panel de control o los cmdlets de Windows PowerShell.
ms.openlocfilehash: 3ced3c26147038cfaba23a8e532982fcf8810592
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="select-allowed-members"></a>Seleccionar los miembros permitidos
 
Creación y administración de salas de Chat persistente es mucho más sencillo con el uso correcto de las categorías. Un administrador de Chat persistente puede definir **AllowedMembers** y **Creators** para cada categoría y también se puede definir la configuración predeterminada de salón de chat y comportamientos que se aplicará a todos los salones de chat creados en la categoría. Los administradores de charla persistente crear y administrar las categorías mediante el panel de control o los cmdlets de Windows PowerShell.
  
Los usuarios, las unidades organizativas (UO) y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría. Después de crea la categoría, pueden elegir usuarios, unidades organizativas y grupos de usuarios de la lista de la categoría **AllowedMembers** como administradores de salones de chat y miembros para administrar y participar en el salón.
  
## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

En la página **Seleccionar los miembros permitidos** puede realizar las siguientes tareas:
  
- [Configuración de categorías](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [Nuevas características de servidor de Chat en grupo](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
Para obtener información detallada sobre los distintos procedimientos que puede realizar mediante el uso de la Skype para el Panel de Control de servidor empresarial, vea [Administrar Skype para Business Server 2015](../../manage/manage.md).
  
## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorías para salones de chat

En **pertenencia**, en la sección **miembros permitidos** , agregue o quite usuarios y otras entidades de seguridad de los servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas y así sucesivamente) que se permiten que se agregará como miembros de los salones de chat que pertenecen a la categoría. Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).
  
### 

Para obtener información detallada sobre las características de servidor de Chat persistente y funciones, consulte [Información general de Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación de planeación. Para obtener información detallada sobre cómo trabajar con las configuraciones de servidor de Chat persistente, consulte [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) en la documentación de implementación y [administración de Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) en la documentación sobre operaciones.
  
## <a name="see-also"></a>Vea también

#### 

[Descripción de la pertenencia de Chat en grupo](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)


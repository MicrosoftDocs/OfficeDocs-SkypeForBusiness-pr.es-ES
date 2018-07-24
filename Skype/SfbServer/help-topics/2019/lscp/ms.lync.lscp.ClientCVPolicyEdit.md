---
title: Directiva de versión de cliente crear nuevos o editar los existentes
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Puede especificar la versión de los clientes que se admiten en su entorno. Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.
ms.openlocfilehash: 4364594de0ef476a802ab127f20b120689dd56a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993806"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Directiva de versión de clientes: Crear nueva o editar existente
 
Puede especificar la versión de los clientes que se admiten en su entorno. Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para que el mayor uso de las características incluidas en Skype para Business Server y para mejorar la experiencia global del usuario, puede usar el filtro de versiones de cliente para restringir las versiones de cliente que se usan en su entorno. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costes asociados al uso de varias versiones de cliente.
  
> [!IMPORTANT]
> Los filtros se enumeran en orden de prioridad. Por ejemplo, si tiene un filtro que permite conectarse a los clientes que estén ejecutando la versión 1.5 o posterior, seguido de un filtro que bloquea los clientes que estén ejecutando una versión anterior a la 2.0, el primer filtro tiene prioridad y permitirá conectarse a los clientes que ejecuten la versión 1.5. 
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva directiva de versión de cliente** o **Editar directiva de versión de cliente** puede realizar las siguientes tareas:
  
- Agregar o modificar el nombre o la descripción de la directiva de versión de cliente.
    
- Agregar o modificar reglas de versión de cliente de la directiva de versión de cliente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito** Identifica el ámbito (sitio, grupo o usuario) de la directiva de versión de cliente.
    
- **Nombre** Puede agregar o modificar el nombre de la directiva de versión de cliente.
    
- **Descripción** Puede agregar una descripción para ayudar a identificar la directiva en la lista en la página Directiva de versión de cliente.
    
- **Nuevo** Puede agregar una nueva regla de versión de cliente a la directiva.
    
- **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una regla de versión del cliente.
    
- **Quitar** Esta opción quita la regla de la versión de cliente seleccionada de la directiva.
    
- **Flechas arriba y abajo** Esta opción mueve la regla de la versión de cliente seleccionada hacia arriba o hacia abajo en prioridad. Las reglas se procesan en el orden mostrado.
    
Para obtener información detallada acerca de la interoperabilidad entre clientes y versiones de cliente, vea [Interoperabilidad del cliente](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx). Para obtener información detallada sobre cómo trabajar con las directivas de versión de cliente, vea [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) en la documentación sobre operaciones.


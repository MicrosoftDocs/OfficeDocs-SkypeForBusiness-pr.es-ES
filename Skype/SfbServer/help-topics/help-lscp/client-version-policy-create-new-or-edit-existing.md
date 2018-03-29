---
title: Directiva de la versión de cliente crear nuevo o editar existente
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Puede especificar la versión de los clientes que se admiten en su entorno. Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para hacer el mayor uso de las características incluidas en Skype para Business Server 2015 y mejorar la experiencia global del usuario, puede utilizar el filtro de la versión de cliente para restringir las versiones de cliente que se utilizan en su entorno. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costes asociados al uso de varias versiones de cliente.
ms.openlocfilehash: 6c1e895dc03d094013f41a34cb21a12a24928172
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Directiva de versión de clientes: Crear nueva o editar existente
 
Puede especificar la versión de los clientes que se admiten en su entorno. Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para hacer el mayor uso de las características incluidas en Skype para Business Server 2015 y mejorar la experiencia global del usuario, puede utilizar el filtro de la versión de cliente para restringir las versiones de cliente que se utilizan en su entorno. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costes asociados al uso de varias versiones de cliente.
  
> [!IMPORTANT]
> Los filtros se enumeran en orden de prioridad. Por ejemplo, si tiene un filtro que permite conectarse a los clientes que estén ejecutando la versión 1.5 o posterior, seguido de un filtro que bloquea los clientes que estén ejecutando una versión anterior a la 2.0, el primer filtro tiene prioridad y permitirá conectarse a los clientes que ejecuten la versión 1.5. 
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva directiva de versión de cliente** o **Editar directiva de versión de cliente** puede realizar las siguientes tareas:
  
- Agregar o modificar el nombre o la descripción de la directiva de versión de cliente.
    
- Agregar o modificar reglas de versión de cliente de la directiva de versión de cliente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito de aplicación** Identifica el ámbito (sitio, grupo o usuario) de la directiva de versión del cliente.
    
- **Nombre** Puede agregar o modificar el nombre de la directiva de versión del cliente.
    
- **Descripción** Puede agregar una descripción para ayudar a identificar la directiva de la lista en la página Directiva de versión del cliente.
    
- **Nuevo** Puede agregar una nueva regla de versión del cliente a la directiva.
    
- **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una regla de la versión de cliente.
    
- **Quitar** Esta opción quita la regla de la versión de cliente seleccionado de la directiva.
    
- **Flechas arriba y abajo** Esta opción mueve la regla de la versión de cliente seleccionado hacia arriba o hacia abajo según la prioridad. Las reglas se procesan en el orden mostrado.
    
Para obtener más información acerca de la interoperabilidad entre los clientes y las versiones de cliente, vea [Interoperabilidad de cliente en la vista previa de 2013 Lync](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeamiento. Para obtener más información sobre cómo trabajar con directivas de la versión de cliente, vea [especificar las versiones de cliente compatible en su organización](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) en la documentación de las operaciones.


---
title: Directiva de versión del cliente crear o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Puede especificar la versión de los clientes que se admiten en su entorno. Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.
ms.openlocfilehash: 2a30a52ea69c1803b04313289310f223fd716b62
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794609"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Directiva de versión de clientes: Crear nueva o editar existente

Puede especificar la versión de los clientes que se admiten en su entorno. Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para aprovechar al máximo las características incluidas en Skype empresarial Server y mejorar la experiencia general del usuario, puede usar el filtro de versión del cliente para restringir las versiones de cliente que se usan en su entorno. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costes asociados al uso de varias versiones de cliente.

> [!IMPORTANT]
> Los filtros se enumeran en orden de prioridad. Por ejemplo, si tiene un filtro que permite conectarse a los clientes que estén ejecutando la versión 1.5 o posterior, seguido de un filtro que bloquea los clientes que estén ejecutando una versión anterior a la 2.0, el primer filtro tiene prioridad y permitirá conectarse a los clientes que ejecuten la versión 1.5.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva directiva de versión de cliente** o **Editar directiva de versión de cliente** puede realizar las siguientes tareas:

- Agregar o modificar el nombre o la descripción de la directiva de versión de cliente.

- Agregar o modificar reglas de versión de cliente de la directiva de versión de cliente.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.

- **Ámbito** Identifica el ámbito (sitio, grupo o usuario) de la Directiva de versión del cliente.

- **Nombre** Puede Agregar o modificar el nombre de la Directiva de versión de cliente.

- **Descripción** Puede Agregar una descripción para ayudarle a identificar la Directiva en la lista de la página de directiva de versión del cliente.

- **Nuevo** Puede Agregar una nueva regla de versión de cliente a la Directiva.

- **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una regla de versión de cliente.

- **Quitar** Esta opción quita la regla de versión de cliente seleccionada de la Directiva.

- **Flechas arriba y abajo** Esta opción mueve la regla de versión de cliente seleccionada hacia arriba o hacia abajo en prioridad. Las reglas se procesan en el orden mostrado.

Para obtener más información sobre la interoperabilidad entre los clientes y las versiones de cliente, consulte [interoperabilidad de cliente](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx). Para más detalles sobre cómo trabajar con las directivas de versión de cliente, mire [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) en la documentación de operaciones.


---
title: Directiva de versión de cliente Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Puede especificar la versión de clientes que se admiten en su entorno. Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.
ms.openlocfilehash: 57c273198a9c88ae26540518c9f892b218b96118
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100696"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Directiva de versiones de cliente: Crear nuevos o editar los existentes

Puede especificar la versión de clientes que se admiten en su entorno. Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para aprovechar al máximo las características incluidas en Skype Empresarial Server y mejorar la experiencia general del usuario, puede usar el filtro de versión de cliente para restringir las versiones de cliente que se usan en su entorno. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costos asociados al uso de varias versiones de cliente.

> [!IMPORTANT]
> Los filtros se enumeran en orden de prioridad. Por ejemplo, si tiene un filtro que permite conectarse a los clientes que estén ejecutando la versión 1.5, seguido de un filtro que bloquee a los clientes que estén ejecutando una versión anterior a la 2.0, el primer filtro tiene prioridad y se permitirá conectarse a los clientes que ejecuten la versión 1.5.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Nueva directiva de versión de cliente** o **Editar directiva de versión de cliente**:

- Agregar o modificar el nombre o la descripción de la directiva de versión de cliente.

- Agregar o modificar reglas de versión de cliente de la directiva de versión de cliente.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

- **Ámbito** Identifica el ámbito (Sitio, Grupo de servidores o Usuario) de la directiva de versión de cliente.

- **Nombre** Puede agregar o modificar el nombre de la directiva de versión de cliente.

- **Descripción** Puede agregar una descripción para ayudar a identificar la directiva en la lista de la página Directiva de versión de cliente.

- **Nuevo** Puede agregar una nueva regla de versión de cliente a la directiva.

- **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de una regla de versión de cliente.

- **Quitar** Esta opción quita la regla de versión de cliente seleccionada de la directiva.

- **Flechas arriba y abajo** Esta opción mueve la regla de versión de cliente seleccionada hacia arriba o hacia abajo en prioridad. Las reglas se procesan en el orden mostrado.

Para obtener más información sobre la interoperabilidad entre clientes y versiones de cliente, vea [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013). Para obtener detalles sobre cómo trabajar con las directivas de versión de cliente, vea [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) en la documentación de operaciones.
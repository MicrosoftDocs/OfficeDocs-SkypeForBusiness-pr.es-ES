---
title: Configuración de la versión de cliente crear nueva o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente. La configuración de la versión de cliente global se instala con Skype empresarial Server y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versiones de cliente.
ms.openlocfilehash: 3ead41348d6a9010187f968140ce4c1146a42db0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823103"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configuración de versiones de cliente: Crear nueva o editar existente

Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente. La configuración de la versión de cliente global se instala con Skype empresarial Server y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versiones de cliente.

También puede crear configuraciones de versión de cliente específicas del sitio, lo que le permite habilitar o deshabilitar el control de versiones de cliente por sitio. Las configuraciones específicas del sitio prevalecen sobre la configuración Global.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:

- Agregar o modificar el nombre de la configuración de versión de cliente.

- Habilitar o deshabilitar el control de versiones de cliente de forma global o para el sitio específico.

- Agregar o modificar la acción predeterminada para la configuración de versión de cliente.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.

- **Ámbito** Identifica el ámbito (global o de sitio) de la configuración de versión del cliente.

- **Nombre** Puede Agregar o modificar el nombre de la configuración de la versión del cliente.

- **Habilitar el control de versiones** Puede habilitar o deshabilitar el control de versiones de cliente globalmente o para el sitio, según el ámbito de la configuración.

- **Acción predeterminada** Puede seleccionar la acción predeterminada que se aplicará cuando un usuario intente iniciar sesión con una aplicación cliente para la que no haya ninguna directiva de versión de cliente específica. Tiene las siguientes opciones:

  - **Permitir** Permite al cliente iniciar sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión del cliente.

  - **Bloquear** Impide que el cliente inicie sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión del cliente.

  - **Bloque con dirección URL** Impide que el cliente inicie sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión del cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.

  - **Permitir con URL** Permite al cliente iniciar sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión del cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.

  - **Dirección URL** Si ha seleccionado **bloquear con URL** o **permitir con URL**, puede especificar la dirección URL de descarga del cliente que se incluirá en el mensaje de error.

Para más detalles sobre la interoperabilidad entre clientes y versiones de clientes, mire [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación. Para más detalles sobre cómo trabajar con configuraciones de versiones de clientes, mire [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de operaciones.


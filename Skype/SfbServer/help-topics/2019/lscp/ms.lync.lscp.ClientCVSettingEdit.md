---
title: Configuración de versión de cliente Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versión de cliente. La configuración de versión de cliente global se instala con Skype Empresarial Server y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versión de cliente.
ms.openlocfilehash: 1f50cff75f4b5dd0d7be0d091e0379bc845f099bff25cd2d5e8eacdee657686c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324439"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configuración de versiones de cliente: Crear nuevos o editar los existentes

Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versión de cliente. La configuración de versión de cliente global se instala con Skype Empresarial Server y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versión de cliente.

También puede crear configuraciones de versión de cliente específicas del sitio, lo que le permite habilitar o deshabilitar el control de versión de cliente por sitio. Las configuraciones específicas del sitio prevalecen sobre la configuración Global.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente**:

- Agregar o modificar el nombre de la configuración de versión de cliente.

- Habilitar o deshabilitar el control de versión de cliente de forma global o para el sitio específico.

- Agregar o modificar la acción predeterminada para la configuración de versión de cliente.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

- **Ámbito** Identifica el ámbito (Global o Site) de la configuración de versión de cliente.

- **Nombre** Puede agregar o modificar el nombre de la configuración de la versión de cliente.

- **Habilitar control de versiones** Puede habilitar o deshabilitar el control de versiones de cliente globalmente o para el sitio, según el ámbito de la configuración.

- **Acción predeterminada** Puede seleccionar la acción predeterminada que se aplicará cuando un usuario intente iniciar sesión con una aplicación cliente para la que no hay ninguna directiva de versión de cliente específica. Tiene las siguientes opciones:

  - **Permitir** Permite al cliente iniciar sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión de cliente.

  - **Bloquear** Impide que el cliente inicia sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión de cliente.

  - **Bloquear con dirección URL** Impide que el cliente inicia sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión de cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.

  - **Permitir con dirección URL** Permite al cliente iniciar sesión si la versión del cliente no coincide con ningún filtro de la lista de directivas de versión de cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.

  - **DIRECCIÓN URL** Si seleccionó **Bloquear con dirección URL** o Permitir con dirección **URL,** puede especificar la dirección URL de descarga del cliente para incluirla en el mensaje de error.

Para obtener más información sobre la interoperabilidad entre clientes y versiones de cliente, consulte [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) en la documentación sobre planeación. Para obtener detalles sobre cómo trabajar con configuraciones de versiones de clientes, vea [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) en la documentación de operaciones.
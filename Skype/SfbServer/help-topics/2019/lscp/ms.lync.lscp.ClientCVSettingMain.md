---
title: Configuración de versiones de cliente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: Además de especificar la versión de los clientes que desea admitir en su entorno, también puede especificar una acción predeterminada para clientes que todavía no tengan definida una directiva de versión. Esto permite restringir las versiones de cliente que se usan en su entorno, lo que puede ayudar a controlar los costes asociados con la compatibilidad con distintas versiones de cliente.
ms.openlocfilehash: 57720ae070f8051febc53b0287d6aa9d87985257
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387198"
---
# <a name="client-version-configuration"></a>Configuración de versiones de cliente

Además de especificar la versión de los clientes que desea admitir en su entorno, también puede especificar una acción predeterminada para clientes que todavía no tengan definida una directiva de versión. Esto permite restringir las versiones de cliente que se usan en su entorno, lo que puede ayudar a controlar los costes asociados con la compatibilidad con distintas versiones de cliente.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Configuración de versión de cliente**:

- Edite la **configuración de versión** de cliente predeterminada (global).

- Crear configuraciones de versión de cliente para un sitio concreto.

- Habilitar y deshabilitar configuraciones de versión de cliente existentes.

> [!NOTE]
> Debido a que los usuarios anónimos no están asociados a un sitio, los usuarios solo se ven afectados por directivas de nivel global.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

- **Nuevo** Puede crear una configuración de versión de cliente para un sitio determinado.

- **Editar** Puede cambiar las opciones de cualquiera de las directivas de versión de cliente. Al usar esta opción, puede hacer lo siguiente:

  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de una configuración de versión de cliente.

  - **Seleccionar todo** Esta opción selecciona todas las configuraciones de versión de cliente de la lista.

  - **Eliminar** Esta opción elimina todas las configuraciones de versión de cliente seleccionadas.

- **Actualizar** Puede actualizar la lista de configuración de versión de cliente para comprobar el estado de las opciones de todas las configuraciones de versión de cliente.

Para obtener más información sobre la interoperabilidad entre clientes y versiones de cliente, consulte [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) en la documentación sobre planeación. Para obtener detalles sobre cómo trabajar con configuraciones de versiones de clientes, vea [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) en la documentación de operaciones.
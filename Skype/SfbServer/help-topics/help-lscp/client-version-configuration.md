---
title: Configuración de versiones de cliente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: Además de especificar la versión de los clientes que desea admitir en su entorno, también puede especificar una acción predeterminada para clientes que todavía no tengan definida una directiva de versión. Esto permite restringir las versiones de cliente que se usan en su entorno, lo que puede ayudar a controlar los costes asociados con la compatibilidad con distintas versiones de cliente.
ms.openlocfilehash: 453ef8b518d7b39f4cd13d4c265dbcab9ea6d95d2ccca3b82bdd8656803a1d20
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277105"
---
# <a name="client-version-configuration"></a>Configuración de versiones de cliente

Además de especificar la versión de los clientes que desea admitir en su entorno, también puede especificar una acción predeterminada para clientes que todavía no tengan definida una directiva de versión. Esto permite restringir las versiones de cliente que se usan en su entorno, lo que puede ayudar a controlar los costes asociados con la compatibilidad con distintas versiones de cliente.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Configuración de versión de cliente**:

- Edite la configuración de versión de cliente predeterminada ( **Global**).

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

Para obtener detalles sobre la interoperabilidad entre clientes y versiones de clientes, vea [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) en la documentación de planeación. Para obtener detalles sobre cómo trabajar con configuraciones de versiones de clientes, vea [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) en la documentación de operaciones.
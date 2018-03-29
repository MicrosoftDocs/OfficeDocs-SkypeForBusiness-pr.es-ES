---
title: Configuración de la versión de cliente crear nuevo o editar existente
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente. La configuración de la versión de cliente Global se instala con Skype para Business Server y se utiliza para habilitar o deshabilitar el control de versiones de cliente para la implementación de todo el servidor. Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versiones de cliente.
ms.openlocfilehash: 19c7cda4924148c6129e3fc3847c2770c51708d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configuración de versiones de cliente: Crear nueva o editar existente
 
Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente. La configuración de la versión de cliente Global se instala con Skype para Business Server y se utiliza para habilitar o deshabilitar el control de versiones de cliente para la implementación de todo el servidor. Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente Global si no desea que se produzca ningún control de versiones de cliente. 
  
También puede crear configuraciones de versión de cliente específicas del sitio, lo que le permite habilitar o deshabilitar el control de versiones de cliente por sitio. Las configuraciones específicas del sitio prevalecen sobre la configuración Global.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En las páginas **Nueva configuración de versión de cliente** o **Editar configuración de versión de cliente** puede realizar las siguientes tareas:
  
- Agregar o modificar el nombre de la configuración de versión de cliente.
    
- Habilitar o deshabilitar el control de versiones de cliente de forma global o para el sitio específico.
    
- Agregar o modificar la acción predeterminada para la configuración de versión de cliente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito de aplicación** Identifica el ámbito (Global o sitio) de la configuración de la versión de cliente.
    
- **Nombre** Puede agregar o modificar el nombre de la configuración de la versión de cliente.
    
- **Habilitar control de versiones** Puede habilitar o deshabilitar el control de versiones de cliente globalmente o para el sitio, según el ámbito de la configuración.
    
- **Acción predeterminada** Puede seleccionar la acción predeterminada que se aplicará cuando un usuario intenta iniciar sesión utilizando una aplicación de cliente para el que no hay ninguna directiva de versión de cliente específico. Tiene las siguientes opciones:
    
  - **Permitir** Permite al cliente iniciar sesión si la versión del cliente no coincide con ningún filtro en la lista de directivas de la versión de cliente.
    
  - **Bloque** Impide que el cliente iniciar sesión si la versión del cliente no coincide con ningún filtro en la lista de directivas de la versión de cliente.
    
  - **Bloque con dirección URL** Impide que el cliente iniciar sesión si la versión del cliente no coincide con ningún filtro en la lista de directivas de la versión de cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.
    
  - **Permitir con dirección URL** Permite al cliente iniciar sesión si la versión del cliente no coincide con ningún filtro en la lista de directivas de la versión de cliente e incluye un mensaje de error que contiene una dirección URL donde se puede descargar un cliente más reciente.
    
  - **Dirección URL** Si ha seleccionado **Bloquear con la dirección URL** o **Permitir con dirección URL**, puede especificar la URL de descarga del cliente para incluir en el mensaje de error.
    
Para obtener más información acerca de la interoperabilidad entre los clientes y las versiones de cliente, vea [Interoperabilidad de cliente en la vista previa de 2013 Lync](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeamiento. Para obtener más información sobre cómo trabajar con las configuraciones de versión de cliente, vea [modificar la acción predeterminada para clientes no admitidas explícitamente o restringido](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de las operaciones.


---
title: Directiva de ubicación
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Las directivas de ubicación determinan si 9-1-1 (E9-1-1) mejorado está habilitado y cómo se usa, así como el modo en que la información de ubicación de usa para usuarios y contactos.
ms.openlocfilehash: cb0f4562acd4904a2fb473b4d828090ce4a653f98090905e7bd9a2b54e240f50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319253"
---
# <a name="location-policy"></a>Directiva de ubicación

Las directivas de ubicación determinan si 9-1-1 (E9-1-1) mejorado está habilitado y cómo se usa, así como el modo en que la información de ubicación de usa para usuarios y contactos.

Las directivas de ubicación incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:

- **Directiva global:** La directiva global se crea de forma predeterminada. Puede editar la directiva global, pero no puede eliminarla. Si intenta eliminarla, toda la configuración se restablecerá a los valores predeterminados.

- **Directivas de sitio (opcional):** Puede crear una o varias directivas de ubicación de sitio, cada una de las cuales se aplica a un sitio específico. Las directivas de sitio anulan la directiva global.

- **Directivas de usuario (opcional):** Puede crear una o varias directivas de ubicación de usuario, cada una de las cuales se aplica a un usuario o grupo de usuarios específicos. Las directivas de usuario anulan la directiva global y las directivas de sitio.

> [!NOTE]
> También puede asignar directivas de ubicación a sitios de red, que son grupos de subredes. Las directivas de ubicación asignadas a los sitios de red prevalecen sobre las demás directivas de usuario. Para obtener más información sobre cómo asignar directivas de ubicación a sitios de red mediante cmdlets, vea Agregar una directiva de ubicación a un sitio de red [en Skype Empresarial Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Para obtener más información sobre Skype Empresarial Server panel de control para asignar una directiva de ubicación a un sitio de red, vea [Configuring Network Sites](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites).

La página **Directiva de ubicación** muestra una lista de todas las directivas de ubicación definidas para su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas desde la página **Directiva de ubicación**:

- Crear una nueva directiva de ubicación de sitio o de ubicación de usuario

- Cambiar la directiva global o una directiva de sitio o de usuario existente

- Eliminar una directiva de sitio o de usuario

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia una nueva directiva de ubicación del sitio o una directiva de ubicación de usuario.

- **Editar** Abre la directiva de ubicación seleccionada para editarla, selecciona todas las directivas de ubicación de la lista o elimina la directiva de sitio o la directiva de usuario seleccionada.

    > [!NOTE]
    > Para la directiva global, **Eliminar** restablece la configuración a los valores predeterminados.

- **Actualizar** Actualiza la lista de directivas de ubicación.

En la siguiente lista se describen los campos de la página.

- **Nombre** Identifica la directiva de ubicación.

- **Ámbito** Identifica el ámbito de la directiva de ubicación: global, de sitio o de usuario.

- **E9-1-1** Se comprueba si los usuarios asignados a esta directiva de ubicación están habilitados para E9-1-1.

- **Ubicación** Especifica si se pide a los usuarios que escriban información de ubicación cuando su cliente se registra con Skype Empresarial Server en una nueva ubicación y si ven un aviso de declinación de responsabilidades si descartan la solicitud sin especificar la información de ubicación.

- **Uso de RTC** Especifica el uso de la red telefónica conmutada (RTC) que se usa para determinar la ruta de voz usada para enrutar llamadas de emergencia de clientes que usan este perfil.

- **Número E9-1-1** Especifica el número que se marca para llegar a los servicios de emergencia.

- **Máscara E9-1-1** Especifica un número que marca un usuario que, a continuación, se convierte en el número de marcado de emergencia.

Para obtener más información Telefonía IP empresarial características y funcionalidades del servicio de emergencia, vea [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) en la documentación sobre planeación. Para obtener detalles sobre cómo trabajar con directivas de ubicación, vea [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) en la documentación de operaciones.
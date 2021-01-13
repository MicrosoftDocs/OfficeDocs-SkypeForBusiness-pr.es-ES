---
title: Directiva de ubicación
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Las directivas de ubicación determinan si 9-1-1 (E9-1-1) mejorado está habilitado y cómo se usa, así como el modo en que la información de ubicación de usa para usuarios y contactos.
ms.openlocfilehash: bb7a63e63864b3d342d37fd62b26f806434644b7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824790"
---
# <a name="location-policy"></a>Directiva de ubicación

Las directivas de ubicación determinan si 9-1-1 (E9-1-1) mejorado está habilitado y cómo se usa, así como el modo en que la información de ubicación de usa para usuarios y contactos.

Las directivas de ubicación incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:

- **Directiva global:** La directiva global se crea de forma predeterminada. Puede editar la directiva global, pero no puede eliminarla. Si intenta eliminarla, toda la configuración se restablecerá a los valores predeterminados.

- **Directivas de sitio (opcional):** Puede crear una o más directivas de ubicación de sitios, cada una de las cuales se aplica a un sitio específico. Las directivas de sitio anulan la directiva global.

- **Directivas de usuario (opcional):** Puede crear una o más directivas de ubicación de usuario, cada una de las cuales se aplica a un usuario o grupo de usuarios específicos. Las directivas de usuario anulan la directiva global y las directivas de sitio.

> [!NOTE]
> También puede asignar directivas de ubicación a sitios de red, que son grupos de subredes. Las directivas de ubicación asignadas a los sitios de red prevalecen sobre las demás directivas de usuario. Para obtener más información sobre cómo asignar directivas de ubicación a sitios de red mediante cmdlets, vea Agregar una directiva de ubicación a un sitio de red [en Skype Empresarial Server.](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md) Para obtener más información sobre cómo usar el Panel de control de Skype Empresarial Server para asignar una directiva de ubicación a un sitio de red, consulte [Configuración de sitios de red.](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)

La página **Directiva de ubicación** muestra una lista de todas las directivas de ubicación definidas para su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas desde la página **Directiva de ubicación**:

- Crear una nueva directiva de ubicación de sitio o de ubicación de usuario

- Cambiar la directiva global o una directiva de sitio o de usuario existente

- Eliminar una directiva de sitio o de usuario

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia una nueva directiva de ubicación de sitio o de ubicación de usuario.

- **Editar** Abre la directiva de ubicación seleccionada para editarla, selecciona todas las directivas de ubicación de la lista o elimina la directiva de sitio o de usuario seleccionada.

    > [!NOTE]
    > Para la directiva global, **Eliminar** restablece la configuración a los valores predeterminados.

- **Actualizar** Actualiza la lista de directivas de ubicación.

En la siguiente lista se describen los campos de la página.

- **Nombre** Identifica la directiva de ubicación.

- **Ámbito** Identifica el ámbito de la directiva de ubicación: global, de sitio o de usuario.

- **E9-1-1** Se comprueba si los usuarios asignados a esta directiva de ubicación están habilitados para E9-1-1.

- **Ubicación** Especifica si se pide a los usuarios que escriban información de ubicación cuando su cliente se registra con Skype Empresarial Server en una nueva ubicación y si ven un aviso de declinación de responsabilidades si descartan la solicitud sin especificar la información de ubicación.

- **Uso de RTC** Especifica el uso de la red telefónica conmutada (RTC) que se usa para determinar la ruta de voz usada para enrutar las llamadas de emergencia de los clientes que usan este perfil.

- **Número E9-1-1** Especifica el número que se marca para llegar a los servicios de emergencia.

- **Máscara E9-1-1** Especifica un número que marca un usuario que, a continuación, se traduce en el número de marcado de emergencia.

Para obtener más información Telefonía IP empresarial características y capacidades del servicio de emergencia, consulte Información general de [E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) en la documentación sobre planeación. Para obtener detalles sobre cómo trabajar con directivas de ubicación, vea [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) en la documentación de operaciones.



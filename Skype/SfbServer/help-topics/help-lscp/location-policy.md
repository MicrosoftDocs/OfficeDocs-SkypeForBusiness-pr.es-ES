---
title: Directiva de ubicación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.
ms.openlocfilehash: cb28dd60793da6681f2a8db71cf40ce8a5eda6fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293476"
---
# <a name="location-policy"></a>Directiva de ubicación

Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.

Las directivas de ubicación incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:

- **Directiva global:** La directiva global se crea de forma predeterminada. Puede editar la directiva global, pero no puede eliminarla. Si intenta quitar la directiva global, todos los valores de configuración se restablecen a los valores predeterminados.

- **Directivas de sitio (opcional):** Puede crear una o más directivas de ubicación de sitios, cada una de las cuales se aplica a un sitio específico. Las directivas de sitio invalidan la directiva global.

- **Directivas de usuario (opcional):** Puede crear una o varias directivas de ubicación de usuario, cada una de las cuales se aplica a un usuario específico o a un grupo de usuarios. Las directivas de usuario invalidan la directiva global y las directivas del sitio.

> [!NOTE]
> También puede asignar directivas de ubicación a sitios de red, que son grupos de subredes. Las directivas de ubicación asignadas a los sitios de red prevalecen sobre las demás directivas de usuario. Para más información sobre cómo asignar directivas de ubicación a sitios de red con cmdlets, consulte [Agregar una directiva de ubicación a un sitio de red en Skype empresarial Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Para obtener detalles sobre el uso del panel de control de Skype empresarial Server para asignar una directiva de ubicación a un sitio de red, consulte [configuración de sitios de red](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

La página **Directiva de ubicación** muestra una lista de todas las directivas de ubicación definidas en la organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Directiva de ubicación** puede realizar las siguientes tareas:

- Crear una directiva de ubicación de sitio o de ubicación de usuario

- Cambiar la directiva global o una directiva de sitio o de usuario existente

- Eliminar una directiva de sitio o de usuario

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia una nueva Directiva de ubicación del sitio o una directiva de ubicación de usuario.

- **Editar** Abre la Directiva de ubicación seleccionada para editarla, selecciona todas las directivas de ubicación de la lista o elimina la Directiva de sitio o la Directiva de usuario seleccionada.

    > [!NOTE]
    > En el caso de la directiva global, con **Eliminar** se restablece la configuración a los valores predeterminados.

- **Actualizar** Actualiza la lista de directivas de ubicación.

En la siguiente lista se describen los campos de la página.

- **Nombre** Identifica la Directiva de ubicación.

- **Ámbito** Identifica el ámbito de la Directiva de Ubicación: global, de sitio o de usuario.

- **E9-1-1** Activado si los usuarios que tienen asignada esta directiva de ubicación están habilitados para E9-1-1.

- **Ubicación** Especifica si se pide a los usuarios que escriban información de ubicación cuando su cliente se registre con Skype empresarial Server en una nueva ubicación y si verán un aviso de declinación de responsabilidades si descartan la pregunta sin especificar la información de ubicación.

- **Uso de RTC** Especifica el uso de la red de telefonía pública conmutada (RTC) que se usa para determinar la ruta de voz usada para enrutar llamadas de emergencia de clientes que usan este perfil.

- **E9-1-1 número** Especifica el número que se marca para alcanzar los servicios de emergencia.

- **Máscara E9-1-1** Especifica un número que un usuario marca y, a continuación, se convierte en el número de marcado de emergencia.

Para obtener más información sobre las características y capacidades del servicio de emergencia de Enterprise Voice, consulte [información general sobre E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) en la documentación de planificación. For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.



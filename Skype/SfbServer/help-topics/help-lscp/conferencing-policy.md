---
title: Directiva de conferencia
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
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: La directiva de conferencias define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada "reunión")
ms.openlocfilehash: 6d69c463a9aa8a1e151b0787dfbfebf4e24fb693
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115370"
---
# <a name="conferencing-policy"></a>Directiva de conferencias

La directiva de conferencias define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada "reunión")

Las directivas de conferencia incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:

- **Directiva global:** La directiva global se crea de forma predeterminada. Puede editar la directiva global, pero no puede eliminarla. Si intenta eliminarla, toda la configuración se restablecerá a los valores predeterminados.

- **Directivas de sitio (opcional):** Puede crear una o varias directivas de conferencia de sitio, cada una de las cuales se aplica a un sitio específico. Las directivas de sitio anulan la directiva global.

- **Directivas de usuario (opcional):** Puede crear una o varias directivas de conferencia de usuario, cada una de las cuales se aplica a un usuario o grupo de usuarios específicos. Las directivas de usuario anulan la directiva global y las directivas de sitio.

La página **Directiva de conferencia** muestra una lista de todas las directivas de conferencia definidas para su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas desde la página **Directiva de ubicación**:

- Crear una nueva directiva de conferencia de sitio o de conferencia de usuario

- Cambiar la directiva global o una directiva de sitio o de usuario existente

- Eliminar una directiva de sitio o de usuario

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia una nueva directiva de conferencia de sitio o una directiva de conferencia de usuario.

- **Editar** Abre la directiva de conferencia seleccionada para editarla, selecciona todas las directivas de conferencia de la lista o elimina la directiva de sitio o la directiva de usuario seleccionada.

    > [!NOTE]
    > Para la directiva global, **Eliminar** restablece la configuración a los valores predeterminados.

- **Actualizar** Actualiza la lista de directivas de conferencia.

En la siguiente lista se describen los campos de la página.

- **Nombre** Identifica la directiva de conferencia.

- **Ámbito** Identifica el ámbito de la directiva de conferencia: global, de sitio o de usuario.

- **Colaboración de datos** Se comprueba si la directiva de conferencia especifica que la colaboración de datos está permitida en las conferencias.

- **Uso compartido de aplicaciones** Se comprueba si la directiva de conferencia especifica que se permite el uso compartido de aplicaciones en conferencias.

- **Audio** Se comprueba si la directiva de conferencia especifica que el audio está permitido en las conferencias.

- **Vídeo** Se comprueba si la directiva de conferencia especifica que el vídeo está permitido en conferencias.

- **RTC** Se comprueba si la directiva de conferencia especifica que se permite la conferencia de acceso telefónico local RTC.

- **Grabación** Se comprueba si la directiva de conferencia especifica que se permite la grabación en conferencias.

Para obtener detalles sobre las características y capacidades de la conferencia, vea [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) en la documentación de planeación. Para obtener detalles sobre cómo trabajar con directivas de conferencias, vea [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) en la documentación de operaciones.
---
title: Directiva de conferencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: La Directiva de conferencia define las características y capacidades que los usuarios tienen disponibles durante una conferencia (también conocido como reunión).
ms.openlocfilehash: 6649471efd9d8d592de1e9395fd6eba8eadb9e23
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700425"
---
# <a name="conferencing-policy"></a>Directiva de conferencia

La Directiva de conferencia define las características y capacidades que los usuarios tienen disponibles durante una conferencia (también conocido como reunión).

Las directivas de Conferencia incluyen la directiva global y, opcionalmente, una o varias directivas de sitio y usuario:

- **Directiva global:** La directiva global se crea de forma predeterminada. Puede editar la directiva global, pero no puede eliminarla. Si intenta quitar la directiva global, todos los valores de configuración se restablecen a los valores predeterminados.

- **Directivas de sitio (opcional):** Puede crear una o más directivas de conferencia de sitios, cada una de las cuales se aplica a un sitio específico. Las directivas de sitio invalidan la directiva global.

- **Directivas de usuario (opcional):** Puede crear una o más directivas de conferencia de usuario, cada una de las cuales se aplica a un usuario específico o a un grupo de usuarios. Las directivas de usuario invalidan la directiva global y las directivas del sitio.

En la página **Directiva de conferencia** se muestra una lista de todas las directivas de conferencia definidas para su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Directiva de ubicación** puede realizar las siguientes tareas:

- Crear una nueva Directiva de conferencia de sitio o una directiva de conferencia de usuario

- Cambiar la directiva global o una directiva de sitio o de usuario existente

- Eliminar una directiva de sitio o de usuario

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia una nueva Directiva de conferencia de sitio o una directiva de conferencia de usuario.

- **Editar** Abre la Directiva de conferencia seleccionada para modificarla, selecciona todas las directivas de conferencia de la lista o elimina la Directiva del sitio o la Directiva de usuario seleccionada.

    > [!NOTE]
    > En el caso de la directiva global, con **Eliminar** se restablece la configuración a los valores predeterminados.

- **Actualizar** Actualiza la lista de directivas de conferencia.

En la siguiente lista se describen los campos de la página.

- **Nombre** Identifica la Directiva de conferencia.

- **Ámbito** Identifica el ámbito de la Directiva de Conferencia: global, de sitio o de usuario.

- **Colaboración de datos** Se activa si la Directiva de conferencia especifica que se permite la colaboración de datos en conferencias.

- **Uso compartido de aplicaciones** Se activa si la Directiva de conferencia especifica que se permite el uso compartido de aplicaciones en conferencias.

- **Audio** Se activa si la Directiva de conferencia especifica que se permite el audio en las conferencias.

- **Vídeo** Se activa si la Directiva de conferencia especifica que se permite el vídeo en las conferencias.

- **RTC** Se activa si la Directiva de conferencia especifica que se permiten las conferencias de acceso telefónico local RTC.

- **Grabación** Se activa si la Directiva de conferencia especifica que la grabación está permitida en las conferencias.

Para más detalles sobre las características y capacidades de la conferencia, mire [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) en la documentación de planeación. Para más detalles sobre cómo trabajar con directivas de conferencias, mire [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) en la documentación de operaciones.



---
title: Configuración de reuniones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Opciones de configuración que definen el tipo de conferencias (también calledmeetings) que los usuarios pueden crear y controlar cómo (o si) los usuarios anónimos y los usuarios de conferencia de acceso telefónico pueden unirse a estas conferencias. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: 5381394d106c19091e6f8c29582358b60aa36912
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911019"
---
# <a name="meeting-configuration"></a>Configuración de reuniones

Las opciones de configuración de reuniones ayudan a definir el tipo de conferencias (también denominadas "reuniones") que los usuarios pueden crear, además de controlar cómo (o si) pueden participar en las conferencias usuarios anónimos o de conferencias de acceso telefónico. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción Reunirse ahora en el cliente.

Las configuraciones de reuniones se aplican en el nivel global, de sitio o de grupo:

- **Configuración de reunión global:** La configuración de reunión global se crea de forma predeterminada. Puede editar la configuración de reunión global, pero no puede eliminar. Si se intenta quitar la configuración de reunión global, se restablecen todas las opciones a los valores predeterminados.

- **Configuración de reunión de sitio (opcional):** Puede crear uno o más sitios configuraciones de reunión, cada uno de los cuales se aplica a un sitio específico. Configuraciones de sitios invalidar la configuración global.

- **Configuración de reunión de grupo de servidores (opcional):** Puede crear uno o más grupo de configuraciones de reunión, cada uno de los cuales se aplica a un grupo de servidores específico. Las configuraciones de grupo de servidores invalidar la configuración global y configuraciones de sitio.

La página **Configuración de reunión** muestra una lista de todas las configuraciones de reuniones definidas en su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Configuración de reunión** puede realizar las siguientes tareas:

- Crear una configuración de reunión de sitio o de reunión de grupo

- Cambiar la configuración global o una configuración de sitio o de grupo existente

- Eliminar una configuración de sitio o de grupo

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia una nueva configuración de reunión de sitio o configuración de reunión de grupo de servidores.

- **Editar** Se abre la configuración de reunión seleccionada para editarla, selecciona todas las configuraciones de reunión en la lista o elimina la configuración de sitio seleccionado o grupo.

    > [!NOTE]
    > En el caso de la configuración de reunión global, con **Eliminar** se restablece la configuración a los valores predeterminados.

- **Actualizar** Actualiza la lista de configuraciones de reunión.

En la siguiente lista se describen los campos de la página.

- **Nombre** Identifica la configuración de reunión.

- **Ámbito** Identifica el ámbito de la configuración de reunión: global, sitio o grupo de servidores.

Para más detalles sobre cómo trabajar con configuraciones de reunión, mire [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) en la documentación de operaciones.



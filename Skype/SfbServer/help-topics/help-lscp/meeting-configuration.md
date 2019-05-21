---
title: Configuración de reuniones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: La configuración de la reunión define el tipo de conferencias (también calledmeetings) que los usuarios pueden crear y controlar cómo (o si) los usuarios anónimos y las conferencias de acceso telefónico local pueden unirse a estas conferencias. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: 82619b255f99dc5a82d6a9cb704fe5443fe83d23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293427"
---
# <a name="meeting-configuration"></a>Configuración de reuniones

Las opciones de configuración de reuniones ayudan a definir el tipo de conferencias (también denominadas "reuniones") que los usuarios pueden crear, además de controlar cómo (o si) pueden participar en las conferencias usuarios anónimos o de conferencias de acceso telefónico. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción Reunirse ahora en el cliente.

Las configuraciones de reuniones se aplican en el nivel global, de sitio o de grupo:

- **Configuración de la reunión global:** De forma predeterminada, se crea la configuración de la reunión global. Puede editar la configuración global de la reunión, pero no puede eliminarla. Si intenta quitar la configuración de la reunión global, todos los valores de configuración se restablecerán en los valores predeterminados.

- **Configuración de la reunión de sitios (opcional):** Puede crear una o más configuraciones de reunión de sitio, cada una de las cuales se aplica a un sitio específico. Las configuraciones de sitio invalidan la configuración global.

- **Configuración de reunión de grupo (opcional):** Puede crear una o más configuraciones de reunión de grupo, cada una de las cuales se aplica a un grupo específico. Las configuraciones de grupo invalidan la configuración global y las configuraciones de sitios.

La página **Configuración de reunión** muestra una lista de todas las configuraciones de reuniones definidas en su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Configuración de reunión** puede realizar las siguientes tareas:

- Crear una configuración de reunión de sitio o de reunión de grupo

- Cambiar la configuración global o una configuración de sitio o de grupo existente

- Eliminar una configuración de sitio o de grupo

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia una nueva configuración de reunión de sitio o configuración de reunión de grupo.

- **Editar** Abre la configuración de la reunión seleccionada para modificarla, selecciona todas las configuraciones de la reunión de la lista o elimina la configuración del sitio o de la agrupación seleccionada.

    > [!NOTE]
    > En el caso de la configuración de reunión global, con **Eliminar** se restablece la configuración a los valores predeterminados.

- **Actualizar** Actualiza la lista de configuraciones de reunión.

En la siguiente lista se describen los campos de la página.

- **Nombre** Identifica la configuración de la reunión.

- **Ámbito** Identifica el ámbito de la configuración de la reunión: global, sitio o grupo.

Para más detalles sobre cómo trabajar con configuraciones de reunión, mire [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) en la documentación de operaciones.



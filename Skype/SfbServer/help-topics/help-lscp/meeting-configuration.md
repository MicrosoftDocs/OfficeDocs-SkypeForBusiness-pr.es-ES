---
title: Configuración de reuniones
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
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Las opciones de configuración de reunión definen el tipo de conferencias (también denominadasmeetings) que los usuarios pueden crear y controlan cómo (o si) los usuarios anónimos y los usuarios de conferencias de acceso telefónico local pueden unirse a estas conferencias. Estas opciones solo se aplican a reuniones programadas. No se aplican a reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: e53297aaae7707f8cc0ae4821a97afb78e0382e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099666"
---
# <a name="meeting-configuration"></a>Configuración de reuniones

Las opciones de configuración de reuniones ayudan a definir el tipo de conferencias (también denominadas "reuniones") que pueden crear los usuarios, además de controlar cómo (o si) pueden participar en las conferencias usuarios anónimos o de conferencias de acceso telefónico. Estas opciones solo se aplican a reuniones programadas. No se aplican a reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en el cliente.

Las configuraciones de reuniones se aplican en el nivel global, de sitio o de grupo:

- **Configuración global de la reunión:** La configuración de reunión global se crea de forma predeterminada. Puede editar la directiva global, pero no puede eliminarla. Si intenta quitar la configuración de reunión global, toda la configuración se restablecerá a los valores predeterminados.

- **Configuración de reunión de sitio (opcional):** Puede crear una o varias configuraciones de reuniones de sitio, cada una de las cuales se aplica a un sitio específico. Las configuraciones de sitio anulan la configuración global.

- **Configuración de reunión de grupo (opcional):** Puede crear una o más configuraciones de reunión de grupo, cada una de las cuales se aplica a un grupo específico. Las configuraciones de grupo anulan la configuración global.

La página **Configuración de reunión** muestra una lista de todas las configuraciones de reuniones definidas para su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas desde la página **Configuración de reunión**:

- Crear una nueva configuración de reunión de sitio o de reunión de grupo

- Cambiar la configuración global o una configuración de sitio o de grupo existente

- Eliminar una configuración de sitio o de grupo

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia una nueva configuración de reunión de sitio o una configuración de reunión de grupo.

- **Editar** Abre la configuración de reunión seleccionada para editarla, selecciona todas las configuraciones de reunión de la lista o elimina la configuración del sitio o el grupo de servidores seleccionados.

    > [!NOTE]
    > Para la configuración de reunión global, **Eliminar** restablece la configuración a los valores predeterminados.

- **Actualizar** Actualiza la lista de configuraciones de reunión.

En la siguiente lista se describen los campos de la página.

- **Nombre** Identifica la configuración de la reunión.

- **Ámbito** Identifica el ámbito de la configuración de la reunión: global, de sitio o de grupo.

Para obtener detalles sobre cómo trabajar con configuraciones de reunión, vea [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) en la documentación de operaciones.
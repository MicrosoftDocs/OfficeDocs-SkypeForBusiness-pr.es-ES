---
title: Configuración de reunión Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Los ajustes de configuración de reunión definen la experiencia de unión de los usuarios a conferencias programadas por usuarios. Estas opciones solo se aplican a reuniones programadas. No se aplican a reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: 4038f4175849481c43d2d8a9fc0849f44f0530906c3702580a892cd0edb17871
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326496"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuración de reuniones: Crear nuevos o editar los existentes

Los ajustes de configuración de reunión definen la experiencia de unión de los usuarios a conferencias programadas por usuarios. Estas opciones solo se aplican a reuniones programadas. No se aplican a reuniones ad hoc creadas haciendo clic en la opción **Reunirse ahora** en el cliente.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Ámbito** Identifica el ámbito de la configuración de reunión que está creando o modificando: global, de sitio o de grupo.

- **Nombre** Las configuraciones de reunión se denominan de forma predeterminada y no se puede cambiar el nombre.

- **Los autores de llamadas RTC omiten la sala de espera** Active esta casilla para admitir automáticamente a los usuarios que están iniciando sesión en la conferencia a través de una línea telefónica de red telefónica conmutada (RTC). Desactive esta casilla para enrutar a los autores de llamadas RTC a la sala de espera, donde se mantienen hasta que un moderador de conferencia les concede acceso a la conferencia.

- **Designar como moderador** Seleccione la categoría de usuarios (además del organizador de la reunión) que se designan automáticamente como presentadores cuando se unen a una conferencia. Independientemente de esta configuración, los moderadores pueden designarse de forma explícita como moderadores cuando se programa la reunión, o se les puede designar como moderadores durante la conferencia. Las opciones son:

  - **Ninguno** Seleccione esta opción si nadie que no sea el organizador se designa automáticamente como moderador.

  - **Empresa** Seleccione esta opción para designar automáticamente solo los miembros de la organización como presentadores.

  - **Todos** Seleccione esta opción para designar automáticamente a cualquiera para que sea moderador.

- **Tipo de conferencia asignado de forma predeterminada** Esta configuración controla si Outlook Conferencing Addin siempre programa conferencias mediante la conferencia asignada del organizador, lo que significa que las conferencias programadas siempre tienen la misma dirección URL de unión y la misma información de audio. Active esta casilla para que las conferencias programadas siempre usen la misma dirección URL. Desactívela para usar una dirección URL distinta para cada conferencia.

- **Admitir usuarios anónimos de forma predeterminada** Active esta casilla si los usuarios anónimos (es decir, no autenticados) pueden asistir a conferencias de forma predeterminada. Desactívela si los usuarios anónimos no pueden asistir a conferencias de forma predeterminada.

- **URL del logotipo** Escriba la dirección URL que tiene la imagen que se usará para las invitaciones de conferencia personalizadas.

- **Url de ayuda** Escriba la dirección URL de un sitio web donde los usuarios puedan obtener ayuda para unirse a la conferencia.

- **Dirección URL de texto legal** Escriba la dirección URL de un sitio web que tenga la información legal y los avisos de declinación de responsabilidades para la conferencia.

- **Texto de pie de página personalizado** Escriba el texto que se usará en invitaciones de conferencia personalizadas.

Para obtener detalles sobre cómo trabajar con configuraciones de reuniones, vea [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) en la documentación de operaciones. Para obtener detalles sobre cómo configurar configuraciones de reuniones para reuniones grandes, vea [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) en la documentación de planeación.
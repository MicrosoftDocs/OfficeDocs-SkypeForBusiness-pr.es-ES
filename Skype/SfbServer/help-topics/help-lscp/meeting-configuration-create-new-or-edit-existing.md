---
title: Configuración de la reunión crear nueva o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Las opciones de configuración de reuniones definen la experiencia de unión de los usuarios a conferencias programadas. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: baf8912e90d68dc175e6cd278cc7a13eff82ae33
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293462"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuración de reuniones: Crear nueva o editar existente

Las opciones de configuración de reuniones definen la experiencia de unión de los usuarios a conferencias programadas. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción **Reunirse ahora** en el cliente.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Ámbito** Identifica el ámbito de la configuración de la reunión que está creando o modificando: global, sitio o grupo.

- **Nombre** Las configuraciones de reunión se denominan de forma predeterminada y el nombre no se puede cambiar.

- Los **autores de llamadas RTC omiten el vestíbulo** Seleccione esta casilla para admitir automáticamente a los usuarios que llaman a la Conferencia a través de una línea de teléfono de red telefónica conmutada (RTC). Desactive esta casilla para enrutar a los autores de llamadas RTC a la sala de espera, donde se mantienen hasta que un moderador de conferencia les concede acceso a la conferencia.

- **Designar como moderador** Seleccione la categoría de usuarios (además del organizador de la reunión) que se designan automáticamente como moderadores cuando se unen a una conferencia. Independientemente de esta configuración, los moderadores pueden designarse de forma explícita como tales cuando se programa la reunión, o bien se les puede designar como moderadores durante la conferencia. Las opciones son:

  - **Ninguna** Seleccione esta opción si nadie más que el organizador se designa automáticamente como moderador.

  - **Empresa** Seleccione esta opción para designar automáticamente solo los miembros de su organización como moderadores.

  - **Todos los usuarios** Seleccione esta opción para designar de forma automática a cualquier persona como moderador.

- **Tipo de conferencia asignado de forma predeterminada** Esta configuración controla si el complemento de conferencia de Outlook siempre programa conferencias mediante la Conferencia asignada al organizador, lo que significa que las conferencias programadas siempre tienen la misma dirección URL de la combinación y la información de audio. Active esta casilla para que las conferencias programadas usen siempre la misma dirección URL. Desactívela para usar una dirección URL distinta en cada conferencia.

- **Admitir usuarios anónimos de forma predeterminada** Active esta casilla si los usuarios anónimos (es decir, no autenticados) pueden asistir a conferencias de forma predeterminada. Desactívela si los usuarios anónimos no pueden asistir a conferencias de forma predeterminada.

- **Dirección URL del logotipo** Escriba la dirección URL que tiene la imagen que se va a usar para las invitaciones de conferencia personalizadas.

- **Dirección URL de ayuda** Escriba la dirección URL de un sitio web donde los usuarios pueden obtener ayuda para unirse a la Conferencia.

- **Dirección URL de texto legal** Escriba la dirección URL de un sitio web que tiene la información legal y las renuncias para la Conferencia.

- **Texto de pie de página personalizado** Escriba el texto que se va a usar en las invitaciones a Conferencia personalizadas.

Para más detalles sobre cómo trabajar con configuraciones de reuniones, mire [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) en la documentación de operaciones. Para más detalles sobre cómo establecer configuraciones de reuniones para reuniones grandes, mire [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) en la documentación de planeación.



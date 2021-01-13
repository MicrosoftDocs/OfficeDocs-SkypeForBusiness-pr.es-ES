---
title: Configuración de reunión Crear nueva o editar existente
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
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Los ajustes de configuración de reunión definen la experiencia de unión de los usuarios a conferencias programadas por usuarios. Estas opciones solo se aplican a reuniones programadas. No se aplican a reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: dc37e3d76a81a09fe2cbd2407f4d3a2dff3d703e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803940"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuración de reuniones: Crear nuevos o editar los existentes

Los ajustes de configuración de reunión definen la experiencia de unión de los usuarios a conferencias programadas por usuarios. Estas opciones solo se aplican a reuniones programadas. No se aplican a reuniones ad hoc creadas haciendo clic en la opción **Reunirse** ahora en el cliente.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Ámbito** Identifica el ámbito de la configuración de reunión que está creando o modificando: global, de sitio o de grupo.

- **Nombre** Las configuraciones de reuniones tienen un nombre predeterminado y no se puede cambiar el nombre.

- **Los autores de llamadas RTC omiten la sala de espera** Active esta casilla para admitir automáticamente a los usuarios que llamen a la conferencia a través de una línea telefónica de red telefónica conmutada (RTC). Desactive esta casilla para enrutar a los autores de llamadas RTC a la sala de espera, donde se mantienen hasta que un moderador de conferencia les concede acceso a la conferencia.

- **Designar como moderador** Seleccione la categoría de usuarios (además del organizador de la reunión) que se designan automáticamente como presentadores cuando se unen a una conferencia. Independientemente de esta configuración, los moderadores pueden designarse de forma explícita como moderadores cuando se programa la reunión, o se les puede designar como moderadores durante la conferencia. Las opciones son:

  - **Ninguno** Seleccione esta opción si nadie más que el organizador se designa automáticamente como moderador.

  - **Compañía** Seleccione esta opción para designar automáticamente solo a los miembros de la organización como presentadores.

  - **Todos** Seleccione esta opción para designar automáticamente a cualquiera como moderador.

- **Tipo de conferencia asignado de forma predeterminada** Esta configuración controla si el Complemento de conferencias de Outlook siempre programa conferencias mediante la conferencia asignada por el organizador, lo que significa que las conferencias programadas siempre tienen la misma dirección URL de unión e información de audio. Active esta casilla para que las conferencias programadas siempre usen la misma dirección URL. Desactívela para usar una dirección URL distinta para cada conferencia.

- **Admitir usuarios anónimos de forma predeterminada** Active esta casilla si los usuarios anónimos (es decir, no autenticados) pueden asistir a conferencias de forma predeterminada. Desactívela si los usuarios anónimos no pueden asistir a conferencias de forma predeterminada.

- **Dirección URL del logotipo** Escriba la dirección URL que tiene la imagen que se usará para las invitaciones de conferencia personalizadas.

- **Dirección URL de ayuda** Escriba la dirección URL de un sitio web donde los usuarios puedan obtener ayuda para unirse a la conferencia.

- **Dirección URL de texto legal** Escriba la dirección URL de un sitio web que tenga la información legal y los avisos de declinación de responsabilidades de la conferencia.

- **Texto de pie de página personalizado** Escriba el texto que se usará en invitaciones de conferencia personalizadas.

Para obtener detalles sobre cómo trabajar con configuraciones de reunión, vea [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) en la documentación de operaciones. Para obtener detalles sobre cómo configurar configuraciones de reuniones para reuniones grandes, vea [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) en la documentación de planeación.



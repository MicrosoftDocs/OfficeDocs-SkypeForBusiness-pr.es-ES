---
title: Configuración de reunión crear nuevos o editar los existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Las opciones de configuración de reuniones definen la experiencia de unión de los usuarios a conferencias programadas. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: e67381ff779b7ef410e1a9accc9dc2e7791c2e43
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244205"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuración de reuniones: Crear nueva o editar existente

Las opciones de configuración de reuniones definen la experiencia de unión de los usuarios a conferencias programadas. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción **Reunirse ahora** en el cliente.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Ámbito** Identifica el ámbito de la configuración de reunión que está creando o modificando: global, sitio o grupo de servidores.

- **Nombre** Las configuraciones de reunión se denominan de forma predeterminada y no se puede cambiar el nombre.

- **Sala de espera el desvío de los autores de llamadas de RTC** Active esta casilla de verificación para admitir automáticamente a los usuarios que se llaman a la conferencia a través de una línea de teléfono telefónica conmutada (RTC). Desactive esta casilla para enrutar a los autores de llamadas RTC a la sala de espera, donde se mantienen hasta que un moderador de conferencia les concede acceso a la conferencia.

- **Designar como moderador** Seleccione la categoría de usuarios (que no sea el organizador de la reunión), que automáticamente se designan como moderadores cuando se unan a una conferencia. Independientemente de esta configuración, los moderadores pueden designarse de forma explícita como tales cuando se programa la reunión, o bien se les puede designar como moderadores durante la conferencia. Las opciones son:

  - **Ninguno** Seleccione esta opción si nadie más que el organizador se designa automáticamente como moderador.

  - **Compañía** Seleccione esta opción para designar automáticamente sólo los miembros de la organización como moderadores.

  - **Todos los usuarios** Seleccione esta opción para designar automáticamente a cualquiera como presentador.

- **Tipo de conferencia asignado de forma predeterminada** Esta configuración controla si el complemento de conferencia de Outlook siempre programa las conferencias mediante el uso del organizador de la conferencia de asignado, lo que significa que programa conferencias siempre tiene la misma dirección URL de combinación y la información de audio. Active esta casilla para que las conferencias programadas usen siempre la misma dirección URL. Desactívela para usar una dirección URL distinta en cada conferencia.

- **Admitir usuarios anónimos de forma predeterminada** Active esta casilla de verificación si anónimos (es decir, no autenticado) los usuarios pueden asistir a las conferencias de forma predeterminada. Desactívela si los usuarios anónimos no pueden asistir a conferencias de forma predeterminada.

- **Dirección URL del logotipo** Escriba la dirección URL que tiene la imagen que se usará para las invitaciones a conferencias personalizadas.

- **Dirección URL de ayuda** Escriba la dirección URL de un sitio Web donde los usuarios pueden obtener asistencia para unirse a la conferencia.

- **Dirección URL del texto legal** Escriba la dirección URL de un sitio Web que contenga información legal y declinación de responsabilidades de la conferencia.

- **Texto de pie de página personalizado** Escriba el texto que se utilizará en las invitaciones a conferencias personalizadas.

Para obtener información detallada sobre cómo trabajar con configuraciones de reunión, vea [crear un o modificar una colección de opciones de configuración que](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) en la documentación sobre operaciones. Para obtener información detallada acerca de cómo establecer configuraciones de reunión para reuniones grandes, consulte [Configuración de seguridad de compatibilidad para reuniones grandes](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) en la documentación de planeación.



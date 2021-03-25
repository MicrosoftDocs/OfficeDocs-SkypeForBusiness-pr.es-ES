---
title: Directiva de conferencia Crear nueva o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: Una directiva de conferencia define las características y capacidades que los usuarios tienen disponibles durante una conferencia (también conocida como reunión).
ms.openlocfilehash: 0599411cd8e0832b1d5d09fc2f8ac6bc676d931d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118899"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Directiva de conferencia: Crear nuevos o editar los existentes

Una directiva de conferencia define las características y capacidades que los usuarios tienen disponibles durante una conferencia (también conocida como reunión).

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Ámbito** Identifica el ámbito de la directiva de conferencia que está creando o modificando: global, de sitio o de usuario.

- **Nombre** Cada directiva de conferencia requiere un nombre. Las directivas de conferencia global y de sitio tienen un nombre predeterminado que no puede cambiarse. Para las directivas de conferencia de usuarios, use un nombre descriptivo que identifique al usuario o al grupo de usuarios.

    > [!NOTE]
    > Una vez guardada la directiva de conferencia, el nombre no se puede cambiar.

- **Descripción** Este campo es opcional. Úselo para proporcionar detalles sobre la directiva de conferencia.

- **Directiva de organizador** La configuración de esta sección se aplica al usuario que organiza una conferencia. Si se selecciona una configuración, el usuario puede organizar una conferencia que tenga la característica especificada. Si no se selecciona ninguna configuración, el usuario no puede organizar una conferencia con esta característica. Estas configuraciones no determinan a lo que el usuario tiene acceso como participante en otras conferencias.

    Haga clic en la flecha arriba o abajo junto a la etiqueta para cerrar o abrir la sección.

- **Tamaño máximo de reunión** el número máximo de usuarios permitidos en una conferencia. De forma predeterminada, el tamaño máximo de conferencia es 250.

- **Permitir que los participantes inviten a usuarios anónimos** Active esta casilla para permitir que los usuarios inviten a usuarios anónimos a conferencias. Los usuarios anónimos son usuarios que no tienen credenciales en los Servicios de dominio de Active Directory de la organización y que, por lo tanto, no están autenticados.

- **Grabación** Especifique si los participantes pueden grabar conferencias. Las opciones son **Ninguno** o **Habilitar grabación**.

- **Permitir que los participantes federados y anónimos registren** Active esta casilla para permitir que los participantes externos y no autenticados graben conferencias.

- **Audio y vídeo** Especifique si los participantes pueden usar audio y vídeo:

  - **Ninguno** Seleccione esta opción para evitar el uso de audio y vídeo.

  - **Habilitar audio IP** Seleccione esta opción para permitir el uso de audio, pero no de vídeo.

  - **Habilitar audio/vídeo IP** Seleccione esta opción para permitir audio y vídeo.

- **Habilitar conferencias de** acceso telefónico local RTC Si ha habilitado el audio en **audio y vídeo,** active esta casilla para permitir que los usuarios puedan llamar a conferencias mediante la red telefónica conmutada (RTC).

- **Permitir que los participantes anónimos marquen hacia fuera** Active esta casilla si permite a los usuarios llamar a conferencias y desea permitir que los usuarios no autenticados (anónimos) se unan a una conferencia mediante la llamada de salida. Mediante las llamadas de salida, el servidor de conferencia llama al usuario y el usuario responde al teléfono para unirse a la conferencia.

- **Permitir que los participantes no habilitados para Telefonía IP empresarial llamar** Si habilitó audio en **Audio/vídeo,** active esta casilla para permitir que los usuarios que no están habilitados para Telefonía IP empresarial unirse a una conferencia mediante la llamada de acceso telefónico. Al realizar la marcación, el servidor de conferencia llama al usuario y el usuario responde al teléfono para unirse a la conferencia.

- **Permitir varias secuencias de vídeo** Si habilitó el vídeo en **Audio/vídeo,** active esta casilla para permitir a los usuarios organizar conferencias con vídeo de vista de galería. Si esta casilla está activada, los usuarios pueden organizar conferencias que envían varias secuencias de vídeo. Si no está activada, los usuarios solo pueden organizar conferencias que envíen una única secuencia de vídeo.

    > [!NOTE]
    > Esta opción determina el tipo de secuencia de vídeo admitido por la conferencia. No determina si los participantes pueden recibir varias secuencias de vídeo. La opción **Permitir a los participantes la conexión a varias secuencias de vídeo** determina si los participantes pueden recibir varias secuencias de vídeo.

- **Colaboración de datos** Especifique si la conferencia permite o no la colaboración de datos. Las opciones son **Ninguno** o **Habilitar colaboración de datos**.

    La siguiente configuración se aplica a la colaboración de datos:

  - **Permitir que los participantes federados y anónimos descarguen contenido** Si permite la colaboración de datos, active esta casilla para permitir que los usuarios externos y no autenticados descarguen contenido, como diapositivas o entregas, de una conferencia.

  - **Permitir que los participantes transfieran archivos** Si permite la colaboración de datos, active esta casilla para permitir transferencias de archivos a todos los participantes durante una conferencia.

  - **Habilitar anotaciones** Si permite la colaboración de datos, active esta casilla para permitir que los participantes realicen anotaciones en pantalla en el contenido compartido durante la conferencia.

  - **Habilitar anotaciones de PowerPoint** Si permite la anotación, active esta casilla para permitir a los participantes realizar anotaciones en diapositivas de PowerPoint compartidas durante la conferencia.

  - **Habilitar sondeos** Si permite la colaboración de datos, active esta casilla para permitir que los participantes puedan realizar una encuesta durante una conferencia.

- **Uso compartido de aplicaciones** Especifique si la conferencia permite el uso compartido de aplicaciones. Las opciones son **Ninguno** o **Deshabilitar el uso compartido de aplicaciones**.

    La siguiente configuración se aplica al uso compartido de aplicaciones:

  - **Permitir que los participantes tomen el control** Si permite el uso compartido de aplicaciones, active esta casilla para permitir que los participantes tomen el control de las aplicaciones o escritorios que se comparten durante la conferencia.

  - **Permitir que los participantes federados y anónimos tomen el control** Si permite el uso compartido de aplicaciones, active esta casilla para permitir que los participantes externos y no autenticados tomen el control de las aplicaciones o escritorios que se comparten durante la conferencia.

- **Directiva de participantes** La configuración de esta sección se aplica a los usuarios como participantes en una conferencia o una sesión de dos participantes. Dado que la siguiente configuración se aplica por usuario, un usuario en una conferencia o sesión de dos participantes puede tener distintas capacidades que el otro en la misma conferencia o sesión entre dos.

    Haga clic en la flecha arriba o abajo junto a la etiqueta para cerrar o abrir la sección.

- Seleccione **Habilitar el uso compartido de aplicaciones y escritorio** para permitir a los usuarios compartir aplicaciones o su escritorio mientras participan en una conferencia o sesión entre dos participantes. Seleccione **Deshabilitar el uso compartido de aplicaciones y escritorio** para impedir a los usuarios compartir aplicaciones o su escritorio mientras participan en una conferencia o sesión entre dos participantes.

- **Habilitar la transferencia de archivos punto a punto** Active esta casilla para permitir transferencias de archivos de persona a persona (es decir, transferencias de archivos que no implican a todos los participantes) durante una conferencia o una sesión de dos partes.

- **Habilitar la grabación punto a punto** Active esta casilla para permitir a los usuarios grabar sesiones de dos partes.

- **Permitir a los participantes unirse a varias secuencias de vídeo** Active esta casilla para permitir que los participantes reciban vídeo de vista de galería en conferencias que lo permitan. Si esta opción no está seleccionada, los participantes solo pueden recibir una única secuencia de vídeo independientemente de lo que permita la conferencia.

    > [!NOTE]
    > La opción **Permitir varias secuencias de vídeo** determina si una conferencia permite varias secuencias de vídeo

Para obtener detalles sobre las características y capacidades de la conferencia, vea [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) en la documentación de planeación. Para obtener detalles sobre cómo trabajar con directivas de conferencias, vea [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) en la documentación de operaciones.
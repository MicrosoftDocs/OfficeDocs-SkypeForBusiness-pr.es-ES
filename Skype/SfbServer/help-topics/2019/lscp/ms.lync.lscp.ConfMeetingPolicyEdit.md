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
description: Una directiva de conferencia define las características y funcionalidades que los usuarios tienen disponibles durante una conferencia (también conocida como reunión).
ms.openlocfilehash: 97b022771f0077239475137496c222748b6ef828
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824890"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Directiva de conferencia: Crear nuevos o editar los existentes

Una directiva de conferencia define las características y funcionalidades que los usuarios tienen disponibles durante una conferencia (también conocida como reunión).

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

- **Permitir a los participantes invitar a usuarios anónimos** Active esta casilla para permitir a los usuarios invitar a usuarios anónimos a conferencias. Los usuarios anónimos son usuarios que no tienen credenciales en los Servicios de dominio de Active Directory de su organización y que, por lo tanto, no están autenticados.

- **Grabación** Especifique si los participantes pueden grabar conferencias. Las opciones son **Ninguno** o **Habilitar grabación**.

- **Permitir que los participantes federados y anónimos grabe** Active esta casilla para permitir que los participantes externos y sin autenticar graben conferencias.

- **Audio y vídeo** Especifica si los participantes pueden usar audio y vídeo:

  - **Ninguno** Seleccione esta opción para impedir el uso de audio y vídeo.

  - **Habilitar audio IP** Seleccione esta opción para permitir el uso de audio, pero no de vídeo.

  - **Habilitar audio y vídeo IP** Seleccione esta opción para permitir tanto audio como vídeo.

- **Habilitar conferencias de acceso telefónico local RTC** Si habilitó el audio en **audio y** vídeo, active esta casilla para permitir que los usuarios puedan llamar a conferencias mediante la red telefónica conmutada (RTC).

- **Permitir que los participantes anónimos marquen** Active esta casilla si permite que los usuarios llamen a conferencias y desea permitir que los usuarios no autenticados (anónimos) se unan a una conferencia mediante llamadas de salida. Mediante las llamadas de salida, el servidor de conferencia llama al usuario y el usuario responde al teléfono para unirse a la conferencia.

- **Permitir que los participantes no habilitados Telefonía IP empresarial llamada** Si habilitó el audio en **audio o** vídeo, active esta casilla para permitir que los usuarios que no están habilitados para Telefonía IP empresarial se unan a una conferencia mediante llamadas de salida. Al realizar la marcación, el servidor de conferencia llama al usuario y el usuario responde al teléfono para unirse a la conferencia.

- **Permitir varias secuencias de vídeo** Si habilitó el vídeo en **audio y vídeo,** active esta casilla para permitir a los usuarios organizar conferencias con vídeo de vista galería. Si esta casilla está activada, los usuarios pueden organizar conferencias que envían varias secuencias de vídeo. Si no está activada, los usuarios solo pueden organizar conferencias que envíen una única secuencia de vídeo.

    > [!NOTE]
    > Esta opción determina el tipo de secuencia de vídeo admitido por la conferencia. No determina si los participantes pueden recibir varias secuencias de vídeo. La opción **Permitir a los participantes la conexión a varias secuencias de vídeo** determina si los participantes pueden recibir varias secuencias de vídeo.

- **Colaboración de datos** Especifique si la conferencia permite o no la colaboración de datos. Las opciones son **Ninguno** o **Habilitar colaboración de datos**.

    La siguiente configuración se aplica a la colaboración de datos:

  - **Permitir que los participantes federados y anónimos descarguen contenido** Si permite la colaboración de datos, active esta casilla para permitir que los usuarios externos y sin autenticar descarguen contenido, como diapositivas o entregas, desde una conferencia.

  - **Permitir a los participantes transferir archivos** Si permite la colaboración de datos, active esta casilla para permitir transferencias de archivos a todos los participantes durante una conferencia.

  - **Habilitar anotaciones** Si permite la colaboración de datos, active esta casilla para permitir a los participantes realizar anotaciones en pantalla en el contenido compartido durante la conferencia.

  - **Habilitar anotaciones de PowerPoint** Si permite la anotación, active esta casilla para permitir a los participantes realizar anotaciones en diapositivas de PowerPoint compartidas durante la conferencia.

  - **Habilitar sondeos** Si permite la colaboración de datos, active esta casilla para permitir a los participantes realizar un sondeo durante una conferencia.

- **Uso compartido de aplicaciones** Especifique si la conferencia permite o no el uso compartido de aplicaciones. Las opciones son **Ninguno** o **Deshabilitar el uso compartido de aplicaciones**.

    La siguiente configuración se aplica al uso compartido de aplicaciones:

  - **Permitir que los participantes tomen el control** Si permite el uso compartido de aplicaciones, active esta casilla para permitir que los participantes tomen el control de las aplicaciones o escritorios que se comparten durante la conferencia.

  - **Permitir que los participantes federados y anónimos tomen el control** Si permite el uso compartido de aplicaciones, active esta casilla para permitir que los participantes externos y sin autenticar tomen el control de las aplicaciones o escritorios que se comparten durante la conferencia.

- **Directiva de participantes** La configuración de esta sección se aplica a los usuarios como participantes en una conferencia o sesión entre dos participantes. Dado que la siguiente configuración se aplica por usuario, un usuario en una conferencia o sesión de dos participantes puede tener distintas capacidades que el otro en la misma conferencia o sesión entre dos.

    Haga clic en la flecha arriba o abajo junto a la etiqueta para cerrar o abrir la sección.

- Seleccione **Habilitar el uso compartido de aplicaciones y escritorio** para permitir a los usuarios compartir aplicaciones o su escritorio mientras participan en una conferencia o sesión entre dos participantes. Seleccione **Deshabilitar el uso compartido de aplicaciones y escritorio** para impedir a los usuarios compartir aplicaciones o su escritorio mientras participan en una conferencia o sesión entre dos participantes.

- **Habilitar la transferencia de archivos punto a punto** Active esta casilla para permitir transferencias de archivos de persona a persona (es decir, transferencias de archivos que no implican a todos los participantes) durante una conferencia o sesión entre dos participantes.

- **Habilitar la grabación punto a punto** Active esta casilla para permitir a los usuarios grabar sesiones entre dos usuarios.

- **Permitir que los participantes se unan con varias secuencias de vídeo** Active esta casilla para permitir que los participantes reciban vídeo de la Vista galería en conferencias que lo permitan. Si esta opción no está seleccionada, los participantes solo pueden recibir una única secuencia de vídeo independientemente de lo que permita la conferencia.

    > [!NOTE]
    > La opción **Permitir varias secuencias de vídeo** determina si una conferencia permite varias secuencias de vídeo

Para obtener detalles sobre las características y capacidades de la conferencia, vea [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) en la documentación de planeación. Para obtener detalles sobre cómo trabajar con directivas de conferencias, vea [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) en la documentación de operaciones.



---
title: Directiva de conferencia crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: Una directiva de conferencia define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada reunión)
ms.openlocfilehash: 0a82ba29db52affab2371d6ce880c120487396c6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691395"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Directiva de conferencia: Crear nueva o editar existente

Una directiva de conferencia define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada reunión)

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Ámbito** Identifica el ámbito de la Directiva de conferencia que está creando o modificando: global, sitio o usuario.

- **Nombre** Cada directiva de conferencia requiere un nombre. Las directivas de conferencia global y de sitio tienen un nombre predeterminado que no se puede cambiar. Para las directivas de conferencia de usuarios, use un nombre descriptivo que identifique al usuario o al grupo de usuarios.

    > [!NOTE]
    > Una vez guardada la directiva de conferencia, el nombre no se puede cambiar.

- **Descripción** Este campo es opcional. Úselo para dar detalles sobre la directiva de conferencia.

- **Directiva del organizador** La configuración de esta sección se aplica al usuario que organiza una conferencia. Si se selecciona una configuración, el usuario puede organizar una conferencia que tenga la característica especificada. Si no se selecciona ninguna configuración, el usuario no puede organizar una conferencia con esta característica. Estas configuraciones no determinan los elementos a los que el usuario tiene acceso como participante en otras conferencias.

    Haga clic en la flecha arriba o abajo junto a la etiqueta para cerrar o abrir la sección.

- **Tamaño máximo** de la reunión el número máximo de usuarios que se permiten en una conferencia. De forma predeterminada, el tamaño máximo de la Conferencia es 250.

- **Permitir a los participantes invitar a usuarios anónimos** Seleccione esta casilla para permitir a los usuarios invitar a usuarios anónimos a conferencias. Los usuarios anónimos son usuarios que no tienen credenciales en los servicios de dominio de Active Directory de su organización y que, por consiguiente, no se autentican.

- **Grabación** Especificar si los participantes pueden grabar conferencias. Las opciones son **Ninguno** o **Habilitar grabación**.

- **Permitir a los participantes federados y anónimos grabar** Seleccione esta casilla para permitir que los participantes externos y no autenticados registren conferencias.

- **Audio o vídeo** Especificar si los participantes pueden usar audio y vídeo:

  - **Ninguna** Seleccione esta opción para evitar el uso de audio y vídeo.

  - **Habilitar audio IP** Seleccione esta opción para permitir el uso de audio pero no de vídeo.

  - **Habilitar audio/vídeo IP** Seleccione esta opción para permitir el audio y el vídeo.

- **Habilitar Conferencia de acceso telefónico local RTC** Si habilitó el audio en **audio o vídeo**, Active esta casilla para permitir que los usuarios puedan llamar a conferencias mediante la red de telefonía pública conmutada (RTC).

- **Permitir que los participantes anónimos llamen** Seleccione esta casilla si permite que los usuarios llamen a conferencias y quiere permitir que usuarios no autenticados (anónimos) se unan a una conferencia con un falso. Con las llamadas de salida, el servidor de conferencia llama al usuario y este responde al teléfono para unirse a la conferencia.

- **Permitir que los participantes no estén habilitados para la telefonía IP empresarial** Si habilitó el audio en **audio o vídeo**, Active esta casilla para permitir que los usuarios que no tengan habilitada la telefonía IP empresarial se unan a una conferencia con un falso. Al realizar la marcación, el servidor de conferencia llama al usuario y este responde al teléfono para unirse a la conferencia.

- **Permitir varias secuencias de vídeo** Si ha habilitado vídeo en **audio o vídeo**, Active esta casilla para permitir que los usuarios organicen conferencias con el vídeo vista de galería. Si esta casilla está activada, podrán organizar conferencias que envían varias secuencias de vídeo. Si no está activada, solo podrán organizar conferencias que envíen una única secuencia de vídeo.

    > [!NOTE]
    > Esta opción determina el tipo de secuencia de vídeo admitido por la conferencia. No determina si los participantes pueden recibir varias secuencias de vídeo. La opción **Permitir a los participantes la conexión a varias secuencias de vídeo** determina si los participantes pueden recibir varias secuencias de vídeo.

- **Colaboración de datos** Especificar si la Conferencia permite o no la colaboración de datos. Las opciones son **Ninguno** o **Habilitar colaboración de datos**.

    La siguiente configuración se aplica a la colaboración de datos:

  - **Permitir a los participantes federados y anónimos descargar contenido** Si permite la colaboración de datos, Active esta casilla para permitir que los usuarios externos y no autenticados descarguen contenido, como diapositivas o documentos, de una conferencia.

  - **Permitir que los participantes transfieran archivos** Si permite la colaboración de datos, Active esta casilla para permitir transferencias de archivos a todos los participantes durante una conferencia.

  - **Habilitar anotaciones** Si permite la colaboración de datos, Active esta casilla para permitir que los participantes puedan crear anotaciones en pantalla en contenido compartido durante la Conferencia.

  - **Habilitar anotaciones de PowerPoint** Si permite una anotación, Active esta casilla para permitir que los participantes realicen anotaciones en las diapositivas de PowerPoint compartidas durante la Conferencia.

  - **Habilitar sondeos** Si permite la colaboración de datos, Active esta casilla para permitir a los participantes mantener un sondeo durante una conferencia.

- **Uso compartido de aplicaciones** Especifique si la Conferencia permite o no el uso compartido de aplicaciones. Las opciones son **Ninguno** o **Deshabilitar el uso compartido de aplicaciones**.

    La siguiente configuración se aplica al uso compartido de aplicaciones:

  - **Permitir que los participantes tomen el control** Si permite el uso compartido de aplicaciones, Active esta casilla para permitir a los participantes tomar el control de las aplicaciones o de los escritorios compartidos durante la Conferencia.

  - **Permitir a los participantes federados y anónimos tomar el control** Si permite el uso compartido de aplicaciones, Active esta casilla para permitir a los participantes externos y no autenticados tomar el control de las aplicaciones o de los escritorios compartidos durante la Conferencia.

- **Política de participantes** La configuración de esta sección se aplica a los usuarios como participantes en una sesión de conferencia o de dos terceros. Dado que la siguiente configuración se aplica por usuario, los usuarios en una conferencia o sesión de dos participantes pueden tener distintas capacidades que el otro en la misma conferencia o sesión entre dos.

    Haga clic en la flecha arriba o abajo junto a la etiqueta para cerrar o abrir la sección.

- Seleccione **Habilitar el uso compartido de aplicaciones y escritorio** para que los usuarios puedan compartir aplicaciones o su escritorio mientras participan en una conferencia o sesión entre dos participantes. Seleccione **Deshabilitar el uso compartido de aplicaciones y escritorio** para impedir que puedan compartir aplicaciones o el escritorio mientras participan en una conferencia o sesión entre dos participantes.

- **Habilitar la transferencia de archivos de punto a punto** Active esta casilla para permitir la transferencia de archivos de persona a persona (es decir, las transferencias de archivos que no implican a todos los participantes) durante una sesión de conferencia o de dos terceros.

- **Habilitar la grabación de punto a punto** Seleccione esta casilla para permitir a los usuarios grabar sesiones de dos proveedores.

- **Permitir que los participantes se unan con varias secuencias de vídeo** Seleccione esta casilla para permitir que los participantes reciban vídeos de la vista de galería en conferencias que lo permitan. Si esta opción no está seleccionada, los participantes solo pueden recibir una única secuencia de vídeo, independientemente de lo que permita la conferencia.

    > [!NOTE]
    > La opción **Permitir varias secuencias de vídeo** determina si una conferencia permite varias secuencias de vídeo

Para más detalles sobre las características y capacidades de la conferencia, mire [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) en la documentación de planeación. Para más detalles sobre cómo trabajar con directivas de conferencias, mire [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) en la documentación de operaciones.



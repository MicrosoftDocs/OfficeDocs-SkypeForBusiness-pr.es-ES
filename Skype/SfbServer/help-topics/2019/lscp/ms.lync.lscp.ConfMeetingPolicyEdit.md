---
title: Directiva de conferencia crear nuevos o editar los existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: Una directiva de conferencia define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada reunión)
ms.openlocfilehash: 4a230f7ce9aeb0943ad754d5ea842b681c4cca48
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20994689"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Directiva de conferencia: Crear nueva o editar existente
 
Una directiva de conferencia define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada reunión)
  
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.
  
- **Ámbito** Identifica el ámbito de la directiva de conferencia que está creando o modificando: global, sitio o usuario.
    
- **Nombre** Cada directiva de conferencia requiere un nombre. Las directivas de conferencia global y de sitio tienen un nombre predeterminado que no se puede cambiar. Para las directivas de conferencia de usuarios, use un nombre descriptivo que identifique al usuario o al grupo de usuarios.
    
    > [!NOTE]
    > Una vez guardada la directiva de conferencia, el nombre no se puede cambiar. 
  
- **Descripción** Este campo es opcional. Úselo para dar detalles sobre la directiva de conferencia.
    
- **Directiva de organizador** La configuración de esta sección se aplica al usuario que organiza una conferencia. Si se selecciona una configuración, el usuario puede organizar una conferencia que tenga la característica especificada. Si no se selecciona ninguna configuración, el usuario no puede organizar una conferencia con esta característica. Estas configuraciones no determinan los elementos a los que el usuario tiene acceso como participante en otras conferencias.
    
    Haga clic en la flecha arriba o abajo junto a la etiqueta para cerrar o abrir la sección.
    
- **Tamaño máximo reunión** el número máximo de usuarios que se permiten en una conferencia. De forma predeterminada, el tamaño máximo de conferencia es 250.
    
- **Permitir que los participantes invitar a usuarios anónimos** Seleccione esta casilla para permitir que los usuarios invitar a usuarios anónimos a las conferencias. Los usuarios anónimos son usuarios que no tienen credenciales en los servicios de dominio de Active Directory de su organización y que, por lo tanto, no se autentican.
    
- **Grabación** Especificar si los participantes pueden registrar las conferencias. Las opciones son **Ninguno** o **Habilitar grabación**.
    
- **Permitir federados y anónimos participantes para registrar** Seleccione esta casilla para permitir que a los participantes externos y sin autenticados a las conferencias de registro.
    
- **Audio y vídeo** Especifique si los participantes pueden usar audio y vídeo:
    
  - **Ninguno** Seleccione esta opción para impedir el uso de audio y vídeo.
    
  - **Habilitar audio IP** Seleccione esta opción para permitir el uso de audio pero no de vídeo.
    
  - **Habilitar IP audio y vídeo** Seleccione esta opción para permitir audio y vídeo.
    
- **Conferencia de acceso telefónico RTC habilitar** Si se habilita el audio en **Audio y vídeo**, Active esta casilla para permitir a los usuarios conectarse a conferencias mediante el uso de la red telefónica conmutada (RTC).
    
- **Permitir que los participantes anónimos a marcar un número** Seleccione esta casilla de verificación si permitir a los usuarios conectarse a conferencias y desea permitir sin autenticar a los usuarios (anónimos) para unirse a una conferencia mediante el uso de salida llamen. Mediante las llamadas de salida, el servidor de conferencia llama al usuario y el usuario responde al teléfono para unirse a la conferencia.
    
- **Permitir que los participantes no habilitados para que Enterprise Voice para marcar un número** Si se habilita el audio en **Audio y vídeo**, Active esta casilla para permitir que a los usuarios que no están habilitados para que Enterprise Voice para unirse a una conferencia mediante el uso de salida llamen. Al realizar la marcación, el servidor de conferencia llama al usuario y este responde al teléfono para unirse a la conferencia.
    
- **Permitir varias secuencias de vídeo** Si se habilita el vídeo en **Audio y vídeo**, Active esta casilla para permitir a los usuarios organizar conferencias con vídeo de vista Galería. Si esta casilla está activada, podrán organizar conferencias que envían varias secuencias de vídeo. Si no está activada, solo podrán organizar conferencias que envíen una única secuencia de vídeo.
    
    > [!NOTE]
    > Esta opción determina el tipo de secuencia de vídeo admitido por la conferencia. No determina si los participantes pueden recibir varias secuencias de vídeo. La opción **Permitir a los participantes la conexión a varias secuencias de vídeo** determina si los participantes pueden recibir varias secuencias de vídeo.
  
- **Colaboración de datos** Especifique si permite o no la conferencia de colaboración de datos. Las opciones son **Ninguno** o **Habilitar colaboración de datos**.
    
    La siguiente configuración se aplica a la colaboración de datos:
    
  - **Permitir federados y anónimos participantes para descargar el contenido** Si permite la colaboración de datos, seleccione esta casilla para permitir que los usuarios externos y sin autenticados descargar el contenido, como diapositivas o documentos, desde una conferencia.
    
  - **Permitir a los participantes transferir archivos** Si permite la colaboración de datos, seleccione esta casilla para permitir transferencias de archivos a todos los participantes durante una conferencia.
    
  - **Habilitar anotaciones** Si permite la colaboración de datos, Active esta casilla para permitir a los participantes en la pantalla realizar anotaciones en contenido compartido durante la conferencia.
    
  - **PowerPoint Habilitar anotaciones** Si permite la anotación, Active esta casilla para permitir a los participantes realizar anotaciones en diapositivas de PowerPoint compartidas durante la conferencia.
    
  - **Habilitar sondeos** Si permite la colaboración de datos, seleccione esta casilla para permitir a los participantes realizar un sondeo durante una conferencia.
    
- **Uso compartido de aplicaciones** Especifique si permite o no la conferencia de uso compartido de aplicaciones. Las opciones son **Ninguno** o **Deshabilitar el uso compartido de aplicaciones**.
    
    La siguiente configuración se aplica al uso compartido de aplicaciones:
    
  - **Permitir a los participantes asumir el control** Si permite el uso compartido de aplicaciones, seleccione esta casilla para permitir que los participantes asumir el control de las aplicaciones o escritorios compartidos durante la conferencia.
    
  - **Permitir federados y anónimos a los participantes asumir el control** Si permite el uso compartido de aplicaciones, seleccione esta casilla para permitir que los participantes externos y sin autenticados a tomar el control de las aplicaciones o escritorios compartidos durante la conferencia.
    
- **Directiva de participantes** La configuración de esta sección se aplica a los usuarios como los participantes de una conferencia o sesión entre dos participantes. Dado que la siguiente configuración se aplica por usuario, los usuarios en una conferencia o sesión de dos participantes pueden tener distintas capacidades que el otro en la misma conferencia o sesión entre dos.
    
    Haga clic en la flecha arriba o abajo junto a la etiqueta para cerrar o abrir la sección.
    
- Seleccione **Habilitar el uso compartido de aplicaciones y escritorio** para que los usuarios puedan compartir aplicaciones o su escritorio mientras participan en una conferencia o sesión entre dos participantes. Seleccione **Deshabilitar el uso compartido de aplicaciones y escritorio** para impedir que puedan compartir aplicaciones o el escritorio mientras participan en una conferencia o sesión entre dos participantes.
    
- **Habilitar transferencia de archivos de punto a punto** Active esta casilla de verificación para permitir a transferencias de archivos entre dos personas (es decir, las transferencias de archivos que no impliquen a todos los participantes) durante una conferencia o sesión entre dos participantes.
    
- **Habilitar grabación punto a punto** Active esta casilla de verificación para permitir a los usuarios grabar sesiones entre dos participantes.
    
- **Permitir que los participantes para unirse a con varias secuencias de vídeo** Seleccione esta casilla para permitir que los participantes recibir vídeo de la vista de galería en las conferencias que le permiten. Si esta opción no está seleccionada, los participantes solo pueden recibir una única secuencia de vídeo, independientemente de lo que permita la conferencia.
    
    > [!NOTE]
    > La opción **Permitir varias secuencias de vídeo** determina si una conferencia permite varias secuencias de vídeo
  
Para obtener información detallada sobre las características de conferencia y funciones, vea [Información general de conferencias](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) en la documentación de planeación. Para obtener información detallada sobre cómo trabajar con directivas de conferencia, vea [Directivas de conferencia](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) en la documentación sobre operaciones.
  


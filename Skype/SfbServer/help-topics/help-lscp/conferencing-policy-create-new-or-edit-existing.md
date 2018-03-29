---
title: Directiva de conferencia crear nuevo o editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: Una directiva de conferencia define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada reunión)
ms.openlocfilehash: 7840eb2d30c40440d82d0cdc6d2bcf38ac894c4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Directiva de conferencia: Crear nueva o editar existente
 
Una directiva de conferencia define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada reunión)
  
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.
  
- **Ámbito de aplicación** Identifica el ámbito de la directiva de la conferencia que está creando o modificando: global, sitio o usuario.
    
- **Nombre** Cada directiva de conferencia requiere un nombre. Las directivas de conferencia global y de sitio tienen un nombre predeterminado que no se puede cambiar. Para las directivas de conferencia de usuarios, use un nombre descriptivo que identifique al usuario o al grupo de usuarios.
    
    > [!NOTE]
    > Una vez guardada la directiva de conferencia, el nombre no se puede cambiar. 
  
- **Descripción** Este campo es opcional. Úselo para dar detalles sobre la directiva de conferencia.
    
- **Directiva de organizador** La configuración de esta sección se aplica al usuario que organiza una conferencia. Si se selecciona una configuración, el usuario puede organizar una conferencia que tenga la característica especificada. Si no se selecciona ninguna configuración, el usuario no puede organizar una conferencia con esta característica. Estas configuraciones no determinan los elementos a los que el usuario tiene acceso como participante en otras conferencias.
    
    Haga clic en la flecha arriba o abajo junto a la etiqueta para cerrar o abrir la sección.
    
- **Tamaño de reunión como máximo** el número máximo de usuarios permitidos en una conferencia. De forma predeterminada, el tamaño máximo de conferencia es 250.
    
- **Permitir que los participantes para invitar a los usuarios anónimos** Active esta casilla de verificación Permitir a los usuarios invitar a los usuarios anónimos a las conferencias. Los usuarios anónimos son los usuarios que no tienen credenciales en servicios de dominio de directorio activo de la organización y que, por lo tanto, no se autentican.
    
- **Grabación** Especificar si los participantes pueden registrar conferencias. Las opciones son **Ninguno** o **Habilitar grabación**.
    
- **Permitir federados y anónimos participantes para grabar** Seleccione esta casilla para permitir que a los participantes externos y no autenticados a las conferencias de registro.
    
- **Audio y vídeo** Especificar si los participantes pueden utilizar audio y vídeo:
    
  - **Ninguno** Seleccione esta opción para impedir el uso de audio y vídeo.
    
  - **Habilitar IP audio** Seleccione esta opción para permitir el uso de audio pero no vídeo.
    
  - **Habilitar IP audio/vídeo** Seleccione esta opción para permitir audio y vídeo.
    
- **Habilitar PSTN marcado en conferencia** Si habilita el audio en **Audio y vídeo**, seleccione esta casilla para permitir a los usuarios conectarse a conferencias mediante el uso de la red telefónica pública conmutada (PSTN).
    
- **Permitir que los participantes anónimos para marcar** Seleccione esta casilla de verificación si se permite a los usuarios conectarse a conferencias y desea permitir que los usuarios (anónimos) no autenticados unirse a una conferencia utilizando marcado a llamar. Mediante las llamadas de salida, el servidor de conferencia llama al usuario y el usuario responde al teléfono para unirse a la conferencia.
    
- **Permitir que los participantes no está habilitados para que la Telefonía IP empresarial marcar** Si habilita el audio en **Audio y vídeo**, seleccione esta casilla de verificación Permitir que usuarios que no están habilitados para que Telefonía IP empresarial a unirse a una conferencia utilizando llamen de acceso telefónico de salida. Al realizar la marcación, el servidor de conferencia llama al usuario y este responde al teléfono para unirse a la conferencia.
    
- **Permitir varias secuencias de vídeo** Si ha habilitado el vídeo en **Audio o vídeo**, seleccione esta casilla para permitir a los usuarios organizar conferencias con vídeo de la galería. Si esta casilla está activada, podrán organizar conferencias que envían varias secuencias de vídeo. Si no está activada, solo podrán organizar conferencias que envíen una única secuencia de vídeo.
    
    > [!NOTE]
    > Esta opción determina el tipo de secuencia de vídeo admitido por la conferencia. No determina si los participantes pueden recibir varias secuencias de vídeo. La opción **Permitir a los participantes la conexión a varias secuencias de vídeo** determina si los participantes pueden recibir varias secuencias de vídeo.
  
- **Colaboración de datos** Especifique si permite o no la conferencia de colaboración de datos. Las opciones son **Ninguno** o **Habilitar colaboración de datos**.
    
    La siguiente configuración se aplica a la colaboración de datos:
    
  - **Permitir federados y anónimos participantes a descargar contenido** Si permite la colaboración de datos, seleccione esta casilla de verificación Permitir que los usuarios no autenticados y externos descargar contenido, como diapositivas o documentos, en una conferencia.
    
  - **Permitir que los participantes para transferir archivos** Si permite la colaboración de datos, seleccione esta casilla de verificación para permitir las transferencias de archivos a todos los participantes durante una conferencia.
    
  - **Habilitar anotaciones** Si permite la colaboración de datos, seleccione esta casilla de verificación para permitir que los participantes en pantalla hacer anotaciones en contenido compartido durante la conferencia.
    
  - **Anotaciones permiten PowerPoint** Si permite la anotación, seleccione esta casilla para permitir a los participantes realizar anotaciones en diapositivas de PowerPoint compartidas durante la conferencia.
    
  - **Habilitar los sondeos** Si permite la colaboración de datos, seleccione esta casilla de verificación Permitir a los participantes contener un sondeo durante una conferencia.
    
- **Uso compartido de aplicaciones** Especifique si permite o no la conferencia compartir aplicaciones. Las opciones son **Ninguno** o **Deshabilitar el uso compartido de aplicaciones**.
    
    La siguiente configuración se aplica al uso compartido de aplicaciones:
    
  - **Permitir que los participantes a tomar el control** Si se permite el uso compartido de aplicaciones, Active esta casilla de verificación para permitir que los participantes puedan tomar el control de las aplicaciones o escritorios compartidos durante la conferencia.
    
  - **Permitir federados y anónimos participantes a tomar el control** Si se permite el uso compartido de aplicaciones, seleccione esta casilla para permitir que los participantes externos y no autenticados a tomar el control de las aplicaciones o escritorios compartidos durante la conferencia.
    
- **Directiva de participante** La configuración de esta sección se aplica a los usuarios como los participantes de una conferencia o una sesión de dos partes. Dado que la siguiente configuración se aplica por usuario, los usuarios en una conferencia o sesión de dos participantes pueden tener distintas capacidades que el otro en la misma conferencia o sesión entre dos.
    
    Haga clic en la flecha arriba o abajo junto a la etiqueta para cerrar o abrir la sección.
    
- Seleccione **Habilitar el uso compartido de aplicaciones y escritorio** para que los usuarios puedan compartir aplicaciones o su escritorio mientras participan en una conferencia o sesión entre dos participantes. Seleccione **Deshabilitar el uso compartido de aplicaciones y escritorio** para impedir que puedan compartir aplicaciones o el escritorio mientras participan en una conferencia o sesión entre dos participantes.
    
- **Habilitar la transferencia de archivos de igual a igual** Active esta casilla de verificación Permitir transferencias de archivos de persona a persona (es decir, transferencias de archivos que implican a todos los participantes) durante una conferencia o una sesión de dos partes.
    
- **Habilitar grabación de igual a igual** Seleccione esta casilla para permitir a los usuarios grabar las sesiones de dos partes.
    
- **Permitir a los participantes a participar con varias secuencias de vídeo** Active esta casilla de verificación para permitir que los participantes puedan recibir vídeo de la Galería de conferencias que le permiten. Si esta opción no está seleccionada, los participantes solo pueden recibir una única secuencia de vídeo, independientemente de lo que permita la conferencia.
    
    > [!NOTE]
    > La opción **Permitir varias secuencias de vídeo** determina si una conferencia permite varias secuencias de vídeo
  
Para obtener más información acerca de las características de conferencia y capacidades, vea [Información general de la conferencia](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) en la documentación de planeamiento. Para obtener más información acerca de cómo trabajar con directivas de conferencia, vea [Directivas de conferencias](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) en la documentación de las operaciones.
  


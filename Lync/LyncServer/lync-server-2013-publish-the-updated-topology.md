---
title: 'Lync Server 2013: Publicar la topología actualizada'
TOCTitle: Publicar la topología actualizada
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48275351
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publicar la topología actualizada en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

Después de actualizar su topología en Generador de topologías, debe publicar la topología en Almacén de administración central para poder configurar y usar Servidor de chat persistente. Se replican copias de solo lectura de los datos a todos los servidores de la topología para mantenerlos sincronizados con los cambios de la topología y otros cambios de configuración.

## Procedimiento para publicar una topología actualizada

Antes de publicar su topología, instale las bases de datos de Servidor de chat persistente. Use Generador de topologías para instalar las bases de datos seleccionando **Acción** e **Instalar base de datos** .

1.  En un equipo en el que se ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo **Admins. del dominio** y del grupo **RTCUniversalServerAdmins** y que disponga de todos los permisos de control (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que va a usar para el almacén de archivos de Servidor de chat persistente (de modo que Generador de topologías pueda configurar las listas de control de acceso discrecional necesarias (DACL)) o una cuenta con derechos de usuario equivalentes.

2.  Inicie Generador de topologías. Seleccione **Descargar topología de la implementación existente** o **Abrir topología desde un archivo local** si lo guardó localmente.

3.  En el árbol de consola, haga clic con el botón secundario en **Lync Server 2013** y luego haga clic en **Publicar topología**.

4.  En la página **Publicar la topología**, haga clic en **Siguiente**.

5.  En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y haga clic en **Finalizar**.
    
    > [!IMPORTANT]  
    > Después de publicar la topología, deberá configurar la compatibilidad para Servidor de chat persistente antes de que se pueda archivar ningún contenido.
    


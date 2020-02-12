---
title: Mover los datos del almacén de archivos a un nuevo almacén de archivos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para su implementación de Skype empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero necesita crear un nuevo recurso compartido. Después deberá realizar los siguientes pasos:'
ms.openlocfilehash: 91ba8393a958188e368ff3f8f5d2a85bcfcc1396
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888459"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Mover los datos del almacén de archivos a un nuevo almacén de archivos en Skype empresarial Server

Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para su implementación de Skype empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero necesita crear un nuevo recurso compartido. Después deberá realizar los siguientes pasos:

1. Cierre los servicios de Skype empresarial Server que usan el almacén de archivos que planea quitar.

2. Defina el almacén de archivos en el generador de topología y publique los cambios para que el nuevo almacén de archivos esté disponible para su implementación.

3. Mueva los datos al nuevo almacén de archivos.

4. Reinicie los servidores o los servicios.

5. Opcionalmente, quite el recurso compartido de archivos y la carpeta de archivos antiguos.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover los datos de un almacén de archivos a otro nuevo

1. Inicie sesión en un equipo como miembro del grupo RTCUniversersalServerAdmins o CsServerAdministrator en el que están instaladas las herramientas administrativas de Skype empresarial Server.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 

4. Para cada grupo de directores, un director, un servidor Standard Edition y un grupo de servidores front-end que usen el almacén de archivos que planea quitar, seleccione el servidor o grupo, haga clic en **acción**y, a continuación, haga clic en **detener todos los servicios**.

5. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

6. Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Skype empresarial Server**y, a continuación, haga clic en **generador de topologías de Skype empresarial Server**.

7. Seleccione un servidor o un grupo que use el almacén de archivos y realice lo siguiente:

   a. Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**. 

   b. En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, haga clic en **Nuevo**.

   c. En **Definir nuevo almacén de archivos**, en **FQDN del servidor de archivos**, escriba el nombre de dominio completo (FQDN) del servidor de archivos. En **Recurso compartido de archivos**, escriba el nombre de la carpeta del nuevo recurso compartido de archivos y después haga clic en **Aceptar**.

     > [!IMPORTANT]
     > Este paso define un nuevo almacén de archivos para usar en el generador de topología. Debe definirlo solo una vez, no en cada servidor. Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido. Para obtener información detallada, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

8. Por cada servidor o grupo que use el almacén de archivos, realice lo siguiente:

   a. Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**.

   b. En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, seleccione el nuevo recurso compartido de archivos y haga clic en **Aceptar**.

9. Publique la topología, compruebe el estado de la replicación y, a continuación, ejecute el Asistente para la implementación de Skype empresarial Server según sea necesario. Para obtener información detallada, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

10. Inicie un símbolo del sistema: haga clic en **Inicio**, haga clic en **Ejecutar**y, a continuación, escriba cmd. exe.

11. En la línea de comandos, escriba:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > El conmutador /S copia los archivos, directorios y subdirectorios. El conmutador /XF omite los archivos con el nombre Meeting.Active. Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos. Para el modificador/LOG, use una ruta de acceso del directorio y un nombre de archivo de registro con el formato C:\Logfiles\log.txt. Este conmutador crea un archivo de registro de operaciones en la ubicación designada.

12. Cuando la copia de datos se haya completado, en el panel de control de Lync Server, haga clic en **topología**y, a continuación, en **Estado**.

13. Por cada servidor o grupo donde haya detenido los servicios, seleccione el servidor o el grupo, haga clic en **Acción** y después en **Iniciar todos los servicios**.         

14. Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología. Para obtener información detallada, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

15. (Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Administradores del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.

## <a name="see-also"></a>Vea también

[Reasignar un servidor a otro almacén de archivos](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Quitar un almacén de archivos](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

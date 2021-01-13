---
title: Mover datos del almacén de archivos a un nuevo almacén de archivos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para su implementación de Skype Empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido. A continuación, debe realizar los siguientes pasos:'
ms.openlocfilehash: 6121083d736075fa9ec58380dbc09ef6a8c4ef68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819610"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Mover datos del almacén de archivos a un nuevo almacén de archivos en Skype Empresarial Server

Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para su implementación de Skype Empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido. A continuación, debe realizar los siguientes pasos:

1. Cierre los servicios de Skype Empresarial Server que usan el almacén de archivos que planea quitar.

2. Defina el almacén de archivos en topology Builder y publique los cambios para que el nuevo almacén de archivos esté disponible para su implementación.

3. Mueva los datos al nuevo almacén de archivos.

4. Reinicie los servidores o servicios.

5. Opcionalmente, quite el recurso compartido de archivos antiguo y la carpeta de archivos.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover los datos de un almacén de archivos a otro nuevo

1. Inicie sesión en un equipo como miembro del grupo RTCUniversersalServerAdmins o CsServerAdministrator donde está instalado Skype Empresarial Server, Herramientas administrativas.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.

4. Para cada grupo de directores, director, servidor Standard Edition y grupo de servidores front-end que use el almacén de archivos que desea quitar, seleccione el servidor o grupo de servidores, haga clic en Acción y, a continuación, haga clic en Detener todos los **servicios.**

5. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

6. Inicie el Generador de topologías: **Haga** clic en Inicio, Todos los **programas,** Skype Empresarial **Server** y, a continuación, haga clic en Generador de topologías de Skype Empresarial **Server.**

7. Seleccione un servidor o grupo de servidores que use el almacén de archivos y haga lo siguiente:

8. Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic **en Editar propiedades.**

9. En **Editar propiedades**, en **Asociaciones**, en Almacén **de archivos**, haga clic en **Nuevo**.

10. En **Definir nuevo almacén de archivos,** en **FQDN** del servidor de archivos, escriba el nombre de dominio completo (FQDN) del servidor de archivos. En **Recurso compartido de** archivos, escriba el nombre de la carpeta para el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.

     > [!IMPORTANT]
     > Este paso define un nuevo almacén de archivos para su uso en topology Builder. Solo se define una vez, no para cada servidor. Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido. Para obtener información detallada, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Para cada servidor o grupo que use el almacén de archivos, haga lo siguiente:

12. Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic **en Editar propiedades.**

13. En **Editar propiedades**, en **Asociaciones**, en almacén **de archivos,** seleccione el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.

14. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Skype Empresarial Server según sea necesario. Para obtener más información, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Inicie un símbolo del sistema: haga clic **en Inicio,** en **Ejecutar** y, a continuación, escriba cmd.exe.

16. Escriba lo siguiente en la línea de comandos:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > El modificador /S copia archivos, directorios y subdirectorios. El modificador /XF omite los archivos denominados Meeting.Active. Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos. Para el modificador /LOG, use una ruta de acceso de directorio y un nombre de archivo de registro en forma de C:\Logfiles\log.txt. Este modificador crea un archivo de registro de operaciones en la ubicación con nombre.

17. Una vez completada la copia de datos, en el Panel de control de Lync Server, haga clic en Topología **y,** a continuación, haga clic en **Estado.**

18. Para cada servidor o grupo en el que detuvo los servicios, seleccione el servidor o grupo de servidores, haga clic en Acción **y,** a continuación, haga clic **en Iniciar todos los servicios.**

19. Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología. Para obtener información detallada, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Admins. del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.

## <a name="see-also"></a>Ver también

[Reasignar un servidor a un almacén de archivos diferente](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Quitar un almacén de archivos](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

---
title: Almacén de archivos de movimiento de datos a un nuevo almacén de archivos en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Si necesitará quitar el servidor de archivos que actualmente está actuando como el almacén de archivos para su Skype para la implementación de Business Server, o si necesita realizar otros cambios que harían que el archivo actual almacén no está disponible, primero debe crear un nuevo recurso compartido. Después deberá realizar los siguientes pasos:'
ms.openlocfilehash: 5051e7ef9c0008fb3b98f7e4b7c67a06a5465d1e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375925"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Almacén de archivos de movimiento de datos a un nuevo almacén de archivos en Skype para Business Server

Si necesitará quitar el servidor de archivos que actualmente está actuando como el almacén de archivos para su Skype para la implementación de Business Server, o si necesita realizar otros cambios que harían que el archivo actual almacén no está disponible, primero debe crear un nuevo recurso compartido. Después deberá realizar los siguientes pasos:

1. Apague el Skype para servicios de Business Server que utilizan el almacén de archivos que se va a quitar.

2. Definir el almacén de archivos en el generador de topología y publique los cambios para que el nuevo archivo de almacenamiento disponibles para la implementación.

3. Mueva los datos al nuevo almacén de archivos.

4. Reinicie los servidores o los servicios.

5. Opcionalmente, quite el recurso compartido de archivos y la carpeta de archivos antiguos.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover los datos de un almacén de archivos a otro nuevo

1. Inicie sesión como miembro del grupo RTCUniversersalServerAdmins o CsServerAdministrator del grupo donde se instalan los Skype para Business Server, las herramientas administrativas en un equipo.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 

4. Para cada grupo de directores, Director, servidor Standard Edition y grupo de servidores Front-End que utiliza el almacén de archivos que se va a quitar, seleccione el servidor o grupo de servidores, haga clic en **acción**y, a continuación, haga clic en **Detener todos los servicios**.

5. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

6. Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Business Server Topology Builder**.

7. Seleccione un servidor o un grupo que use el almacén de archivos y realice lo siguiente:

8. Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**. 

9. En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, haga clic en **Nuevo**.

10. En **Definir nuevo almacén de archivos**, en **FQDN del servidor de archivos**, escriba el nombre de dominio completo (FQDN) del servidor de archivos. En **Recurso compartido de archivos**, escriba el nombre de la carpeta del nuevo recurso compartido de archivos y después haga clic en **Aceptar**.

     > [!IMPORTANT]
     > En este paso se define un nuevo almacén de archivos para su uso en el generador de topología. Debe definirlo solo una vez, no en cada servidor. Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido. Para obtener más información, consulte [definir el almacén de archivos para el Front-End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Por cada servidor o grupo que use el almacén de archivos, realice lo siguiente:

12. Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**.

13. En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, seleccione el nuevo recurso compartido de archivos y haga clic en **Aceptar**.

14. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Skype para el Asistente para la implementación de Business Server según sea necesario. Para obtener información detallada, vea [Procedimientos comunes para Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Inicie un símbolo del sistema: haga clic en **Inicio**, haga clic en **Ejecutar**y, a continuación, escriba cmd.exe.

16. En la línea de comandos, escriba:

    ```
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > El conmutador /S copia los archivos, directorios y subdirectorios. El conmutador /XF omite los archivos con el nombre Meeting.Active. Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos. Para el modificador /LOG, use un nombre de archivo de registro y la ruta de acceso de Active directory en forma de C:\Logfiles\log.txt. Este conmutador crea un archivo de registro de operaciones en la ubicación designada.

17. Cuando la copia de datos se complete, en el Panel de Control de Lync Server, haga clic en **topología**y, a continuación, haga clic en **estado**.

18. Por cada servidor o grupo donde haya detenido los servicios, seleccione el servidor o el grupo, haga clic en **Acción** y después en **Iniciar todos los servicios**.

19. Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología. Para obtener información detallada, vea [quitar un almacén de archivos](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Administradores del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.

## <a name="see-also"></a>Vea también

[Reasignar un servidor a un almacén de archivos diferente](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Quitar un almacén de archivos](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
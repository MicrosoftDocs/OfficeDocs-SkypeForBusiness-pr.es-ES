---
title: Mover los datos del almacén de archivos a un nuevo almacén de archivos en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para la implementación de Skype empresarial Server 2015, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido. A continuación, debe realizar los siguientes pasos:'
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215591"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Mover los datos del almacén de archivos a un nuevo almacén de archivos en Skype empresarial Server 2015

Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para la implementación de Skype empresarial Server 2015, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido. A continuación, debe realizar los siguientes pasos:

1. Apague los servicios de Skype empresarial Server 2015 que usan el almacén de archivos que planea quitar.

2. Definir el almacén de archivos en Topology Builder y publicar los cambios para poner el nuevo almacén de archivos a disposición de la implementación.

3. Mueva los datos al nuevo almacén de archivos.

4. Reinicie los servidores o los servicios.

5. Si lo desea, puede quitar el recurso compartido de archivos y la carpeta de archivos antiguos.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover los datos de un almacén de archivos a otro nuevo

1. Inicie sesión en un equipo como miembro del grupo Grupo rtcuniversersalserveradmins o CsServerAdministrator donde están instaladas las herramientas administrativas de Skype empresarial Server 2015.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.

4. Para cada grupo de directores, Director, servidor Standard Edition y grupo de servidores front-end que use el almacén de archivos que piensa quitar, seleccione el servidor o grupo de servidores, haga clic en **acción**y, a continuación, haga clic en **detener todos los servicios**.

5. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

6. Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.

7. Seleccione un servidor o grupo de servidores que use el almacén de archivos y realice lo siguiente:

8. Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic en **Editar propiedades**.

9. En **Editar propiedades**, en **asociaciones**, en **almacén de archivos**, haga clic en **nuevo**.

10. En **definir nuevo almacén de archivos**, en **FQDN del servidor de archivos**, escriba el nombre de dominio completo (FQDN) del servidor de archivos. En **recurso compartido de archivos**, escriba el nombre de la carpeta para el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.

     > [!IMPORTANT]
     > En este paso se define un nuevo almacén de archivos para su uso en el generador de topologías. Solo tiene que definirla una vez, no para cada servidor. Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido. Para obtener información detallada, consulte [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Para cada servidor o grupo de servidores que use el almacén de archivos, haga lo siguiente:

12. Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic en **Editar propiedades**.

13. En **Editar propiedades**, en **asociaciones**, en **almacén de archivos**, seleccione el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.

14. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Skype empresarial Server según sea necesario. Para obtener más información, consulte [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Inicie un símbolo del sistema: haga clic en **Inicio**y en **Ejecutar**y, a continuación, escriba cmd.exe.

16. Escriba lo siguiente en la línea de comandos:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > El modificador/S copia sobre archivos, directorios y subdirectorios. El modificador/XF omite los archivos denominados Meeting. Active. Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos. Para el conmutador/LOG, use una ruta de acceso de directorio y un nombre de archivo de registro con el formato C:\Logfiles\log.txt. Este modificador crea un archivo de registro de operaciones en la ubicación indicada.

17. Una vez completada la copia de datos, en el panel de control de Lync Server, haga clic en **topología**y, a continuación, en **Estado**.

18. Para cada servidor o grupo de servidores donde haya detenido los servicios, seleccione el servidor o el grupo de servidores, haga clic en **acción**y, a continuación, haga clic en **iniciar todos los servicios**.

19. Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología. Para obtener información detallada, consulte [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Admins. del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.

## <a name="see-also"></a>Vea también

[Reasignar un servidor a un almacén de archivos diferente](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Quitar un almacén de archivos](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

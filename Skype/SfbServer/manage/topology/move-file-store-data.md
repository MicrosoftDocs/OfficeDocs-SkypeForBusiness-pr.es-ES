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
description: 'Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para la implementación de Skype Empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido. A continuación, debe realizar los pasos siguientes:'
ms.openlocfilehash: dbe9d239680d592a4d309d97577c6a6bad702239
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103176"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Mover datos del almacén de archivos a un nuevo almacén de archivos en Skype Empresarial Server

Si necesita quitar el servidor de archivos que actualmente actúa como almacén de archivos para la implementación de Skype Empresarial Server, o si necesita realizar otros cambios que hagan que el almacén de archivos actual no esté disponible, primero debe crear un nuevo recurso compartido. A continuación, debe realizar los pasos siguientes:

1. Cierre los servicios de Skype Empresarial Server que usan el almacén de archivos que tiene previsto quitar.

2. Defina el almacén de archivos en el Generador de topologías y publique los cambios para que el nuevo almacén de archivos esté disponible para la implementación.

3. Mueva los datos al nuevo almacén de archivos.

4. Reinicie los servidores o servicios.

5. Opcionalmente, quite el recurso compartido de archivos antiguo y la carpeta de archivos.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover los datos de un almacén de archivos a otro nuevo

1. Inicie sesión en un equipo como miembro del grupo RTCUniversersalServerAdmins o CsServerAdministrator donde está instalado Skype Empresarial Server, Herramientas administrativas.

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.

4. Para cada grupo de directores, director, servidor Standard Edition y grupo de servidores front-end que use el almacén de archivos que tiene previsto quitar, seleccione el servidor o grupo de servidores, haga clic en Acción y, a continuación, haga clic en Detener todos los **servicios**.

5. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

6. Iniciar generador de topologías: haga clic **en Inicio**, en **Todos** los programas, en Skype Empresarial **Server** y, a continuación, en Generador de **topologías de Skype Empresarial Server**.

7. Seleccione un servidor o grupo que use el almacén de archivos y haga lo siguiente:

   a. Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic **en Editar propiedades**.

   b. En **Editar propiedades**, en **Asociaciones**, en Almacén **de archivos,** haga clic en **Nuevo**.

   c. En **Definir nuevo almacén de archivos**, en **FQDN** del servidor de archivos, escriba el nombre de dominio completo (FQDN) del servidor de archivos. En **Recurso compartido de** archivos , escriba el nombre de la carpeta para el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.

     > [!IMPORTANT]
     > Este paso define un nuevo almacén de archivos para su uso en el Generador de topologías. Solo se define una vez, no para cada servidor. Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido. Para obtener información detallada, consulte [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).

8. Para cada servidor o grupo que use el almacén de archivos, haga lo siguiente:

   a. Haga clic con el botón secundario en el servidor o grupo de servidores y, a continuación, haga clic **en Editar propiedades**.

   b. En **Editar propiedades**, en **Asociaciones**, en Almacén **de archivos**, seleccione el nuevo recurso compartido de archivos y, a continuación, haga clic en **Aceptar**.

9. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Skype Empresarial Server según sea necesario. Para obtener más información, consulte [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).

10. Inicie un símbolo del sistema: haga clic **en Inicio**, en **Ejecutar** y, a continuación, escriba cmd.exe.

11. Escriba lo siguiente en la línea de comandos:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > El modificador /S copia sobre archivos, directorios y subdirectorios. El modificador /XF omite los archivos denominados Meeting.Active. Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos. Para el modificador /LOG, use una ruta de acceso de directorio y un nombre de archivo de registro en forma de C:\Logfiles\log.txt. Este modificador crea un archivo de registro de operaciones en la ubicación con nombre.

12. Una vez completada la copia de datos, en el Panel de control de Lync Server, haga clic **en Topología** y, a continuación, haga clic en **Estado**.

13. Para cada servidor o grupo en el que detuvo los servicios, seleccione el servidor o grupo de servidores, haga clic en Acción **y,** a continuación, haga clic **en Iniciar todos los servicios**.

14. Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología. Para obtener información detallada, consulte [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).

15. (Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Admins. del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.

## <a name="see-also"></a>Ver también

[Reasignar un servidor a un almacén de archivos diferente](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))

[Quitar un almacén de archivos](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))
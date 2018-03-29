---
title: Mover los datos del almacén de archivos a un almacén de archivos nuevo en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/30/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si debe quitar el servidor de archivos que actualmente está actuando como el almacén de archivos para su Skype para la implementación de Business Server 2015, o si necesita realizar otros cambios que harían que el archivo actual almacén disponible, primero debe crear un nuevo recurso compartido. Después deberá realizar los siguientes pasos:'
ms.openlocfilehash: 567db1e418d5c5c63af8e52146c5d6e1272d7677
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Mover los datos del almacén de archivos a un almacén de archivos nuevo en Skype Empresarial Server 2015
 
Si debe quitar el servidor de archivos que actualmente está actuando como el almacén de archivos para su Skype para la implementación de Business Server 2015, o si necesita realizar otros cambios que harían que el archivo actual almacén disponible, primero debe crear un nuevo recurso compartido. Después deberá realizar los siguientes pasos:
  
1. Apagar el Skype para servicios de 2015 de Business Server que utilizan el almacén de archivos que se va a quitar.
    
2. Defina el almacén de archivos en el generador de topología y publicar los cambios para que el nuevo archivo almacenar disponible para su implementación.
    
3. Mueva los datos al nuevo almacén de archivos.
    
4. Reinicie los servidores o los servicios.
    
5. Opcionalmente, quite el recurso compartido de archivos y la carpeta de archivos antiguos.
    
### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Para mover los datos de un almacén de archivos a otro nuevo

1. Inicie sesión en un equipo como miembro del grupo RTCUniversersalServerAdmins o CsServerAdministrator, donde están instalados el Skype para Business Server 2015, herramientas administrativas.
    
2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **.  
    
4. Para cada grupo de directores, Director, servidor Standard Edition y grupo de Front-End que utiliza el almacén de archivos que se va a quitar, seleccione el servidor o grupo de servidores, haga clic en **acción**y, a continuación, haga clic en **Detener todos los servicios**. 
    
5. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    
6. Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para el generador de topología de Business Server 2015**.
    
7. Seleccione un servidor o un grupo que use el almacén de archivos y realice lo siguiente:
    
   a. Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**.  
    
   b. En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, haga clic en **Nuevo**.
    
   c. En **Definir nuevo almacén de archivos**, en **FQDN del servidor de archivos**, escriba el nombre de dominio completo (FQDN) del servidor de archivos. En **Recurso compartido de archivos**, escriba el nombre de la carpeta del nuevo recurso compartido de archivos y después haga clic en **Aceptar**.
    
    > [!IMPORTANT]
    > Este paso define un nuevo almacén de archivo para su uso en el generador de topología. Debe definirlo solo una vez, no en cada servidor. Antes de publicar la topología, deberá crear el recurso compartido de archivos definido en el servidor de archivos definido. Para obtener más información, vea [definir el almacén de archivos para el Front-End](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx). 
  
8. Por cada servidor o grupo que use el almacén de archivos, realice lo siguiente:
    
   a. Haga clic con el botón derecho en el servidor o en el grupo y, a continuación, haga clic en **Editar propiedades**.
    
   b. En **Editar propiedades** > **Asociaciones** > **Almacén de archivos**, seleccione el nuevo recurso compartido de archivos y haga clic en **Aceptar**.
    
9. Publicar la topología, comprobar el estado de la replicación y vuelva a ejecutar el Skype para el Asistente para implementación de Business Server según sea necesario. Para obtener más información, consulte [Procedimientos comunes para quitar servidores de Lync y componentes](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).
    
10. Inicie un símbolo del sistema: haga clic en **Inicio**, haga clic en **Ejecutar**y, a continuación, escriba cmd.exe.
    
11. En la línea de comandos, escriba:
    
     ```
     Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>

     ```

    > [!TIP]
    > El conmutador /S copia los archivos, directorios y subdirectorios. El conmutador /XF omite los archivos con el nombre Meeting.Active. Las versiones actuales de robocopy.exe con el conmutador /MT dispara considerablemente la velocidad de copiado, debido a que usa varios subprocesos. Para el modificador /LOG, utilice un nombre de archivo de registro y la ruta de acceso de directorio en forma de C:\Logfiles\log.txt. Este conmutador crea un archivo de registro de operaciones en la ubicación designada. 
  
12. Una vez finalizada, en el Panel de Control de Lync Server la copia de datos, haga clic en **topología**y, a continuación, haga clic en **estado**.
    
13. Por cada servidor o grupo donde haya detenido los servicios, seleccione el servidor o el grupo, haga clic en **Acción** y después en **Iniciar todos los servicios**. 
    
14. Quite el antiguo almacén de archivos de la topología y, a continuación, publique la topología. Para obtener más información, vea [quitar un almacén de archivos](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).
    
15. (Opcional) Inicie sesión como miembro del grupo Administradores local o del grupo Administradores del dominio en el equipo que contenía el almacén de archivos que acaba de eliminar y quite el directorio y el recurso compartido de archivos anteriores.
    
## <a name="see-also"></a>Vea también


[Reasignar un servidor a otro almacén de archivo](http://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)
  
[Quitar un almacén de archivos](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)


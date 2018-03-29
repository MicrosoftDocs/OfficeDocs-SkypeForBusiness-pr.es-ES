---
title: Agregar bases de datos de archivado a una implementación existente en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumen: Leer este tema para aprender a agregar bases de datos de archiving a su Skype para la implementación de Business Server 2015.'
ms.openlocfilehash: 09185eed2a8bd0cc9b2a03fc6361abeadbd01829
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server-2015"></a>Agregar bases de datos de archivado a una implementación existente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a agregar bases de datos de archiving a su Skype para la implementación de Business Server 2015.
  
Es preciso incorporar el archivado a la topología para poder configurar la implementación a fin de admitir el archivado. La información de este tema explica cómo utilizar el generador de topología para:
  
- Agregar una base de datos de archivado a la topología.
    
- Publicar la topología actualizados para agregar la base de datos de archiving a su Skype para la implementación de Business Server 2015.
    
> [!NOTE]
> Si desea utilizar la integración de Microsoft Exchange para almacenar el archiving de datos y archivos en servidores de Exchange para todos los usuarios en la implementación, no especifique información **almacenar Archiving de SQL Server** o **SQL Server utilizar el almacén del reflejo** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Agregar una base de datos de archivado a la topología

1. En un equipo que está ejecutando Skype para Business Server o en el que el Skype para herramientas administrativas Business Server están instaladas, inicie sesión con una cuenta que sea miembro del grupo local de usuarios (o una cuenta con derechos de usuario equivalentes).
    
2. Iniciar el generador de topología.
    
3. En el árbol de consola, vaya al grupo de servidores front-end en el que desee implementar el archivado y, luego, haga clic en el nombre de dicho grupo donde desee implementar el archivado.
    
4. En el menú **Acción**, haga clic en **Editar propiedades**. 
    
5. En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.
    
6. Desplácese hacia abajo hasta **Archivado**.
    
7. Marque la casilla **Archivado**.
    
8. En **almacenar el Archiving de SQL Server,** siga uno de estos procedimientos:
    
   - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar. Si todos los usuarios están alojados en Microsoft Exchange Server 2013 o superior, puede archivar Skype para comunicaciones empresariales para todos los usuarios de Exchange. En este caso, no es necesario configurar SQL Server Archiving de almacén.
    
   - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server** , haga lo siguiente:
    
   - En **Nombre de dominio completo de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo almacén de SQL Server.
    
   - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
   - Si la instancia de SQL Server especificada está en una relación de reflejo, active la casilla de verificación **SQL de esta instancia es de reflejo de la relación** y, a continuación, en **número de puerto de espejo**, especifique el número de puerto.
    
9. Si desea utilizar el reflejo de almacén de SQL Server, seleccione **Habilitar SQL Server almacén espejado**y, a continuación, haga lo siguiente:
    
   - Para utilizar un almacén de SQL Server existente para el reflejo, en el cuadro de lista desplegable **espejo de almacenamiento de Archiving de SQL Server** , haga clic en el nombre del almacén de SQL Server que desea utilizar para la creación de reflejo.
    
   - Para especificar un nuevo almacén de SQL Server para la creación de reflejo, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server** , siga uno de estos procedimientos:
    
    a. En el **FQDN de SQL Server**, especifique el FQDN de la de SQL Server en el que desea crear el nuevo almacén de SQL Server.
    
    b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
    c. Si la instancia de SQL Server especificada está en una relación de reflejo, active la casilla de verificación **SQL de esta instancia es de reflejo de la relación** y, a continuación, en **número de puerto de espejo**, especifique el número de puerto.
    
   - Si habilita la creación de reflejos de SQL Server y desea incluir un SQL Server reflejo a testigo (una tercera independiente de SQL Server instancia que puede detectar el estado de las instancias de SQL Server y el espejo primarios), seleccione la **testigo de espejado de usar SQL Server para habilitar automática conmutación por error** y, a continuación, siga uno de los siguientes:
    
    a. En el **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo SQL Server testigo de creación de reflejo.
    
    b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
    
    c. Si la instancia de SQL Server especificada está en una relación de reflejo, active la casilla de verificación **SQL de esta instancia es de reflejo de la relación** y, a continuación, en **número de puerto de espejo**, especifique el número de puerto.
    
10. Para guardar la configuración, haga clic en **Aceptar**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publicar la topología actualizada para agregar una base de datos de archivado a la implementación

1. En un equipo que está ejecutando Skype para Business Server o en el que el Skype para herramientas administrativas Business Server están instaladas, inicie sesión con una cuenta que sea miembro del grupo local de usuarios (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios local, pero para publicar una topología, que es necesario para agregar un servidor a la topología, debe utilizar una cuenta que sea miembro del grupo **Administradores de dominio** y el **RTCUniversalServer Administradores de** grupo y que tiene permisos de control total (leer, escribir y modificar) en el recurso compartido de archivo que está utilizando para el Skype para el almacén de archivos de Business Server (para que el generador de topología puede configurar la lista de control de acceso discrecional (DACL), o una cuenta con derechos equivalentes.
  
2. Abra la topología que creó en la sección anterior mediante el generador de topología.
    
3. En el árbol de consola, haga clic derecho en **Skype para Business Server**y, a continuación, haga clic en **Publicar la topología**.
    
4. En la página **Publicar la topología**, haga clic en **Siguiente**.
    
5. En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y, luego, haga clic en **Siguiente**. 
    
    > [!NOTE]
    > Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos. > Sólo bases de datos en servidores dedicados de SQL pueden instalarse utilizando el generador de topología. Las bases de datos en servidores SQL Server que se han combinado con otros componentes de servidor necesitan instalarse al ejecutar la instalación local en dicho equipo. 
  
6. En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.
    
    > [!IMPORTANT]
    > Una vez publicada la topología, necesita configurar las opciones y las directivas para el archivado antes de que se pueda archivar cualquier contenido. Para obtener información detallada, vea [Configurar opciones de Skype para Business Server 2015 de archiving](configure-archiving-options.md) configurar políticas y [archiving para Skype para Business Server 2015](configure-archiving-policies.md). 
  


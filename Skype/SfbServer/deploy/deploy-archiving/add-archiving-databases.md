---
title: Agregar bases de datos de archivado a una implementación existente de Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumen: Lea este tema para obtener información sobre cómo agregar bases de datos de archivado a su Skype para la implementación de Business Server.'
ms.openlocfilehash: 083b6329cdf27331ba861b96a74f94e2ae5aa912
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229463"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Agregar bases de datos de archivado a una implementación existente de Skype para Business Server
 
**Resumen:** Lea este tema para obtener información sobre cómo agregar bases de datos de archivado a su Skype para la implementación de Business Server.
  
Es preciso incorporar el archivado a la topología para poder configurar la implementación a fin de admitir el archivado. La información de este tema explica cómo usar el generador de topología para:
  
- Agregar una base de datos de archivado a la topología.
    
- Publicar la topología actualizada para agregar la base de datos de archivado a su Skype para la implementación de Business Server.
    
> [!NOTE]
> Si desea utilizar la integración de Microsoft Exchange para almacenar datos de archivado y los archivos en los servidores de Exchange para todos los usuarios de la implementación, no especifique información de **almacén de SQL Server de archivado** o **la creación de reflejo de almacén de SQL Server de uso** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Agregar una base de datos de archivado a la topología

1. En un equipo que ejecuta Skype para Business Server o en el que el Skype para instaladas las herramientas administrativas de Business Server, inicie sesión con una cuenta que sea miembro del grupo local de usuarios (o una cuenta con derechos de usuario equivalentes).
    
2. Iniciar el generador de topología.
    
3. En el árbol de consola, vaya al grupo de servidores front-end en el que desee implementar el archivado y, luego, haga clic en el nombre de dicho grupo donde desee implementar el archivado.
    
4. En el menú **Acción**, haga clic en **Editar propiedades**. 
    
5. En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.
    
6. Desplácese hacia abajo hasta **Archivado**.
    
7. Marque la casilla **Archivado**.
    
8. En **almacén de SQL Server de archivado,** siga uno de estos procedimientos:
    
   - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar. Si todos los usuarios están hospedados en Microsoft Exchange Server 2013, o por encima, puede archivar Skype para comunicaciones de negocio para todos los usuarios de Exchange. En este caso, no es necesario configurar el almacenamiento de archivado de SQL Server.
    
   - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server** , realice lo siguiente:
    
   - En **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo almacén de SQL Server.
    
   - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
   - Si la instancia de SQL Server especificada está en una relación de la creación de reflejo, active la casilla de verificación **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
    
9. Si desea usar la creación de reflejo del almacén de SQL Server, seleccione el **almacén de SQL Server de habilitar la creación de reflejo**y, a continuación, haga lo siguiente:
    
   - Para usar un almacén de SQL Server existente para la creación de reflejos, en el cuadro de lista desplegable de **reflejo del almacén de SQL Server de archivado** , haga clic en el nombre del almacén de SQL Server que desea usar para la creación de reflejo.
    
   - Para especificar un nuevo almacén de SQL Server para la creación de reflejos, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server** , realice una de las siguientes opciones:
    
     a. En **FQDN de SQL Server**, especifique el FQDN del servidor SQL en el que desea crear el nuevo almacén de SQL Server.
    
     b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
     c. Si la instancia de SQL Server especificada está en una relación de la creación de reflejo, active la casilla de verificación **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
    
   - Si habilita la creación de reflejos de SQL Server y desea incluir un testigo (independiente, tercera instancia de SQL Server que puede detectar el estado de las instancias de SQL Server y el servidor reflejado principales) la creación de reflejos de SQL Server, seleccione la **testigo de reflejo de utilizar SQL Server para habilitar automática conmutación por error** casilla de verificación y, a continuación, realice uno de los siguientes:
    
     a. En **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo testigo de reflejo de SQL Server.
    
     b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
    
     c. Si la instancia de SQL Server especificada está en una relación de la creación de reflejo, active la casilla de verificación **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
    
10. Para guardar la configuración, haga clic en **Aceptar**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publicar la topología actualizada para agregar una base de datos de archivado a la implementación

1. En un equipo que ejecuta Skype para Business Server o en el que el Skype para instaladas las herramientas administrativas de Business Server, inicie sesión con una cuenta que sea miembro del grupo local de usuarios (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología mediante una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, que es necesario para agregar un servidor a la topología, debe usar una cuenta que sea miembro del grupo **Administradores** del dominio y el **RTCUniversalServer Los administradores de** grupo y que tiene permisos de control total (leer, escribir y modificar) en el que va a usar para la Skype para almacén de archivos de Business Server (para que el generador de topología pueda configurar la lista de control de acceso discrecional (DACL), o un recurso compartido de archivos cuenta con derechos equivalentes.
  
2. Abra la topología que creó en la sección anterior con el generador de topología.
    
3. En el árbol de consola, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Publicar topología**.
    
4. En la página **Publicar la topología**, haga clic en **Siguiente**.
    
5. En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y, luego, haga clic en **Siguiente**. 
    
    > [!NOTE]
    > Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos. > bases de datos sólo en servidores dedicada de SQL Server se pueden instalar mediante el generador de topología. Las bases de datos en servidores SQL Server que se han combinado con otros componentes de servidor necesitan instalarse al ejecutar la instalación local en dicho equipo. 
  
6. En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.
    
    > [!IMPORTANT]
    > Una vez publicada la topología, necesita configurar las opciones y las directivas para el archivado antes de que se pueda archivar cualquier contenido. Para obtener información detallada, vea [Configurar opciones de Skype para Business Server de archivado](configure-archiving-options.md) y [Configurar directivas de Skype para Business Server de archivado](configure-archiving-policies.md). 
  


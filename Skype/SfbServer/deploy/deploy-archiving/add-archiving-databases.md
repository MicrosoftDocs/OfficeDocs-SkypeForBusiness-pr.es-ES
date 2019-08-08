---
title: Agregar bases de datos de archivado a una implementación existente en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumen: Lea este tema para obtener información sobre cómo agregar bases de datos de archivado a su implementación de Skype empresarial Server.'
ms.openlocfilehash: b7d429206e003042922b9b9cae6de420fdf517bb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234378"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Agregar bases de datos de archivado a una implementación existente en Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo agregar bases de datos de archivado a su implementación de Skype empresarial Server.
  
Es preciso incorporar el archivado a la topología para poder configurar la implementación a fin de admitir el archivado. La información de este tema explica cómo usar el generador de topología para:
  
- Agregar una base de datos de archivado a la topología.
    
- Publique la topología actualizada para agregar la base de datos de archivado a su implementación de Skype empresarial Server.
    
> [!NOTE]
> Si desea usar la integración de Microsoft Exchange para almacenar los datos y archivos de los servidores de Exchange de todos los usuarios de su implementación, no especifique el **almacenamiento de SQL Server** en el almacén o use la información de reflejo de la **tienda de SQL Server** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Agregar una base de datos de archivado a la topología

1. En un equipo que ejecute Skype empresarial Server o en el que estén instaladas las herramientas administrativas de Skype empresarial Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
2. Iniciar el generador de topología.
    
3. En el árbol de consola, vaya al grupo de servidores front-end en el que desee implementar el archivado y, luego, haga clic en el nombre de dicho grupo donde desee implementar el archivado.
    
4. En el menú **Acción**, haga clic en **Editar propiedades**. 
    
5. En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.
    
6. Desplácese hacia abajo hasta **Archivado**.
    
7. Marque la casilla **Archivado**.
    
8. En **archivar almacén de SQL Server,** realice una de las siguientes acciones:
    
   - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar. Si todos los usuarios están alojados en Microsoft Exchange Server 2013 o una versión posterior, puede archivar las comunicaciones de Skype empresarial para todos los usuarios de Exchange. En este caso, no es necesario configurar el almacén de archivado de SQL Server.
    
   - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:
    
   - En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo almacén de SQL Server.
    
   - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
   - Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
    
9. Si desea usar el reflejo de la tienda SQL Server, seleccione **Habilitar reflejo de la tienda SQL Server**y, a continuación, haga lo siguiente:
    
   - Para usar un almacén de SQL Server existente para la creación de reflejo, en el cuadro de lista desplegable archivado reflejado de **SQL Server** , haga clic en el nombre del almacén de SQL Server que desea usar para el reflejo.
    
   - Para especificar un nuevo almacén de SQL Server para la creación de reflejo, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:
    
     a. En **FQDN de SQL Server**, especifique el nombre completo del servidor SQL Server en el que desea crear el nuevo almacén de SQL Server.
    
     b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
     c. Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
    
   - Si habilita el reflejo de SQL Server y desea incluir un testigo de reflejo de SQL Server (una tercera, instancia de SQL Server independiente que puede detectar el estado del servidor SQL Server principal y de las instancias reflejadas), seleccione el **testigo de reflejo de SQL Server para habilitar la activación automática. casilla de verificación conmutación por error** y realice una de las siguientes acciones:
    
     a. En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo testigo de reflejo de SQL Server.
    
     b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
    
     c. Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
    
10. Para guardar la configuración, haga clic en **Aceptar**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publicar la topología actualizada para agregar una base de datos de archivado a la implementación

1. En un equipo que ejecute Skype empresarial Server o en el que estén instaladas las herramientas administrativas de Skype empresarial Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para agregar un servidor a la topología, debe usar una cuenta que sea miembro del grupo de **administradores de dominio** y la de **RTCUniversalServer Grupo administradores** y que tiene permisos de control total (lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Skype empresarial Server (para que el generador de topología pueda configurar la lista de control de acceso discrecional (DACL) obligatoria o una cuenta con derechos equivalentes.
  
2. Abra la topología que creó en la sección anterior con el generador de topologías.
    
3. En el árbol de consola, haga clic con el botón secundario en **Skype empresarial Server**y, a continuación, haga clic en **publicar topología**.
    
4. En la página **Publicar la topología**, haga clic en **Siguiente**.
    
5. En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y, luego, haga clic en **Siguiente**. 
    
    > [!NOTE]
    > Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos. > solo se pueden instalar bases de datos en servidores SQL dedicados mediante el generador de topologías. Las bases de datos en servidores SQL Server que se han combinado con otros componentes de servidor necesitan instalarse al ejecutar la instalación local en dicho equipo. 
  
6. En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.
    
    > [!IMPORTANT]
    > Una vez publicada la topología, necesita configurar las opciones y las directivas para el archivado antes de que se pueda archivar cualquier contenido. Para obtener más información, vea [configurar las opciones de archivado para Skype empresarial Server](configure-archiving-options.md) y [configurar directivas de archivado para Skype empresarial Server](configure-archiving-policies.md). 
  


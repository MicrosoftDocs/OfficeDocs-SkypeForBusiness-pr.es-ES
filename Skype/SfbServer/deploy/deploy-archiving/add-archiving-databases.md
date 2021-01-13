---
title: Agregar bases de datos de archivado a una implementación existente en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumen: lea este tema para obtener información sobre cómo agregar bases de datos de archivado a la implementación de Skype Empresarial Server.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820680"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Agregar bases de datos de archivado a una implementación existente en Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo agregar bases de datos de archivado a su implementación de Skype Empresarial Server.
  
Debe incorporar el archivado a la topología para poder configurar la implementación a fin de admitir el archivado. La información de este tema explica cómo usar topology Builder para:
  
- Agregue una base de datos de archivado a la topología.
    
- Publique la topología actualizada para agregar la base de datos de archivado a su implementación de Skype Empresarial Server.
    
> [!NOTE]
> Si desea usar la integración de Microsoft Exchange para almacenar archivos y datos de archivado en servidores de Exchange para todos los usuarios de la implementación, no especifique el almacén de **SQL Server** de archivado ni use la información de creación de reflejos del almacén **de SQL Server.**
  
### <a name="add-an-archiving-database-to-your-topology"></a>Agregar una base de datos de archivado a la topología

1. En un equipo que ejecute Skype Empresarial Server o en el que estén instaladas las herramientas administrativas de Skype Empresarial Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
2. Inicie el Generador de topologías.
    
3. En el árbol de la consola, vaya al grupo de servidores front-end en el que desea implementar el archivado y, a continuación, haga clic en el nombre del grupo de servidores front-end donde desea implementar el archivado.
    
4. En el menú **Acción**, haga clic en **Editar propiedades**. 
    
5. En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.
    
6. Desplácese a  **Archivado**.
    
7. Seleccione la casilla **Archivado**.
    
8. En **Almacén SQL Server archivado,** realice una de las siguientes acciones:
    
   - Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar. Si todos los usuarios están en Microsoft Exchange Server 2013 o posterior, puede archivar las comunicaciones de Skype Empresarial para todos los usuarios de Exchange. En este caso, no es necesario configurar el SQL Server de archivado.
    
   - Para especificar un nuevo almacén SQL Server, haga clic  en Nuevo y, a continuación, en el cuadro de diálogo Definir nuevo almacén de SQL Server, haga lo siguiente: 
    
   - En **SQL Server FQDN,** especifique el FQDN del servidor en el que desea crear el nuevo SQL Server almacén.
    
   - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre** y especifique la instancia que desee usar.
    
   - Si la instancia SQL Server especificada está en una relación de creación de reflejos, active la casilla Esta instancia **SQL** está en relación de reflejo y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.
    
9. Si quieres usar la creación SQL Server reflejo del almacén, selecciona **Habilitar SQL Server** creación de reflejos de la Tienda y, a continuación, haz lo siguiente:
    
   - Para usar un almacén de SQL Server existente para  la creación de reflejos, en el cuadro de lista desplegable Reflejo del almacén de SQL Server de archivado, haga clic en el nombre del almacén de SQL Server que desea usar para la creación de reflejos.
    
   - Para especificar un nuevo almacén SQL Server para creación de reflejos, haga clic en Nuevo y, a continuación, en el cuadro de diálogo Definir nuevo almacén de **SQL Server,** realice una de las siguientes acciones:
    
     a. En **SQL Server FQDN,** especifique el FQDN de la SQL Server en la que desea crear el nuevo SQL Server almacén.
    
     b. Haga clic en **Instancia predeterminada** para utilizar la instancia predeterminada o, para especificar una instancia diferente, haga clic en **Instancia denominada** y, a continuación, haga clic en la instancia que desee utilizar.
    
     c. Si la instancia SQL Server especificada está en una relación de creación de reflejos, active la casilla Esta instancia **SQL** está en relación de reflejo y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.
    
   - Si habilita la creación de reflejos de SQL Server y desea incluir un testigo de creación de reflejo de SQL Server (una tercera instancia de SQL Server independiente que pueda detectar el estado de las instancias principales de SQL Server y de reflejo), active la casilla Usar testigo de creación de reflejos de SQL Server para habilitar la conmutación por error automática y, **a** continuación, realice una de las siguientes acciones:
    
     a. En **SQL Server FQDN,** especifique el FQDN del servidor en el que desea crear el nuevo testigo de creación SQL Server reflejo.
    
     b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
    
     c. Si la instancia SQL Server especificada está en una relación de creación de reflejos, active la casilla Esta instancia **SQL** está en relación de reflejo y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.
    
10. Para guardar la configuración, haga clic en **Aceptar**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publicar la topología actualizada para agregar una base de datos de archivado a la implementación

1. En un equipo que ejecute Skype Empresarial Server o en el que estén instaladas las herramientas administrativas de Skype Empresarial Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios local (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología mediante una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para agregar  un servidor a la topología, debe usar una cuenta que sea miembro del grupo Administradores de dominio y del grupo **RTCUniversalServerAdmins,** y que tenga permisos de control total (lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Skype Empresarial Server (para que el Generador de topologías pueda configurar la lista de control de acceso discrecional (DACL) necesaria o una cuenta con derechos equivalentes.
  
2. Abra la topología que creó en la sección anterior con el Generador de topologías.
    
3. En el árbol de la consola, haga clic con el botón secundario **en Skype Empresarial Server** y, a continuación, haga clic en Publicar **topología.**
    
4. En la página **Publicar la topología**, haga clic en **Siguiente**.
    
5. En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y haga clic en **Siguiente**. 
    
    > [!NOTE]
    > Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos. > solo las bases de datos en servidores SQL dedicados se pueden instalar mediante el Generador de topologías. Las bases de datos en los servidores SQL Server que están instaladas con otros componentes de servidor se deben instalar ejecutando la configuración local en el equipo. 
  
6. En la página **Asistente de publicación completado**, compruebe que la topología se haya publicado correctamente y, a continuación, haga clic en **Finalizar**.
    
    > [!IMPORTANT]
    > Una vez publicada la topología, debe configurar opciones y directivas para el archivado antes de que se pueda archivar cualquier contenido. Para obtener más información, consulte [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and Configure archiving policies for Skype for Business [Server](configure-archiving-policies.md). 
  


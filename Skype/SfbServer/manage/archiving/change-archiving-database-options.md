---
title: Cambiar las opciones de base de datos de archivado en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumen: Obtenga información sobre cómo cambiar las opciones de base de datos archivado de Skype para Business Server.'
ms.openlocfilehash: 8e2c1f0ef90f193f157b1387f1fa65278efea60d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891233"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Cambiar las opciones de base de datos de archivado en Skype para Business Server

**Resumen:** Obtenga información sobre cómo cambiar las opciones de base de datos archivado de Skype para Business Server.
  
Si implementa el archivado con almacenamiento de SQL Server para el archivado de almacenamiento para cualquiera de los usuarios, puede realizar la base de datos siguiente cambios de almacenamiento de información:
  
- Usar una base de datos de SQL Server diferente para el almacenamiento de archivado. Esto incluye la base de datos de archivado principal y cualquier base de datos que se usa para la creación de reflejos de SQL Server.
    
- Cambiar a la integración de Microsoft Exchange para almacenar datos de archivado y los archivos en los servidores de Exchange. Si todos los usuarios están hospedados en los servidores de Exchange y desea usar el almacenamiento de información de Microsoft Exchange para todos los usuarios de la implementación, debe quitar las bases de datos de almacén de SQL Server de la topología. 
    
Para realizar cualquiera de estos cambios, debe ejecutar el generador de topología, realice los cambios y, a continuación, vuelva a publicar la topología. No se especifica la información de **almacén de SQL Server de archivado** o **la creación de reflejo de almacén de habilitar SQL Server** , a menos que tenga Skype para los usuarios de negocio que no están hospedados en servidores de Exchange.
  
## <a name="change-archiving-database-options"></a>Cambiar las opciones de base de datos de archivado

1. En un equipo que ejecuta Skype para Business Server o en el que el Skype para instaladas las herramientas administrativas de Business Server, inicie sesión con una cuenta que sea miembro del grupo local de usuarios (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología mediante una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, que es necesario para agregar un componente a la topología, debe usar una cuenta que sea miembro del grupo **Administradores** del dominio y el **RTCUniversalSer verAdmins** grupo y que tiene permisos de control total (es decir, leer, escribir y modificar) en el recurso compartido de archivos que va a usar para la Skype para almacén de archivos de Business Server (es decir, de modo que el generador de topología puede configurar el control de acceso discrecional requerido listas (DACL), o una cuenta con derechos equivalentes.
  
2. Iniciar el generador de topología.
    
3. En el árbol de consola, explore el grupo de servidores front-end en los que ha implementado el servidor de archivado y, luego, haga clic en el nombre del grupo de servidores front-end al que quiere modificar las opciones de la base de datos.
    
4. En el menú **Acción**, haga clic en **Editar propiedades**. 
    
5. En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.
    
6. Desplácese hacia abajo hasta **Archivado**.
    
7. En **Archivado**, haga lo siguiente:
    
   - Para cambiar a otro almacén de SQL Server existente, en **Almacén SQL Server de archivado**, en el cuadro de desplegable, haga lo siguiente:
    
   - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
    
   - Para especificar un nuevo almacén de SQL Server, haga clic en **Nuevo** y, en el cuadro de diálogo **Definir un nuevo almacén de SQL Server**, haga lo siguiente:
    
     - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
    
     - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server** , realice lo siguiente:
    
       - En **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo almacén de SQL Server.
    
       - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
       - Si la instancia de SQL Server especificada está en una relación de la creación de reflejo, active la casilla de verificación **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
    
   - Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, luego, haga lo siguiente:
    
     - Para usar un almacén de SQL Server existente para la creación de reflejos, en el cuadro de lista desplegable de **reflejo del almacén de SQL Server de archivado** , haga clic en el nombre del almacén de SQL Server que desea usar para la creación de reflejo.
    
     - Para especificar un nuevo almacén de SQL Server para la creación de reflejos, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server** , realice una de las siguientes opciones:
    
       a. En **FQDN de SQL Server**, especifique el FQDN del servidor SQL en el que desea crear el nuevo almacén de SQL Server.
    
       b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
       c. Si la instancia de SQL Server especificada está en una relación de la creación de reflejo, active la casilla de verificación **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
    
   - Si habilita la creación de reflejos de SQL Server y desea agregar o cambiar un testigo (independiente, tercera instancia de SQL Server que puede detectar el estado de las instancias de servidor principal y reflejada de SQL Server principales) la creación de reflejos de SQL Server, seleccione el testigo de reflejo de utilizar SQL Server **a habilitar la conmutación por error automática** casilla de verificación y, a continuación, realice uno de los siguientes:
    
      a. En **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo testigo de reflejo de SQL Server.
    
      b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
    
      c. Si la instancia de SQL Server especificada está en una relación de la creación de reflejo, active la casilla de verificación **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
    
   - Para cambiar a la integración de Microsoft Exchange para almacenar datos de archivado y los archivos en los servidores de Exchange (si todos los usuarios de su implementación están hospedados en los servidores de Exchange), elimine toda la información de las bases de datos de archivado.
    
     > [!IMPORTANT]
     > Si tiene cualquier Skype para los usuarios de negocio que no están hospedados en servidores de Exchange, no elimine la información del almacén de SQL Server. 
  
8. Para guardar la configuración, haga clic en **Aceptar**.
    
    > [!IMPORTANT]
    > Los cambios que realice en el generador no tendrá efecto hasta que se publique la nueva topología. Para obtener información detallada, vea [las bases de datos de archivado de agregar a una implementación existente de Skype para Business Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Cambiar la ubicación de la base de datos de archivado mediante el uso de Windows PowerShell

En la mayoría de los casos, no necesitará cambiar la ubicación de la base de datos de archivado, que se especifica al instalar el servidor de archivado. Sin embargo, si se debe producir un error de hardware o a otro problema, puede apuntar el servidor de archivado a una nueva base de datos mediante el cmdlet **Set-CsArchivingServer** .
  
En el ejemplo siguiente se cambia la ubicación de la base de datos de archivado para el ArchivingServer:atl-cs-001.contoso.com el servidor de archivado. En este ejemplo, la nueva base de datos se encuentra en ArchivingDatabase:atl-sql-001.contoso.com:
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```



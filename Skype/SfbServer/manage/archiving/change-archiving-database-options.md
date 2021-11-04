---
title: Cambiar las opciones de base de datos de archivado en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumen: obtenga información sobre cómo cambiar las opciones de la base de datos de archivado para Skype Empresarial Server.'
ms.openlocfilehash: 240d590b7f22e4756351939be6ecab55ea108b79
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767938"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Cambiar las opciones de base de datos de archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo cambiar las opciones de la base de datos de archivado Skype Empresarial Server.
  
Si implementa el archivado con SQL Server para el almacenamiento de archivado para cualquiera de los usuarios, puede realizar los siguientes cambios en el almacenamiento de la base de datos:
  
- Use una base de SQL Server de datos diferente para el almacenamiento de archivado. Esto incluye la base de datos de archivado principal y cualquier base de datos que use para SQL Server creación de reflejo.
    
- Cambie a La integración Exchange Microsoft para almacenar datos de archivado y archivos en Exchange servidores. Si todos los usuarios se encuentran en sus servidores de Exchange y desea usar el almacenamiento de Microsoft Exchange para todos los usuarios de la implementación, debe quitar las bases de datos del almacén SQL Server de la topología. 
    
Para realizar cualquiera de estos cambios, debe ejecutar el Generador de topologías, realizar los cambios y, a continuación, volver a publicar la topología. No especifique **El almacén de SQL Server** ni Habilitar la información de creación de reflejo de SQL Server almacén, **a** menos que tenga Skype Empresarial usuarios que no estén Exchange servidores.
  
## <a name="change-archiving-database-options"></a>Cambiar las opciones de base de datos de archivado

1. En un equipo que ejecuta Skype Empresarial Server o en el que están instaladas las herramientas administrativas de Skype Empresarial Server, inicie sesión con una cuenta que sea miembro del grupo usuarios local (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología mediante una cuenta que sea miembro del grupo usuarios local, pero para publicar una topología, que es necesaria para agregar  un componente a la topología, debe usar una cuenta que sea miembro del grupo Administradores de dominio y del grupo **RTCUniversalServerAdmins,** y que tenga permisos de control total (es decir,  read, write, and modify) on the file share that you are using for the Skype Empresarial Server file store (that is, so that Topology Builder can configure the discretionary access control lists (DACLs), or an account with equivalent rights.
  
2. Inicie el Generador de topologías.
    
3. En el árbol de consola, explore el grupo de servidores front-end en los que ha implementado el servidor de archivado y, a continuación, haga clic en el nombre del grupo de servidores front-end al que quiere modificar las opciones de la base de datos.
    
4. En el menú **Acción**, haga clic en **Editar propiedades**. 
    
5. En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.
    
6. Desplácese hacia abajo hasta **Servidor de archivado**.
    
7. En **Servidor de archivado**, haga lo siguiente:
    
   - Para cambiar a un almacén de SQL Server existente diferente, en  **Almacén SQL Server de archivado**, en el cuadro de desplegable, haga lo siguiente:
    
   - Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
    
   - Para especificar un nuevo almacén de SQL Server, haga clic en **Nuevo** y en el cuadro de diálogo **Definir un nuevo almacén de SQL Server** lleve a cabo lo siguiente:
    
     - Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
    
     - Para especificar un nuevo SQL Server, haga clic en **Nuevo** y, a continuación, en el cuadro de diálogo Definir nuevo **SQL Server store,** haga lo siguiente:
    
       - En **SQL Server FQDN**, especifique el FQDN del servidor en el que desea crear el nuevo SQL Server almacén.
    
       - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre** y especifique la instancia que desee usar.
    
       - Si la instancia SQL Server especificada está en una relación de creación de reflejo, active la casilla Esta instancia **SQL** está en relación de creación de reflejos y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.
    
   - Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, a continuación, haga lo siguiente:
    
     - Para usar un almacén de SQL Server existente para crear reflejos, en el cuadro de lista desplegable Reflejo del almacén de **archivado SQL Server,** haga clic en el nombre del almacén de SQL Server que desea usar para crear reflejos.
    
     - Para especificar un nuevo SQL Server de creación de reflejos, haga clic en Nuevo **y,** a continuación, en el cuadro de diálogo Definir nuevo almacén de **SQL Server,** realice una de las siguientes acciones:
    
       a. En **SQL Server FQDN**, especifique el FQDN de la SQL Server en la que desea crear el nuevo SQL Server almacén.
    
       b. Haga clic en **Instancia predeterminada** para utilizar la instancia predeterminada o, para especificar una instancia diferente, haga clic en **Instancia denominada** y, a continuación, haga clic en la instancia que desee utilizar.
    
       c. Si la instancia SQL Server especificada está en una relación de creación de reflejo, active la casilla Esta instancia **SQL** está en relación de creación de reflejos y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.
    
   - Si habilita la creación de reflejos de SQL Server y desea agregar o cambiar un testigo de creación de reflejo de SQL Server (una tercera instancia de SQL Server independiente que pueda detectar el estado del servidor principal de SQL Server y las instancias reflejadas SQL Server), active la casilla Usar un testigo de creación de reflejos para habilitar la conmutación por error automática **y, a** continuación,  realice una de las siguientes acciones:
    
      a. En **SQL Server FQDN**, especifique el FQDN del servidor en el que desea crear el nuevo testigo SQL Server creación de reflejo.
    
      b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
    
      c. Si la instancia SQL Server especificada está en una relación de creación de reflejo, active la casilla Esta instancia **SQL** está en relación de creación de reflejos y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.
    
   - Para cambiar a la integración de Microsoft Exchange para almacenar datos de archivado y archivos en servidores Exchange (si todos los usuarios de la implementación se encuentran en los servidores de Exchange), elimine toda la información de las bases de datos de archivado.
    
     > [!IMPORTANT]
     > Si tiene algún usuario Skype Empresarial que no se encuentra en Exchange servidores, no elimine la información SQL Server almacén. 
  
8. Para guardar la configuración, haga clic en **Aceptar**.
    
    > [!IMPORTANT]
    > Los cambios realizados en el Generador de topologías no tienen efecto hasta que publique la nueva topología. Para obtener más información, vea [Agregar bases de datos de archivado a una implementación existente en Skype Empresarial Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Cambie la ubicación de la base de datos de archivado mediante Windows PowerShell

En la mayoría de los casos, no tendrá que cambiar la ubicación de la base de datos de archivado, que se especifica al instalar el servidor de archivado. Sin embargo, si se produce un error de hardware u otro problema, puede apuntar el servidor de archivado a una nueva base de datos mediante el cmdlet **Set-CsArchivingServer.**
  
En el ejemplo siguiente se cambia la ubicación de la base de datos de archivado para el servidor de archivado ArchivingServer:atl-cs-001.contoso.com Archiving Server. En este ejemplo, la nueva base de datos se encuentra en ArchivingDatabase:atl-sql-001.contoso.com:
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```



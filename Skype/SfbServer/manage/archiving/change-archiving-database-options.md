---
title: Cambiar las opciones de base de datos de archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumen: Conozca cómo cambiar opciones de base de datos archivado de Skype para Business Server 2015.'
ms.openlocfilehash: 5bb7ee9329cc3fa7a0795115f9a0d11768ab7aa4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="change-archiving-database-options-in-skype-for-business-server-2015"></a>Cambiar las opciones de base de datos de archivado en Skype Empresarial Server 2015

**Resumen:** Obtenga información sobre cómo cambiar opciones de base de datos archivado de Skype para Business Server 2015.
  
Si se implementa archivado mediante el almacenamiento de SQL Server para archiving de almacenamiento de información para cualquiera de los usuarios, puede realizar la siguiente base de datos cambios de almacenamiento de información:
  
- Utilice otra base de datos de SQL Server para el almacenamiento de archiving. Esto incluye la base de datos de archivado principal y cualquier base de datos que se utiliza para la creación de reflejos de SQL Server.
    
- Cambie a la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange de archiving. Si todos los usuarios alojados en los servidores de Exchange y desea utilizar almacenamiento de información de Microsoft Exchange para todos los usuarios en la implementación, debe quitar las bases de datos de almacén de SQL Server de la topología. 
    
Para realizar cualquiera de estos cambios, debe ejecutar el generador de topología, realice los cambios y, a continuación, vuelva a publicar la topología. No especifique información de **Archiving SQL Server almacenar** o **Habilitar SQL Server almacén reflejo** , a menos que tenga Skype para usuarios de negocios que no están alojados en servidores de Exchange.
  
## <a name="change-archiving-database-options"></a>Cambiar las opciones de base de datos de archivado

1. En un equipo que está ejecutando Skype para Business Server o en el que el Skype para herramientas administrativas Business Server están instaladas, inicie sesión con una cuenta que sea miembro del grupo local de usuarios (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios local, pero para publicar una topología, que es necesario agregar un componente a la topología, debe utilizar una cuenta que sea miembro del grupo **Administradores de dominio** y el **RTCUniversalSer verAdmins** group y que tenga permisos de control total (es decir, leer, escribir y modificar) en el recurso compartido de archivo que está utilizando para el Skype para el almacén de archivos de Business Server (es decir, de modo que el generador de topología puede configurar el control de acceso discrecional requerido listas (DACL), o una cuenta con derechos equivalentes.
  
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
    
    - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server** , haga lo siguiente:
    
      - En **Nombre de dominio completo de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo almacén de SQL Server.
    
      - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
      - Si la instancia de SQL Server especificada está en una relación de reflejo, active la casilla de verificación **SQL de esta instancia es de reflejo de la relación** y, a continuación, en **número de puerto de espejo**, especifique el número de puerto.
    
  - Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, luego, haga lo siguiente:
    
    - Para utilizar un almacén de SQL Server existente para el reflejo, en el cuadro de lista desplegable **espejo de almacenamiento de Archiving de SQL Server** , haga clic en el nombre del almacén de SQL Server que desea utilizar para la creación de reflejo.
    
    - Para especificar un nuevo almacén de SQL Server para la creación de reflejo, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server** , siga uno de estos procedimientos:
    
      a. En el **FQDN de SQL Server**, especifique el FQDN de la de SQL Server en el que desea crear el nuevo almacén de SQL Server.
    
      b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
      c. Si la instancia de SQL Server especificada está en una relación de reflejo, active la casilla de verificación **SQL de esta instancia es de reflejo de la relación** y, a continuación, en **número de puerto de espejo**, especifique el número de puerto.
    
  - Si habilita la creación de reflejos de SQL Server y desea agregar o cambiar un SQL Server reflejo a testigo (una tercera independiente de SQL Server instancia que puede detectar el estado de las instancias de servidor y reflejo de SQL Server principales), seleccione el testigo de espejado de uso SQL Server ** habilitar la conmutación por error automática** casilla de verificación y, a continuación, siga uno de los siguientes:
    
      a. En el **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo SQL Server testigo de creación de reflejo.
    
      b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
    
      c. Si la instancia de SQL Server especificada está en una relación de reflejo, active la casilla de verificación **SQL de esta instancia es de reflejo de la relación** y, a continuación, en **número de puerto de espejo**, especifique el número de puerto.
    
  - Para cambiar a la integración de Microsoft Exchange para almacenar datos de archiving y archivos en servidores de Exchange (si todos los usuarios en la implementación están alojados en los servidores de Exchange), eliminar toda la información para el Archiving de bases de datos.
    
    > [!IMPORTANT]
    > Si tiene cualquier Skype para usuarios de negocios que no están alojados en servidores de Exchange, no elimine la información de almacenamiento de SQL Server. 
  
8. Para guardar la configuración, haga clic en **Aceptar**.
    
    > [!IMPORTANT]
    > Los cambios que realice en el generador de topología no surtan efecto hasta que se publique la nueva topología. Para obtener información detallada, vea [agregar bases de datos archivados a una implementación existente de Skype para Business Server 2015](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Cambiar la ubicación de la base de datos de archivado con Windows PowerShell

En la mayoría de los casos, no será necesario que cambie la ubicación de la base de datos de archivado, que se especifica al instalar el servidor de archivado. Pero, si se produce un error de hardware o cualquier otro problema, puede apuntar el servidor de archivado hacia una base de datos nueva con el cmdlet **Set-CsArchivingServer**.
  
En el ejemplo siguiente se cambia la ubicación de la base de datos de archivado para el ArchivingServer:atl-cs-001.contoso.com servidor de archivado. En este ejemplo, la nueva base de datos se encuentra en ArchivingDatabase:atl-sql-001.contoso.com:
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```



---
title: Cambiar las opciones de la base de datos de archivado en Skype Empresarial Server
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
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumen: obtenga información sobre cómo cambiar las opciones de bases de datos de archivado para Skype Empresarial Server.'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817700"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Cambiar las opciones de la base de datos de archivado en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo cambiar las opciones de bases de datos de archivado para Skype Empresarial Server.
  
Si implementa el archivado mediante SQL Server almacenamiento de archivado para cualquiera de los usuarios, puede realizar los siguientes cambios en el almacenamiento de la base de datos:
  
- Use una base de SQL Server de datos de archivado diferente para el almacenamiento de archivado. Esto incluye la base de datos de archivado principal y cualquier base de datos que use para SQL Server creación de reflejos.
    
- Cambie a la integración de Microsoft Exchange para almacenar archivos y datos de archivado en servidores exchange. Si todos los usuarios están en sus servidores de Exchange y desea usar el almacenamiento de Microsoft Exchange para todos los usuarios de la implementación, debe quitar las bases de datos del almacén de SQL Server de la topología. 
    
Para realizar cualquiera de estos cambios, debe ejecutar el Generador de topologías, realizar los cambios y, a continuación, volver a publicar la topología. No especifique el almacén **de SQL Server** ni habilite la información de creación de reflejos del almacén de **SQL Server, a** menos que tenga usuarios de Skype Empresarial que no estén en servidores de Exchange.
  
## <a name="change-archiving-database-options"></a>Cambiar las opciones de base de datos de archivado

1. En un equipo que ejecute Skype Empresarial Server o en el que estén instaladas las herramientas administrativas de Skype Empresarial Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesario para agregar  un componente a la topología, debe usar una cuenta que sea miembro del grupo Administradores de dominio y del grupo **RTCUniversalServerAdmins,** y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Skype Empresarial Server (es decir, para que topology Builder pueda configurar las listas de control de acceso discrecional (DACL) necesarias o una cuenta con derechos equivalentes.
  
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
    
     - Para especificar un nuevo almacén SQL Server, haga clic  en Nuevo y, a continuación, en el cuadro de diálogo Definir nuevo almacén de SQL Server, haga lo siguiente: 
    
       - En **SQL Server FQDN,** especifique el FQDN del servidor en el que desea crear el nuevo SQL Server almacén.
    
       - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre** y especifique la instancia que desee usar.
    
       - Si la instancia SQL Server especificada está en una relación de creación de reflejos, active la casilla Esta instancia **SQL** está en relación de reflejo y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.
    
   - Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, a continuación, haga lo siguiente:
    
     - Para usar un almacén de SQL Server existente para  la creación de reflejos, en el cuadro de lista desplegable Reflejo del almacén de SQL Server de archivado, haga clic en el nombre del almacén de SQL Server que desea usar para la creación de reflejos.
    
     - Para especificar un nuevo almacén SQL Server para creación de reflejos, haga clic en Nuevo y, a continuación, en el cuadro de diálogo Definir nuevo almacén de **SQL Server,** realice una de las siguientes acciones:
    
       a. En **SQL Server FQDN,** especifique el FQDN de la SQL Server en la que desea crear el nuevo SQL Server almacén.
    
       b. Haga clic en **Instancia predeterminada** para utilizar la instancia predeterminada o, para especificar una instancia diferente, haga clic en **Instancia denominada** y, a continuación, haga clic en la instancia que desee utilizar.
    
       c. Si la instancia SQL Server especificada está en una relación de creación de reflejos, active la casilla Esta instancia **SQL** está en relación de reflejo y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.
    
   - Si habilita la creación de reflejos de SQL Server y desea agregar o cambiar un testigo de creación de reflejo de SQL Server (una tercera instancia independiente de SQL Server que puede detectar el estado del servidor SQL Server principal y las instancias reflejadas), active la casilla Usar testigo de creación de reflejos de SQL Server para habilitar la conmutación por error automática y, **a** continuación, realice una de las siguientes acciones:
    
      a. En **SQL Server FQDN,** especifique el FQDN del servidor en el que desea crear el nuevo testigo de creación SQL Server reflejo.
    
      b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
    
      c. Si la instancia SQL Server especificada está en una relación de creación de reflejos, active la casilla Esta instancia **SQL** está en relación de reflejo y, a continuación, en Número de puerto **reflejado,** especifique el número de puerto.
    
   - Para cambiar a la integración de Microsoft Exchange para almacenar archivos y datos de archivado en servidores exchange (si todos los usuarios de la implementación están en sus servidores exchange), elimine toda la información de las bases de datos de archivado.
    
     > [!IMPORTANT]
     > Si tiene usuarios de Skype Empresarial que no están en servidores de Exchange, no elimine la SQL Server almacenar. 
  
8. Para guardar la configuración, haga clic en **Aceptar**.
    
    > [!IMPORTANT]
    > Los cambios que realice en el Generador de topologías no se realizarán hasta que publique la nueva topología. Para obtener más información, consulte [Agregar bases de datos de archivado a una implementación existente en Skype Empresarial Server.](../../deploy/deploy-archiving/add-archiving-databases.md) 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Cambiar la ubicación de la base de datos de archivado mediante Windows PowerShell

En la mayoría de los casos, no será necesario cambiar la ubicación de la base de datos de archivado, que se especifica al instalar el servidor de archivado. Sin embargo, si se produce un error de hardware u otro problema, puede apuntar el servidor de archivado a una nueva base de datos mediante el cmdlet **Set-CsArchivingServer.**
  
En el siguiente ejemplo se cambia la ubicación de la base de datos de archivado para el servidor de archivado ArchivingServer:atl-cs-001.contoso.com Archiving Server. En este ejemplo, la nueva base de datos se encuentra en ArchivingDatabase:atl-sql-001.contoso.com:
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```



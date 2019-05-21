---
title: Cambiar las opciones de la base de datos de archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumen: Aprenda a cambiar las opciones de la base de datos de archivado para Skype empresarial Server.'
ms.openlocfilehash: 56aa29ef185176ce3b080572723c566455731dc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299989"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Cambiar las opciones de la base de datos de archivado en Skype empresarial Server

**Resumen:** Obtenga información sobre cómo cambiar las opciones de la base de datos de archivado para Skype empresarial Server.
  
Si implementa el archivado con almacenamiento de SQL Server para archivar el almacenamiento de cualquiera de los usuarios, puede realizar los siguientes cambios de almacenamiento en la base de datos:
  
- Use una base de datos de SQL Server diferente para archivar almacenamiento. Esto incluye la base de datos de archivado principal y cualquier base de datos que use para el reflejo de SQL Server.
    
- Cambie a la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange. Si todos los usuarios están alojados en los servidores de Exchange y desea usar el almacenamiento de Microsoft Exchange para todos los usuarios de su implementación, debe quitar las bases de datos del almacén de SQL Server de su topología. 
    
Para realizar alguno de estos cambios, debe ejecutar el generador de topología, realizar los cambios y, a continuación, volver a publicar la topología. No especifique el **archivado de SQL Server Store** ni habilitar la información de reflejo de la **tienda de SQL Server** , a menos que tenga usuarios de Skype empresarial que no estén alojados en los servidores de Exchange.
  
## <a name="change-archiving-database-options"></a>Cambiar las opciones de base de datos de archivado

1. En un equipo que ejecute Skype empresarial Server o en el que estén instaladas las herramientas administrativas de Skype empresarial Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para agregar un componente a la topología, debe usar una cuenta que sea miembro del grupo de **administradores de dominio** y la de **RTCUniversalSer Grupo verAdmins** y que tiene permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Skype empresarial Server (es decir, el generador de topología puede configurar el control de acceso discrecional requerido listas (DACL) o una cuenta con derechos equivalentes.
  
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
    
     - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:
    
       - En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo almacén de SQL Server.
    
       - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
       - Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
    
   - Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, luego, haga lo siguiente:
    
     - Para usar un almacén de SQL Server existente para la creación de reflejo, en el cuadro de lista desplegable archivado reflejado de **SQL Server** , haga clic en el nombre del almacén de SQL Server que desea usar para el reflejo.
    
     - Para especificar un nuevo almacén de SQL Server para la creación de reflejo, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:
    
       a. En **FQDN de SQL Server**, especifique el nombre completo del servidor SQL Server en el que desea crear el nuevo almacén de SQL Server.
    
       b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
    
       c. Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
    
   - Si habilita el reflejo de SQL Server y quiere agregar o cambiar un testigo de reflejo de SQL Server (una tercera, instancia independiente de SQL Server que puede detectar el estado del servidor SQL Server principal y de las instancias reflejadas), seleccione **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** y, después, realice una de las siguientes acciones:
    
      a. En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo testigo de reflejo de SQL Server.
    
      b. Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
    
      c. Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
    
   - Para cambiar a la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange (si todos los usuarios de su implementación están alojados en los servidores de Exchange), elimine toda la información para archivar bases de datos.
    
     > [!IMPORTANT]
     > Si tiene algún usuario de Skype empresarial que no esté alojado en servidores de Exchange, no elimine la información de la tienda SQL Server. 
  
8. Para guardar la configuración, haga clic en **Aceptar**.
    
    > [!IMPORTANT]
    > Los cambios que haga en el generador de topología no se aplicarán hasta que publique la nueva topología. Para obtener más información, vea [Agregar bases de datos de archivado a una implementación existente en Skype empresarial Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Cambiar la ubicación de la base de datos de archivado mediante Windows PowerShell

En la mayoría de los casos, no tendrá que cambiar la ubicación de la base de datos de archivado, que se especifica al instalar el servidor de archivado. Sin embargo, si se produce un error de hardware u otro problema, puede indicar al servidor de archivado a una nueva base de datos con el cmdlet **set-CsArchivingServer** .
  
En el ejemplo siguiente se cambia la ubicación de la base de datos de archivado del ArchivingServer: ATL-CS-001.contoso.com Server archiving. En este ejemplo, la nueva base de datos se encuentra en ArchivingDatabase: ATL-SQL-001.contoso.com:
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```



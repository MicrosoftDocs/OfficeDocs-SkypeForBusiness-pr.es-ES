---
title: Agregar almacén de SQL Server del servidor de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Servidor de archivado requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de archivo. Puede seleccionar una base de datos de SQL Server definida previamente que se usará para el archiving o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que reside la base de datos de SQL Server y la instancia de SQL Server que que desea utilizar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: 2c63b6bf71c156bc62e07add023f3049af399095
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="51803-104">Agregar almacén de SQL Server del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="51803-104">Add Archiving Server SQL Server Store</span></span>
 
<span data-ttu-id="51803-105">Servidor de archivado requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="51803-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="51803-106">Puede seleccionar una base de datos de SQL Server definida previamente que se usará para el archiving o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que reside la base de datos de SQL Server y la instancia de SQL Server que que desea utilizar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).</span><span class="sxs-lookup"><span data-stu-id="51803-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="51803-107">Si la cuenta que se utiliza para publicar la topología tiene los derechos de usuario apropiados y los permisos, puede crear la base de datos de archivado (LcsLog) al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="51803-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="51803-108">También puede crear la base de datos posteriormente, como parte del procedimiento de instalación, o en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="51803-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="51803-109">Para instalar y distribuir las bases de datos en el servidor basado en SQL Server para archiving, debe ser miembro del grupo de administradores del sistema de SQL Server para el servidor basado en SQL Server donde está instalando los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="51803-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="51803-110">Si no es un miembro del grupo de administradores del sistema de SQL Server, debe solicitar a agregarse al grupo hasta que los archivos de base de datos se implementan.</span><span class="sxs-lookup"><span data-stu-id="51803-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="51803-111">Si no puede realizarse un miembro del grupo Administradores del sistema, debe proporcionar el Administrador de la base de datos de SQL Server con la secuencia de comandos para configurar e implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="51803-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="51803-112">Para obtener más información acerca de los derechos de usuario y los permisos que necesita llevar a cabo los procedimientos, consulte [Permisos de implementación de SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="51803-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  


---
title: Agregar almacén de archivado de Front-End
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: El archivado requiere una edición de 64 bits compatible del software de base de datos de Microsoft SQL Server para almacenar los datos de archivado. Puede seleccionar una base de datos de SQL Server definido previamente que se usará para el archivado, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que la base de datos de SQL Server se residan, además de la instancia de SQL Se servidor que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: 0dc4192c2eb6e7d9569094d6b03c7fb5fcebf6ad
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2018
ms.locfileid: "19990038"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="532a2-104">Agregar almacén de archivado de Front-End</span><span class="sxs-lookup"><span data-stu-id="532a2-104">Add Front End Archiving Store</span></span>
 
<span data-ttu-id="532a2-105">El archivado requiere una edición de 64 bits compatible del software de base de datos de Microsoft SQL Server para almacenar los datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="532a2-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="532a2-106">Puede seleccionar una base de datos de SQL Server definido previamente que se usará para el archivado, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que la base de datos de SQL Server se residan, además de la instancia de SQL Se servidor que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).</span><span class="sxs-lookup"><span data-stu-id="532a2-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="532a2-107">Si la cuenta que se usa para publicar la topología tiene los permisos y derechos de usuario adecuados, puede crear la base de datos de supervisión al publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="532a2-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="532a2-108">También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación.</span><span class="sxs-lookup"><span data-stu-id="532a2-108">You can also create the database later, included as part of the installation procedure.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="532a2-109">Para instalar e implementar las bases de datos en el servidor basado en SQL Server para la supervisión, debe ser miembro del grupo de administradores del sistema de SQL Server para el servidor de SQL Server donde va a instalar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="532a2-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="532a2-110">Si no es un miembro del grupo de sysadmin de SQL Server, debe solicitar que se agregará al grupo hasta que se implementan los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="532a2-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="532a2-111">Si no se puede realizar un miembro del grupo Administradores del sistema, debe proporcionar el Administrador de la base de datos de SQL Server con la secuencia de comandos para configurar e implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="532a2-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="532a2-112">Para obtener información detallada sobre los derechos de usuario y los permisos que se deben llevar a cabo los procedimientos, vea [Permisos de implementación para SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="532a2-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  


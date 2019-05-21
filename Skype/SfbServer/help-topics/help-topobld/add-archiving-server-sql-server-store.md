---
title: Agregar almacén de SQL Server del servidor de archivado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: El servidor de archivado requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de archivo. Puede seleccionar una base de datos de SQL Server definida previamente para que se use para archivar o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: cda788a83b67b94f4064ca2f967878b88527b0c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304943"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="daca2-104">Agregar almacén de SQL Server del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="daca2-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="daca2-105">El servidor de archivado requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="daca2-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="daca2-106">Puede seleccionar una base de datos de SQL Server definida previamente para que se use para archivar o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).</span><span class="sxs-lookup"><span data-stu-id="daca2-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="daca2-107">Si la cuenta que se usa para publicar la topología tiene los derechos de usuario y permisos adecuados, puede crear la base de datos de archivado (LcsLog) cuando publique la topología.</span><span class="sxs-lookup"><span data-stu-id="daca2-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="daca2-108">También puede crear la base de datos más adelante, como parte del procedimiento de instalación o de otro modo.</span><span class="sxs-lookup"><span data-stu-id="daca2-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="daca2-109">Para instalar e implementar las bases de datos en el servidor basado en SQL Server para archivar, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor basado en SQL Server en el que va a instalar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="daca2-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="daca2-110">Si no es miembro del grupo sysadmins de SQL Server, debe solicitar que se agregue al grupo hasta que se implementen los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="daca2-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="daca2-111">Si no puede hacerse miembro del grupo sysadmins, debe proporcionar el administrador de la base de datos de SQL Server con el script para configurar e implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="daca2-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="daca2-112">Para obtener información sobre los permisos y derechos de usuario que necesita para realizar los procedimientos, consulte [permisos de implementación para SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="daca2-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>



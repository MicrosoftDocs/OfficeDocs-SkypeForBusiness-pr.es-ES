---
title: Agregar almacén de SQL Server del servidor de archivado
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: El servidor de archivado requiere una edición compatible de 64 bits del software SQL Server base de datos para almacenar los datos de archivo. Puede seleccionar una base de datos SQL Server definida previamente para el archivado o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: ff6cec0d083e4597dec7ae61df08b16ff8feab7f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100216"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="e4e3a-104">Agregar almacén de SQL Server del servidor de archivado</span><span class="sxs-lookup"><span data-stu-id="e4e3a-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="e4e3a-105">El servidor de archivado requiere una edición compatible de 64 bits del software SQL Server base de datos para almacenar los datos de archivo.</span><span class="sxs-lookup"><span data-stu-id="e4e3a-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="e4e3a-106">Puede seleccionar una base de datos SQL Server definida previamente para el archivado o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).</span><span class="sxs-lookup"><span data-stu-id="e4e3a-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="e4e3a-p103">Si la cuenta que se usa para publicar la topología dispone de los permisos y derechos de usuario pertinentes, puede crear la base de datos de archivado (LcsLog) al publicar la topología. La base de datos también puede crearse más adelante, como parte del procedimiento de instalación, o de otra forma.</span><span class="sxs-lookup"><span data-stu-id="e4e3a-p103">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology. You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="e4e3a-109">Para instalar e implementar las bases de datos en el servidor basado en SQL Server para archivado, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e4e3a-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="e4e3a-110">Si no es miembro del grupo SQL Server sysadmins, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e4e3a-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="e4e3a-111">Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e4e3a-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="e4e3a-112">Para más información sobre los permisos y derechos de usuario que necesita para realizar los procedimientos, consulte [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) en la documentación sobre la implementación.</span><span class="sxs-lookup"><span data-stu-id="e4e3a-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>
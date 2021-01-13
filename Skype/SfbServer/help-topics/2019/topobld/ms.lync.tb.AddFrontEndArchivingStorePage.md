---
title: Agregar almacén de archivado front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: El archivado requiere una edición de 64 bits compatible del software Microsoft SQL Server base de datos para almacenar los datos de archivado. Puede seleccionar una base de datos de SQL Server definida anteriormente para su archivado o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que va a residir la base de datos de SQL Server, además de la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada) o una instancia con nombre que especifique).
ms.openlocfilehash: a0a9528b141730da91d233774a6c676956c9b19b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833530"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="3619e-104">Agregar almacén de archivado front-end</span><span class="sxs-lookup"><span data-stu-id="3619e-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="3619e-105">El archivado requiere una edición de 64 bits compatible del software Microsoft SQL Server base de datos para almacenar los datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="3619e-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="3619e-106">Puede seleccionar una base de datos de SQL Server definida anteriormente para su archivado o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que va a residir la base de datos de SQL Server, además de la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada) o una instancia con nombre que especifique).</span><span class="sxs-lookup"><span data-stu-id="3619e-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="3619e-p103">Si la cuenta utilizada para publicar la topología tiene los permisos y derechos de usuario adecuados, puede crear la base de datos de supervisión al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="3619e-p103">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology. You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="3619e-109">Para instalar e implementar las bases de datos en el servidor basado en SQL Server para la supervisión, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3619e-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="3619e-110">Si no es miembro del grupo sysadmin de SQL Server, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3619e-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="3619e-111">Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="3619e-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="3619e-112">Para más información sobre los permisos y derechos de usuario que necesita para realizar los procedimientos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación sobre la implementación.</span><span class="sxs-lookup"><span data-stu-id="3619e-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>



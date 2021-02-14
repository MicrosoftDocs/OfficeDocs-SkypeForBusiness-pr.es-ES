---
title: Agregar almacén SQL Server front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Una implementación de servidor Standard Edition instala automáticamente el software de base de datos Microsoft SQL Server Express y la base SQL Server datos. Por lo tanto, todas las opciones se han sobreababado previamente y no se pueden realizar cambios en la configuración predeterminada.
ms.openlocfilehash: 939f12fa02951074e487066337c8bb76af59143a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824080"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="c2ff9-104">Agregar almacén SQL Server front-end</span><span class="sxs-lookup"><span data-stu-id="c2ff9-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="c2ff9-105">Una implementación de servidor Standard Edition instala automáticamente el software de base de datos Microsoft SQL Server Express y la base SQL Server datos.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="c2ff9-106">Por lo tanto, todas las opciones se han sobreababado previamente y no se pueden realizar cambios en la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="c2ff9-107">El grupo de servidores front-end de una implementación de servidor Enterprise Edition requiere una edición de 64 bits compatible del software de base de datos SQL Server para la base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="c2ff9-108">Puede seleccionar una base de datos SQL Server definida anteriormente para usarla para la base de datos back-end o definir una nueva base de datos SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que se va a residir la base de datos de SQL Server y la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada) o una instancia con nombre que especifique).</span><span class="sxs-lookup"><span data-stu-id="c2ff9-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="c2ff9-109">También puede elegir habilitar la creación de reflejos en el almacén de SQL Server y especificar un testigo de reflejos para la conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="c2ff9-110">Para obtener más información SQL Server compatibilidad con clústeres y software de base de [datos,](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) consulte la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="c2ff9-111">Para obtener más información sobre cómo configurar SQL Server para la base de datos back-end, consulte[Configurar SQL Server para Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="c2ff9-p105">Si la cuenta que se utiliza para publicar la topología tiene los permisos y derechos de usuario adecuados, puede crear la base de datos back-end (comunicaciones en tiempo real (CTR)) al publicar la topología. También puede crear la base de datos más adelante, como parte del procedimiento de instalación.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-p105">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology. You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="c2ff9-114">Para instalar e implementar las bases de datos en el servidor basado en SQL Server para una implementación enterprise Edition, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="c2ff9-115">Si no es miembro del grupo sysadmins de SQL Server, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="c2ff9-116">Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c2ff9-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="c2ff9-117">Para más información sobre los permisos y derechos de usuario que se necesitan para realizar estos procedimientos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span><span class="sxs-lookup"><span data-stu-id="c2ff9-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>



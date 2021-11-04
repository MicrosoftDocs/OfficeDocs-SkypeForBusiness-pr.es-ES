---
title: Agregar almacén SQL Server front-end
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Una Standard Edition de servidor instala automáticamente el software de base de datos Microsoft SQL Server Express y la base SQL Server datos. Por lo tanto, todas las opciones están prepobladas y no puede realizar cambios en la configuración predeterminada.
ms.openlocfilehash: 31d8df413d03c02ede0a2e0c24a63bea7381e65e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60757312"
---
# <a name="add-front-end-sql-server-store"></a>Agregar almacén SQL Server front-end

Una Standard Edition de servidor instala automáticamente el software de base de datos Microsoft SQL Server Express y la base SQL Server datos. Por lo tanto, todas las opciones están prepobladas y no puede realizar cambios en la configuración predeterminada.

El grupo de servidores front-end de una implementación Enterprise Edition servidor requiere una edición compatible de 64 bits del software de base de datos SQL Server para la base de datos back-end. Puede seleccionar una base de datos SQL Server definida previamente para usarla para la base de datos back-end o definir una nueva base de datos SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que reside la base de datos de SQL Server y la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique). También puede elegir habilitar la creación de reflejos en el almacén de SQL Server y especificar un testigo de reflejos para la conmutación por error automática.

Para obtener más información SQL Server soporte técnico, consulte [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) en la documentación sobre compatibilidad. Para obtener más información sobre cómo configurar SQL Server para la base de datos back-end, consulte[Configurar SQL Server para Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) en la documentación sobre implementación.

> [!NOTE]
> Si la cuenta que se utiliza para publicar la topología tiene los permisos y derechos de usuario adecuados, puede crear la base de datos back-end (comunicaciones en tiempo real (CTR)) al publicar la topología. También puede crear la base de datos más adelante, como parte del procedimiento de instalación.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para una implementación de Enterprise Edition, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos. Si no es miembro del grupo SQL Server sysadmins, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos. Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos. Para más información sobre los permisos y derechos de usuario que se necesitan para realizar estos procedimientos, consulte [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).
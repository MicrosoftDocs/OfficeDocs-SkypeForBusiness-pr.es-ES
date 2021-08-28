---
title: Agregar almacén SQL Server de servidor de supervisión
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: El servidor de supervisión requiere una edición compatible de 64 bits SQL Server software de base de datos para almacenar los datos de supervisión. Puede seleccionar una base de datos SQL Server definida previamente para la supervisión o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: 474259fc1985277b2ac795651d6115ec608a6b40
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606499"
---
# <a name="add-monitoring-server-sql-server-store"></a>Agregar almacén SQL Server de servidor de supervisión

El servidor de supervisión requiere una edición compatible de 64 bits SQL Server software de base de datos para almacenar los datos de supervisión. Puede seleccionar una base de datos SQL Server definida previamente para la supervisión o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).

Para obtener más información SQL Server soporte técnico, consulte [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) en la documentación sobre compatibilidad. Para obtener más información acerca de la base de datos de supervisión, incluida la colocación de la base de datos de supervisión, consulte [Supported Server Location](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) en la documentación sobre compatibilidad, Planning for[Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) en la documentación de planeación y SQL Server Data and Log [File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) en la documentación de implementación.

> [!NOTE]
> Si la cuenta usada para publicar la topología tiene los permisos y derechos de usuario correspondientes, puede crear la base de datos de supervisión cuando publique la topología. La base de datos también puede crearse más adelante, como parte del procedimiento de instalación. > Para instalar e implementar las bases de datos en el servidor basado en SQL Server para la supervisión, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos. Si no es miembro del grupo SQL Server sysadmin, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos. Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos. Para obtener más información sobre los derechos y permisos de usuario que necesita para llevar a cabo estos [procedimientos,](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) consulte Deployment Permissions for SQL Server en la documentación sobre implementación.
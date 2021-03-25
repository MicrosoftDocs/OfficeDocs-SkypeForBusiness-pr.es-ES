---
title: Agregar almacén SQL Server de servidor de supervisión
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: El servidor de supervisión requiere una edición de 64 bits compatible SQL Server software de base de datos para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definida previamente para su supervisión o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada). , o una instancia con nombre que especifique).
ms.openlocfilehash: 5c1ef4c7b2474a094492aa7905c044a5da145ff5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119729"
---
# <a name="add-monitoring-server-sql-server-store"></a>Agregar almacén SQL Server de servidor de supervisión

El servidor de supervisión requiere una edición de 64 bits compatible SQL Server software de base de datos para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definida previamente para su supervisión o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada). , o una instancia con nombre que especifique).

Para obtener más información SQL Server soporte técnico, consulte [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) en la documentación sobre compatibilidad. Para obtener más información sobre la base de datos de supervisión, incluida la colocación de la base de datos de supervisión, consulte [Supported Server Location](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) en la documentación sobre compatibilidad, Planning for[Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) en la documentación de planeación y SQL Server Data and Log [File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) en la documentación de implementación.

> [!NOTE]
> Si la cuenta usada para publicar la topología tiene los permisos y derechos de usuario correspondientes, puede crear la base de datos de supervisión cuando publique la topología. La base de datos también puede crearse más adelante, como parte del procedimiento de instalación. > Para instalar e implementar las bases de datos en el servidor basado en SQL Server para la supervisión, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos. Si no es miembro del grupo SQL Server sysadmin, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos. Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos. Para obtener más información sobre los derechos y permisos de usuario que necesita para llevar a cabo estos [procedimientos,](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) consulte Deployment Permissions for SQL Server en la documentación sobre implementación.
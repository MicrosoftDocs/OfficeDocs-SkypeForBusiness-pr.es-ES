---
title: Agregar almacén SQL Server front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Una implementación de servidor Standard Edition instala automáticamente el software de base de datos Microsoft SQL Server express y la base SQL Server datos. Por lo tanto, todas las opciones están prepobladas y no puede realizar cambios en la configuración predeterminada.
ms.openlocfilehash: 6861fd20c8f3e164a4d8d713dfc725bd2f949acd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118679"
---
# <a name="add-front-end-sql-server-store"></a>Agregar almacén SQL Server front-end

Una implementación de servidor Standard Edition instala automáticamente el software de base de datos Microsoft SQL Server express y la base SQL Server datos. Por lo tanto, todas las opciones están prepobladas y no puede realizar cambios en la configuración predeterminada.

El grupo de servidores front-end de una implementación de servidor Enterprise Edition requiere una edición compatible de 64 bits del software de base de datos SQL Server para la base de datos back-end. Puede seleccionar una base de datos de SQL Server definida previamente para usarla para la base de datos back-end o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que debe residir la base de datos de SQL Server y la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada). , o una instancia con nombre que especifique). También puede elegir habilitar la creación de reflejos en el almacén de SQL Server y especificar un testigo de reflejos para la conmutación por error automática.

Para obtener más información SQL Server soporte técnico, consulte [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) en la documentación sobre compatibilidad. Para obtener más información sobre cómo SQL Server para la base de datos back-end, [consulte Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) en la documentación sobre implementación.

> [!NOTE]
> Si la cuenta que se utiliza para publicar la topología tiene los permisos y derechos de usuario adecuados, puede crear la base de datos back-end (comunicaciones en tiempo real (CTR)) al publicar la topología. También puede crear la base de datos más adelante, como parte del procedimiento de instalación.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para una implementación de Enterprise Edition, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos. Si no es miembro del grupo SQL Server sysadmins, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos. Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos. Para más información sobre los permisos y derechos de usuario que se necesitan para realizar estos procedimientos, consulte [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).
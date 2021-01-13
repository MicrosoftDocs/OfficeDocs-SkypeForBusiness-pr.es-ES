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
description: Una implementación de servidor Standard Edition instala automáticamente el software de base de datos Microsoft SQL Server Express y la base SQL Server datos. Por lo tanto, todas las opciones se han sobreabatado previamente y no se pueden realizar cambios en la configuración predeterminada.
ms.openlocfilehash: d1a3fd6a27ab6229f84e8b74259be6a2da7652f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811640"
---
# <a name="add-front-end-sql-server-store"></a>Agregar almacén SQL Server front-end

Una implementación de servidor Standard Edition instala automáticamente el software de base de datos Microsoft SQL Server Express y la base SQL Server datos. Por lo tanto, todas las opciones se han sobreabatado previamente y no se pueden realizar cambios en la configuración predeterminada.

El grupo de servidores front-end de una implementación de servidor Enterprise Edition requiere una edición de 64 bits compatible del software de base de datos SQL Server para la base de datos back-end. Puede seleccionar una base de datos SQL Server definida anteriormente para usarla para la base de datos back-end o definir una nueva base de datos SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que se va a residir la base de datos de SQL Server y la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada) o una instancia con nombre que especifique). También puede elegir habilitar la creación de reflejos en el almacén de SQL Server y especificar un testigo de reflejos para la conmutación por error automática.

Para obtener más información SQL Server compatibilidad con clústeres y software de base de datos, consulte La compatibilidad con clústeres y [software](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) de base de datos en la documentación sobre compatibilidad. Para obtener más información sobre cómo SQL Server para la base de datos back-end, consulte [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) en la documentación sobre implementación.

> [!NOTE]
> Si la cuenta que se utiliza para publicar la topología tiene los permisos y derechos de usuario adecuados, puede crear la base de datos back-end (comunicaciones en tiempo real (CTR)) al publicar la topología. También puede crear la base de datos más adelante, como parte del procedimiento de instalación.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para una implementación enterprise Edition, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmins de SQL Server, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos. Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos. Para más información sobre los permisos y derechos de usuario que se necesitan para realizar estos procedimientos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).



---
title: Agregar almacén de SQL Server del servidor de archivado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: El servidor de archivado requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de archivo. Puede seleccionar una base de datos de SQL Server definida previamente para que se use para archivar o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: 9d9d5af7e769a22c7742029d786826e3d2b3c998
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304103"
---
# <a name="add-archiving-server-sql-server-store"></a>Agregar almacén de SQL Server del servidor de archivado

El servidor de archivado requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de archivo. Puede seleccionar una base de datos de SQL Server definida previamente para que se use para archivar o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).

> [!NOTE]
> Si la cuenta que se usa para publicar la topología tiene los derechos de usuario y permisos adecuados, puede crear la base de datos de archivado (LcsLog) cuando publique la topología. También puede crear la base de datos más adelante, como parte del procedimiento de instalación o de otro modo.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para archivar, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor basado en SQL Server en el que va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmins de SQL Server, debe solicitar que se agregue al grupo hasta que se implementen los archivos de base de datos. Si no puede hacerse miembro del grupo sysadmins, debe proporcionar el administrador de la base de datos de SQL Server con el script para configurar e implementar las bases de datos. Para obtener información sobre los permisos y derechos de usuario que necesita para realizar los procedimientos, consulte [permisos de implementación para SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.



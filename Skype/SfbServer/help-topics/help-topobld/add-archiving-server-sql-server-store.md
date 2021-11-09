---
title: Agregar almacén de SQL Server del servidor de archivado
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: El servidor de archivado requiere una edición compatible de 64 bits del software SQL Server base de datos para almacenar los datos de archivo. Puede seleccionar una base de datos SQL Server definida previamente para su archivado o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que desea usar para el nuevo datab de SQL Server ase (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: a0f2b40bcf5d24063c689bbc760a57b14b98ad28
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832204"
---
# <a name="add-archiving-server-sql-server-store"></a>Agregar almacén de SQL Server del servidor de archivado

El servidor de archivado requiere una edición compatible de 64 bits del software SQL Server base de datos para almacenar los datos de archivo. Puede seleccionar una base de datos SQL Server definida previamente para su archivado o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que desea usar para el nuevo datab de SQL Server ase (que puede ser la instancia predeterminada o una instancia con nombre que especifique).

> [!NOTE]
> Si la cuenta que se usa para publicar la topología dispone de los permisos y derechos de usuario pertinentes, puede crear la base de datos de archivado (LcsLog) al publicar la topología. La base de datos también puede crearse más adelante, como parte del procedimiento de instalación, o de otra forma.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para el archivado, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos. Si no es miembro del grupo SQL Server sysadmins, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos. Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos. Para más información sobre los permisos y derechos de usuario que necesita para realizar los procedimientos, consulte [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) en la documentación sobre la implementación.
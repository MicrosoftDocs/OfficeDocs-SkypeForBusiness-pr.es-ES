---
title: Agregar almacén de SQL Server del servidor de archivado
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
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: El servidor de archivado requiere una edición de 64 bits compatible del software SQL Server base de datos para almacenar los datos de archivo. Puede seleccionar una base de datos de SQL Server definida anteriormente para su archivado o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: 5200562ce8db04b741bfba7f62fbe42a2c8f47df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803690"
---
# <a name="add-archiving-server-sql-server-store"></a>Agregar almacén de SQL Server del servidor de archivado

El servidor de archivado requiere una edición de 64 bits compatible del software SQL Server base de datos para almacenar los datos de archivo. Puede seleccionar una base de datos de SQL Server definida anteriormente para su archivado o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server y la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).

> [!NOTE]
> Si la cuenta que se usa para publicar la topología dispone de los permisos y derechos de usuario pertinentes, puede crear la base de datos de archivado (LcsLog) al publicar la topología. La base de datos también puede crearse más adelante, como parte del procedimiento de instalación, o de otra forma.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para el archivado, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmins de SQL Server, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos. Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos. Para más información sobre los permisos y derechos de usuario que necesita para realizar los procedimientos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación sobre la implementación.



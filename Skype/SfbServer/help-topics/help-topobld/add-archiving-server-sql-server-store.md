---
title: Agregar almacén de SQL Server del servidor de archivado
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Servidor de archivado requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de archivo. Puede seleccionar una base de datos de SQL Server definida previamente que se usará para el archiving o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que reside la base de datos de SQL Server y la instancia de SQL Server que que desea utilizar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: 2c63b6bf71c156bc62e07add023f3049af399095
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-server-sql-server-store"></a>Agregar almacén de SQL Server del servidor de archivado
 
Servidor de archivado requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de archivo. Puede seleccionar una base de datos de SQL Server definida previamente que se usará para el archiving o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que reside la base de datos de SQL Server y la instancia de SQL Server que que desea utilizar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
  
> [!NOTE]
> Si la cuenta que se utiliza para publicar la topología tiene los derechos de usuario apropiados y los permisos, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos posteriormente, como parte del procedimiento de instalación, o en caso contrario. 
  
> [!NOTE]
> Para instalar y distribuir las bases de datos en el servidor basado en SQL Server para archiving, debe ser miembro del grupo de administradores del sistema de SQL Server para el servidor basado en SQL Server donde está instalando los archivos de base de datos. Si no es un miembro del grupo de administradores del sistema de SQL Server, debe solicitar a agregarse al grupo hasta que los archivos de base de datos se implementan. Si no puede realizarse un miembro del grupo Administradores del sistema, debe proporcionar el Administrador de la base de datos de SQL Server con la secuencia de comandos para configurar e implementar las bases de datos. Para obtener más información acerca de los derechos de usuario y los permisos que necesita llevar a cabo los procedimientos, consulte [Permisos de implementación de SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.
  


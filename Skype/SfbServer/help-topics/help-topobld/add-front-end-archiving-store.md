---
title: Agregar almacén de archivado front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: El archivado requiere una edición compatible de 64 bits de Microsoft SQL Server para almacenar los datos de archivado. Puede seleccionar una base de datos de SQL Server definida previamente para usarla para archivar o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que va a residir la base de datos de SQL Server, además de la instancia de SQL se rVer que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: e315e27ddb96d018ca0bead13564ad88e944cd34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820932"
---
# <a name="add-front-end-archiving-store"></a>Agregar almacén de archivado front-end

El archivado requiere una edición compatible de 64 bits de Microsoft SQL Server para almacenar los datos de archivado. Puede seleccionar una base de datos de SQL Server definida previamente para usarla para archivar o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que va a residir la base de datos de SQL Server, además de la instancia de SQL se rVer que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).

> [!NOTE]
> Si la cuenta usada para publicar la topología tiene los derechos de usuario y permisos adecuados, puede crear la base de datos de supervisión al publicar su topología. También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para la supervisión, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor basado en SQL Server en el que va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmin de SQL Server, debe solicitar que lo agregue al grupo hasta que se implementen los archivos de base de datos. Si no puede hacerse miembro del grupo sysadmins, debe proporcionar el administrador de la base de datos de SQL Server con el script para configurar e implementar las bases de datos. Para obtener información sobre los permisos y derechos de usuario que necesita para realizar los procedimientos, consulte [permisos de implementación para SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.



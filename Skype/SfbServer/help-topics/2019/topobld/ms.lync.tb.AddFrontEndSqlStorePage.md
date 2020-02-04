---
title: Agregar almacén SQL Server front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Una implementación de servidor Standard Edition instala automáticamente el software de base de datos de Microsoft SQL Server Express y la base de datos de SQL Server requeridos. Por lo tanto, todas las opciones se rellenan previamente y no puede realizar cambios en la configuración predeterminada.
ms.openlocfilehash: b7f76eca506160013b4b7db5e60ea1cc298511b4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689230"
---
# <a name="add-front-end-sql-server-store"></a>Agregar almacén SQL Server front-end

Una implementación de servidor Standard Edition instala automáticamente el software de base de datos de Microsoft SQL Server Express y la base de datos de SQL Server requeridos. Por lo tanto, todas las opciones se rellenan previamente y no puede realizar cambios en la configuración predeterminada.

El grupo de servidores front end de una implementación de servidor Enterprise Edition requiere una edición de 64 bits compatible del software de base de datos de SQL Server para la base de datos back-end. Puede seleccionar una base de datos de SQL Server definida previamente para usar en la base de datos back-end o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que va a residir la base de datos de SQL Server y la instancia de SQL S. erver que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique). También puede habilitar el reflejo en la tienda SQL Server y especificar un testigo de reflejo para la conmutación por error automática.

Para obtener más información sobre el soporte técnico de SQL Server, consulte compatibilidad con el [software y el agrupamiento de bases de datos](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) en la documentación de soporte. Para obtener detalles sobre cómo configurar SQL Server para la base de datos back-end, consulte [configurar SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) en la documentación de implementación.

> [!NOTE]
> Si la cuenta que se usa para publicar la topología tiene los derechos de usuario y los permisos adecuados, puede crear la base de datos back-end (RTC) al publicar su topología. También puede crear la base de datos más adelante, incluyendo como parte del procedimiento de instalación.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para una implementación de Enterprise Edition, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor basado en SQL Server en el que va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmins de SQL Server, debe solicitar que se agregue al grupo hasta que se implementen los archivos de base de datos. Si no puede hacerse miembro del grupo sysadmins, debe proporcionar el administrador de la base de datos de SQL Server con el script para configurar e implementar las bases de datos. Para obtener información sobre los permisos y derechos de usuario que necesita para realizar los procedimientos, consulte [permisos de implementación para SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).



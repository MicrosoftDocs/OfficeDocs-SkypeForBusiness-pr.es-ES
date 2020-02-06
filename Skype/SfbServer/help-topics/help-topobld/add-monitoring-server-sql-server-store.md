---
title: Agregar almacén SQL Server de servidor de supervisión
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: El servidor de supervisión requiere una edición compatible de 64 bits de SQL Server para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definida previamente para que se use para la supervisión, o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL. Servidor que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: f1950b01aba29ddff6c7622a6fead726bf835ef3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820752"
---
# <a name="add-monitoring-server-sql-server-store"></a>Agregar almacén SQL Server de servidor de supervisión

El servidor de supervisión requiere una edición compatible de 64 bits de SQL Server para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definida previamente para que se use para la supervisión, o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL. Servidor que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).

Para obtener más información sobre el soporte técnico de SQL Server, consulte compatibilidad con el [software y el agrupamiento de bases de datos](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) en la documentación de soporte. Para más información sobre la base de datos de supervisión, incluyendo collocation de la base de datos de supervisión, consulte [Ubicación de servidor admitida](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación de compatibilidad,[planeamiento de la supervisión](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) en la documentación de planeación y la ubicación del [archivo de registro y datos de SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.

> [!NOTE]
> Si la cuenta usada para publicar la topología tiene los derechos de usuario y permisos adecuados, puede crear la base de datos de supervisión al publicar su topología. También puede crear la base de datos más adelante, incluyendo como parte del procedimiento de instalación. > para instalar e implementar las bases de datos en el servidor basado en SQL Server para la supervisión, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor basado en SQL Server en el que va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmin de SQL Server, debe solicitar que se agregue al grupo hasta que se implementen los archivos de base de datos. Si no puede hacerse miembro del grupo sysadmins, debe proporcionar el administrador de la base de datos de SQL Server con el script para configurar e implementar las bases de datos. Para obtener información sobre los permisos y derechos de usuario que necesita para realizar estos procedimientos, consulte [permisos de implementación para SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.



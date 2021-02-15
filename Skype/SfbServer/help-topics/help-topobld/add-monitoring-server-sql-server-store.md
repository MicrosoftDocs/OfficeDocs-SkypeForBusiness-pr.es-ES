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
description: El servidor de supervisión requiere una edición de 64 bits compatible SQL Server software de base de datos para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definida anteriormente para la supervisión o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada) o una instancia con nombre que especifique).
ms.openlocfilehash: 53e8a95b179c3e15f52b694710248b5155ef8d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828700"
---
# <a name="add-monitoring-server-sql-server-store"></a>Agregar almacén SQL Server de servidor de supervisión

El servidor de supervisión requiere una edición de 64 bits compatible SQL Server software de base de datos para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definida anteriormente para la supervisión o definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada) o una instancia con nombre que especifique).

Para obtener más información SQL Server compatibilidad con clústeres y software de base de [datos,](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) consulte la documentación sobre compatibilidad. Para obtener más información sobre la base de [](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) datos de supervisión, incluida la colocación de la base de datos de supervisión, consulte Ubicación del servidor compatible en la documentación sobre[compatibilidad,](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) Planeación de supervisión en la documentación de planeación y ubicación de archivos de registro y datos de [SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación sobre implementación.

> [!NOTE]
> Si la cuenta usada para publicar la topología tiene los permisos y derechos de usuario correspondientes, puede crear la base de datos de supervisión cuando publique la topología. La base de datos también puede crearse más adelante, como parte del procedimiento de instalación. > Para instalar e implementar las bases de datos en el servidor basado en SQL Server para supervisión, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server donde va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmin de SQL Server, debe solicitar que se le agregó al grupo hasta que se implementen los archivos de base de datos. Si no puede ser miembro del grupo sysadmins, debe proporcionar al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos. Para obtener más información sobre los permisos y derechos de usuario que necesita para llevar a cabo estos [procedimientos,](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) consulte Permisos de implementación para SQL Server en la documentación sobre implementación.



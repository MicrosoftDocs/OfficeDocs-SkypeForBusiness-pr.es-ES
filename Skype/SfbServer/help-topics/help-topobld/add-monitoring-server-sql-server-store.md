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
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: El servidor de supervisión requiere una edición de 64 bits compatible de SQL Server para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server previamente definida para usarla para la supervisión, o bien definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL Server que desee usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que haya especificado).
ms.openlocfilehash: adeb5385b385345163d7dc99b0a652837ab8bca4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217901"
---
# <a name="add-monitoring-server-sql-server-store"></a>Agregar almacén SQL Server de servidor de supervisión

El servidor de supervisión requiere una edición de 64 bits compatible de SQL Server para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server previamente definida para usarla para la supervisión, o bien definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que residirá la base de datos de SQL Server, además de la instancia de SQL Server que desee usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que haya especificado).

Para obtener más información acerca del soporte técnico de SQL Server, consulte [Database Software and clustering support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) en la documentación sobre compatibilidad. Para obtener más información sobre la base de datos de supervisión, incluida la combinación de la base de datos de supervisión, consulte Supported [Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supporting Documentation,[Planning for monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) en la documentación de planeación y [SQL Server Data and log file Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación sobre implementación.

> [!NOTE]
> Si la cuenta usada para publicar la topología tiene los permisos y derechos de usuario correspondientes, puede crear la base de datos de supervisión cuando publique la topología. La base de datos también puede crearse más adelante, como parte del procedimiento de instalación. > para instalar e implementar las bases de datos en el servidor basado en SQL Server para la supervisión, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server en el que va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmin de SQL Server, debe solicitar que se agregue al grupo hasta que se implementen los archivos de la base de datos. Si no se puede convertir en miembro del grupo sysadmins, debe proporcionar al administrador de la base de datos de SQL Server el script para configurar e implementar las bases de datos. Para obtener más información sobre los permisos y derechos de usuario necesarios para llevar a cabo estos procedimientos, vea [Deployment permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación sobre implementación.



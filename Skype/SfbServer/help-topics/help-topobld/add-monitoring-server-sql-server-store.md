---
title: Agregar almacén de SQL Server de servidor de supervisión
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: El servidor de supervisión requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definido previamente que se usará para la supervisión, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que reside la base de datos de SQL Server, además de la instancia de SQL Servidor que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: f636531038c331a4e038178675304e7c48cfca0e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005594"
---
# <a name="add-monitoring-server-sql-server-store"></a>Agregar almacén de SQL Server de servidor de supervisión
 
El servidor de supervisión requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definido previamente que se usará para la supervisión, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que reside la base de datos de SQL Server, además de la instancia de SQL Servidor que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
  
Para obtener más información acerca de SQL Server admite, vea [admitir la agrupación en clústeres y Software de base de datos](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) en la documentación referente a. Para obtener información detallada acerca de la base de datos supervisión, incluida la combinación de la base de datos de supervisión, consulte [Compatibles con la ubicación del servidor](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación de compatibilidad,[planeación de supervisión](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) en la documentación de planeación y [datos de SQL Server y la ubicación del archivo de registro](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.
  
> [!NOTE]
> Si la cuenta que se usa para publicar la topología tiene los permisos y derechos de usuario adecuados, puede crear la base de datos de supervisión al publicar la topología. También puede crear la base de datos más adelante, incluidos como parte del procedimiento de instalación. > Para instalar e implementar las bases de datos en el servidor basado en SQL Server para la supervisión, debe ser miembro del grupo de administradores del sistema de SQL Server para el servidor de SQL Server donde va a instalar los archivos de base de datos. Si no es un miembro del grupo de sysadmin de SQL Server, debe solicitar que se agregará al grupo hasta que se implementan los archivos de base de datos. Si no se puede realizar un miembro del grupo Administradores del sistema, debe proporcionar el Administrador de la base de datos de SQL Server con la secuencia de comandos para configurar e implementar las bases de datos. Para obtener información detallada sobre los derechos de usuario y los permisos que se deben llevar a cabo estos procedimientos, vea [Permisos de implementación para SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.
  


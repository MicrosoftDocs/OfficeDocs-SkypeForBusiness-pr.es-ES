---
title: Agregar almacén de SQL Server del servidor de supervisión
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Servidor de supervisión requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definido anteriormente se utiliza para supervisar, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que reside la base de datos de SQL Server, además de la instancia de SQL Servidor que desea utilizar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: f52f44acd9ca57112da75fcc368d8ebaae99b081
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-monitoring-server-sql-server-store"></a>Agregar almacén de SQL Server del servidor de supervisión
 
Servidor de supervisión requiere una edición de 64 bits compatible del software de base de datos de SQL Server para almacenar los datos de supervisión. Puede seleccionar una base de datos de SQL Server definido anteriormente se utiliza para supervisar, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que reside la base de datos de SQL Server, además de la instancia de SQL Servidor que desea utilizar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
  
Para obtener más información acerca de SQL Server admite, consulte el [Software de base de datos y admite clústeres](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) en la documentación de soporte. Para obtener más información acerca de la supervisión la base de datos, incluyendo la colocación de la base de datos de supervisión, consulte [Ubicación de servidor compatible](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) en la documentación de soporte,[planificación de supervisión](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) en la documentación de planificación y [de datos de SQL Server y la ubicación del archivo de registro](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) en la documentación de implementación.
  
> [!NOTE]
> Si la cuenta utilizada para publicar la topología tiene los derechos de usuario apropiados y los permisos, puede crear la base de datos de supervisión al publicar la topología. También puede crear la base de datos más adelante, incluidos como parte del procedimiento de instalación. > Para instalar y distribuir las bases de datos en el servidor basado en SQL Server para supervisar, debe ser miembro del grupo de administradores del sistema de SQL Server para el servidor basado en SQL Server donde está instalando los archivos de base de datos. Si no es un miembro del grupo de sysadmin de SQL Server, debe solicitar a agregarse al grupo hasta que los archivos de base de datos se implementan. Si no puede realizarse un miembro del grupo Administradores del sistema, debe proporcionar el Administrador de la base de datos de SQL Server con la secuencia de comandos para configurar e implementar las bases de datos. Para obtener más información acerca de los derechos de usuario y los permisos que necesita llevar a cabo estos procedimientos, vea [Permisos de implementación de SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.
  


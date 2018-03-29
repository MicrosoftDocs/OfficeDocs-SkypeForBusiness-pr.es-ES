---
title: Agregar Front-End de almacenamiento de Archiving
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: El archivado requiere una edición de 64 bits compatible del software de base de datos de Microsoft SQL Server para almacenar los datos de archivado. Puede seleccionar una base de datos de SQL Server definida previamente que se utilizará para archiving, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que la base de datos de SQL Server que se resida, además de la instancia de SQL Se nera que desea utilizar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
ms.openlocfilehash: 528c8062b07593a4c7e4cc00f3d1d2566c05f77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-archiving-store"></a>Agregar Front-End de almacenamiento de Archiving
 
El archivado requiere una edición de 64 bits compatible del software de base de datos de Microsoft SQL Server para almacenar los datos de archivado. Puede seleccionar una base de datos de SQL Server definida previamente que se utilizará para archiving, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que la base de datos de SQL Server que se resida, además de la instancia de SQL Se nera que desea utilizar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique).
  
> [!NOTE]
> Si la cuenta utilizada para publicar la topología tiene los derechos de usuario apropiados y los permisos, puede crear la base de datos de supervisión al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación. 
  
> [!NOTE]
> Para instalar y distribuir las bases de datos en el servidor basado en SQL Server para supervisar, debe ser miembro del grupo de administradores del sistema de SQL Server para el servidor basado en SQL Server donde está instalando los archivos de base de datos. Si no es un miembro del grupo de sysadmin de SQL Server, debe solicitar que se agrega al grupo hasta que los archivos de base de datos se implementan. Si no puede realizarse un miembro del grupo Administradores del sistema, debe proporcionar el Administrador de la base de datos de SQL Server con la secuencia de comandos para configurar e implementar las bases de datos. Para obtener más información acerca de los derechos de usuario y los permisos que necesita llevar a cabo los procedimientos, consulte [Permisos de implementación de SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) en la documentación de implementación.
  


---
title: Agregar almacén de de SQL Server de extremo frontal
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Una implementación de Standard Edition server instala automáticamente el software necesario de la base de datos Microsoft SQL Server Express y base de datos de SQL Server. Por lo tanto, todas las opciones se completan automáticamente y no puede realizar cambios a la configuración predeterminada.
ms.openlocfilehash: facb2e91511323e6fc87015016b060ba5076c8f6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-sql-server-store"></a>Agregar almacén de de SQL Server de extremo frontal
 
Una implementación de Standard Edition server instala automáticamente el software necesario de la base de datos Microsoft SQL Server Express y base de datos de SQL Server. Por lo tanto, todas las opciones se completan automáticamente y no puede realizar cambios a la configuración predeterminada.
  
El grupo de servidores frontales de una implementación de Enterprise Edition server requiere una edición de 64 bits compatible del software de base de datos de SQL Server para la base de datos back-end. Puede seleccionar una base de datos de SQL Server definida previamente que se utilizará para la base de datos back-end, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que la base de datos de SQL Server es que resida y la instancia de SQL S servidor que desea utilizar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique). También puede optar por habilitar la creación de reflejos en el almacén de SQL Server y especificar a un testigo para la conmutación por error automática espejado.
  
Para obtener más información acerca de SQL Server admite, consulte el [Software de base de datos y admite clústeres](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) en la documentación de soporte. Para obtener más información acerca de cómo configurar SQL Server para la base de datos back-end, vea [Configurar SQL Server para Lync Server 2010](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) en la documentación de implementación.
  
> [!NOTE]
> Si la cuenta que se utiliza para publicar la topología tiene los derechos de usuario apropiados y los permisos, puede crear la base de datos back-end (comunicaciones en tiempo real (RTC)) al publicar la topología. También puede crear la base de datos más adelante, incluidos como parte del procedimiento de instalación. 
  
> [!NOTE]
> Para instalar y distribuir las bases de datos en el servidor basado en SQL Server para una implementación de Enterprise Edition, debe ser miembro del grupo de administradores del sistema de SQL Server para el servidor basado en SQL Server donde está instalando los archivos de base de datos. Si no es un miembro del grupo de administradores del sistema de SQL Server, debe solicitar a agregarse al grupo hasta que los archivos de base de datos se implementan. Si no puede realizarse un miembro del grupo Administradores del sistema, debe proporcionar el Administrador de la base de datos de SQL Server con la secuencia de comandos para configurar e implementar las bases de datos. Para obtener más información acerca de los derechos de usuario y los permisos que necesita llevar a cabo los procedimientos, consulte [Permisos de implementación de SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx). 
  


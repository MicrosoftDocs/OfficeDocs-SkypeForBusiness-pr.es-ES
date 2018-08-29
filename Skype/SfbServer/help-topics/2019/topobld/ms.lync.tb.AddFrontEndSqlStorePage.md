---
title: Agregar almacén de Front-End SQL Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Una implementación de Standard Edition server instala automáticamente el software de base de datos de Microsoft SQL Server Express requerido y la base de datos de SQL Server. Por lo tanto, todas las opciones se rellena automáticamente y no se puede realizar cambios a la configuración predeterminada.
ms.openlocfilehash: 31abc84b05486ae2aefe361bfd239714f6e91189
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245792"
---
# <a name="add-front-end-sql-server-store"></a>Agregar almacén de Front-End SQL Server

Una implementación de Standard Edition server instala automáticamente el software de base de datos de Microsoft SQL Server Express requerido y la base de datos de SQL Server. Por lo tanto, todas las opciones se rellena automáticamente y no se puede realizar cambios a la configuración predeterminada.

El grupo de servidores Front-End de una implementación de Enterprise Edition server requiere una edición de 64 bits compatible del software de base de datos de SQL Server para la base de datos back-end. Puede seleccionar una base de datos de SQL Server definido previamente que se usará para la base de datos back-end, o definir una nueva base de datos de SQL Server mediante la especificación de un nombre de dominio completo (FQDN) del servidor en el que se residen la base de datos de SQL Server y la instancia de SQL S servidor que desea usar para la nueva base de datos de SQL Server (que puede ser la instancia predeterminada o una instancia con nombre que especifique). También puede optar por habilitar la creación de reflejos en el almacén de SQL Server y especificar a un testigo de reflejo para conmutación por error automática.

Para obtener más información acerca de SQL Server admite, vea [admitir la agrupación en clústeres y Software de base de datos](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) en la documentación referente a. Para obtener información detallada acerca de cómo configurar SQL Server para la base de datos back-end, vea [Configurar SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) en la documentación de implementación.

> [!NOTE]
> Si la cuenta que se usa para publicar la topología tiene los permisos y derechos de usuario adecuados, puede crear la base de datos back-end (comunicaciones en tiempo real (RTC)) al publicar la topología. También puede crear la base de datos más adelante, incluidos como parte del procedimiento de instalación.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para una implementación de Enterprise Edition, debe ser miembro del grupo de administradores del sistema de SQL Server para el servidor de SQL Server donde va a instalar los archivos de base de datos. Si no es un miembro del grupo de sysadmin de SQL Server, debe solicitar que se agregará al grupo hasta que se implementan los archivos de base de datos. Si no se puede realizar un miembro del grupo Administradores del sistema, debe proporcionar el Administrador de la base de datos de SQL Server con la secuencia de comandos para configurar e implementar las bases de datos. Para obtener información detallada sobre los derechos de usuario y los permisos que se deben llevar a cabo los procedimientos, vea [Permisos de implementación para SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).



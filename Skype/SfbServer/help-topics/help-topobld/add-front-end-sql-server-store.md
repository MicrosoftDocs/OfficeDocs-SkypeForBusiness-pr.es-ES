---
title: Agregar almacén SQL Server front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Una implementación de servidor Standard Edition instala automáticamente el software de base de datos de Microsoft SQL Server Express necesario y la base de datos de SQL Server. Por lo tanto, todas las opciones se rellenan previamente y no puede realizar cambios en la configuración predeterminada.
ms.openlocfilehash: 614c3a852bb52a73c8a3f71ee467a2d71f82e9b6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216501"
---
# <a name="add-front-end-sql-server-store"></a>Agregar almacén SQL Server front-end

Una implementación de servidor Standard Edition instala automáticamente el software de base de datos de Microsoft SQL Server Express necesario y la base de datos de SQL Server. Por lo tanto, todas las opciones se rellenan previamente y no puede realizar cambios en la configuración predeterminada.

El grupo de servidores front-end de una implementación de servidor Enterprise Edition requiere una edición de 64 bits compatible del software de base de datos de SQL Server para la base de datos back-end. Puede seleccionar una base de datos de SQL Server previamente definida para usarla para la base de datos back-end, o bien definir una nueva base de datos de SQL Server especificando un nombre de dominio completo (FQDN) del servidor en el que va a residir la base de datos de SQL Server y la instancia de SQL Server que desea usar para la nueva base de datos de SQL Server o una instancia con nombre que haya especificado). También puede elegir habilitar la creación de reflejos en el almacén de SQL Server y especificar un testigo de reflejos para la conmutación por error automática.

Para obtener más información acerca del soporte técnico de SQL Server, consulte [Database Software and clustering support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) en la documentación sobre compatibilidad. Para obtener más información sobre cómo configurar SQL Server para la base de datos back-end, consulte[Configurar SQL Server para Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) en la documentación sobre implementación.

> [!NOTE]
> Si la cuenta que se utiliza para publicar la topología tiene los permisos y derechos de usuario adecuados, puede crear la base de datos back-end (comunicaciones en tiempo real (CTR)) al publicar la topología. También puede crear la base de datos más adelante, como parte del procedimiento de instalación.

> [!NOTE]
> Para instalar e implementar las bases de datos en el servidor basado en SQL Server para una implementación de Enterprise Edition, debe ser miembro del grupo sysadmins de SQL Server para el servidor basado en SQL Server en el que va a instalar los archivos de base de datos. Si no es miembro del grupo sysadmins de SQL Server, debe solicitar que se agregue al grupo hasta que se implementen los archivos de la base de datos. Si no se puede convertir en miembro del grupo sysadmins, debe proporcionar al administrador de la base de datos de SQL Server el script para configurar e implementar las bases de datos. Para más información sobre los permisos y derechos de usuario que se necesitan para realizar estos procedimientos, consulte [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).



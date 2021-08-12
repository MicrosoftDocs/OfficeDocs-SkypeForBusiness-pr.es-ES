---
title: Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: obtenga información sobre cómo agregar más bases de datos de Skype Empresarial Server a un grupo de disponibilidad AlwaysOn existente y obtenga información sobre los pasos adicionales necesarios después de aplicar la revisión o actualización de un servidor back-end que forma parte de un grupo de disponibilidad AlwaysOn en Skype Empresarial Server.'
ms.openlocfilehash: 705fc69d1c29807a0f32276a28268f2da932056d38e306db45b8c68e81f9a11b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314456"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype Empresarial Server

Siga los pasos descritos en este artículo para agregar más bases de datos de Skype Empresarial Server a un grupo de disponibilidad AlwaysOn existente en Skype Empresarial Server y descubra los pasos adicionales necesarios después de aplicar la revisión o actualización de un servidor back-end que forma parte de un grupo de disponibilidad AlwaysOn en Skype Empresarial Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Agregar bases de datos a un grupo de disponibilidad AlwaysOn 

1. Abra SQL Server Management Studio y vaya al Grupo de disponibilidad AlwaysOn. Conmutación por error a la réplica principal.
    
2. En el Generador de topologías, establezca SQL Server FQDN del grupo de disponibilidad AlwaysOn en el FQDN del nodo principal de ese grupo.
    
   - Abra el Generador de topologías, **seleccione Descargar topología de la implementación existente** y haga clic en **Aceptar**.
    
   - Expanda Skype Empresarial Server, expanda la topología y expanda **SQL Server Stores**. Haga clic con el botón secundario en SQL almacén del nuevo grupo de disponibilidad AlwaysOn y haga clic **en Editar propiedades**.
    
   - En la parte inferior de la página, en el cuadro **SQL Server FQDN,** escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.
    
3. Publique la topología. En el **menú Acción,** **haga clic en Topología** y, a continuación, en **Publicar**. A continuación, en la página de confirmación, haga clic **en Siguiente**.
    
4. Use SQL Server Management Studio para agregar la nueva base de datos al grupo de disponibilidad AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Aplicar revisiones o actualizar un SQL Server en un grupo de disponibilidad AlwaysOn

Después de aplicar una revisión a un servidor back-end que forma parte de un grupo de disponibilidad AlwaysOn, debe volver a publicar la topología.

1. Instale la actualización en el servidor Skype Empresarial o servidores.
    
2. Ejecute el siguiente comando de PowerShell en el Shell de administración de Skype Empresarial (ha iniciado sesión con una cuenta con permiso adecuado para aplicar cambios en las bases de datos de SQL AlwaysOn) de la siguiente manera:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Donde [sqlpool.contoso.com] se reemplaza por el nombre de dominio completo (FQDN) del grupo de disponibilidad AlwaysOn.

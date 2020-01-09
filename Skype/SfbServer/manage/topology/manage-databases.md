---
title: Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: Aprenda a agregar más bases de datos de Skype empresarial Server a un grupo de disponibilidad AlwaysOn existente y obtenga más información sobre los pasos adicionales necesarios después de la revisión o la actualización de un servidor back-end que forma parte de un grupo de disponibilidad AlwaysOn en Skype para Business Server.'
ms.openlocfilehash: 221964eb7d8dfcbb0303a0e1148de4fcef6cec51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991545"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype empresarial Server

Siga los pasos descritos en este artículo para agregar más bases de datos de Skype empresarial Server a un grupo de disponibilidad AlwaysOn existente en Skype empresarial Server y conocer los pasos adicionales necesarios después de la revisión o actualizar un servidor back-end que forma parte de Grupo disponibilidad en Skype empresarial Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Agregar bases de datos a un grupo de disponibilidad AlwaysOn 

1. Abra SQL Server Management Studio y vaya al grupo disponibilidad AlwaysOn. Conmuta por error a la réplica principal.
    
2. En el generador de topología, establezca el FQDN de SQL Server del grupo de disponibilidad AlwaysOn en el FQDN del nodo principal de ese grupo.
    
   - Abra el generador de topologías, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.
    
   - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. Haga clic con el botón derecho en el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.
    
   - En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.
    
3. Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**.
    
4. Use SQL Server Management Studio para agregar la nueva base de datos al grupo de disponibilidad AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Revisar o actualizar un SQL Server en un grupo de disponibilidad AlwaysOn

Después de revisar un servidor back-end que forma parte de un grupo de disponibilidad AlwaysOn, debe volver a publicar la topología.

1. Instale la actualización en su servidor o servidores de Skype empresarial.
    
2. Ejecute el siguiente comando de PowerShell en el shell de administración de Skype empresarial (sesión iniciada con una cuenta que se ha cometido correctamente para aplicar cambios en las bases de datos de SQL AlwaysOn) de la siguiente manera:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Donde [sqlpool.contoso.com] se reemplaza por el nombre de dominio completo (FQDN) del grupo de disponibilidad AlwaysOn.

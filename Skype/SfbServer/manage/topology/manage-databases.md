---
title: Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: Obtenga información sobre cómo agregar más Skype para bases de datos de Business Server a un grupo existente de disponibilidad AlwaysOn y obtenga información sobre los pasos adicionales necesarios después de la revisión o actualizar un servidor Back-End que forma parte de un grupo de disponibilidad AlwaysOn en Skype para Business Server.'
ms.openlocfilehash: 8d25e7d3aa1e840be7eb246e6aaa3065b65b7ff7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875414"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Administrar bases de datos con un grupo de disponibilidad AlwaysOn en Skype para Business Server

Use los pasos de este artículo para agregar más Skype para bases de datos de Business Server a un grupo de disponibilidad AlwaysOn existente de Skype para Business Server y obtenga información acerca de los pasos adicionales necesarios después de una revisión o actualización de un servidor Back-End que forma parte de un AlwaysOn Grupo de disponibilidad en Skype para Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Agregar las bases de datos a un grupo de disponibilidad AlwaysOn 

1. Abra SQL Server Management Studio y navegue hasta el grupo de disponibilidad AlwaysOn. Conmutación por error se a la réplica principal.
    
2. En el generador de topología, establezca el FQDN del grupo de disponibilidad AlwaysOn de SQL Server en el FQDN del nodo principal de ese grupo.
    
   - Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.
    
   - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. Haga clic en el almacén de SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.
    
   - En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.
    
3. Publique la topología. En el menú **Acción**, haga clic en **Topología** y después en **Publicar**. A continuación, en la página de confirmación, haga clic en **Siguiente**.
    
4. Use SQL Server Management Studio para agregar la nueva base de datos para el grupo de disponibilidad AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Una revisión o actualizar un servidor SQL Server en un grupo de disponibilidad AlwaysOn

Después de la aplicación de revisiones de un servidor Back-End que forma parte de un grupo de disponibilidad AlwaysOn, debe volver a publicar la topología.

1. Instalar la actualización en su Skype para Business server o servidores.
    
2. Ejecute el siguiente comando de PowerShell en su Skype para Shell de administración de negocio (iniciado la sesión con una cuenta que sea adecuadamente con permisos únicos para aplicar los cambios a las bases de datos de AlwaysOn de SQL) como sigue:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Donde [sqlpool.contoso.com] se sustituye por el nombre de dominio completo (FQDN) de su grupo de disponibilidad AlwaysOn.

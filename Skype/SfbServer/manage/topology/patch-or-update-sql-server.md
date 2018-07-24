---
title: Una revisión o actualización de un servidor SQL Server en un grupo de disponibilidad AlwaysOn en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Resumen: Obtenga información acerca de los pasos adicionales necesarios después de la revisión, o actualizar un servidor Back-End que forma parte de un grupo de disponibilidad AlwaysOn en Skype para Business Server.'
ms.openlocfilehash: 7227bdc61e7accbdd6f6e760e1a33d9a2b76eb30
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982989"
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server"></a>Una revisión o actualización de un servidor SQL Server en un grupo de disponibilidad AlwaysOn en Skype para Business Server
 
**Resumen:** Obtenga información acerca de los pasos adicionales necesarios después de una revisión o actualización de un servidor Back-End que forma parte de un grupo de disponibilidad AlwaysOn en Skype para Business Server.
  
Después de la aplicación de revisiones de un servidor Back-End que forma parte de un grupo de disponibilidad AlwaysOn, debe volver a publicar la topología.
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a>Aplicar las revisiones o actualizar un servidor SQL Server que forma parte de un grupo de disponibilidad AlwaysOn

1. Instalar la actualización en su Skype para Business server o servidores.
    
2. Ejecute el siguiente comando de PowerShell en su Skype para Shell de administración de negocio (iniciado la sesión con una cuenta que sea adecuadamente con permisos únicos para aplicar los cambios a las bases de datos de AlwaysOn de SQL) como sigue:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Donde [sqlpool.contoso.com] se sustituye por el nombre de dominio completo (FQDN) de su grupo de disponibilidad AlwaysOn.
    


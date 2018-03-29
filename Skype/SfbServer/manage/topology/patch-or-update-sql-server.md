---
title: Revisiones o actualizaciones a un SQL Server en un grupo de disponibilidad AlwaysOn en Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Resumen: Conozca los pasos adicionales necesarios después de la revisión se o actualizar a un nuevo servidor que forma parte de un grupo de disponibilidad AlwaysOn en Skype para Business Server.'
ms.openlocfilehash: 8f5c9131e59ccedd7f590f696fe53aa6c18c7d22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>Revisiones o actualizaciones a un SQL Server en un grupo de disponibilidad AlwaysOn en Skype para Business Server 2015
 
**Resumen:** Obtenga información sobre los pasos adicionales necesarios después de revisar o actualizar un nuevo servidor que forma parte de un grupo de disponibilidad AlwaysOn en Skype para Business Server.
  
Después de la revisión de un nuevo servidor que forma parte de un grupo de disponibilidad AlwaysOn, debe volver a publicar la topología.
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a>Revisión o actualización de un SQL Server que forma parte de un grupo de disponibilidad AlwaysOn

1. Instalar la actualización en su Skype para Business server o servidores.
    
2. Ejecute el siguiente comando de PowerShell en su Skype para el Shell de administración de negocios (iniciado la sesión con una cuenta que sea adecuadamente tiene permiso para aplicar los cambios a las bases de datos SQL AlwaysOn) como sigue:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Donde [sqlpool.contoso.com] se reemplaza por el nombre de dominio completo (FQDN) de su grupo de disponibilidad AlwaysOn.
    


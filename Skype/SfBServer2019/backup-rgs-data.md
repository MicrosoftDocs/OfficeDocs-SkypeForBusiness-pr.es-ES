---
title: Copia de seguridad de Servicio de grupo de respuesta (RGS) en Skype Empresarial Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Obtenga información sobre cómo hacer una copia Servicio de grupo de respuesta (RGS) en Skype Empresarial Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824074"
---
# <a name="back-up-response-group-service-rgs-data"></a>Copia de seguridad de Servicio de grupo de respuesta datos de Servicio de grupo de respuesta (RGS)

Con la actualización acumulativa de julio de Skype Empresarial Server 2019, hemos incluido la capacidad de incluir datos RGS como parte de la copia de seguridad estándar.

## <a name="rgs-data-replication"></a>Replicación de datos RGS

Para probar la funcionalidad de replicación de datos RGS, siga los pasos siguientes:

1. Instale la actualización acumulativa de julio en todos los front-ends (FE) del grupo emparejado.
1. Instale la base de datos RGS en ambos miembros del grupo emparejado:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Ejecute el siguiente cmdlet en ambos grupos de servidores para replicar los datos RGS existentes en las tablas de copia de seguridad para que RGSBackupService pueda seleccionar los datos:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Habilite RGSBackupService (esto habilitará RGSBackupService globalmente. Si este parámetro se establece en true, RGSBackupService empezará a sincronizar datos RGS en grupos emparejados (ambos grupos deben ser CU1). Espere unos minutos para empezar. Inicialmente, el estado de RGS BackupService será NotInitialized.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Para comprobar BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Para comprobar DataReplication entre grupos de servidores, use estos cmdlets (estos cmdlets muestran solo los datos del grupo de propietarios):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Para comprobar los datos RGS del grupo de propietarios y sus datos de copia de seguridad:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Compruebe la funcionalidad del flujo de trabajo realizando una llamada de audio al flujo de trabajo.
1. Conmutación por error del grupo de propietarios de RGS.
1. Compruebe la funcionalidad del flujo de trabajo realizando una llamada de audio al flujo de trabajo.
1. Conmutación por recuperación del grupo de servidores.
1. Actualice los datos de RGS en el grupo de servidores de origen y realice otra conmutación por error para comprobar que los cambios se reflejan en el grupo de copia de seguridad. RGS debe comportarse de la misma manera que se comportaba antes de la conmutación por error.

> [!TIP]
> Se recomienda realizar estos pasos en una gran cantidad de datos y realizar conmutación por error y conmutación por recuperación frecuentes. También se deben replicar los nuevos RGS creados después de esta actualización cu.

## <a name="rgs-cmdlets"></a>Cmdlets RGS

- Para comprobar BackupServiceStatus (el estado de exportación debe estar en estado final o estable. El estado de importación debe estar en el estado Normal. RGSBackupservice debe estar habilitado.
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Para sincronizar completamente los datos RGS en el grupo de servidores de copia de seguridad (esto sincronizará los datos RGS completos en el grupo de servidores de copia de seguridad).
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Para sincronizar completamente el almacén de archivos RGS en el grupo de servidores de copia de seguridad (esto sincronizará los datos RGS completos en el grupo de servidores de copia de seguridad).
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Para sincronizar datos delta de RGS en el grupo de servidores de copia de seguridad (esto sincronizará los datos delta en el grupo de copia de seguridad solo para RGS).
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Para sincronizar todos los datos del módulo, incluido RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Para deshabilitar RGSBackupService (esto deshabilitará RGSBackupService globalmente. Si este parámetro se establece en true, RGSBackupService se deshabilitará en todos los grupos emparejados.
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`

---
title: Copia de seguridad de los datos del servicio de grupo de respuesta (RGS) en Skype empresarial Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: Obtenga información sobre cómo hacer una copia de seguridad de los datos del servicio de grupo de respuesta (RGS) en Skype empresarial Server 2019.
ms.openlocfilehash: 0a37b4d4771a75513666597de5eb87dedcbcd0c7
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821337"
---
# <a name="back-up-response-group-service-rgs-data"></a>Hacer una copia de seguridad de los datos del servicio de grupo de respuesta (RGS)

Con la actualización acumulativa de Skype empresarial Server 2019 de julio, hemos incluido la capacidad de incluir datos RGS como parte de la copia de seguridad estándar.

## <a name="rgs-data-replication"></a>Replicación de datos RGS

Siga los pasos que se indican a continuación para probar la funcionalidad de replicación de datos.

1. Instale la actualización acumulativa de julio en todos los front-ends (FEs) del grupo emparejado.
1. Instale la base de datos RGS en ambos miembros del grupo emparejado:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Ejecute el siguiente cmdlet en ambos grupos para replicar los datos RGS existentes en las tablas de copia de seguridad de modo que los datos puedan ser recogidos por RGSBackupService:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Habilitar RGSBackupService (esto le permitirá RGSBackupService globalmente. Si este parámetro se establece en true, RGSBackupService comenzará a sincronizar los datos de RGS en los grupos emparejados (los dos grupos deben ser CU1). Espere unos minutos hasta que se inicie. Inicialmente, el estado de RGS BackupService será NotInitialized.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Para comprobar BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Para comprobar la replicación de datos entre grupos, use estos cmdlets (estos cmdlets solo muestran los datos del grupo de propietarios):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Para comprobar los datos del grupo de propietarios RGS y sus datos de copia de seguridad:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Comprobar la funcionalidad de flujo de trabajo realizando una llamada de audio al flujo de trabajo.
1. Conmute por error al grupo de propietarios de RGS.
1. Comprobar la funcionalidad de flujo de trabajo realizando una llamada de audio al flujo de trabajo.
1. Failback de la agrupación.
1. Actualice los datos de RGS en el grupo de origen y realice otra conmutación por error para comprobar que los cambios se reflejan en el grupo de copia de seguridad. RGS debe comportarse de la misma manera en que se comporta antes de la conmutación por error.

> [!TIP]
> Le recomendamos que realice estos pasos en una gran mayoría de datos y realice tareas de recuperación y conmutación por error frecuentes. También se debe replicar cualquier nuevo RGS creado después de esta actualización de CU.

## <a name="rgs-cmdlets"></a>Cmdlets de RGS

- Para comprobar BackupServiceStatus (el estado de exportación debe estar en el estado final o permanente). El estado de la importación debe ser normal. RGSBackupservice debe estar habilitado.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Para sincronizar completamente los datos de RGS en el grupo de copia de seguridad (esto sincronizará los datos RGS completos del grupo de copias de seguridad):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Para sincronizar completamente el almacén de datos RGS en el grupo de copias de seguridad (esto sincronizará los datos RGS completos en el grupo de copias de seguridad):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Para sincronizar los datos Delta de RGS en el grupo de copia de seguridad (esto sincronizará los datos Delta en el grupo de copia de seguridad solo para RGS):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Para sincronizar todos los datos de módulo, incluido RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Para deshabilitar RGSBackupService (se deshabilitará RGSBackupService globalmente. Si este parámetro se establece en true, RGSBackupService se deshabilitará en todos los grupos emparejados.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`

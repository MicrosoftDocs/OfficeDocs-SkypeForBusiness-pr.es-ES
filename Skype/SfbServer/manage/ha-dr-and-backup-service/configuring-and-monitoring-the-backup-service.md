---
title: Configurar y supervisar el servicio de copia de seguridad
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede usar Skype para comandos de Shell de administración de Business Server para configurar y supervisar el servicio de copia de seguridad.
ms.openlocfilehash: f06da0cad4bf6a7deb5ab098530bfea548db21f9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222887"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configurar y supervisar el servicio de copia de seguridad de Skype para Business Server

Puede usar el siguiente Skype para comandos de Shell de administración de Business Server para configurar y supervisar el servicio de copia de seguridad. Para restaurar la información de conferencia almacenada en el almacén de archivos de un grupo de servidores Front-End, vea [Restaurar contenidos de conferencia mediante el servicio de copia de seguridad](#restore-conference-contents-using-the-backup-service), más adelante.

> [!NOTE]  
> Grupo RTCUniversalServerAdmins es el único grupo que tiene permisos para ejecutar **Get-CsBackupServiceStatus** de forma predeterminada. Para usar este cmdlet, inicie sesión como un miembro de este grupo. O bien, puede conceder acceso a este comando a otros grupos (por ejemplo, CSAdministrator) mediante el cmdlet **Set-CsBackupServiceConfiguration** .

## <a name="to-see-the-backup-service-configuration"></a>Para ver la configuración del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceConfiguration

El valor predeterminado de SyncInterval es de dos minutos.

## <a name="to-set-the-backup-service-sync-interval"></a>Para establecer el intervalo de sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Por ejemplo, el siguiente establece el intervalo en tres minutos.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Aunque se puede usar este cmdlet para cambiar el intervalo de sincronización predeterminado para el servicio de copia de seguridad, no debe hacer por lo que a menos que sea absolutamente necesario, como la sincronización de intervalo tiene un gran impacto en el rendimiento del servicio de copia de seguridad y el objetivo de punto de recuperación (RPO).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Para obtener el estado del servicio de copia de seguridad para un determinado grupo de servidores

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> El estado de sincronización del servicio de copia de seguridad se define unidirectionally desde un grupo de servidores (P1) a su grupo de copia de seguridad (P2). El estado de la sincronización de P1 a P2 puede ser diferente de P2 a P1. Para P1 a P2, el servicio de copia de seguridad está en un estado "constante" si todos los cambios realizados en P1 se replican completamente a través de a P2 dentro del intervalo de sincronización. No es en el estado "final" Si no hay ningún cambio para que esté sincronizada de P1 a P2. Ambos Estados indicarán una instantánea del servicio de copia de seguridad en el momento en que se ejecuta el cmdlet. No implica que el estado devuelto permanecerá tal cual después. En particular, el estado "final" seguirá contener sólo si P1 no se genera ningún cambio después de ejecuta el cmdlet. Esto es así en el caso de conmutación por error P1 a P2 después de P1 se coloca en el modo de solo lectura como parte de la lógica de ejecución **Invoke-CsPoolfailover** .

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Para obtener información acerca de la relación de copia de seguridad para un determinado grupo de servidores

Ejecute el siguiente cmdlet:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Para forzar una sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Restauración de contenidos de conferencia mediante el servicio de copia de seguridad 

Si no está disponible la información de conferencia almacenada en el almacén de archivos de un grupo de servidores Front-End, debe restaurar esta información para que los usuarios alojados en el grupo de servidores mantienen sus datos de conferencia. Si el grupo de servidores Front-End que ha perdido datos de la conferencia se corresponde con otro grupo de servidores Front-End, puede usar el servicio de copia de seguridad para restaurar los datos.

También debe realizar esta tarea si ha generado un error en un grupo de servidores completa y haya se lleve a cabo a través de sus usuarios a un grupo de copia de seguridad. Cuando estos usuarios se no se pudo volver a través de su grupo de servidores original, debe usar este procedimiento para copiar el contenido de su conferencias así como su grupo de servidores original.

Se supone que grupo1 se empareja con Grupo2, y se perderán los datos de conferencia en el grupo1. Puede usar el cmdlet siguiente para invocar el servicio de copia de seguridad para restaurar el contenido:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Restaurar el contenido de la conferencia puede tardar algún tiempo, dependiendo de su tamaño. Puede usar el cmdlet siguiente para comprobar el estado del proceso:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

El proceso se realiza cuando este cmdlet devuelve un valor de estado estable para el módulo de conferencia de datos.
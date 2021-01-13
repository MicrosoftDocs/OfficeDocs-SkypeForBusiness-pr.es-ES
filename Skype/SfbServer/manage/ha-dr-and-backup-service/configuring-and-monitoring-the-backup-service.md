---
title: Configurar y supervisar el servicio de copia de seguridad
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede usar los comandos del Shell de administración de Skype Empresarial Server para configurar y supervisar el servicio de copia de seguridad.
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817200"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configuración y supervisión del servicio de copia de seguridad en Skype Empresarial Server

Puede usar los siguientes comandos del Shell de administración de Skype Empresarial Server para configurar y supervisar el servicio de copia de seguridad. Para restaurar la información de conferencia almacenada en el almacén de archivos de un grupo de servidores front-end, consulte Restaurar el contenido de conferencia mediante el servicio de copia de [seguridad](#restore-conference-contents-using-the-backup-service), a continuación.

> [!NOTE]  
> El grupo RTCUniversalServerAdmins es el único grupo que tiene permisos para ejecutar **Get-CsBackupServiceStatus** de forma predeterminada. Para usar este cmdlet, inicie sesión como miembro de este grupo. O bien, puede conceder acceso a este comando a otros grupos (por ejemplo, CSAdministrator) mediante el uso del cmdlet **Set-CsBackupServiceConfiguration**.

## <a name="to-see-the-backup-service-configuration"></a>Para ver la configuración del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceConfiguration

El valor predeterminado de SyncInterval es de dos minutos.

## <a name="to-set-the-backup-service-sync-interval"></a>Para establecer el intervalo de sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Por ejemplo, lo siguiente establece el intervalo en tres minutos.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Aunque puede usar este cmdlet para cambiar el intervalo de sincronización predeterminado para el servicio de copia de seguridad, no debe hacerlo a menos que sea absolutamente necesario, puesto que el intervalo de sincronización tiene un gran impacto en el rendimiento del servicio de copia de seguridad y en el objetivo del punto de recuperación (RPO).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Para obtener el estado del servicio de copia de seguridad para un determinado grupo de servidores

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> El estado de la sincronización del servicio de copia de seguridad se define unidireccionalmente desde un grupo de servidores (P1) hasta su grupo de servidores de copia de seguridad (P2). El estado de sincronización de P1 a P2 puede ser diferente que el de P2 a P1. Para P1 a P2, el servicio de copia de seguridad está en un estado "constante" si todos los cambios realizados en P1 se replican completamente sobre P2 dentro del intervalo de sincronización. Está en el estado "final" si no hay ningún cambio más que se vaya a sincronizar de P1 a P2. Ambos estados indican una instantánea del servicio de copia de seguridad en el momento en que se ejecuta el cmdlet. Esto no implica que el estado devuelto permanezca tal cual después. En particular, el estado "final" continuará manteniéndose solo si P1 no genera ningún cambio después de que se ejecute el cmdlet. Esto es cierto en caso de que se produzca un error de P1 sobre P2 después de que P1 se sitúe en el modo de solo lectura como parte de la lógica de ejecución de **Invoke-CsPoolfailover**.

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Para obtener información acerca de la relación de copia de seguridad de un determinado grupo de servidores

Ejecute el siguiente cmdlet:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Para forzar una sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Restauración del contenido de conferencia mediante el servicio de copia de seguridad 

Si la información de conferencia almacenada en el almacén de archivos de un grupo de servidores front-end deja de estar disponible, debe restaurar esta información para que los usuarios que están en el grupo conserven sus datos de conferencia. Si el grupo de servidores front-end que ha perdido datos de conferencia está emparejado con otro grupo de servidores front-end, puede usar el servicio de copia de seguridad para restaurar los datos.

También debe realizar esta tarea si se produce un error en un grupo de servidores entero y tiene que realizar la conmutación por error de sus usuarios a un servidor de copia de seguridad. Cuando estos usuarios se conmutan por error a su grupo de servidores original, también debe utilizar este procedimiento para copiar su contenido de conferencia de vuelta a su grupo de servidores original.

Supongamos que Grupo1 se usa junto con Grupo2 y que los datos de conferencia de Grupo1 se pierde. Puede usar el siguiente cmdlet para invocar el servicio de copia de seguridad para restaurar el contenido:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

La restauración de los contenidos de conferencia podría demorar un poco, según su tamaño. Puede utilizar el siguiente cmdlet para ver el estado del proceso:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

El proceso finaliza cuando este cmdlet devuelve un valor de Estado parejo para el módulo de datos de conferencia.

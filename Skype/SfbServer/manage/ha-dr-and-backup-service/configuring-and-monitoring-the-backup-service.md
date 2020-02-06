---
title: Configurar y supervisar el servicio de copia de seguridad
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede usar los comandos de Shell de administración de Skype empresarial para configurar y supervisar el servicio de copia de seguridad.
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818221"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configurar y supervisar el servicio de copia de seguridad en Skype empresarial Server

Puede usar los siguientes comandos de Shell de administración de Skype empresarial para configurar y supervisar el servicio de copia de seguridad. Para restaurar la información de conferencia almacenada en el almacén de archivos de un grupo de servidores front-end, vea [restaurar el contenido de la Conferencia con el servicio de copia de seguridad](#restore-conference-contents-using-the-backup-service)a continuación.

> [!NOTE]  
> El grupo RTCUniversalServerAdmins es el único grupo que tiene permisos para ejecutar **Get-CsBackupServiceStatus** de forma predeterminada. Para usar este cmdlet, inicia sesión como miembro de este grupo. O bien, puede conceder acceso a este comando a otros grupos (por ejemplo, CSAdministrator) mediante el cmdlet **set-CsBackupServiceConfiguration** .

## <a name="to-see-the-backup-service-configuration"></a>Para ver la configuración del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceConfiguration

El valor predeterminado de SyncInterval es de dos minutos.

## <a name="to-set-the-backup-service-sync-interval"></a>Para establecer el intervalo de sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Por ejemplo, la siguiente establece el intervalo en tres minutos.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Aunque puede usar este cmdlet para cambiar el intervalo de sincronización predeterminado del servicio de copia de seguridad, no debe hacerlo a menos que sea absolutamente necesario, ya que el intervalo de sincronización tiene un gran impacto en el rendimiento del servicio de copia de seguridad y el objetivo de punto de recuperación (RPO).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Para obtener el estado del servicio de copia de seguridad de un grupo en particular

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> El estado de sincronización del servicio de copia de seguridad se define de forma unidireccional desde un grupo (P1) a su grupo de copia de seguridad (P2). El estado de sincronización de P1 a P2 puede ser diferente del de P2 a P1. Para P1 a P2, el servicio de copia de seguridad se encuentra en estado "estable" si todos los cambios realizados en P1 se replican por completo a P2 dentro del intervalo de sincronización. Está en el estado "final" si no hay más cambios para sincronizar de P1 a P2. Ambos Estados indican una instantánea del servicio de copia de seguridad en el momento en que se ejecuta el cmdlet. No implica que el estado devuelto permanecerá como está después. En concreto, el estado "final" seguirá teniendo solo si P1 no genera ningún cambio después de que se ejecute el cmdlet. Esto es cierto en el caso de que se produzca un error P1 a través de la P2 después de poner P1 en modo de solo lectura como parte de la lógica de ejecución **Invoke-CsPoolfailover** .

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Para obtener información sobre la relación de copia de seguridad de un grupo de servidores determinado

Ejecute el siguiente cmdlet:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Para forzar la sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Restaurar el contenido de la Conferencia con el servicio de copia de seguridad 

Si la información de la Conferencia almacenada en el almacén de archivos de un grupo de servidores front-end no está disponible, debe restaurar esta información para que los usuarios alojados en el grupo conserven sus datos de la Conferencia. Si el grupo de servidores front-end que ha perdido los datos de la Conferencia está emparejado con otro grupo de servidores front-end, puede usar el servicio de copia de seguridad para restaurar los datos.

También debe realizar esta tarea si se ha producido un error en un grupo completo y tiene que migrar por error sus usuarios a un grupo de copia de seguridad. Cuando estos usuarios no realicen una conmutación por error a su grupo original, debe usar este procedimiento para copiar el contenido de la Conferencia a su grupo original.

Supongamos que Pool1 está emparejado con Pool2, y se pierden los datos de la Conferencia en Pool1. Puede usar el siguiente cmdlet para invocar el servicio de copia de seguridad para restaurar el contenido:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

La restauración del contenido de la Conferencia puede llevar algún tiempo, dependiendo de su tamaño. Puede usar el siguiente cmdlet para comprobar el estado del proceso:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

El proceso se realiza cuando este cmdlet devuelve un valor de estado estable para el módulo de conferencia de datos.

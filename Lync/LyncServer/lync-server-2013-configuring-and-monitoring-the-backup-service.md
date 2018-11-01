---
title: 'Lync Server 2013: Configurar y supervisar el servicio de copia de seguridad'
TOCTitle: Configurar y supervisar el servicio de copia de seguridad
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48276626
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar y supervisar el servicio de copia de seguridad en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Puede usar los siguientes comandos de Shell de administración de Lync Server para configurar y supervisar el servicio de copia de seguridad.


> [!NOTE]
> El grupo RTCUniversalServerAdmins es el único grupo que tiene permisos para ejecutar <STRONG>Get-CsBackupServiceStatus</STRONG> de forma predeterminada. Para usar este cmdlet, inicie sesión como miembro de este grupo. O bien, puede conceder acceso a este comando a otros grupos (por ejemplo, CSAdministrator) mediante el uso del cmdlet <STRONG>Set-CsBackupServiceConfiguration</STRONG>.



## Para ver la configuración del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceConfiguration

El valor predeterminado de SyncInterval es de dos minutos.

## Para establecer el intervalo de sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Por ejemplo, lo siguiente establece el intervalo en tres minutos.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

> [!IMPORTANT]  
> Aunque puede usar este cmdlet para cambiar el intervalo de sincronización predeterminado para el servicio de copia de seguridad, no debe hacerlo a menos que sea absolutamente necesario, puesto que el intervalo de sincronización tiene un gran impacto en el rendimiento del servicio de copia de seguridad y en el objetivo del punto de recuperación (RPO).



## Para obtener el estado del servicio de copia de seguridad para un determinado grupo de servidores

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>


> [!NOTE]
> El estado de la sincronización del servicio de copia de seguridad se define unidireccionalmente desde un grupo de servidores (P1) hasta su grupo de servidores de copia de seguridad (P2). El estado de sincronización de P1 a P2 puede ser diferente que el de P2 a P1. Para P1 a P2, el servicio de copia de seguridad está en un estado "constante" si todos los cambios realizados en P1 se replican completamente sobre P2 dentro del intervalo de sincronización. Está en el estado "final" si no hay ningún cambio más que se vaya a sincronizar de P1 a P2. Ambos estados indican una instantánea del servicio de copia de seguridad en el momento en que se ejecuta el cmdlet. Esto no implica que el estado devuelto permanezca tal cual después. En particular, el estado "final" continuará manteniéndose solo si P1 no genera ningún cambio después de que se ejecute el cmdlet. Esto es cierto en caso de que se produzca un error de P1 sobre P2 después de que P1 se sitúe en el modo de solo lectura como parte de la lógica de ejecución de <STRONG>Invoke-CsPoolfailover</STRONG>.



## Para obtener información acerca de la relación de copia de seguridad de un determinado grupo de servidores

Ejecute el siguiente cmdlet:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## Para forzar una sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]


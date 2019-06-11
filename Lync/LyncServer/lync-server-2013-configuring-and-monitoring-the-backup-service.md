---
title: 'Lync Server 2013: Configurar y supervisar el servicio de copia de seguridad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a800014b3327e83426c9f758b7d5359c1ce6c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Configurar y supervisar el servicio de copia de seguridad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Puede usar los siguientes comandos de Shell de administración de Lync Server para configurar y supervisar el servicio de copia de seguridad.

<div>


> [!NOTE]  
> El grupo RTCUniversalServerAdmins es el único grupo que tiene permisos para ejecutar <STRONG>Get-CsBackupServiceStatus</STRONG> de forma predeterminada. Para usar este cmdlet, inicia sesión como miembro de este grupo. O bien, puede conceder acceso a este comando a otros grupos (por ejemplo, CSAdministrator) mediante el cmdlet <STRONG>set-CsBackupServiceConfiguration</STRONG> .



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>Para ver la configuración del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceConfiguration

El valor predeterminado de SyncInterval es de dos minutos.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>Para establecer el intervalo de sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Por ejemplo, la siguiente establece el intervalo en tres minutos.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Aunque puede usar este cmdlet para cambiar el intervalo de sincronización predeterminado del servicio de copia de seguridad, no debe hacerlo a menos que sea absolutamente necesario, ya que el intervalo de sincronización tiene un gran impacto en el rendimiento del servicio de copia de seguridad y el objetivo de punto de recuperación (RPO).



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Para obtener el estado del servicio de copia de seguridad de un grupo en particular

Ejecute el siguiente cmdlet:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> El estado de sincronización del servicio de copia de seguridad se define de forma unidireccional desde un grupo (P1) a su grupo de copia de seguridad (P2). El estado de sincronización de P1 a P2 puede ser diferente del de P2 a P1. Para P1 a P2, el servicio de copia de seguridad se encuentra en estado "estable" si todos los cambios realizados en P1 se replican por completo a P2 dentro del intervalo de sincronización. Está en el estado "final" si no hay más cambios para sincronizar de P1 a P2. Ambos Estados indican una instantánea del servicio de copia de seguridad en el momento en que se ejecuta el cmdlet. No implica que el estado devuelto permanecerá como está después. En concreto, el estado "final" seguirá teniendo solo si P1 no genera ningún cambio después de que se ejecute el cmdlet. Esto es cierto en el caso de que se produzca un error P1 a través de la P2 después de poner P1 en modo de solo lectura como parte de la lógica de ejecución <STRONG>Invoke-CsPoolfailover</STRONG> .



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Para obtener información sobre la relación de copia de seguridad de un grupo de servidores determinado

Ejecute el siguiente cmdlet:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>Para forzar la sincronización del servicio de copia de seguridad

Ejecute el siguiente cmdlet:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>


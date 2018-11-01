---
title: "Restaurar contenidos de conferencia mediante el servicio de copias de seguridad"
TOCTitle: Restauración de contenidos de conferencia mediante el servicio de copias de seguridad
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49889054
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauración de contenidos de conferencia mediante el servicio de copias de seguridad en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Si la información de conferencia almacenada en el almacén de archivos de un grupo de servidores front-end deja de estar disponible, debe restaurar esta información de modo tal que los usuarios hospedados en el grupo de servidores conserven sus datos de conferencia. Si el grupo de servidores front-end que ha perdido datos de conferencia se usa junto con otro grupo de servidores front-end, puede utilizar el servicio de copia de seguridad para restaurar los datos.

También debe realizar esta tarea si se produce un error en un grupo de servidores entero y tiene que realizar la conmutación por error de sus usuarios a un servidor de copia de seguridad. Cuando estos usuarios se conmutan por error a su grupo de servidores original, también debe utilizar este procedimiento para copiar su contenido de conferencia de vuelta a su grupo de servidores original.

Supongamos que Grupo1 se usa junto con Grupo2 y que los datos de conferencia de Grupo1 se pierde. Puede utilizar el siguiente cmdlet para invocar el servicio de copia de seguridad para restaurar los contenidos:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

La restauración de los contenidos de conferencia podría demorar un poco, según su tamaño. Puede utilizar el siguiente cmdlet para ver el estado del proceso:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

El proceso finaliza cuando este cmdlet devuelve un valor de Estado parejo para el módulo de datos de conferencia.


---
title: 'Lync Server 2013: Conmutación por error de una base de datos reflejada'
TOCTitle: Conmutación por error de una base de datos reflejada
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48275611
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conmutación por error de una base de datos reflejada en Lync Server 2013

 

_**Última modificación del tema:** 2014-03-14_

Si ha configurado su base de datos back-end para que use la creación de reflejos sincronizados con un testigo, la conmutación por error es automática. Si ha configurado la creación de reflejos sincronizados sin testigo, puede usar los siguientes procedimientos para conmutar por error y conmutar por recuperación su base de datos. También puede usar estos procedimientos para conmutar por error y conmutar por recuperación manualmente sus bases de datos aunque haya configurado un testigo.

## Procedimiento para conmutar por error su base de datos back-end

1.  Antes de la conmutación por error, determine qué base de datos back-end es la principal y cuál es la reflejada escribiendo el siguiente cmdlet:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Si Almacén de administración central está hospedado en este grupo de servidores, escriba el siguiente cmdlet para determinar cuál es la principal y cuál la reflejada para Almacén de administración central:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Realice la conmutación por error de la base de datos del usuario:
    
      - Si ha fallado la principal y está realizando la conmutación por error de la reflejada, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Si ha fallado la reflejada y está realizando la conmutación por error de la principal, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Si el grupo de servidores hospeda Servidor de administración central, realice la conmutación por error de Almacén de administración central.
    
      - Si ha fallado la principal y está realizando la conmutación por error de la reflejada, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Si ha fallado la reflejada y está realizando la conmutación por error de la principal, escriba:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose


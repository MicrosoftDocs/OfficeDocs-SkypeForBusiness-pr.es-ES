---
title: Actualización o mejora de los servidores front-end en Lync Server 2013
TOCTitle: Actualización o mejora de los servidores front-end en Lync Server 2013
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48274662
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Actualización o mejora de los servidores front-end en Lync Server 2013

 

_**Última modificación del tema:** 2013-06-28_

Los servidores front-end de un grupo de servidores de Enterprise Edition se organizan en *dominios de actualización*. Estos son subconjuntos de servidores front-end del grupo de servidores. Los dominios de actualización los crea automáticamente la Generador de topologías.

Al actualizar los servidores, debe hacerlo en un dominio de actualización a la vez. Ponga inactivo cada servidor en un dominio de actualización, actualícelo y, a continuación, reinícielo antes de continuar con otro dominio de actualización. Asegúrese de llevar la cuenta de los dominios de actualización y servidores que haya actualizado hasta ahora. Use el siguiente diagrama de flujo al actualizar cada servidor.

![Actualizar el diagrama de flujo de los servidores](images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "Actualizar el diagrama de flujo de los servidores")

## Para aplicar una actualización a los servidores front-end de un grupo de servidores

1.  En un servidor front-end del grupo de servidores, ejecute el siguiente cmdlet:
    
    **Get-CsPoolUpgradeReadinessState**
    
    Si el valor de *PoolUpgradeState* es **Busy**, espere durante 10 minutos y, a continuación, pruebe **Get-CsPoolUpgradeReadinessState** de nuevo. Si ve **Busy** durante al menos tres veces consecutivas, tras esperar 10 minutos entre cada intento, o si ve cualquier resultado de **InsufficientActiveFrontEnds** para **PoolUpgradeState,** entonces hay un problema con el grupo de servidores. Si este grupo de servidores se usa junto con otro grupo de servidores front-end en una topología de recuperación ante desastres, debería realizar la conmutación por error del grupo de servidores al grupo de servidores de copia de seguridad y, a continuación, actualizar los servidores de este grupo de servidores. Para obtener detalles, vea [Conmutación por error de un grupo en Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Si el valor de *PoolUpgradeState* es **Ready**, vaya al paso 2.

2.  El cmdlet **Get-CsPoolUpgradeReadinessState** también devuelve información acerca de cada dominio de actualización del grupo de servidores y acerca de qué servidor de front-end se encuentra en cada dominio de actualización. Si el valor de **ReadyforUpgrade** es **True** para el dominio de actualización que contiene el servidor o los servidores que desea actualizar, puede actualizar de manera segura dichos servidores ahora. Para ello, haga lo siguiente:
    
    1.  Detenga las nuevas conexiones a los servidores front-end que va a actualizar mediante el cmdlet `Stop-CsWindowsService -Graceful -Verbose`.
        

        > [!NOTE]
        > Si va a llevar a cabo estas actualizaciones de servidor durante un tiempo programado de inactividad del servidor, puede ejecutar este cmdlet sin el parámetro ‘-<STRONG>Graceful</STRONG>‘, de la siguiente manera: <STRONG>Stop-CsWindowsService</STRONG>. Esto apagará de inmediato los servicios, sin esperar a que se completen todas las solicitudes de servicio existentes.

    
    2.  Actualice los servidores asociados con este dominio de actualización.
    
    3.  Reinicie los servidores y asegúrese de que están aceptando nuevas conexiones.

3.  Repita los pasos 1 y 2 para cada uno de los demás dominios de actualización en el grupo, hasta que todos los Servidores front-end se hayan actualizado.


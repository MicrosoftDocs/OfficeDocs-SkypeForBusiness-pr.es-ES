---
title: Agregar o quitar un servidor front-end en Lync Server 2013
TOCTitle: Agregar o quitar un servidor front-end en Lync Server 2013
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48276327
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar o quitar un servidor front-end en Lync Server 2013

 

_**Última modificación del tema:** 2016-01-21_

Cuando agrega un servidor front-end a un grupo o cuando quita un servidor front-end de un grupo, debe reiniciar el grupo. Para evitar interrupciones del servicio para los usuarios, use el siguiente procedimiento al agregar o quitar un servidor front-end.

## Para agregar o quitar servidores front-end

1.  Si desea quitar servidores front-end, primero detenga las nuevas conexiones a esos servidores. Para ello, puede usar el siguiente cmdlet:
    
        Stop -CsWindowsServices -Graceful

2.  Cuando los servidores que se quitará no tienen sesiones actuales, detenga los servicios de Lync Server en esos servidores.

3.  Abra el Generador de topologías, y agregue o quite los servidores necesarios.

4.  Publique la topología.

5.  Si el grupo pasó de tener dos Servidores front-end a más de dos, o pasó de tener más de dos servidores a exactamente dos, debe escribir el siguiente cmdlet:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Si el grupo tiene tres o más servidores, debe haber al menos tres de esos servidores en ejecución cuando escriba este cmdlet.

6.  Reinicie todos los Servidores front-end del grupo, de a uno por vez.


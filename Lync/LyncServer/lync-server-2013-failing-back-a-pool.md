---
title: 'Lync Server 2013: Conmutación por recuperación de grupo'
TOCTitle: Conmutación por recuperación de grupo
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48275454
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conmutación por recuperación de grupo en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Una vez que el grupo que experimentó el desastre está de nuevo en línea (es decir, el Grupo1 en este ejemplo), siga los pasos siguientes para restaurar su implementación al estado de funcionamiento normal.

Tenga en cuenta que el proceso de conmutación por error tarda en completarse. Como referencia, un grupo de 20.000  usuarios suele tardar 60 minutos.

1.  Realice la recuperación de los usuarios que estaban hospedados originalmente en el Grupo1 y se han conmutado por error al Grupo2 escribiendo el siguiente cmdlet:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

No es necesario realizar otros. Si conmutó por error a Servidor de administración central, puede dejarlo en el Grupo2.


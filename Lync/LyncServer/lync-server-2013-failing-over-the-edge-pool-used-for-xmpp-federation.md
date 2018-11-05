---
title: "Conmutación por error para grupo de servidores perimetrales para la federación XMPP"
TOCTitle: Conmutación por error para el grupo de servidores perimetrales para la federación XMPP
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49889195
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

En su organización, hay un grupo perimetral designada como el grupo para la federación XMPP. Si este grupo se desactiva, debe conmutar por error la federación XMPP para que use otro grupo perimetral antes de que la federación XMPP pueda volver a trabajar.

Al instalar primero los grupos perimetrales y habilitar la federación XMPP, puede simplificar el proceso de recuperación ante desastres estableciendo registros SRV de DNS externos para todos los grupos perimetrales para la federación XMPP, en lugar de solo uno. Cada uno de estos registros SRV debe tener establecida una prioridad diferente. Todo el tráfico de la federación XMPP atraviesa el grupo con el registro SRV con la prioridad más alta. Para más información sobre cómo habilitar y configurar la federación XMPP, vea [Configurar la federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

En el procedimiento siguiente, EdgePool1 es el grupo que originalmente alojó la federación XMPP y EdgePool2 es el grupo que alojará ahora la federación de XMPP.

## Conmutación por error para el grupo de servidores perimetrales para la federación XMPP

1.  Si no tiene implementado otro grupo perimetral (además del que está desactivado), implemente dicha grupo. Para más información, vea [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  En cada servidor perimetral del nuevo grupo perimetral que alojará ahora la federación XMPP (EdgePool2), ejecute el siguiente cmdlet:
    
        Stop-CsWindowsService

3.  Ejecute el siguiente cmdlet para cambiar la ruta de la federación XMPP a EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    En este ejemplo, Site2 es el sitio que contiene el grupo perimetral que alojará ahora la federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral del grupo.

4.  En el servidor DNS externo, cambie el registro DNS A para la federación XMPP para que apunte a EdgeServer2.contoso.com.

5.  Si todavía no tiene un registro DNS SRV para la federación XMPP que se resuelva en el grupo de servidores perimetrales que ahora hospedará la federación XMPP, agréguelo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Compruebe que el grupo de servidores perimetrales que ahora hospedará la federación XMPP tiene el puerto 5269 abierto externamente.

7.  Inicie los servicios en todos los servidores perimetrales del grupo perimetral que alojará ahora la federación XMPP:
    
        Start-CsWindowsService


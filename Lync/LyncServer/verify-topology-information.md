---
title: Comprobar la información de la topología
TOCTitle: Comprobar la información de la topología
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48276298
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar la información de la topología

 

_**Última modificación del tema:** 2012-09-26_

El primer paso para comprobar si la combinación se completó correctamente es ver la información de topología de Office Communications Server 2007 R2 que se combinó con Lync Server 2013. En el Generador de topologías, el nodo **BackCompatSite** muestra el nombre de dominio completo (FQDN) de cada servidor y grupo de servidores Office Communications Server 2007 R2 que haya combinado.

## Para ver BackCompatSite en el Generador de topologías

1.  En el entorno de Office Communications Server 2007 R2, abra la herramienta administrativa de Office Communications Server 2007 R2, y anote los FQDN de los servidores y grupos de servidores heredados.

2.  En el entorno de Lync Server 2013, abra el Generador de topologías y expanda el nodo **BackCompatSite** .

3.  Compruebe que se muestren los FQDN de los servidores y grupos de servidores que desea combinar.
    

    > [!NOTE]
    > En <STRONG>BackCompatSite</STRONG> , no verá ninguna información sobre roles del servidor instalados en un servidor front-end o en un servidor Standard Edition. Solo se mostrarán los roles del servidor necesarios para la interoperabilidad entre Office Communications Server 2007 R2 y Lync Server 2013.



![Cuadro de diálogo BackCompatSite del Generador de topologías](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Cuadro de diálogo BackCompatSite del Generador de topologías")

También puede usar el Panel de control de Lync Server 2013 para ver la topología combinada. En el Panel de control de Lync Server 2013, puede ver cada FQDN del servidor, FQDN del grupo y nombre del sitio de la topología combinada. Los servidores combinados tienen un nombre de **Sitio** de **BackCompatSite** .

## Para ver la topología combinada en el Panel de control de Lync Server 2013

1.  Abra Panel de control de Lync Server 2013.

2.  Haga clic en **Topología** .

3.  En la pestaña **Estado** , busque **BackCompatSite** en la columna **Sitio** para comprobar si aparecen los servidores y grupos de servidores que combinó.

![Panel de control de Lync Server mostrando una topología combinada](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Panel de control de Lync Server mostrando una topología combinada")

Para ver información más detallada sobre un grupo combinado, use el cmdlet **Get-CsPool** . Además de la información disponible en el Generador de topologías y en el Panel de control de Lync Server 2013, este cmdlet muestra los servicios que se ejecutan en el grupo de servidores Lync Server 2013.


> [!NOTE]
> Al publicar la topología después de ejecutar el asistente para combinaciones en el Generador de topologías, los directorios de conferencia se combinarán en Lync Server 2013. Los directorios de conferencia se pueden comprobar ejecutando el cmdlet <STRONG>Get-CsConferenceDirectory</STRONG>.



## Para ver los servicios de un grupo combinado

1.  Abra Shell de administración de Lync Server 2013.

2.  En la línea de comandos, escriba:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Por ejemplo:
    
        Get-CsPool -Identity pool02.contoso.net

## Para comprobar los directorios de conferencia combinados

1.  Abra Shell de administración de Lync Server 2013.

2.  En la línea de comandos, escriba:
    
        Get-CsConferenceDirectory

3.  Compruebe que todos los directorios de conferencia del servidor o grupo de servidores que está combinando estén ahora en Lync Server 2013.


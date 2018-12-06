---
title: 'Lync Server 2013: Control de admisión de llamadas en un enlace troncal SIP'
TOCTitle: Control de admisión de llamadas en un enlace troncal SIP
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48275813
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Control de admisión de llamadas en un enlace troncal SIP en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-22_

Para implementar el control de admisión de llamadas (CAC) en un tronco SIP, debe crear un sitio de red para representar al proveedor de servicios de telefonía de Internet (ITSP). Para aplicar valores de directivas de ancho de banda al tronco SIP, debe crear una directiva entre el sitio de red de su empresa y el sitio de red que cree para representar al ITSP.

La siguiente ilustración muestra un ejemplo de implementación de CAC en un tronco SIP.

**Configuración de CAC en un tronco SIP**

![Diagrama de enlace troncal SIP del control de admisión de llamadas](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Diagrama de enlace troncal SIP del control de admisión de llamadas")

Para configurar el CAC en un tronco SIP, deberá realizar las siguientes tareas durante la implementación de CAC:

1.  Cree un sitio de red para representar al ITSP. Asocie el sitio de red a una región de red adecuada y asigne un ancho de banda de cero para el audio y el vídeo de este sitio de red. Para ver más detalles, consulte [Configurar sitios de red para CAC en Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) en la documentación sobre implementación.
    

    > [!NOTE]
    > Para el ITSP, no funciona esta configuración de sitio de red. Los valores de la directiva de ancho de banda se aplican, en realidad, en el paso 2.



2.  Cree un vínculo entre sitios para el tronco SIP, usando los valores de los parámetros correspondientes al sitio que creó en el paso 1. Por ejemplo, use el nombre del sitio de red de su empresa como el valor del parámetro NetworkSiteID1 y el sitio de red ITSP como el valor del parámetro NetworkSiteID2. Para obtener información detallada, consulte [Crear directivas entre sitios de red en Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) en la documentación sobre implementación. Vea también la documentación de Shell de administración de Lync Server para obtener información sobre el cmdlet New-CsNetworkInterSitePolicy.

3.  Consulte a su ITSP la dirección IP del punto de terminación de medios del controlador de borde de sesión (SBC). Agregue esa dirección IP con una máscara de subred de 32 al sitio de red que representa al ITSP. Para ver más detalles, consulte [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).


---
title: "Configurar la federación para un proveedor de servicios de audioconferencia"
TOCTitle: Configurar la federación para un proveedor de servicios de audioconferencia
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn510996(v=OCS.15)
ms:contentKeyID: 59955437
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la federación para un proveedor de servicios de audioconferencia Lync Server 2013

 

_**Última modificación del tema:** 2014-07-24_

Si desea usar un proveedor de audioconferencia (ACP) para la implementación híbrida (Lync Server local con Lync Online), tiene que configurar la federación entre la implementación de Lync local y el asociado del ACP como servidor del asociado permitido. Para configurar la federación, agregue el dominio del asociado del ACP y el servidor perimetral (también se puede denominar servidor proxy de acceso) a la lista de dominios federados para la implementación local. A continuación, su asociado del ACP tendrá que agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos. Póngase en contacto con su proveedor del ACP para obtener más detalles. Su asociado del ACP tendrá que agregar el FQDN de su grupo de servidores perimetrales local a su lista de dominios federados permitidos

  - **Cómo agregar el dominio del ACP y el servidor perimetral como un dominio federado permitido**
    
    Para agregar el dominio del ACP como un servidor de asociado permitido (dominio federado permitido), siga los pasos que encontrará en [Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md). Para el servidor perimetral, agregue el FQDN del servidor perimetral del asociado del ACP. Puede que tenga que contactar con el asociado del ACP para obtener el FQDN del servidor perimetral, que el ACP también puede denominar servidor proxy de acceso.

  - **Proporcione el FQDN de su grupo de servidores perimetrales al asociado del ACP**
    
    El asociado del ACP tiene que configurar la federación para agregar su dominio local como un servidor de asociado permitido agregando el FQDN de su grupo de servidores perimetrales como un dominio federado permitido.


---
title: "Prise en ch. des certif. comportant des caractères génériques Lync Server 2013"
TOCTitle: Compatibilidad de certificado de comodín
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48274402
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad de certificado de comodín en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-21_

Lync Server 2013 usa certificados para suministrar cifrado de comunicaciones y autenticación de identidad de servidor. En algunos casos, como la publicación web mediante proxy inverso, no es necesaria la coincidencia sólida de entradas de nombre alternativo de sujeto (SAN) con el nombre de dominio completo (FQDN) del servidor que presenta el servicio. En estos casos, puede usar certificados con entradas de SAN de comodín (conocidas generalmente como “certificados de comodín”) para reducir el costo de un certificado solicitado de una entidad de certificación pública y para reducir la complejidad del proceso de planeamiento para certificados.

> [!WARNING]  
> Para retener la funcionalidad de los dispositivos de comunicaciones unificadas (UC) (por ejemplo, teléfonos de escritorio), debe probar el certificado implementado con cuidado para garantizar que los dispositivos funcionan correctamente después de implementar un certificado de comodín.



No hay compatibilidad para una entrada de comodín como nombre de sujeto (también denominado nombre común o CN) para ninguna función. Las siguientes funciones de servidor son compatibles al usar entradas de comodín en el SAN:

  **Proxy inverso.**   La entrada de comodín en el SAN es compatible con el certificado de publicación de URL simple (de reunión y marcación).  

  **Proxy inverso.**   La entrada de comodín en el SAN es compatible con las entradas de SAN para LyncDiscover en el certificado de publicación.  

  **Director.**   La entrada de comodín en el SAN es compatible con URL simples (de reunión y marcación) para LyncDiscover y LyncDiscoverInternal en componentes web de Director.  

  **Servidor front-end ( Standard Edition) y Grupo de servidores front-end ( Enterprise Edition).** La entrada de comodín en el SAN es compatible con URL simples (de reunión y marcación) y para entradas en el SAN para LyncDiscover y LyncDiscoverInternal en componentes web de front-end.  

  **Mensajería unificada de Exchange (UM).**   El servidor no usa entradas de SAN cuando se implementa como servidor independiente.  

  **Microsoft Exchange Server Servidor de acceso de cliente.**   Las entradas de comodín en el SAN son compatibles para clientes internos y externos.  

  **Mensajería unificada de Exchange (UM) y Microsoft Exchange Server Servidor de acceso de cliente en el mismo servidor.**   Las entradas de comodín en el SANson compatibles.  

Funciones de servidor que no se abordan en este tema:

  - Funciones de servidor interno (incluidos, entre otros, Servidor de mediación, Servidor de archivado y supervisión, Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia)

  - Interfaces de Servidor perimetral externas

  - Interfaces de Servidor perimetral internas
    

    > [!NOTE]
    > Para la interfaz de Servidor perimetral interna, se puede asignar al SAN una entrada de comodín, y es compatible. No se hace una consulta al SAN en el Servidor perimetral interno, y una entrada de comodín en el SAN es de valor limitado.



Para obtener información detallada sobre las configuraciones de certificados, incluido el uso de comodines en los certificados, consulte los siguientes temas:

  - [Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisitos de certificado para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Resumen de certificado - Carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumen de certificado - Director único en Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Resumen de certificado - Grupo de director escalado, equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Resumen de certificado - Proxy inverso en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Instrucciones para integrar mensajería unificada local y Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Para obtener información detallada sobre la configuración de certificados para Exchange, incluido el uso de comodines, consulte la documentación de producto de Exchange 2013.


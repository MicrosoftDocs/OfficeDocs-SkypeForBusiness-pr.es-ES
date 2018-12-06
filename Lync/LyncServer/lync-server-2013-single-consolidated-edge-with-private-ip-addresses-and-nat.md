---
title: "Lync Server 2013: Servidor perimetral consolidado simple con IP privadas y NAT"
TOCTitle: Servidor perimetral consolidado simple con direcciones IP privadas y NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48276967
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Servidor perimetral consolidado simple con direcciones IP privadas y NAT en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Si su organización necesita compatibilidad para menos de 15 000 conexiones de cliente del Servicio perimetral de acceso, 1000 conexiones cliente del Servicio de conferencia web de Lync Server y 500 sesiones simultáneas del servicio perimetral A/V, además de no ser importante la alta disponibilidad del servidor perimetral, esta topología ofrece las ventajas del hardware de menor coste y de una implementación más sencilla. Si necesita una mayor capacidad o requiere alta disponibilidad, deberá implementar la topología de servidor perimetral consolidada escalada. Para obtener información detallada, consulte uno de los siguientes:

  [Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  

  [Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  

  [Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)  

La figura no muestra Directores, un rol de servidor opcional implementado en la red interna entre los Servidores perimetrales y sus Grupos de servidores front-end o su servidor. Para más información sobre la topología para directores, vea [Componentes requeridos para el director en Lync Server 2013](lync-server-2013-components-required-for-the-director.md). La figura representa un único proxy inverso.


> [!NOTE]
> La figura se muestra a título orientativo y para mostrar un ejemplo de dirección IP, pero no tiene como objetivo representar flujos de comunicación reales con el tráfico entrante y saliente correcto. La figura representa una vista de alto nivel de posible tráfico. Los detalles del flujo de tráfico, según pertenezcan a la entrada (a puertos de escucha) o salida (a clientes o servidores de destino), se representan en el diagrama de resumen de puertos en cada escenario. Por ejemplo, TCP 443 es en realidad solo entrante (al perímetro o proxy inverso), y solo es un flujo bidireccional desde la perspectiva de un protocolo (TCP). Además, la figura muestra la naturaleza del tráfico, a medida que cambia cuando se produce la conversión NAT (conversión de direcciones de red) (la dirección de destino se cambia al entrar, la dirección de origen se cambia al salir). El firewall interno y externo, y las interfaces de servidor de ejemplo, se muestran solo como referencia. Por último, se muestran la puerta de enlace predeterminada de ejemplo y las relaciones de ruta, siempre que sea aplicable. Observe también que el diagrama usa la zona DNS <EM>.com</EM> para representar la zona DNS externa para el proxy inverso y los Servidores perimetrales, y la zona DNS <EM>.net</EM> se refiere a la zona DNS interna.



Microsoft Lync Server 2013 tiene como novedad la compatibilidad con el direccionamiento IPv6. Al igual que ocurre con el direccionamiento IPv4, las direcciones IPv6 se asignan de tal manera que las direcciones forman parte del espacio de direcciones IPv6 asignado. Las direcciones de este tema se dan solo como ejemplo. Obtenga direcciones IPv6 que funcionen en la implementación, proporcione el ámbito correcto y se producirá una interoperación con el direccionamiento interno y el externo. Windows Server proporciona una función que es importante para la tarea IPv6 transicional y la comunicación de IPv4 a IPv6 denominada de *pila dual* . La pila dual es una pila de red diferente y diferenciada para IPv4 y para IPv6. Le permite asignar direcciones para IPv4 e IPv6 simultáneamente y permite al servidor comunicarse con otros hosts y clientes basándose en cuáles son sus requisitos.

Normalmente, los tipos de direcciones que utilizará para el direccionamiento IPv6 serán las direcciones IPv6 globales (similares a las direcciones IPv4 públicas), las direcciones locales únicas de IPv6 (similares a los intervalos de direcciones de IPv4 privados) y las direcciones locales de vínculo de IPv6 (similares a las direcciones IP privadas automáticas de Windows Server para IPv4)

Existen tecnologías de conversión de direcciones de red (NAT) para IPv6 que permitirán un NAT de IPv6 a IPv4 (normalmente denominado NAT64) y un NAT de IPv6 a IPv6 (normalmente denominado NAT66). La existencia de tecnologías NAT significa que los cinco escenarios presentados para Lync ServerServidores perimetrales siguen siendo válidos.

> [!WARNING]  
> IPv6 es un tema complejo y necesita una planeación cuidadosa con el equipo de redes y el proveedor de Internet para garantizar que las direcciones que asigna en el nivel de servidor de Windows y en el nivel de Lync Server 2013 funcionen tal como se esperaba. Vea los vínculos al final de este tema para consultar los recursos adicionales sobre la planeación de IPv6 y su direccionamiento.



**Topología perimetral consolidada de un solo equipo**

![Topología perimetral consolidada única](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "Topología perimetral consolidada única")

> [!IMPORTANT]  
> Si usa el Control de admisión de llamadas (CAC), sigue teniendo que asignar direcciones de IPv4 a la interfaz interna de Servidor perimetral. CAC usa las direcciones IPv4 y debe tenerlas disponibles para funcionar.



## En esta sección

  - [Resumen de certificado - Servidor perimetral consolidado simple con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Resumen de puerto - Perímetro consolidado de un solo equipo con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Resumen DNS - Servidor perimetral consolidado simple con dirección IP privada mediante NAT en Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

## Vea también

#### Otros recursos

[Arquitectura de direccionamiento de IP Versión 6](http://tools.ietf.org/html/rfc4291)  
[Formato de dirección de unidifusión global de IPv6](http://tools.ietf.org/html/rfc3587)  
[Direcciones de unidifusión IPv6 locales únicas](http://tools.ietf.org/html/rfc4193)


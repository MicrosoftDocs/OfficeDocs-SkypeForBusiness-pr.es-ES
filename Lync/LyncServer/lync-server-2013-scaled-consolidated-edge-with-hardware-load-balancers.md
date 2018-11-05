---
title: "Lync Server 2013: Servidor perimetral consol. ampliado con equilib. carga de hardware"
TOCTitle: Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48275538
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En la topología del Grupo de servidores perimetrales, se implementan dos o más Servidores perimetrales como grupo de carga equilibrada en la red perimetral del centro de datos. El equilibrio de carga del hardware se usa para el tráfico a las interfaces de Servidor perimetral interna y externa.

Si su organización necesita admitir más de 15 000 conexiones de cliente al Servidor perimetral de acceso, 1000 conexiones de cliente activas al Servicio perimetral de conferencia web o 500 sesiones de Servicio perimetral A/V simultáneas y, además, la alta disponibilidad del Servidor perimetral es un aspecto importante, esta topología ofrece las ventajas de escalabilidad y compatibilidad con la conmutación por error.

La figura no muestra Directores, un rol de servidor opcional implementado en la red interna entre los Servidores perimetrales y su Grupos de servidores front-end o servidor. Para obtener más información sobre la topología de los Directores, consulte [Componentes requeridos para el director en Lync Server 2013](lync-server-2013-components-required-for-the-director.md).


> [!NOTE]
> La figura que mostramos aquí es de carácter orientativo y sirve de ejemplo de direccionamiento&nbsp;IP. No ilustra flujos de comunicación reales de tráfico entrante y saliente. Constituye más bien una vista de alto nivel del posible tráfico. En el diagrama de resumen de puertos de cada escenario encontrará información detallada del flujo del tráfico de entrada (hacia los puertos de escucha) y de salida (hacia los clientes o servidores de destino). Por ejemplo, TCP&nbsp;443 es realmente solo de entrada (hacia el Servidor perimetral o proxy inverso) y es únicamente un flujo bidireccional desde el punto de vista del protocolo (TCP). La figura refleja también la naturaleza del tráfico a medida que cambia cuando se realiza la traducción de direcciones de red (NAT) (la dirección de destino cambia en la entrada y la dirección de origen, en la salida). Los ejemplos de firewall interno y externo y de las interfaces de servidor son solo para tenerlos como referencia. Por último, se muestran ejemplos de relaciones de rutas y puertas de enlace predeterminadas cuando corresponde. Observe también que en el diagrama se usa la zona DNS <EM>.com</EM> para representar la zona DNS externa tanto del proxy inverso como de los Servidores perimetrales, mientras que la zona DNS <EM>.net</EM> hace referencia a la zona DNS interna.



Microsoft Lync Server 2013 tiene como novedad la compatibilidad con el direccionamiento IPv6. Al igual que ocurre con el direccionamiento IPv4, las direcciones IPv6 se asignan de tal manera que las direcciones forman parte del espacio de direcciones IPv6 asignado. Las direcciones de este tema se dan solo como ejemplo. Obtenga direcciones IPv6 que funcionen en la implementación, proporcione el ámbito correcto y se producirá una interoperación con el direccionamiento interno y el externo. Windows Server proporciona una función que es importante para la tarea IPv6 transicional y la comunicación de IPv4 a IPv6 denominada de *pila dual* . La pila dual es una pila de red diferente y diferenciada para IPv4 y para IPv6. Le permite asignar direcciones para IPv4 e IPv6 simultáneamente y permite al servidor comunicarse con otros hosts y clientes basándose en cuáles son sus requisitos.

Normalmente, los tipos de direcciones que utilizará para el direccionamiento IPv6 serán las direcciones IPv6 globales (similares a las direcciones IPv4 públicas), las direcciones locales únicas de IPv6 (similares a los intervalos de direcciones de IPv4 privados) y las direcciones locales de vínculo de IPv6 (similares a las direcciones IP privadas automáticas de Windows Server para IPv4)

Existen tecnologías de conversión de direcciones de red (NAT) para IPv6 que permitirán un NAT de IPv6 a IPv4 (normalmente denominado NAT64) y un NAT de IPv6 a IPv6 (normalmente denominado NAT66). La existencia de tecnologías NAT significa que los cinco escenarios presentados para Lync ServerServidores perimetrales siguen siendo válidos.

> [!WARNING]  
> IPv6 es un tema complejo y necesita una planeación cuidadosa con el equipo de redes y el proveedor de Internet para garantizar que las direcciones que asigna en el nivel de servidor de Windows y en el nivel de Lync Server 2013 funcionen tal como se esperaba. Vea los vínculos al final de este tema para consultar los recursos adicionales sobre la planeación de IPv6 y su direccionamiento.



**Configuración del equilibrador de carga de hardware**

Para obtener información detallada, vea la sección “Requisitos del equilibrador de carga de hardware para un servidor perimetral A/V” en [Componentes necesarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).

**Topología perimetral consolidada escalada (carga de hardware equilibrada)**

![Topología perimetral consolidada escalada](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "Topología perimetral consolidada escalada")

> [!IMPORTANT]  
> Si usa el Control de admisión de llamadas (CAC), sigue teniendo que asignar direcciones de IPv4 a la interfaz interna de Servidor perimetral. CAC usa las direcciones IPv4 y debe tenerlas disponibles para funcionar.



## En esta sección

  - [Resumen de certificado - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Resumen DNS - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

## Vea también

#### Otros recursos

[Arquitectura de direccionamiento de IP Versión 6](http://tools.ietf.org/html/rfc4291)  
[Formato de dirección de unidifusión global de IPv6](http://tools.ietf.org/html/rfc3587)  
[Direcciones de unidifusión IPv6 locales únicas](http://tools.ietf.org/html/rfc4193)


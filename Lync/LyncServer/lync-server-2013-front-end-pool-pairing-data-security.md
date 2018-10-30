---
title: 'Lync Server 2013: Seguridad de datos en emparejamiento grupos de servidores front-end'
TOCTitle: Seguridad de datos en el emparejamiento de grupos de servidores front-end
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49889802
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Seguridad de datos en el emparejamiento de grupos de servidores front-end en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

El Servicio de copia de seguridad es un mecanismo de replicación de datos introducido en Lync Server 2013 que transfiere datos de usuario y contenido de conferencias entre dos Grupos de servidores front-end emparejados a través de dos centros de datos para posibilitar la recuperación en caso de desastre. Los datos de usuario contienen los URI de SIP, además de listas de contactos y configuraciones. El contenido de conferencias incluye las cargas de Microsoft PowerPoint 2010, así como las pizarras usadas en las conferencias. En el grupo de servidores de origen, los datos de usuario y el contenido de las conferencias se exportan desde el almacenamiento local, se comprimen y se transfieren al grupo de servidores de destino, donde se descomprimirán e importarán al almacenamiento local. El Servicio de copia de seguridad supone que el vínculo de comunicaciones entre los dos centros de datos está dentro de la red corporativa protegida de Internet. No cifra los datos transferidos entre los centros de datos, ni se encapsulan de forma nativa dentro de un protocolo seguro, como HTTPS. Por tanto, cabe la posibilidad de que personal interno desde la red corporativa lance un ataque de tipo "man-in-the-middle" (MitM, o intermediario).

## Evaluación de los riesgos de seguridad

Las empresas que implementen Lync Server 2013 en varios centros de datos y utilicen la característica de recuperación ante desastres deben asegurarse de que el tráfico entre centros de datos está protegido mediante la intranet corporativa. Las empresas preocupadas por la protección de ataques internos deben proteger los vínculos de comunicación entre los centros de datos.

Por regla general, se supone que los centros de datos de una empresa están protegidos detrás de la intranet corporativa. Existen otros muchos tipos de datos confidenciales de la empresa que se transfieren entre estos centros de datos. La infraestructura de TI de la empresa corre un grave riesgo si no protege estos vínculos de comunicación entre centros de datos.

Si bien el riesgo de ataques de tipo "man in the middle" dentro de la red corporativa es real, es relativamente limitado en comparación con la exposición del tráfico a Internet. Concretamente, los datos de usuario que expone el Servicio de copia de seguridad (como los URI de SIP) suelen estar disponibles para todos los empleados de la compañía a través de otros medios, como la libreta de direcciones global de Exchange u otros programas informáticos de directorios. Por ello, el principal objetivo deber ser proteger la WAN entre los dos centros de datos cuando se usa el Servicio de copia de seguridad para copiar datos entre los dos grupos de servidores emparejados.

## Reducción de los riesgos de seguridad

Existen muchas formas de mejorar la protección de la seguridad para el tráfico del Servicio de copia de seguridad, desde la restricción del acceso a los centros de datos, hasta la protección del transporte WAN entre los dos centros de datos. En la mayoría de los casos, las empresas que implementan Lync Server 2013 ya cuentan con la infraestructura de seguridad que necesitan. Para las empresas que necesitan orientación, la solución que ofrece Microsoft es un ejemplo de cómo crear una infraestructura de TI segura. Sin embargo, no es la única solución, ni siquiera la solución preferida para Lync Server. Nosotros recomendamos a los clientes corporativos que elijan una solución específica para sus necesidades, basada en su infraestructura de TI y sus requisitos. La solución de ejemplo de Microsoft emplea IPSec y directivas de grupo para el aislamiento del servidor y del dominio. Si desea información adicional, vea [http://go.microsoft.com/fwlink/?linkid=268544\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268544%26clcid=0xc0a). Si tiene alguna pregunta o comentario, póngase en contacto con secwish@microsoft.com.

Otra posible solución consiste en usar IPsec solamente para ayudar a proteger los datos enviados por el propio servicio de copia de seguridad. Si elige este método, deberá configurar las reglas IPsec del protocolo SMB para los siguientes servidores, donde los grupos A y B son dos Grupos de servidores front-end emparejados.

  - El servicio SMB (TCP/445) de cada Servidor front-end del grupo A al almacén de archivos que usa el grupo B.

  - El servicio SMB (TCP/445) de cada Servidor front-end del grupo B al almacén de archivos que usa el grupo A.

> [!WARNING]  
> IPsec no está pensado para reemplazar la seguridad en el nivel de la aplicación, como SSL/TLS. Una ventaja de utilizar IPsec es que puede ofrecer seguridad de tráfico de red para las aplicaciones existentes sin necesidad de cambiarlas. Las empresas que, simplemente, quieren proteger el transporte entre los dos centros de datos deben consultar a sus respectivos proveedores de hardware de redes sobre las formas de configurar conexiones WAN seguras con los equipos del proveedor.



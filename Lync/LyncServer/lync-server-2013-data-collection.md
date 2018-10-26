---
title: 'Lync Server 2013: Recopilación de datos'
TOCTitle: Recopilación de datos
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48276954
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Recopilación de datos en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

En Microsoft Lync Server 2013  software de comunicaciones, puede ejecutar la Microsoft Lync Server 2013, herramienta de planeación sin documentar sus direcciones IP existentes y propuestas, y los nombres de dominio completo (FQDN) del servidor perimetral, aunque es muy difícil hacerlo sin tener errores de configuración. Por ejemplo si, durante un período de tiempo, debe haber coexistencia, un error habitual es volver a usar los FQDN de una implementación perimetral ya existente para la implementación perimetral de Lync Server 2013. Si tiene las direcciones IP existentes y las direcciones IP propuestas, así como los FQDN en una misma hoja de cálculo, tabla u otra forma visual, le será más fácil evitar problemas de configuración durante la instalación.

> [!WARNING]  
> Si ha usado versiones anteriores de la Herramienta de planeación, probablemente la haya usado para crear la topología y el documento de topología exportada para utilizarlos en la Generador de topologías para publicar la topología. La capacidad para exportar la topología se eliminó de Herramienta de planeación. No aconsejamos usar una versión anterior de la Herramienta de planeación para crear un documento de topología para Lync Server 2013. Los resultados son impredecibles.



Por consiguiente, recomendamos usar la plantilla de de recolección de datos siguiente, que corresponde a su topología perimetral, para recopilar los distintos FQDN y direcciones IP que deberá introducir en la Herramienta de planeación. Al documentar la configuración actual y propuesta, puede situar los valores en el contexto adecuado para su entorno de producción. Además, se verá obligado a pensar en cómo configurará la coexistencia y las nuevas características, como direcciones URL sencillas, recursos compartidos de archivos, y equilibrio de carga.

La exitosa implementación de Microsoft Lync Server 2013 depende de conocer la interacción de los componentes individuales y la fiabilidad de estos. Al recopilar datos de su red e infraestructura de servidor existentes, y al aplicar la guía de planeación en estas secciones, puede integrar los componentes de Lync Server 2013  Servidor perimetral en su infraestructura.

Presentado en [Elección de una topología en Lync Server 2013](lync-server-2013-choosing-a-topology.md), hay tres arquitecturas principales sin variaciones, para un total de cinco posibles escenarios de implementación. Uno de estos será el punto de partida para su colección de datos. Las direcciones IP, nombres de servidores y nombres de dominio son ejemplos que coinciden con el certificado, firewall y diagramas DNS coincidentes que detallan la información necesaria para una completa solución de planeación. El valor de los diagramas y rellenar los valores del certificado, de DNS y de firewall requeridos es especialmente importante en las comunicaciones entre equipos, en las que la administración de la autoridad de certificación, de la configuración de firewall y de DNS es administrada por equipos distintos del que planea la implementación. Los diagramas proporcionan información sobre los componentes requeridos que pueden usarse para comunicar estos requisitos para la colaboración entre equipos.

Los diagramas proporcionados son genéricos intencionadamente, pero permiten recopilar todos los datos pertinentes que son necesarios para la comunicación de requisitos en un escenario de varios equipos, donde varios grupos se encargan de la red, los firewalls, la creación y administración de certificados, la implementación de servidores y la administración de servidores. Tener a mano la información necesaria para configurar la red, los firewalls, los puertos y protocolos, los certificados y los servidores es de gran importancia cuando la implementación de Lync Server está en curso.

**Servidor perimetral y Grupo de servidores perimetrales**

![Servidor perimetral y grupo de servidores perimetrales](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "Servidor perimetral y grupo de servidores perimetrales")

**Proxy inverso**

![Proxy inverso](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "Proxy inverso")

**Director o Grupo de directores**

![Director y grupo de directores](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "Director y grupo de directores")


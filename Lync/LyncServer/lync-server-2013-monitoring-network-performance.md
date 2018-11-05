---
title: 'Lync Server 2013: supervisar el rendimiento de red'
TOCTitle: Supervisar el rendimiento de red
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn720923(v=OCS.15)
ms:contentKeyID: 62246714
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supervisar el rendimiento de red en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 es una tecnología de comunicaciones en tiempo real que depende en gran medida de la red para habilitar la comunicación entre usuarios, ya sea mediante mensajería instantánea (IM), llamadas de voz o comunicación por vídeo. Por ello es importante supervisar continuamente el rendimiento de la red para garantizar que la modalidad de comunicación elegida ofrezca la mejor experiencia posible.

El rendimiento de la red puede medirse en dos niveles:

  - **Rendimiento general de la red**   Este nivel de medición permite a la organización crear una "imagen general" de su red y suele implementarse mediante sistemas de supervisión de red de terceros. Estos sistemas reciben datos de rendimiento y capacidad de dispositivos de red remotos, como routers, y se activan y desactivan a lo largo de la red para que los administradores puedan determinar el estado de cualquier componente en cualquier momento del día.

  - **Rendimiento de un servidor Individual**   Este nivel de medición se limita a un servidor concreto y ayuda a los administradores a valorar el rendimiento de red del mismo con el fin de resolver problemas específicos o determinar el rendimiento a lo largo de un periodo determinado, como parte del proceso de planificación de la capacidad.

Puede supervisar la red mediante las herramientas descritas en las siguientes secciones.

## Herramientas para la supervisión del rendimiento general de la red

## System Center Operations Manager 2012

System Center Operations Manager proporciona una administración de servicios de un extremo a otro fácil de personalizar y ampliar, para lograr así mejores niveles de servicio en todo el entorno de TI. Esto permite a los equipos de operaciones y administración de TI identificar y resolver incidencias que afectan al estado de los servicios de TI distribuidos. La administración de servicios de un extremo a otro no se limita a los entornos basados en Microsoft. La compatibilidad con Servicios Web para administración (WS-Management), el Protocolo simple de administración de redes (SNMP) y las soluciones de partners permite incluir en la supervisión de servicios de System Center Operations Manager 2012 sistemas que no ejecutan sistemas operativos o hardware de Microsoft.

## System Center Operations Manager 2012 y soluciones de administración de red de terceros

**EMC Smarts**   EMC Solutions for Operations Manager le ayuda a resolver rápidamente problemas de nivel de servicio. Podrá administrar y supervisar toda la cadena de servicios de TI desde una única solución integrada y automatizada. Podrá identificar fácilmente las causas de un problema de rendimiento y disponibilidad y resolverlo más rápidamente, lo que reducirá los efectos y los costes. Entre las principales ventajas están las siguientes:

  - Administración avanzada y fácil de usar   Céntrese en ofrecer valor empresarial estratégico y no en ordenar y filtrar manualmente alertas confusas.

  - **Resolución más rápida**   Resuelva las incidencias de TI y responda a las necesidades empresariales más rápido, lo que reduce los efectos y los costes.

  - **Operaciones simplificadas**   Evite la complejidad en TI combinando varias herramientas, aplicaciones y terminales de administración.

Puede encontrar más información aquí:

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Soluciones para Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

## Soluciones de terceros

**HP Network Management Center (antes conocido como HP OpenView)**   [HP Network Management Center](https://h10078.www1.hp.com/cda/hpms/display/main/hpms_content.jsp?zn=bto%26cp=1-11-15-119_4000_100__) proporciona administración integrada de errores y rendimiento para mejorar la disponibilidad y el rendimiento de red. Network Management Center es parte de la solución automatizada de administración de red de HP, que unifica la gestión de errores, rendimiento, configuración y cambios.

**Productos de automatización y administración de red de Cisco**   Cisco dispone de varios productos de administración para la empresa, como CiscoWorks LAN Management Solution y Cisco Network Analysis Module, que ayudan a mejorar la eficiencia operativa y reducen el tiempo de inactividad de la red. Para obtener más información sobre estos productos, visite el sitio web de Cisco en [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).

Protocolo simple de administración de redes (SNMP)   El Protocolo simple de administración de redes (SNMP) es un estándar que define una estrategia de administración de redes TCP/IP. SNMP le permite capturar información de configuración y estado de la red y enviar dicha información a un equipo designado para la supervisión de eventos. Este protocolo emplea una arquitectura distribuida que incluye lo siguiente:

  - Varios nodos administrados, cada uno con una entidad SNMP denominada agente que proporciona acceso remoto al instrumental de administración.

  - Al menos una entidad SNMP conocida como administrador que ejecuta aplicaciones para supervisar y controlar los elementos administrados. Estos elementos son dispositivos como servidores, routers, etcétera, que son supervisados y controlados accediendo a su información de administración.

  - Se utiliza el protocolo SNMP para comunicar información de administración entre los puestos de administración y los agentes. Esta información se refiere a una recopilación de objetos administrados que residen en un almacén de información virtual denominado Base de datos de información de administración (MIB).


> [!NOTE]
> Más arriba se han ofrecido algunos ejemplos de soluciones de supervisión de red de terceros. No se trata de una lista completa y Microsoft no tiene preferencia por ninguna solución específica. Consulte con un proveedor de servicios de red y con su proveedor de tecnología para determinar cuál es la mejor solución de supervisión de red para su organización.



## Herramientas para la supervisión del rendimiento de red de un servidor concreto

## System Center Operations Manager 2012

System Center Operations Manager 2012 permite a los administradores ver el rendimiento de red de cada servidor mediante el pack de administración de Windows Server 2012. El pack de administración del sistema operativo de Windows Server incluye un pack de administración de rendimiento que permite supervisar el rendimiento y el estado del adaptador de red.

## Monitor de red de Windows

Recopila, muestra y analiza el uso de recursos en un servidor y mide el tráfico de red. Monitor de red supervisa exclusivamente la actividad de red. El análisis de estos datos y de los registros de rendimiento permite determinar el uso de la red, identificar problemas y predecir necesidades futuras.

Para obtener más información sobre Monitor de red 3.4, aprender a instalar y configurar la aplicación y capturar y analizar datos, consulte esta sesión: Información general sobre Monitor de red 3.3. Vea también el blog de Monitor de red en: <http://blogs.technet.com/b/netmon/>.


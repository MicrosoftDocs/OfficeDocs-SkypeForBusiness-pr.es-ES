---
title: 'Lync Server 2013: Instalar software opcional'
TOCTitle: Instalar software opcional
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615032(v=OCS.15)
ms:contentKeyID: 52061721
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar software opcional en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

La Microsoft Lync Server 2013, herramienta de planeación está diseñada para exportar a Microsoft Excel y Microsoft Visio. Si bien estas aplicaciones no son obligatorias para el funcionamiento de la Herramienta de planeación, aportan un valor significativo a la implementación y la documentación del diseño.

## Software opcional

## Microsoft Excel

La exportación de su diseño a Microsoft Excel genera un informe con cuatro pestañas en la hoja de cálculo:

  - Resumen: Muestra información sobre la configuración local, incluidos el recuento de usuario, la configuración de capacidad, los roles virtualizados e información del perfil del servidor.

  - Perfil de hardware: Muestra un informe sobre las configuraciones de hardware recomendadas para los servidores que se especifican en la topología, incluidos la CPU, la memoria, el disco y la interfaz de red. También contempla la cantidad y las especificaciones recomendadas para los componentes de servidor. De igual modo, cada servidor está definido por el sitio para proporcionar una representación completa de los requisitos del servidor por sitio.

  - Requisitos de los puertos: Muestra un informe de todos los puertos que están habilitados y la asociación con el equilibrio de carga del Sistema de nombres de dominio (DNS LB) y los equilibradores de carga de hardware (HLB). Este informe es útil para planear las configuraciones de DNS LB y HLB y del firewall.

  - Informe de resumen: Muestra un resumen general de la configuración necesaria para configurar la red del Servidor perimetral.

  - Informe de certificados: Muestra el nombre del firmante y los nombres alternativos del firmante que se precisan para los certificados necesarios para que el Servidores perimetrales se ejecute.

  - Informe de firewall: Muestra los puertos de origen y de destino y direcciones IP de las interfaces tanto interna como externa.

  - Informe DNS: Muestra el nombre de dominio completo (FQDN) y direcciones IP/VIP que se necesitan para cada entrada DNS que se cree.

## Microsoft Visio

La exportación del diseño a Microsoft Visio genera un diagrama para su uso en fines de documentación de la topología y la infraestructura configuradas. El diagrama importado se puede modificar y reorganizar para adaptarlo a sus necesidades de documentación. El típico diagrama de Visio incluirá:


> [!NOTE]
> Si el diseño es lo suficientemente grande como para necesitar más de tres servidores front-end, se creará una página adicional para el Grupo de servidores front-end, los Servidores front-end, el equipo que ejecuta SQL Server, las direcciones&nbsp;IP y los FQDN.



  - Topología global: Diagrama de sitios de Lync Server 2013 configurados.

  - Ficha Nombre de sitio: Muestra la topología de configuración de sitio con el Servidor perimetral, firewall, red telefónica conmutada (RTC) con puertas de enlace y la implementación de servidor interna. La implementación interna está formada por servidores y grupos de servidores configurados, incluidos los grupos de servidores front-end, los servidores basados en SQL Server, Servicios de dominio de Active Directory, los directores, los servidores de Mensajería unificada de Exchange (UM), los servidores de buzones de Exchange, Office Web Apps Server, los Servidores de mediación y los Servidores de chat persistente.

  - Diagrama de red perimetral: Diagrama en el que se detalla la configuración del Servidor perimetral con direcciones IP y FQDN asociados. El equilibrio de carga de DNS y los equilibradores de carga de hardware también están incluidos. Además, se muestran los directores y el Servidor front-end o el Grupo de servidores front-end, con las configuraciones de DNS LB o HLB asociadas y la dirección IP (la Herramienta de planeación admite direcciones tanto IPv4 como IPv6) y el FQDN asignados.

## Vea también

#### Tareas

[Instalar la herramienta de planeación en Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)


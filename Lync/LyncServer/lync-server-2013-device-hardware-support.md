---
title: 'Lync Server 2013: Compatibilidad con hardware de dispositivos'
TOCTitle: Compatibilidad con hardware de dispositivos
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48276488
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad con hardware de dispositivos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Es necesario realizar configuraciones de hardware específicas antes de implementar teléfonos IP y dispositivos analógicos.

Los teléfonos IP que ejecutan Lync Phone Edition admiten el protocolo LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discovery) y Power over Ethernet (PoE).  Para usar el protocolo LLDP-MED, el conmutador debe admitir IEEE802.1AB y ANSI/TIA-1057. Para usar PoE, el conmutador debe admitir PoE802.3AF o 802.3at.

Para habilitar LLDP-MED, el administrador debe habilitar LLDP mediante la ventana de la consola del conmutador y establecer la directiva de red LLDP-MED con el identificador de VLAN de voz correcto.

Además, si su implementación incluye dispositivos analógicos, debe configurar la puerta de enlace analógica para que use Lync Server y la puerta de enlace debe ser una de las siguientes:

  - Un adaptador de teléfono analógico (ATA)

  - Una puerta de enlace analógica RTC

  - Una aplicación de sucursal con funciones de supervivencia que incluya una puerta de enlace analógica de RTC

  - Una aplicación de sucursal con funciones de supervivencia que incluya una puerta de enlace RTC que se comunique con un ATA

Para obtener información sobre cómo configurar una puerta de enlace analógica, vea "Planeación para implementar dispositivos analógicos" en [http://go.microsoft.com/fwlink/?linkid=268537\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268537%26clcid=0xc0a) en la biblioteca de TechNet de Lync Server 2010. (Los dispositivos analógicos funcionan igual en Lync Server 2013 que en Lync Server 2010).

> [!IMPORTANT]  
> Puede configurar el conmutador para 9-1-1 mejorado (E9-1-1), si el conmutador lo admite.



---
title: 'Lync Server 2013: Componentes de conectividad con RTC'
TOCTitle: Componentes de conectividad con RTC
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48275599
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes de conectividad con RTC en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Una solución de telefonía VoIP profesional debe proporcionar llamadas entrantes y realizadas a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada. Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas. Desde la perspectiva del usuario, una llamada entre la infraestructura de Telefonía IP empresarial y la RTC debe parecer exactamente igual que otra sesión de SIP.

En las conexiones de RTC, puede implementar enlaces troncales SIP o una puerta de enlace RTC (con una PBX, también denominada vínculo SIP directo, o sin ella).

## Enlace troncal SIP

Como alternativa al uso de puertas de enlace RTC, puede conectar la solución de Telefonía IP empresarial a la RTC usando el enlace troncal SIP. El enlace troncal SIP habilita los siguientes escenarios:

  - Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.

  - Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.

El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP.

## Puertas de enlace RTC

Las puertas de enlace RTC son dispositivos de otro fabricante que convierten la señalización y los medios entre la infraestructura de Telefonía IP empresarial y una red telefónica conmutada (RTC) o una central de conmutación (PBX). Las puertas de enlace RTC trabajan con el servidor de mediación para presentar una llamada de RTC o de PBX a un cliente de Telefonía IP empresarial. El servidor de mediación también presenta llamadas de los clientes de Telefonía IP empresarial a la puerta de enlace RTC para redirigir las llamadas a la RTC o a la PBX. Para obtener una lista de los socios que trabajan con Microsoft para proporcionar dispositivos que funcionen con Lync Server, consulte el sitio web referente a los socios de comunicaciones unificadas de Microsoft en [http://go.microsoft.com/fwlink/?linkid=202836\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=202836%26clcid=0xc0a).

## Centrales de conmutación

Si ya dispone de una infraestructura de voz que usa una central de conmutación (PBX), puede usar su PBX con Telefonía IP empresarial de Lync Server.

Los escenarios de integración de Telefonía IP empresarial y PBX admitidos son los siguientes:

  - IP-PBX que admite desvío de medios, con un servidor de mediación.

  - IP-PBX que requiere una puerta de enlace de RTC independiente.

  - PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace de RTC independiente.


> [!NOTE]
> El desvío de medios no interactuará con todas las puertas de enlace RTC, sistemas IP-PBX y SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. El desvío de medios solo se permite con los productos y las versiones recogidos en Ingeniería completa para Microsoft Lync, en <A href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0xC0A</A>.



Para obtener más información acerca de los socios que ofrecen soluciones de Telefonía IP empresarial, consulte el sitio web referente a los socios de comunicaciones unificadas de Microsoft en [http://go.microsoft.com/fwlink/?linkid=202836\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=202836%26clcid=0xc0a).

Para obtener más información acerca de los socios que ofrecen soluciones de hardware de Telefonía IP empresarial, incluidas las puertas de enlace de RTC, consulte el sitio web referente a los socios de comunicaciones unificadas de Microsoft en [http://go.microsoft.com/fwlink/?linkid=202836\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=202836%26clcid=0xc0a).


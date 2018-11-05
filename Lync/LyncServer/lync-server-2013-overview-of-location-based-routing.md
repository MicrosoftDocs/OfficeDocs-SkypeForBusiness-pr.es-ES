---
title: 'Lync Server 2013: Información general sobre el enrutamiento basado en ubicación'
TOCTitle: Información general sobre el enrutamiento basado en ubicación
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994032(v=OCS.15)
ms:contentKeyID: 52061633
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre el enrutamiento basado en ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

El enrutamiento basado en localización introduce un nuevo conjunto de reglas que modifica el enrutamiento de llamadas RTC nacionales e internacionales para evitar que se omitan los números de pago de RTC. El enrutamiento basado en localización proporciona la flexibilidad para delimitar estas reglas a regiones específicas, puertas de enlace específicas o a un conjunto específico formado solo por usuarios.

Los escenarios siguientes ilustran los principales tipos de restricciones que puede exigir el enrutamiento basado en localización:

  - Llamadas de salida: el enrutamiento basado en localización puede exigir que las llamadas salientes se realicen desde una puerta de enlace RTC que se encuentre en la misma región en la que está la persona que llama para omitir los números de pago de RTC, lo que evita que las llamadas salgan de una puerta de enlace RTC ubicada en una región diferente de la persona que llama.

  - Llamadas de entrada: el enrutamiento basado en localización puede evitar llamadas RTC a extremos del anillo de Lync si la puerta de enlace RTC que enruta la llamada entrante no se encuentra en la misma región que el usuario al que llama Lync.

  - Regiones desconocidas: el enrutamiento basado en localización restringe las llamadas RTC entrantes y salientes desde y hacia los usuarios que se encuentran en ubicaciones indeterminadas (por ejemplo, usuarios remotos que se conectan mediante Internet o situados en regiones desconocidas).

  - Regiones internacionales: el enrutamiento basado en localización exige el enrutamiento de las llamadas salientes a través de las puertas de enlace RTC internacionales si no se puede encontrar una puerta de enlace local en la ubicación del usuario.

## Vea también

#### Otros recursos

[Planificar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)


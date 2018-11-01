---
title: 'Lync Server 2013: Decidir cómo implementar Microsoft Lync'
TOCTitle: Decidir cómo implementar Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48275621
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Decidir cómo implementar Lync Server 2013

 

_**Última modificación del tema:** 2012-10-03_

A la hora de planear Lync, lo primero que hay que decidir es cómo implementar Microsoft Lync: como Lync Server 2013 local o como Skype Empresarial Online con Microsoft Office 365 en la nube.

  - **Lync Server 2013 local :** esta opción proporciona el conjunto completo de características de Lync, además de una gran flexibilidad para configurar, personalizar y poner en funcionamiento la implementación. La organización se encarga de instalar todos los servidores en el sitio y de su mantenimiento. Con una implementación local dispondrá de todas las características de Lync Server.

  - **Skype Empresarial Online en la nube :** Skype Empresarial Online está dirigido a organizaciones que desean disfrutar de las ventajas que el producto ofrece en cuanto a costos y agilidad en las reuniones, la presencia y la mensajería instantánea basados en la nube, sin tener que sacrificar las capacidades de categoría empresarial de Lync Server. Con Skype Empresarial Online, Microsoft implementa y mantiene la infraestructura de servidor necesaria, además de administrar sus actualizaciones, revisiones y mantenimiento continuo. Algunas de las características disponibles en la implementación local no lo están en Skype Empresarial Online.

El tipo de implementación que más le convenga dependerá de las cargas de trabajo que desee implementar y de la situación financiera y geográfica de su organización.

## Lync Server

Se recomienda implementar Lync Server si se necesitan las características siguientes:

  - **Capacidades completas de Telefonía IP empresarial**   Si desea implementar una solución completa de Telefonía IP empresarial para reemplazar su PBX o para utilizar características avanzadas de llamada, necesitará una implementación de Lync Server local. La implementación local admite la conectividad directa con troncos y sistemas PBX, además de características telefónicas avanzadas como los grupos de respuesta y el Estacionamiento de llamadas. Actualmente, Lync Online no admite estas funcionalidades.

  - **Controles de calidad de medios**   Si quiere disponer de todo el conjunto de características para el control de calidad de los medios, como el servicio de control de admisión de llamadas (CAC) o la Calidad de servicio (QoS), le interesará realizar una implementación local.

  - **Chat persistente**   Si necesita implementar la característica de chat persistente en su organización, elija la opción de implementación local.

  - **Aplicaciones de servicio de terceros**   Solo las implementaciones locales pueden trabajar con aplicaciones de terceros de confianza que usen la API administrada de comunicaciones unificadas (UCMA).

  - **Compañías multinacionales o multirregionales que necesiten compatibilidad regional**   Si tiene centros de datos en varios países o regiones y necesita implementar y administrar servidores a nivel regional, se recomienda la implementación local, ya que proporciona este tipo de características de administración regional.

  - **Control total sobre directivas, actualizaciones e informes**   Con una implementación local de Lync Server, dispondrá de acceso a todo el conjunto de directivas de cliente y de servidor, a los intervalos de actualización y a la supervisión y otros informes. Lync Online proporciona un subconjunto de informes y ajustes de directiva, además de posibilidades limitadas, aunque significativas, para la aceptación de actualizaciones.

## Lync Online

Si ninguno de los aspectos enumerados en la lista anterior le resulta fundamental, puede que desee escoger Lync Online para una administración e implementación más sencillas. Lync Online ofrece un conjunto de características robustas de conferencia, presencia y mensajería instantánea, y admite las videollamadas y las llamadas de voz a través de IP entre usuarios de la organización.


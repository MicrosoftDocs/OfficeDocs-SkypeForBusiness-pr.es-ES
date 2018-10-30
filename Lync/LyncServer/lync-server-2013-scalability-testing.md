---
title: Prueba de escalabilidad
TOCTitle: Prueba de escalabilidad
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48276538
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prueba de escalabilidad

 

_**Última modificación del tema:** 2012-10-01_

Lync Server 2013 proporciona la infraestructura de servidor para todas las comunicaciones en tiempo real de Lync Server, incluida mensajería instantánea (MI), presencia, conferencias y Telefonía IP empresarial. Esto incluye todas las características que usan los recursos de hardware de un grupo de Lync Server 2013 y, por consiguiente, inciden en el rendimiento y la escala. No todas las organizaciones usan todas las características del mismo modo.

Por ejemplo, algunas organizaciones pueden usar vídeo en las conferencias con mucha frecuencia mientras que otras apenas lo usan o no lo usan en absoluto. Algunas organizaciones prefieren compartir diapositivas de PowerPoint a realizar un uso compartido de las aplicaciones, mientras que otras prefieren lo contrario. Las organizaciones que implementan Telefonía IP empresarial puede que usen mucho (o no) Aplicación de grupo de respuesta. La mayoría de las organizaciones implementan Servidores de supervisión, pero son tantas las que implementan Servidores de archivado. Además, no todas las organizaciones tienen la misma infraestructura (por ejemplo, las capacidades de hardware y red, o el número y el tamaño de los grupos implementados). La diversidad de características e infraestructuras supone un desafío para las pruebas de escalabilidad, ya que no se pueden simular todas las combinaciones posibles de características e infraestructuras.

Para determinar la compatibilidad de escalabilidad de Lync Server, se realizan pruebas usando simultáneamente todas las características de Lync Server, según un modelo de uso medio (modelo de usuario). Para determinar el modelo de usuario adecuado para las cargas de trabajo de Lync Server, se analizan muchos tipos de datos, como encuestas para los clientes, comentarios del programa de mejora de la experiencia del usuario de Microsoft, datos de uso de Lync Server procedentes del departamento de TI interno de Microsoft y datos obtenidos del servicio de Live Meeting. En muchos casos, el modelo de usuario incluye una desviación hacia las cargas más pesadas para proporcionar un margen cómodo de uso a la organización.

En las pruebas de escalabilidad, se configuran grupos de Lync Server 2013 en función de las especificaciones recomendadas de hardware y de software, como los componentes de la infraestructura (Servicios de dominio de Active Directory, equilibradores de carga de hardware y firewalls). Se configuran entornos de Lync Server lo más parecidos posible a entornos habituales del mundo real. Y se usa la herramienta de esfuerzo y rendimiento de Lync Server 2013 para simular las cargas de Lync Server 2013 (sobre la base del modelo de usuario).

Las pruebas de escalabilidad se repiten varias veces (incluidas varias ejecuciones de pruebas de tres semanas). Los resultados de todas las pruebas se usan para mejorar el ajuste del rendimiento y comprobar la compatibilidad de las cifras de escalabilidad del modelo de usuario.


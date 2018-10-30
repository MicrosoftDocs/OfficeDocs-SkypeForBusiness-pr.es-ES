---
title: 'Lync Server 2013: Reducir la mensajería instantánea no solicitada'
TOCTitle: Reducir la mensajería instantánea no solicitada en Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn518335(v=OCS.15)
ms:contentKeyID: 60505979
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Reducir la mensajería instantánea no solicitada en Lync Server 2013

 

_**Última modificación del tema:** 2013-12-05_

La aplicación de filtro inteligente de mensaje instantáneo ayuda a proteger la implementación de Microsoft Lync Server 2013 de los virus más comunes afectando mínimamente a la experiencia de los usuarios. El filtro inteligente de mensaje instantáneo ofrece las siguientes prestaciones:

  - Mejor filtrado de direcciones URL

  - Mejor filtrado de transferencias de archivos

Use el filtro inteligente de mensaje instantáneo para configurar filtros que bloqueen los mensajes instantáneos no solicitados o potencialmente dañinos procedentes de extremos desconocidos más allá del firewall corporativo. Los filtros se configuran especificando los criterios que se van a usar para determinar lo que se va a bloquear, como mensajes instantáneos que contienen hipervínculos y archivos con extensiones específicas.

Antes de implementar la aplicación de filtro inteligente de mensaje instantáneo, es necesario saber cómo se aplican las opciones de filtrado cuando se enrutan los mensajes de un servidor de Lync Server 2013 a otro. Estas opciones de filtrado se aplican de manera coherente, independientemente de si los servidores se encuentran en una o en varias organizaciones. Esta coherencia se aplica a la forma en que los avisos y advertencias personalizados se insertan en los mensajes y se envían a través de los servidores.

La opción de filtrado recomendada es permitir los mensajes instantáneos con hipervínculos, pero obligar al filtro inteligente de mensaje instantáneo a que deshabilite el vínculo anteponiendo un carácter de subrayado. Si elige esta opción, tendrá además la oportunidad de redactar un aviso que va a aparecer al principio de cada mensaje instantáneo que contenga un hipervínculo.

La segunda opción de filtrado consiste en permitir los mensajes instantáneos con hipervínculos no modificados. Si elige esta opción, tendrá además la oportunidad de redactar una advertencia que se va a insertar en cada mensaje (opción recomendada).

La tercera opción consiste en bloquear todos los mensajes instantáneos que contengan un hipervínculo. Si elige esta opción, el servidor envía una advertencia al usuario. Debe escribir esta advertencia.


---
title: 'Lync Server 2013: procedimientos recomendados para entornos de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d02d9ed669cf9404b1bf8d07db32c9d331769ec9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a>Procedimientos recomendados para entornos de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-04_

Se deben aplicar los siguientes principios generales a las operaciones en curso del sistema:

  - **Comprender y utilizar MOF**   MOF es una colección de procedimientos recomendados, principios y modelos que proporcionan orientación técnica a las organizaciones sobre la administración de activos de ti, como las operaciones diarias de Lync Server 2013. Las siguientes instrucciones de MOF pueden ayudarle a conseguir confiabilidad, disponibilidad, compatibilidad y capacidad de administración de sistemas de producción críticos para los productos de Microsoft. Para obtener más información, consulte [Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).

  - **Obtenga información sobre los procedimientos recomendados para Lync Server 2013**   le recomendamos que implemente procedimientos prácticos y probados para administrar Lync Server 2013. El uso de métodos probados, probados y documentados de administración de operaciones puede resultar más eficaz que el desarrollo de sus propios métodos.

  - **Las operaciones independientes en procesos**   diarios, semanales y mensuales documentan las tareas operativas necesarias que se realizarán con regularidad. La documentación sobre cómo realizar tareas ayuda a asegurarse de que la información se conserva cuando hay un cambio en el entorno operativo, como cuando se implementan nuevas tecnologías o cuando se producen cambios en el personal. Se recomienda que las tareas operativas se separan en cargas de trabajo fáciles de administrar, en las que las tareas se realizan diariamente, semanalmente y mensualmente. Las tareas diarias podrían centrar esfuerzos en el funcionamiento de un sistema, y las tareas mensuales se centrarían más en asegurar el mantenimiento a largo plazo de un sistema.
    
    Este documento se puede usar en entornos que implementan solo componentes de mensajería instantánea y presencia (IM/P) o mensajería instantánea/P con Enterprise Voice. Cuando las tareas o los elementos de lista de comprobación son específicos de Enterprise Voice, esto se menciona y, si el entorno no incluye la telefonía IP empresarial, es posible que se omita la parte.

  - **Implementar las herramientas necesarias para el funcionamiento de Lync Server 2013**   muchas herramientas están disponibles para ayudar a solucionar problemas, automatizar tareas y ayudar a supervisar y mantener el entorno de Lync Server 2013. Definir un conjunto estándar de herramientas para su organización, de modo que las tareas realizadas por el equipo de operaciones se realicen de forma precisa, eficiente, coherente y controlada. También debe implementar procesos para realizar un seguimiento de incidentes y cambios de configuración importantes.

<div>

## <a name="reference"></a>Referencia

Para las ventajas de los lectores que aún no están familiarizados con los conceptos básicos de la administración de servidores, se proporciona información general sobre las prácticas de administración de servidores. Los lectores que ya están familiarizados con la administración de servidores pueden omitir esta sección.

Los procedimientos recomendados son recomendaciones que se basan en el conocimiento y la experiencia que los profesionales de TI han ganado en muchos entornos. Proporcionan procedimientos estándar para las tareas típicas que los administradores de Lync Server deben realizar diariamente y muestran las herramientas que deben usar para administrar un entorno de Lync Server.

Las tareas típicas para los administradores de Lync son las siguientes:

  - **La administración**   de la capacidad y la disponibilidad definen cómo y qué se debe medir para predecir los requisitos futuros de capacidad y para informar sobre la capacidad, la confiabilidad y la disponibilidad de los sistemas. Debe comprobar que se ajusta el tamaño de los servidores que ejecutan Lync Server para controlar la carga en el sistema y que el tiempo de inactividad imprevisto se mantiene bajo los niveles definidos en el contrato de nivel de servicio (SLA). Además, tendrá que actualizar el hardware para seguir cumpliendo los requisitos definidos.

  - **Administración de cambios y administración**   de la configuración controle cómo se realizan los cambios en los sistemas de ti. Esto debe incluir la prueba, los comentarios sobre la aplicación y los planes de contingencia, la documentación de todos los cambios y la aprobación de la administración en caso de producirse problemas. Mantener un registro de los activos de software y hardware y sus configuraciones.

  - **Administración del sistema**   métodos estándar para realizar tareas administrativas, como la administración de bases de datos y la administración de sitios.

  - **La administración**   de seguridad tiene una directiva y un plan detallados que protegen la confidencialidad de los datos, la integridad de los datos y la disponibilidad de los datos de la infraestructura de ti. Esto incluye actividades y tareas cotidianas relacionadas con el mantenimiento y el ajuste de la infraestructura de seguridad de ti.

  - **Solución de problemas del sistema**   métodos de esquema para tratar problemas inesperados, incluidos pasos para evitar problemas similares en el futuro.

  - **Los contratos**   de nivel de servicio mantienen un conjunto de objetivos para el rendimiento de los sistemas de ti y miden regularmente el rendimiento frente a estos objetivos.

  - **Documentar**los procedimientos estándar del documento, como la información de configuración y las lecciones aprendidas, y ponerlos a disposición de los miembros del personal que los necesiten.    Cuando se realicen cambios en la configuración, actualice la documentación en consecuencia.

</div>

<div>

## <a name="related-sections"></a>Secciones relacionadas

Revise los siguientes temas sobre las operaciones del sistema antes de continuar:

  - [Administración de la capacidad y la disponibilidad en Lync Server 2013](lync-server-2013-capacity-and-availability-management.md)

  - [Administración de cambios en Lync Server 2013](lync-server-2013-change-management.md)

  - [Administración de la configuración en Lync Server 2013](lync-server-2013-configuration-management.md)

  - [Administración del sistema en Lync Server 2013](lync-server-2013-system-administration.md)

  - [Acuerdos de nivel de servicio en Lync Server 2013](lync-server-2013-service-level-agreements.md)

  - [Documentación en Lync Server 2013](lync-server-2013-documentation.md)

  - [Procedimientos estándar en Lync Server 2013](lync-server-2013-standard-procedures.md)

  - [Procedimientos de emergencia en Lync Server 2013](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


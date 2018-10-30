﻿---
title: 'Lync Server 2013: Definir los requisitos para la supervisión'
TOCTitle: Definir los requisitos para la supervisión de la organización
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48276804
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir los requisitos para la supervisión en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-05_

La simplificación de la implementación y la instalación de la supervisión en Microsoft Lync Server 2013 también ha simplificado el proceso de definición de los requisitos de la organización para la supervisión. No obstante, sigue habiendo cuestiones clave que deben abordarse antes de empezar a instalar y configurar Lync Server 2013:

**¿Qué tipo de datos desea supervisar?** Lync Server 2013 permite supervisar dos tipos de datos diferentes: datos de registro de detalles de la llamada (CDR) y datos de calidad de la experiencia (QoE). El registro de los detalles de la llamada permite realizar el seguimiento del uso de las características de Lync Server, como las llamadas telefónicas de voz sobre IP (VoIP); la mensajería instantánea (MI); las transferencias de archivos; las audioconferencias o videoconferencias (A/V) y las sesiones de uso compartido de aplicaciones. Con esta información es más fácil saber qué características de Lync Server se usan (y cuáles no) y cuándo se usan. Los datos de calidad de la experiencia permiten mantener un registro de la calidad de las llamadas de audio y las videollamadas realizadas en la organización e incluyen, entre otros, el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

Si decide habilitar la supervisión en Lync Server 2013, puede habilitar tanto la supervisión CDR como la supervisión QoE, o bien elegir habilitar un tipo de supervisión y dejar el otro tipo inhabilitado. Por ejemplo, supongamos que sus usuarios usan la mensajería instantánea y la transferencia de archivos, pero no las audiollamadas ni las videollamadas. En este caso, no tiene sentido habilitar la supervisión QoE. Igualmente, con Lync Server es más fácil habilitar e inhabilitar la supervisión después de implementar la supervisión. Por ejemplo, supongamos que decidió implementar la supervisión, pero con la supervisión QoE inhabilitada. Si los usuarios empiezan a tener problemas con las audiollamadas o las videollamadas, puede habilitar la supervisión QoE y usar los datos obtenidos para solucionar más fácilmente estos problemas.

La instalación de la supervisión al mismo tiempo que la instalación de Lync Server no tiene ninguna ventaja (ni inconveniente) especial en comparación con la instalación de la supervisión después de instalar Lync Server. Solo hay que tener en cuenta que, antes de instalar la supervisión, debe seleccionar un PC para que hospede el almacén de supervisión de back-end y que ese PC debe tener una versión compatible de SQL Server instalada y configurada para poder usarlo en la supervisión. Si tiene SQL Server instalado en un PC que ya está listo para su uso, instale la supervisión al mismo tiempo que instala Lync Server. Si no tiene un PC back-end listo, instale Lync Server y después instale la supervisión, cuando el PC back-end este listo para usarlo.

**¿Cuándo desea instalar la supervisión?** La supervisión se puede instalar y configurar al mismo tiempo que instala y configura Lync Server 2013. El Asistente para la implementación de Lync Server le dará la oportunidad de asociar los grupos de servidores front-end a una base de datos de supervisión durante la instalación. También puede instalar la supervisión después de instalar Lync Server. Para ello, use el Generador de topologías para asociar los grupos de servidores front-end y los servidores a una base de datos de supervisión y después publicar la topología revisada.

**¿Cuántas bases de datos de supervisión back-end necesita?** Una sola base de datos de supervisión puede dar soporte a decenas de miles de usuarios (para Microsoft Lync Server 2010, se calculaba que una base de datos combinada para la supervisión y el archivado podía dar soporte a 240 000 usuarios). Además, múltiples servidores front-end pueden usar una sola base de datos de supervisión. Si tiene tres grupos de servidores front-end en la organización, asocie los tres al mismo almacén back-end.

Esto significa simplemente que, para muchas organizaciones, la capacidad de la base de datos no será el factor determinante a la hora de determinar el número de bases de datos de supervisión back-end que se necesitarán. En su lugar, es posible que se dé más importancia a la velocidad de red. Supongamos que tiene tres grupos de servidores front-end, pero uno de estos grupos de servidores se encuentra en una conexión de red lenta. En ese caso, puede que desee tener dos bases de datos de supervisión: una base de datos para los dos grupos de servidores con la conexión de red buena, y otra base de datos para el grupo de servidores con la conexión de red más lenta.

Cuando planee la supervisión de la infraestructura, tenga en cuenta también que Lync Server 2013 es compatible con el uso de bases de datos reflejadas. La creación de reflejo de la base de datos es una forma de mantener al mismo tiempo dos copias de una misma base de datos, cada una de ellas en un servidor diferente. Cada vez que se escriben datos en la base de datos principal, esos mismos datos se escriben en la base de datos reflejada. Si se produce un error en la base de datos principal o esta deja de estar disponible, puede "conmutar por error" a la base de datos reflejada con un sencillo comando PowerShell de Lync Server. Por ejemplo:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

En términos de planificación, esto es importante, ya que será necesario duplicar el número de bases de datos necesarias: además de cada base de datos principal, necesitará otra base de datos que haga de reflejo.

**¿Necesitan sus sitios de Lync Server sus propias configuraciones de supervisión personalizadas?** Cuando instala Lync Server 2013, también instala colecciones globales de configuración CDR y QoE. Estas colecciones globales le dan la capacidad de aplicar la misma configuración CDR y QoE a toda la organización. En muchos casos, esto será suficiente. A menudo, es posible que quiera que la supervisión CDR esté habilitada para todos los usuarios.

No obstante, en ocasiones querrá aplicar otras configuraciones en sitios diferentes. Por ejemplo, quizás quiera usar la supervisión CDR y QoE en el sitio de Redmond, pero desee usar solo la supervisión CDR en el sitio de Dublín. Igualmente, es posible que quiera conservar los datos de supervisión durante 60 días en el sitio de Redmond, y mantener ese mismo tipo de datos durante 30 días en el sitio de Dublín. Lync Server 2013 le permite crear colecciones diferentes de configuración CDR y QoE en el ámbito del sitio. De esta forma, podrá administrar cada sitio de forma diferente. Esto incluye la habilitación y la deshabilitación de la supervisión, así como la configuración de la administración como, por ejemplo, cuánto tiempo se retendrán los datos.

Puede tomar esta decisión antes o después de implementar la supervisión. Por ejemplo, implemente la supervisión y administre toda la organización con la configuración global. Si más tarde cambia de opinión, cree una colección de valores para, por ejemplo, el sitio de Redmond y después use la configuración para administrar la supervisión de Redmond. (La configuración aplicada en el ámbito del sitio, siempre tiene preferencia sobre la configuración aplicada en el ámbito global). Si vuelve a cambiar de opinión, solo tiene que eliminar la configuración aplicada al sitio de Redmond. Cuando se elimina una colección de configuración de un sitio, se aplica automáticamente la colección global de configuración al sitio.


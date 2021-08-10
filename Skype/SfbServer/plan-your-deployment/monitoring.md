---
title: Planear la supervisión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Resumen: revise este tema mientras planea el servicio de supervisión en Skype Empresarial Server.'
ms.openlocfilehash: 0845fb0aa266b955fd86ebc7abf418b98034e31334fbc50dbbb048040e943cf4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306741"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planear la supervisión en Skype Empresarial Server

**Resumen:** Revise este tema mientras planea el servicio de supervisión en Skype Empresarial Server.

El servicio de supervisión de Skype Empresarial Server permite a los administradores recopilar datos de uso y calidad para las sesiones de comunicación que tienen lugar en su organización, lo que les permite identificar tendencias y problemas. La supervisión continua de la implementación le permite detectar los problemas antes de tiempo y mantener satisfechos a los usuarios de su organización.

La supervisión Skype Empresarial Server no requiere un rol de servidor independiente (como era el caso en versiones anteriores de Lync); en su lugar, el servicio de supervisión está integrado en cada servidor front-end. La supervisión no está habilitada de forma predeterminada en Skype Empresarial Server. Este artículo le ayudará a determinar si habilitar la supervisión durante o después de la configuración Skype Empresarial Server inicial y qué recursos SQL necesitará para admitir las actividades de supervisión. Si no está seguro exactamente de qué es o no se supervisa y cómo puede ser útil la supervisión, vaya a [Conceptos básicos sobre supervisión](monitoring.md#Basics). Para comenzar el proceso de planeación, vaya [a Definir los requisitos para la supervisión](monitoring.md#requirements). Para obtener más información sobre los SQL de supervisión, vaya [a SQL requisitos de supervisión](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Conceptos básicos sobre supervisión
<a name="Basics"> </a>

Una sesión es un término genérico para la conexión de un usuario a un:

- Conferencia

- Herramienta de conferencia como audio/vídeo o uso compartido de aplicaciones

- Otro usuario a través de una conversación punto a punto, como mensajería instantánea o una llamada de audio

> [!NOTE]
> Skype Empresarial Server realiza un seguimiento de la información sobre cada sesión: quién llamó a quién; qué puntos de conexión se usaron en la sesión; cuánto tiempo ha durado la sesión; cuál era la calidad percibida de la sesión; y así sucesivamente. Skype Empresarial Server no registra ni almacena la llamada real en sí. Esto incluye sesiones de mensajería instantánea: aunque Skype Empresarial Server registra información sobre sesiones de mensajería instantánea, no mantiene un registro de cada mensaje instantáneo que se envió durante la sesión.

La información básica de detalles de llamadas recopilada por Skype Empresarial Server para cada sesión puede usarse para:

- **Análisis de retorno de la inversión (ROI).** Los administradores pueden comparar los datos de uso con datos similares recopilados para su sistema de telefonía anterior con el fin de mostrar ahorros de costos y ayudar a justificar la implementación de Skype Empresarial Server.

- **Administración de inventario de dispositivos**. La información de administración de activos ayuda a los administradores a identificar dispositivos antiguos que aún están en uso que deben reemplazarse e identificar dispositivos caros que no se usan o que no se usan.

- **Servicio de asistencia**. Los datos de solución de problemas ayudan a los ingenieros a determinar por qué error en la llamada de un usuario, sin tener que recopilar registros del lado cliente o del servidor. El personal de soporte técnico que no tiene un conocimiento técnico profundo del cliente y el Skype Empresarial Server puede acceder Skype Empresarial fácilmente a esta información.

- **Solución de problemas del sistema**. Permite a los administradores detectar problemas importantes que podrían impedir que los usuarios finales realicen tareas básicas como unirse a una conferencia, establecer una llamada o enviar un mensaje instantáneo.

La supervisión también proporciona un mecanismo que permite a los puntos de conexión SIP (como Skype Empresarial) proporcionar información de solución de problemas a la que el administrador no tendría acceso de otro modo:

- **Métricas multimedia que afectan a la calidad**. Estas métricas tratan la transmisión real de la llamada en sí; proporcionan una especie de travelogue a medida que la llamada recorre la red. Estas métricas (que incluyen aspectos como pérdida de paquetes, vibración y tiempos de ida y vuelta) proporcionan información sobre lo que sucedió con la llamada desde el momento en que dejó el extremo de una persona hasta el momento en que llegó al punto de conexión de la otra persona.

- **Problemas notificados al usuario final**. Estas métricas incluyen notificaciones de mala calidad que Skype Empresarial presenta a los usuarios finales en casos en los que están demasiado lejos de un micrófono, hablan demasiado suavemente, tienen una conexión de red deficiente o están experimentando mala calidad porque otro programa en el equipo está consumiendo los recursos disponibles.

- **Información del entorno**. Estas métricas detallan factores de calidad de llamadas, como el tipo de micrófono y altavoces que se usan, si el usuario está conectado a través de una conexión VPN y si el usuario está en una conexión inalámbrica.

Al final de cada llamada, los extremos compatibles con SIP transmiten esta información al servidor front-end que facilitó la llamada. No tiene que hacer nada para que los puntos de conexión transmitan esa información; ese comportamiento se basa en el protocolo SIP. Sin embargo, si quieres recopilar y almacenar esa información, debes instalar y habilitar la supervisión. Si instala y habilita la supervisión, los agentes que ejecutan en el servidor front-end recopilan la información de llamadas y se retransmiten a un par de SQL Server datos. El servicio de supervisión (en forma de "agentes unificados de recopilación de datos") se coloca en todos los servidores front-end.

## <a name="define-your-requirements-for-monitoring"></a>Definir los requisitos para la supervisión
<a name="requirements"> </a>

Todavía hay varios problemas clave que deben solucionarse antes de empezar a instalar y configurar la supervisión con Skype Empresarial Server:

 **¿Cuándo desea instalar la supervisión?** La supervisión se puede instalar y configurar al mismo tiempo que se instala y configura Skype Empresarial Server; el Skype Empresarial Server de implementación le proporcionará la oportunidad de asociar los grupos de servidores front-end con una base de datos de supervisión durante la instalación. Como alternativa, puede instalar la supervisión después Skype Empresarial Server se haya instalado; Esto se puede hacer mediante el Generador de topologías para asociar los grupos de servidores front-end con una base de datos de supervisión y, a continuación, publicar la topología revisada.

Tenga en cuenta que SQL Server debe instalarse y configurarse antes de implementar y configurar la supervisión. Sin embargo, solo necesita implementar SQL Server sí mismo; las bases de datos de supervisión se crearán automáticamente cuando publique la Skype Empresarial Server topología.

 **¿Qué tipo de datos desea supervisar?** Skype Empresarial Server permite supervisar dos tipos generales de datos: datos de registro detallado de llamadas (CDR) y datos de calidad de la experiencia (QoE). La grabación detallada de llamadas proporciona una forma de realizar un seguimiento del uso de Skype Empresarial Server características como llamadas telefónicas de voz sobre IP (VoIP); mensajería instantánea (MI); transferencias de archivos; conferencias de audio y vídeo (A/V); y sesiones de uso compartido de aplicaciones. Esta información le ayuda a saber qué características Skype Empresarial Server se usan (y cuáles no) y también proporciona información sobre cuándo se usan estas características. Los datos de calidad de la experiencia permiten mantener un registro de la calidad de las llamadas de audio y las videollamadas realizadas en la organización e incluyen, entre otros, el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

Si decide habilitar la supervisión en Skype Empresarial Server puede habilitar la supervisión de CDR y la supervisión de QoE, o bien puede habilitar un tipo de supervisión mientras deja deshabilitado el otro tipo. Por ejemplo, supongamos que sus usuarios usan la mensajería instantánea y la transferencia de archivos, pero no las audiollamadas ni las videollamadas. En este caso, no tiene sentido habilitar la supervisión QoE. Del mismo modo, Skype Empresarial Server facilita la habilitación y deshabilitación de la supervisión después de implementar la supervisión. Por ejemplo, supongamos que decidió implementar la supervisión, pero con la supervisión QoE inhabilitada. Si los usuarios empiezan a tener problemas con las audiollamadas o las videollamadas, puede habilitar la supervisión QoE y usar los datos obtenidos para solucionar más fácilmente estos problemas.

No hay ninguna ventaja (o desventaja) particular para instalar la supervisión al mismo tiempo que se instala Skype Empresarial Server en lugar de instalar la supervisión después de Skype Empresarial Server se ha instalado. Solo hay que tener en cuenta que, antes de instalar la supervisión, debe seleccionar un PC para que hospede el almacén de supervisión de back-end y que ese PC debe tener una versión compatible de SQL Server instalada y configurada para poder usarlo en la supervisión. Si ya ha instalado SQL Server en un equipo y ese equipo está listo para su uso, puede instalar la supervisión al mismo tiempo que instala Skype Empresarial Server. Si no tiene un equipo back-end listo, puede continuar con la instalación de Skype Empresarial Server por sí mismo y, a continuación, instalar la supervisión siempre que el equipo back-end esté listo para su uso.

 **¿Cuántas bases de datos de supervisión de back-end necesita?** Se calculó que una base de datos collocada para la supervisión y el archivado podría admitir a 240 000 Skype Empresarial Server usuarios). Además, varios grupos de servidores front-end pueden usar una única base de datos de supervisión; si tiene tres grupos de servidores front-end en su organización, puede asociar los tres grupos con el mismo almacén back-end.

Para muchas organizaciones, la capacidad de la base de datos no será el factor determinante a la hora de determinar el número de bases de datos de supervisión back-end que se requieren. En su lugar, es posible que se dé más importancia a la velocidad de red. Supongamos que tiene tres grupos de servidores front-end, pero uno de estos grupos de servidores se encuentra en una conexión de red lenta. En ese caso, puede que desee tener dos bases de datos de supervisión: una base de datos para los dos grupos de servidores con la conexión de red buena, y otra base de datos para el grupo de servidores con la conexión de red más lenta.

También debe tener en cuenta que Skype Empresarial Server admite el uso de bases de datos reflejadas. La creación de reflejo de la base de datos es una forma de mantener al mismo tiempo dos copias de una misma base de datos, cada una de ellas en un servidor diferente. Cada vez que se escriben datos en la base de datos principal, esos mismos datos se escriben en la base de datos reflejada. Si la base de datos principal debe producir un error o dejar de estar disponible, puede "conmutar por error" a la base de datos reflejada mediante un sencillo Skype Empresarial Server comando de PowerShell. Por ejemplo:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

En términos de planificación, esto es importante, ya que será necesario duplicar el número de bases de datos necesarias: además de cada base de datos principal, necesitará otra base de datos que haga de reflejo.

 **¿Los Skype Empresarial Server necesitan sus propias configuraciones de supervisión personalizadas?** Al instalar Skype Empresarial Server también se instalan colecciones globales de opciones de configuración de CDR y QoE; estas colecciones globales le dan la capacidad de aplicar la misma configuración de CDR y QoE a toda la organización. En muchos casos, esto será suficiente: a menudo querrá, por ejemplo, tener habilitada la supervisión de CDR para todos los usuarios.

Sin embargo, también puede haber ocasiones en las que quieras aplicar diferentes configuraciones a diferentes sitios. Por ejemplo, quizás quiera usar la supervisión de CDR y QoE en el sitio redmond, pero solo usar la supervisión de CDR en su sitio de Dublín. Del mismo modo, es posible que desee conservar los datos de supervisión durante 60 días en el sitio redmond, pero solo necesita mantener este tipo de datos durante 30 días en el sitio de Dublín. Skype Empresarial Server permite crear colecciones independientes de opciones de configuración de CDR y QoE en el ámbito del sitio; que le permite administrar cada sitio de forma diferente. (Esto incluye la habilitación y deshabilitación de la supervisión, así como la configuración de opciones de administración, como el tiempo que se deben conservar los datos).

Puede tomar esta decisión antes o después de implementar la supervisión. Por ejemplo, implemente la supervisión y administre toda la organización con la configuración global. Si más tarde cambia de opinión, cree una colección de valores para, por ejemplo, el sitio de Redmond y después use la configuración para administrar la supervisión de Redmond. (La configuración aplicada en el ámbito del sitio, siempre tiene preferencia sobre la configuración aplicada en el ámbito global). Si vuelve a cambiar de opinión, solo tiene que eliminar la configuración aplicada al sitio de Redmond. Cuando se elimina una colección de configuración de un sitio, se aplica automáticamente la colección global de configuración al sitio.

## <a name="sql-requirements-for-monitoring"></a>SQL requisitos de supervisión
<a name="topologies"> </a>

Los agentes de recopilación de datos unificados se instalan y activan automáticamente en cada servidor front-end al habilitar la supervisión. Para obtener versiones compatibles de SQL Server y otros detalles, vea Requisitos del [servidor para Skype Empresarial Server 2015](requirements-for-your-environment/server-requirements.md)

Los datos de supervisión pueden compartir una SQL Server con otros tipos de datos. Normalmente, la base de datos de registro de detalles de llamadas (LcsCdr) y la base de datos de calidad de la experiencia (QoEMetrics) comparten la misma instancia SQL usuario; también es común que las dos bases de datos de supervisión se den en la misma SQL que la base de datos de archivado (LcsLog). Acerca del único requisito real con SQL Server instancias es que cualquier instancia de SQL Server se limita a lo siguiente:

- Una instancia de la base Skype Empresarial Server back-end de 2015. (Como regla general, no se recomienda colocar la base de datos de supervisión en la misma instancia de SQL, o incluso en el mismo equipo, que la base de datos back-end. Aunque técnicamente es posible, se ejecuta el riesgo de que la base de datos de supervisión use el espacio en disco necesario para la base de datos back-end).

- Una instancia de la base de datos de registro de detalles de llamadas.

- Una instancia de la base de datos de calidad de la experiencia.

- Una instancia de la base de datos de archivado.

En otras palabras, no puede tener dos instancias de la base de datos LcsCdr en la misma instancia de SQL Server. Si necesita varias instancias de la base de datos LcsCdr, debe configurar varias instancias de SQL Server.

## <a name="see-also"></a>Consulte también


[Implementación de supervisión](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)
---
title: Planear la supervisión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Resumen: Revise este tema mientras planea el servicio de supervisión en Skype empresarial Server.'
ms.openlocfilehash: e03fc9714cbb958a9c34bb14db0129a94e49692b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297284"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planear la supervisión en Skype empresarial Server

**Resumen:** Revise este tema mientras planea el servicio de supervisión en Skype empresarial Server.

El servicio de supervisión de Skype empresarial Server proporciona a los administradores una manera de recopilar datos de uso y calidad de las sesiones de comunicación que tienen lugar en su organización, lo que les permite identificar tendencias y problemas. La supervisión continua de la implementación le permite detectar problemas de forma anticipada y mantener satisfechos a los usuarios de la organización.

La supervisión en Skype empresarial Server no requiere un rol de servidor independiente (como es el caso de las versiones anteriores de Lync). en su lugar, el servicio de supervisión está integrado en cada servidor front-end. La supervisión no está habilitada de forma predeterminada en Skype empresarial Server. Este artículo le ayudará a determinar si debe habilitar la supervisión durante o después de la configuración inicial de Skype empresarial Server y qué recursos SQL necesitará para admitir las actividades de supervisión. Si no está seguro de qué es o qué no se supervisa exactamente y cómo puede resultar útil la supervisión, vaya a [conceptos básicos sobre la supervisión](monitoring.md#Basics). Para comenzar el proceso de planeación, vaya a [definir los requisitos para la supervisión](monitoring.md#requirements). Para obtener más información sobre los requisitos de SQL para la supervisión, vaya a [requisitos de SQL para la supervisión](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Datos básicos de la supervisión
<a name="Basics"> </a>

Una sesión es un término genérico para la conexión de un usuario a:

- Una conferencia

- Una herramienta de conferencia, como Audio/vídeo o Uso compartido de aplicaciones

- Otro usuario a través de una conversación punto a punto, como un mensaje instantáneo o una llamada de audio

> [!NOTE]
> Skype empresarial Server realiza un seguimiento de la información sobre cada sesión: quién llamó a quién; los puntos de conexión que se usaron en la sesión; la duración de la sesión es la última. Cuál fue la calidad percibida de la sesión; y así sucesivamente. Skype empresarial Server no graba ni almacena la llamada real. Esto incluye sesiones de mensajería instantánea: aunque Skype empresarial Server registra información sobre las sesiones de mensajería instantánea, no mantiene un registro de todos los mensajes instantáneos que se enviaron durante la sesión.

La información de detalles de llamada básica recopilada por Skype empresarial Server para cada sesión se puede usar para:

- Análisis de **rendimiento de la inversión (ROI)**. Los administradores pueden comparar los datos de uso con datos similares recopilados para su sistema de telefonía anterior con el fin de mostrar ahorros de costos y ayudar a justificar la implementación de Skype empresarial Server.

- **Administración del inventario de dispositivos**. La información de administración de activos ayuda a los administradores a identificar los dispositivos antiguos que todavía se usan y que precisan reemplazarse, y a identificar los dispositivos costosos que no se utilizan o tienen poco uso.

- **Servicio de asistencia**. La solución de problemas de datos ayuda a los ingenieros a determinar por qué ha fallado la llamada de un usuario, sin tener que recopilar registros del lado del servidor o del cliente. Esta información puede ser accesible y comprensible para el personal de soporte técnico que no tiene un profundo conocimiento técnico del cliente de Skype empresarial y de Skype empresarial Server.

- **Solución de problemas del sistema**. Los administradores pueden detectar problemas importantes que pueden impedir que los usuarios finales lleven a cabo tareas básicas, como unirse a una conferencia, realizar una llamada o enviar un mensaje instantáneo.

La supervisión también proporciona un mecanismo que permite que los puntos de conexión SIP (como Skype empresarial) proporcionen información de resolución de problemas a la que el administrador no tendría acceso de otra manera:

- **Métricas de medios que inciden en la calidad**. Son métricas que se centran en la transmisión real de la llamada. Ofrecen una especie de cuaderno de viaje de todo el recorrido de la llamada a través de la red. Estas métricas (que engloban aspectos como la pérdida de paquetes, la vibración y los tiempos de ida y vuelta) informan de lo que ha sucedido en la llamada desde que dejó el extremo de una persona hasta que llegó al extremo de la otra.

- **Problemas notificados al usuario final**. Estas métricas incluyen notificaciones de mala calidad que la aplicación de Skype empresarial presenta a los usuarios finales en casos en los que están demasiado lejos de un micrófono, hablan demasiado, tienen una mala conexión de red o experimentan una mala calidad porque otro programa de la el equipo está consumiendo los recursos disponibles.

- **Información del entorno**. Estas métricas detallan los factores de calidad de la llamada, como el tipo de micrófono y altavoces que se usan, si el usuario se conecta a través de una conexión VPN y si tiene una conexión inalámbrica.

Al término de cada llamada, los extremos compatibles con SIP transmiten esta información al servidor front-end que hizo posible la llamada. No hay que hacer absolutamente nada para que esto suceda, puesto que este comportamiento está integrado en el protocolo SIP. Pero, si desea recopilar y guardar esta información, necesitará instalar y habilitar la supervisión, ya que, al hacerlo, los agentes que se ejecutan en el servidor front-end recopilarán la información de las llamadas y la transmitirán a un par de bases de datos de SQL Server. El servicio de supervisión (en la forma de los "agentes de recopilación de datos unificados") se combina en todos los servidores front-end. 

## <a name="define-your-requirements-for-monitoring"></a>Definir los requisitos para la supervisión
<a name="requirements"> </a>

Aún hay varios problemas clave que se deben solucionar antes de empezar a instalar y configurar la supervisión con Skype empresarial Server:

 **¿Cuándo desea instalar la supervisión?** La supervisión se puede instalar y configurar al mismo tiempo que se instala y configura Skype empresarial Server. el Asistente para la implementación de Skype empresarial Server le proporcionará la oportunidad de asociar los grupos de aplicaciones front-end con una base de datos de supervisión durante la configuración. También puede instalar la supervisión después de instalar Skype empresarial Server. Esto se puede realizar con el generador de topologías para asociar los servidores y los servidores front-end con una base de datos de supervisión y, a continuación, publicar la topología revisada.

Recuerde que es preciso que SQL Server esté instalado y configurado antes de implementar y configurar la supervisión. Sin embargo, solo necesita implementar SQL Server en sí; las bases de datos de supervisión se crearán cuando publique la topología de su servidor de Skype empresarial.

 **¿Qué tipo de datos desea supervisar?** Skype empresarial Server permite supervisar dos tipos generales de datos: datos de grabación de llamadas (CDR) y datos de calidad de la experiencia (QoE). Grabación de detalles de llamadas le permite realizar un seguimiento del uso de las características de Skype empresarial Server, como las llamadas telefónicas de voz a través de IP (VoIP); mensajería instantánea (mi); transferencias de archivos; conferencias de audio y vídeo (A/V); y sesiones de uso compartido de aplicaciones. Esta información le ayuda a saber qué características de Skype empresarial Server se usan (y cuáles no), y también proporciona información sobre cuándo se usan estas características. Los datos de calidad de la experiencia permiten mantener un registro de la calidad de las llamadas de audio y vídeo realizadas en la organización e incluyen, entre otros, la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

Si elige habilitar la supervisión en Skype empresarial Server, puede habilitar la supervisión de CDR y la supervisión de QoE, o bien, puede elegir habilitar un tipo de supervisión y dejar el otro tipo desactivado. Por ejemplo, supongamos que sus usuarios usan la mensajería instantánea y la transferencia de archivos, pero no las llamadas de audio o vídeo. En este caso, no tiene sentido habilitar la supervisión de QoE. Del mismo modo, Skype empresarial Server facilita la activación y desactivación del monitoreo después de haber implementado la supervisión. Por ejemplo, supongamos que decidió implementar la supervisión, pero con la supervisión de QoE inicialmente deshabilitada. Si los usuarios empiezan a tener problemas con las llamadas de audio o vídeo, puede habilitar la supervisión de QoE y usar los datos obtenidos para solucionar más fácilmente estos problemas.

No hay ventajas (o desventaja) específicas para instalar la supervisión al mismo tiempo que instala Skype empresarial Server en lugar de instalar la supervisión después de instalar Skype empresarial Server. Solo hay que tener en cuenta que, antes de instalar la supervisión, es preciso seleccionar un equipo para que hospede el almacén de supervisión de back-end y que ese equipo precisa tener una versión compatible de SQL Server instalada y configurada para poder usarlo en la supervisión. Si ya ha instalado SQL Server en un equipo y ese equipo está listo para su uso, puede instalar la supervisión al mismo tiempo que instala Skype empresarial Server. Si no tiene un equipo de back-end listo, puede continuar con la instalación de Skype empresarial Server por sí mismo y, a continuación, instalar la supervisión siempre que el equipo back-end esté listo para su uso.

 **¿Cuántas bases de datos de supervisión de backend necesita?** Se estimó que una base de datos colocada para la supervisión y el archivado podían admitir usuarios de 240.000 Skype empresarial Server. Además, varias agrupaciones front end pueden usar una sola base de datos de supervisión; Si tiene tres grupos front-end de su organización, puede asociar los tres grupos con el mismo almacén de back-end.

Para muchas organizaciones, la capacidad de la base de datos no será el factor determinante a la hora de establecer la cantidad de bases de datos de supervisión back-end que se necesitarán. En su lugar, es posible que se dé más importancia a la velocidad de red. Supongamos que tiene tres grupos de servidores front-end, pero uno de estos grupos de servidores se encuentra en una conexión de red lenta. En ese caso, puede que desee tener dos bases de datos de supervisión: una base de datos para los dos grupos de servidores con la conexión de red buena y otra base de datos para el grupo de servidores con la conexión de red más lenta.

También debe tener en cuenta que Skype empresarial Server admite el uso de bases de datos reflejadas. La creación de reflejo de la base de datos es una forma de mantener al mismo tiempo dos copias de una base de datos, cada una de ellas en un servidor diferente. Cada vez que se escriben datos en la base de datos principal, esos mismos datos se escriben en la base de datos reflejada. Si la base de datos principal falla o no está disponible, puede realizar la "conmutación por error" a la base de datos reflejada mediante un simple comando de PowerShell de Skype empresarial Server. Por ejemplo:

```
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

En términos de planeación, esto es importante, ya que será necesario duplicar la cantidad de bases de datos necesarias, ya que, aparte de cada base de datos principal, necesitará otra base de datos que haga de reflejo.

 **¿Sus sitios de Skype empresarial Server necesitan tener sus propias configuraciones de supervisión personalizadas?** Al instalar Skype empresarial Server, también se instalan colecciones globales de parámetros de configuración de CDR y QoE; Estas colecciones internacionales le ofrecen la posibilidad de aplicar la misma configuración de CDR y QoE a toda la organización. In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

En cambio, en ocasiones querrá aplicar otras configuraciones en sitios diferentes. Por ejemplo, quizás quiera usar la supervisión de CDR y QoE en el sitio de Redmond, pero desee usar solo la supervisión de CDR en el sitio de Dublín. Igualmente, es posible que quiera conservar los datos de supervisión durante 60 días en el sitio de Redmond, y mantener ese mismo tipo de datos durante 30 días en el sitio de Dublín. Skype empresarial Server le permite crear colecciones separadas de parámetros de configuración de CDR y QoE en el ámbito del sitio; Esto le permite administrar cada sitio de forma diferente. De esta forma, podrá administrar cada sitio de forma diferente (esto incluye la habilitación y la deshabilitación de la supervisión, así como también la configuración de las opciones de administración como, por ejemplo, cuánto tiempo se retendrán los datos).

Puede tomar esta decisión antes o después de implementar la supervisión. Por ejemplo, implemente la supervisión y administre toda la organización con la configuración global. Si más tarde cambia de opinión, cree una colección de opciones independiente para, por ejemplo, el sitio de Redmond y después use esta configuración para administrar la supervisión de Redmond. (La configuración aplicada en el ámbito de sitio siempre tiene preferencia sobre la configuración aplicada en el ámbito global). Si vuelve a cambiar de opinión, solo tiene que eliminar las opciones de configuración aplicadas al sitio de Redmond. Cuando se elimina una colección de opciones de configuración de un sitio, se aplica automáticamente la colección global de configuración al sitio.

## <a name="sql-requirements-for-monitoring"></a>Requisitos de SQL para la supervisión
<a name="topologies"> </a>

Cuando se habilita la supervisión, se instalan y activan automáticamente en cada servidor los agentes de recopilación de datos unificados. Para versiones compatibles de SQL Server y otros detalles, consulte [requisitos del servidor para Skype empresarial server 2015](requirements-for-your-environment/server-requirements.md)

Al supervisar los datos se puede compartir una instancia de SQL Server con otros tipos de datos. Generalmente, las bases de datos del registro detallado de llamadas (LcsCdr) y de la calidad de la experiencia (QoEMetrics) comparten la misma instancia de SQL. También es habitual que las dos bases de datos de supervisión se encuentren en la misma instancia de SQL que la base de datos de archivado (LcsLog). El único requisito real con relación a las instancias de SQL Server es que cada una de ellas se limite conforme a lo siguiente:

- Una instancia de la base de datos back-end de Skype empresarial Server 2015. Como norma general, no recomendamos que la base de datos de supervisión se encuentre en la misma instancia de SQL, ni siquiera en el mismo equipo, que la base de datos back-end. Aunque técnicamente es posible, corre el riesgo de que la base de datos de supervisión agote el espacio en disco que necesita la base de datos back-end.

- Una instancia de la base de datos del registro detallado de llamadas.

- Una instancia de la base de datos de la calidad de la experiencia.

- Una instancia de la base de datos de archivado.

En otras palabras, no puede tener dos instancias de la base de datos LcsCdr en la misma instancia de SQL Server. Si necesita varias instancias de la base de datos LcsCdr, tendrá que configurar varias instancias de SQL Server.

## <a name="see-also"></a>Vea también


[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

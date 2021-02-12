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
description: 'Resumen: revise este tema al planear el servicio de supervisión en Skype Empresarial Server.'
ms.openlocfilehash: b2f269d3e4cc62ca08ee423858e13d12b23bddd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825630"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planear la supervisión en Skype Empresarial Server

**Resumen:** Revise este tema mientras planea el servicio de supervisión en Skype Empresarial Server.

El servicio de supervisión de Skype Empresarial Server permite a los administradores recopilar datos de uso y calidad para las sesiones de comunicación que tienen lugar en su organización, lo que les permite identificar tendencias y problemas. La supervisión continua de la implementación le permite detectar problemas pronto y mantener satisfechos a los usuarios de su organización.

La supervisión en Skype Empresarial Server no requiere un rol de servidor independiente (como era el caso en versiones anteriores de Lync); en su lugar, el servicio de supervisión está integrado en cada servidor front-end. La supervisión no está habilitada de forma predeterminada en Skype Empresarial Server. Este artículo le ayudará a determinar si habilitará la supervisión durante o después de la configuración inicial de Skype Empresarial Server y qué recursos SQL necesitará para admitir las actividades de supervisión. Si no está seguro exactamente de lo que se supervisa o no y de cómo puede resultar útil la supervisión, vaya a [Conceptos básicos sobre supervisión.](monitoring.md#Basics) Para comenzar el proceso de planeación, vaya [a Definir los requisitos para la supervisión.](monitoring.md#requirements) Para obtener más información sobre los SQL de supervisión, vaya [a SQL para la supervisión.](monitoring.md#topologies)

## <a name="basics-about-monitoring"></a>Conceptos básicos sobre supervisión
<a name="Basics"> </a>

Una sesión es un término genérico para la conexión de un usuario a:

- Conferencia

- Herramienta de conferencia, como audio/vídeo o uso compartido de aplicaciones

- Otro usuario a través de una conversación punto a punto, como la mensajería instantánea o una llamada de audio

> [!NOTE]
> Skype Empresarial Server realiza un seguimiento de la información sobre cada sesión: quién llamó a quién; qué puntos de conexión se usaron en la sesión; cuánto tiempo ha durado la sesión; cuál era la calidad percibida de la sesión; y así sucesivamente. Skype Empresarial Server no registra ni almacena la llamada real. Esto incluye sesiones de mensajería instantánea: aunque Skype Empresarial Server registra información acerca de las sesiones de mensajería instantánea, no mantiene un registro de cada mensaje instantáneo que se envió durante la sesión.

La información básica de detalles de llamadas recopilada por Skype Empresarial Server para cada sesión se puede usar para:

- **Análisis de retorno de la inversión (ROI).** Los administradores pueden comparar los datos de uso con datos similares recopilados para su sistema de telefonía anterior con el fin de mostrar ahorros de costos y ayudar a justificar la implementación de Skype Empresarial Server.

- **Administración de inventario de dispositivos.** La información de administración de activos ayuda a los administradores a identificar dispositivos antiguos que aún están en uso que deben reemplazarse e identificar dispositivos costosos que no se usan o que no se usan.

- **Help Desk**. Los datos de solución de problemas ayudan a los ingenieros de soporte técnico a determinar por qué se ha generado un error en la llamada de un usuario, sin tener que recopilar registros del lado cliente o del servidor. El personal de soporte técnico que no tiene un conocimiento técnico profundo del cliente de Skype Empresarial y Skype Empresarial Server puede tener acceso a esta información y comprenderla fácilmente.

- **Solución de problemas del sistema.** Permite a los administradores detectar problemas importantes que podrían impedir que los usuarios finales realicen tareas básicas, como unirse a una conferencia, establecer una llamada o enviar un mensaje instantáneo.

La supervisión también proporciona un mecanismo que permite a los extremos SIP (como Skype Empresarial) proporcionar información de solución de problemas a la que el administrador no tendría acceso de otro modo:

- **Métricas multimedia que afectan a la calidad.** Estas métricas se tratan con la transmisión real de la llamada en sí; proporcionan una clase de viajes a medida que la llamada viaja por la red. Estas métricas (que incluyen aspectos como la pérdida de paquetes, la vibración y los tiempos de ida y vuelta) proporcionan información sobre lo que sucedió con la llamada desde el momento en que dejó el extremo de una persona hasta el momento en que llegó al extremo de la otra persona.

- **Problemas notificados al usuario final.** Estas métricas incluyen notificaciones de calidad deficientes que Skype Empresarial presenta a los usuarios finales en los casos en los que están demasiado lejos de un micrófono, hablan demasiado bien, tienen una conexión de red deficiente o tienen mala calidad porque otro programa del equipo consume los recursos disponibles.

- **Información del entorno.** Estas métricas detallan los factores de calidad de la llamada, como el tipo de micrófono y altavoces que se usan, si el usuario está conectado a través de una conexión VPN y si el usuario está en una conexión inalámbrica.

Al final de cada llamada, los extremos compatibles con SIP transmiten esta información al servidor front-end que facilitaba la llamada. No tiene que hacer nada para que los puntos de conexión transmitan esa información; ese comportamiento está integrado en el protocolo SIP. Sin embargo, si desea recopilar y almacenar esa información, debe instalar y habilitar la supervisión. Si instala y habilita la supervisión, los agentes que ejecutan el servidor front-end recopilan la información de la llamada y se retransmiten a un par de bases SQL Server de datos. El servicio de supervisión (en forma de "agentes unificados de recopilación de datos") se coloca en todos los servidores front-end.

## <a name="define-your-requirements-for-monitoring"></a>Definir los requisitos para la supervisión
<a name="requirements"> </a>

Todavía hay varios problemas clave que deben resolverse antes de empezar a instalar y configurar la supervisión con Skype Empresarial Server:

 **¿Cuándo desea instalar la supervisión?** La supervisión se puede instalar y configurar al mismo tiempo que se instala y configura Skype Empresarial Server; El Asistente para la implementación de Skype Empresarial Server le proporcionará la oportunidad de asociar los grupos de servidores front-end con una base de datos de supervisión durante la instalación. Como alternativa, puede instalar la supervisión después de instalar Skype Empresarial Server; Esto se puede hacer mediante el Generador de topologías para asociar los servidores y grupos de servidores front-end con una base de datos de supervisión y, a continuación, publicar la topología revisada.

Tenga en cuenta que SQL Server deben instalarse y configurarse antes de implementar y configurar la supervisión. Sin embargo, solo necesita implementar SQL Server sí mismo; Las bases de datos de supervisión se crearán automáticamente al publicar la topología de Skype Empresarial Server.

 **¿Qué tipo de datos desea supervisar?** Skype Empresarial Server le permite supervisar dos tipos generales de datos: datos de registro detallado de llamadas (CDR) y datos de calidad de la experiencia (QoE). El registro detallado de llamadas permite realizar un seguimiento del uso de las características de Skype Empresarial Server, como las llamadas telefónicas de voz sobre IP (VoIP); mensajería instantánea (MI); transferencias de archivos; conferencia de audio y vídeo (A/V); y sesiones de uso compartido de aplicaciones. Esta información le ayuda a saber qué características de Skype Empresarial Server se usan (y cuáles no) y también proporciona información sobre cuándo se usan estas características. Los datos de calidad de la experiencia permiten mantener un registro de la calidad de las llamadas de audio y las videollamadas realizadas en la organización e incluyen, entre otros, el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

Si decide habilitar la supervisión en Skype Empresarial Server, puede habilitar la supervisión de CDR y la supervisión de QoE, o bien puede habilitar un tipo de supervisión y dejar el otro tipo deshabilitado. Por ejemplo, supongamos que sus usuarios usan la mensajería instantánea y la transferencia de archivos, pero no las audiollamadas ni las videollamadas. En este caso, no tiene sentido habilitar la supervisión QoE. Del mismo modo, Skype Empresarial Server facilita la habilitación y deshabilitación de la supervisión después de implementar la supervisión. Por ejemplo, supongamos que decidió implementar la supervisión, pero con la supervisión QoE inhabilitada. Si los usuarios empiezan a tener problemas con las audiollamadas o las videollamadas, puede habilitar la supervisión QoE y usar los datos obtenidos para solucionar más fácilmente estos problemas.

No hay ninguna ventaja (o desventaja) particular para instalar la supervisión al mismo tiempo que la instalación de Skype Empresarial Server frente a la instalación de la supervisión después de instalar Skype Empresarial Server. Solo hay que tener en cuenta que, antes de instalar la supervisión, debe seleccionar un PC para que hospede el almacén de supervisión de back-end y que ese PC debe tener una versión compatible de SQL Server instalada y configurada para poder usarlo en la supervisión. Si ya ha instalado SQL Server en un equipo y ese equipo está listo para su uso, puede instalar la supervisión al mismo tiempo que instala Skype Empresarial Server. Si no tiene un equipo back-end listo, puede continuar con la instalación de Skype Empresarial Server por sí mismo y, a continuación, instalar la supervisión siempre que el equipo back-end esté listo para su uso.

 **¿Cuántas bases de datos de supervisión back-end necesita?** Se calculó que una base de datos para la supervisión y el archivado podría admitir 240 000 usuarios de Skype Empresarial Server. Además, varios grupos de servidores front-end pueden usar una única base de datos de supervisión; Si tiene tres grupos de servidores front-end en su organización, puede asociar los tres grupos con el mismo almacén back-end.

Para muchas organizaciones, la capacidad de las bases de datos no será el factor determinante a la hora de determinar el número de bases de datos de supervisión back-end que se requieren. En su lugar, es posible que se dé más importancia a la velocidad de red. Supongamos que tiene tres grupos de servidores front-end, pero uno de estos grupos de servidores se encuentra en una conexión de red lenta. En ese caso, puede que desee tener dos bases de datos de supervisión: una base de datos para los dos grupos de servidores con la conexión de red buena, y otra base de datos para el grupo de servidores con la conexión de red más lenta.

También debe tener en cuenta que Skype Empresarial Server admite el uso de bases de datos reflejadas. La creación de reflejo de la base de datos es una forma de mantener al mismo tiempo dos copias de una misma base de datos, cada una de ellas en un servidor diferente. Cada vez que se escriben datos en la base de datos principal, esos mismos datos se escriben en la base de datos reflejada. Si la base de datos principal debe producir un error o dejar de estar disponible, puede "conmutar por error" a la base de datos reflejada mediante un sencillo comando de PowerShell de Skype Empresarial Server. Por ejemplo:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

En términos de planificación, esto es importante, ya que será necesario duplicar el número de bases de datos necesarias: además de cada base de datos principal, necesitará otra base de datos que haga de reflejo.

 **¿Los sitios de Skype Empresarial Server necesitan sus propias configuraciones de supervisión personalizadas?** Al instalar Skype Empresarial Server, también instala colecciones globales de opciones de configuración de CDR y QoE; estas colecciones globales le dan la capacidad de aplicar la misma configuración de CDR y QoE a toda la organización. En muchos casos, esto será suficiente: a menudo querrá, por ejemplo, tener habilitada la supervisión de CDR para todos los usuarios.

Sin embargo, también puede haber ocasiones en las que desee aplicar configuraciones diferentes a sitios diferentes. Por ejemplo, quizás quiera usar la supervisión de CDR y QoE en su sitio de Redmond, pero solo use la supervisión de CDR en su sitio de Dublín. Del mismo modo, es posible que desee conservar los datos de supervisión durante 60 días en el sitio redmond, pero solo necesita mantener este tipo de datos durante 30 días en el sitio de Dublín. Skype Empresarial Server le permite crear colecciones independientes de opciones de configuración de CDR y QoE en el ámbito del sitio; que le permite administrar cada sitio de forma diferente. (Esto incluye la habilitación y deshabilitación de la supervisión, así como la configuración de opciones de administración, como cuánto tiempo se conservarán los datos).

Puede tomar esta decisión antes o después de implementar la supervisión. Por ejemplo, implemente la supervisión y administre toda la organización con la configuración global. Si más tarde cambia de opinión, cree una colección de valores para, por ejemplo, el sitio de Redmond y después use la configuración para administrar la supervisión de Redmond. (La configuración aplicada en el ámbito del sitio, siempre tiene preferencia sobre la configuración aplicada en el ámbito global). Si vuelve a cambiar de opinión, solo tiene que eliminar la configuración aplicada al sitio de Redmond. Cuando se elimina una colección de configuración de un sitio, se aplica automáticamente la colección global de configuración al sitio.

## <a name="sql-requirements-for-monitoring"></a>SQL de supervisión
<a name="topologies"> </a>

Los agentes de recopilación de datos unificados se instalan y activan automáticamente en cada servidor front-end cuando se habilita la supervisión. Para obtener versiones compatibles de SQL Server y otros detalles, consulte Requisitos del servidor [para Skype Empresarial Server 2015](requirements-for-your-environment/server-requirements.md)

Los datos de supervisión pueden compartir una SQL Server con otros tipos de datos. Normalmente, la base de datos de registro de detalles de llamadas (LcsCdr) y la base de datos de calidad de la experiencia (QoEMetrics) comparten la misma SQL usuario; también es común que las dos bases de datos de supervisión se encontrarán en la misma SQL que la base de datos de archivado (LcsLog). El único requisito real con SQL Server instancias es que cualquier instancia de SQL Server está limitada a lo siguiente:

- Una instancia de la base de datos back-end de Skype Empresarial Server 2015. (Como regla general, no se recomienda instalar la base de datos de supervisión en la misma instancia de SQL, o incluso en el mismo equipo, que la base de datos back-end. Aunque técnicamente es posible, se corre el riesgo de que la base de datos de supervisión use espacio en disco necesario para la base de datos back-end).

- Una instancia de la base de datos de registro detallado de llamadas.

- Una instancia de la base de datos de calidad de la experiencia.

- Una instancia de la base de datos de archivado.

En otras palabras, no puede tener dos instancias de la base de datos LcsCdr en la misma instancia de SQL Server. Si necesita varias instancias de la base de datos LcsCdr, deberá configurar varias instancias de SQL Server.

## <a name="see-also"></a>Vea también


[Implementación de supervisión](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

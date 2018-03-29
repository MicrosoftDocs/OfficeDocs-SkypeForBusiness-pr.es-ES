---
title: Planificar el seguimiento en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Resumen: Revisar este tema al planear el servicio de supervisión en Skype para Business Server 2015.'
ms.openlocfilehash: 82cad33f6094711f592633229db81b598df56fcb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-monitoring-in-skype-for-business-server-2015"></a>Planificar el seguimiento en Skype Empresarial Server 2015
 
**Resumen:** Revise este tema al planear el servicio de supervisión en Skype para Business Server 2015.
  
El servicio de supervisión en Skype para Business Server 2015 proporciona a los administradores recopilar datos de uso y calidad de las sesiones de comunicación llevadas a cabo en su organización, lo que les permite identificar tendencias y problemas. La supervisión continua de la implementación permite detectar problemas a tiempo y mantener satisfechos a los usuarios de su organización. 
  
Supervisión en Skype por Business Server requieren una función de servidor distinta (como ocurría en versiones anteriores de Lync); en su lugar, el servicio de supervisión está integrado en cada servidor Front-End. Seguimiento no está habilitado de forma predeterminada en Skype para Business Server. Este artículo le ayudará a determinar si se habilita la supervisión durante o después de su Skype inicial de configuración del servidor de la empresa y qué recursos SQL debe apoyan las actividades de supervisión. Si no estás seguro exactamente lo que es o no supervisada y cómo supervisión puede ser útil, vaya a [conceptos básicos acerca de la supervisión](monitoring.md#Basics). Para comenzar el proceso de diseño, vaya a [definir los requerimientos para la supervisión](monitoring.md#requirements). Para obtener más detalles sobre los requisitos de SQL para supervisar, vaya a [requisitos de SQL para supervisar](monitoring.md#topologies).
  
## <a name="basics-about-monitoring"></a>Datos básicos de la supervisión
<a name="Basics"> </a>

Una sesión es un término genérico para la conexión de un usuario a a:
  
- Una conferencia
    
- Una herramienta de conferencia, como Audio/vídeo o Uso compartido de aplicaciones
    
- Otro usuario a través de una conversación punto a punto, como un mensaje instantáneo o una llamada de audio
    
> [!NOTE]
> Skype para Business Server realiza un seguimiento de información acerca de cada sesión: quién llama a quién; los extremos se utilizan en la sesión; ¿cuánto ha durado la sesión; ¿Cuál fue la calidad percibida de la sesión; y así sucesivamente. Skype para Business Server no registrar y almacenar la propia llamada. Que incluye sesiones de mensajería instantáneas: aunque Skype para Business Server registra información acerca de las sesiones de mensajería instantáneas, no mantiene un registro de todos los mensajes instantáneos que se envían durante la sesión. 
  
La información de detalle de llamada básico recopilada por Skype para Business Server para cada sesión puede utilizarse para:
  
- Análisis de **rendimiento de la inversión (ROI)**. Los administradores pueden comparar los datos de uso con datos similares recopilados para que su sistema de telefonía anterior con el fin de mostrar los ahorros de costos y ayudar a justificar la implementación de Skype para Business Server.
    
- **Administración del inventario de dispositivos**. La información de administración de activos ayuda a los administradores a identificar los dispositivos antiguos que todavía se usan y que precisan reemplazarse, y a identificar los dispositivos costosos que no se utilizan o tienen poco uso.
    
- **Servicio de asistencia**. Datos de solución de problemas ayuda soporte ingenieros determinan por qué un usuario llamada genera el error, sin tener que recopilar registros de lado de servidor o cliente. Esta información puede acceder fácilmente y se entiende por personal de soporte que no tienen un profundo conocimiento técnico de la Skype para Business client y Skype para Business Server 2015.
    
- **Solución de problemas del sistema**. Los administradores pueden detectar problemas importantes que pueden impedir que los usuarios finales lleven a cabo tareas básicas, como unirse a una conferencia, realizar una llamada o enviar un mensaje instantáneo.
    
Supervisión, también proporciona un mecanismo que permite los extremos SIP (por ejemplo, Skype para el negocio) para proporcionar información de solución de problemas que el Administrador de otra manera no tendría acceso a:
  
- **Métricas de medios que inciden en la calidad**. Son métricas que se centran en la transmisión real de la llamada. Ofrecen una especie de cuaderno de viaje de todo el recorrido de la llamada a través de la red. Estas métricas (que engloban aspectos como la pérdida de paquetes, la vibración y los tiempos de ida y vuelta) informan de lo que ha sucedido en la llamada desde que dejó el extremo de una persona hasta que llegó al extremo de la otra.
    
- **Problemas notificados al usuario final**. Estas métricas incluyen notificaciones de mala calidad que Skype para Business presenta a los usuarios finales en casos donde están demasiado lejos del micrófono, hablando en un tono demasiado suave, tiene una conexión de red pobre, o si tiene mala calidad porque otro programa en la consume los recursos disponibles en el equipo.
    
- **Información del entorno**. Estas métricas detallan los factores de calidad de la llamada, como el tipo de micrófono y altavoces que se usan, si el usuario se conecta a través de una conexión VPN y si tiene una conexión inalámbrica.
    
Al término de cada llamada, los extremos compatibles con SIP transmiten esta información al servidor front-end que hizo posible la llamada. No hay que hacer absolutamente nada para que esto suceda, puesto que este comportamiento está integrado en el protocolo SIP. Pero, si desea recopilar y guardar esta información, necesitará instalar y habilitar la supervisión, ya que, al hacerlo, los agentes que se ejecutan en el servidor front-end recopilarán la información de las llamadas y la transmitirán a un par de bases de datos de SQL Server. El servicio de supervisión (en la forma de los "agentes de recopilación de datos unificados") se combina en todos los servidores front-end.  
  
## <a name="define-your-requirements-for-monitoring"></a>Definir los requisitos para la supervisión
<a name="requirements"> </a>

Todavía hay varios aspectos clave que se deben solucionar antes de empezar a instalar y configurar la supervisión con Skype para Business Server 2015:
  
 **¿Cuándo desea instalar la supervisión?** Supervisión puede instalarse y configurarse al mismo tiempo, instalar y configurar Skype para Business Server 2015; el Skype para el Asistente para implementación de Business Server 2015 le proporcionará la oportunidad para asociar las agrupaciones de Front-End con una base de datos de supervisión durante la instalación. Como alternativa, puede instalar supervisión después de instalar Skype para Business Server 2015 propio; Esto puede hacerse mediante el generador de topología para asociar los pools de Front-End y los servidores con una base de datos de supervisión, y después publicar la topología revisada.
  
Recuerde que es preciso que SQL Server esté instalado y configurado antes de implementar y configurar la supervisión. Sin embargo, sólo debe implementar SQL Server las bases de datos de supervisión se creará automáticamente al publicar su Skype para la topología de servidores de empresa.
  
 **¿Qué tipo de datos desea supervisar?** Skype para Business Server 2015 permite supervisar dos tipos generales de datos: llamada detallando datos de grabación (CDR) y calidad de la experiencia (QoE). Registro de detalles de llamada proporciona una manera de hacer un seguimiento del uso de Skype para Business Server 2015 características tales como voz sobre IP (VoIP) llamadas de teléfono; mensajería instantánea (IM); transferencias de archivos; audio y vídeo (A / V) conferencia; y sesiones de uso compartido de aplicaciones. Esta información le ayuda a saber qué Skype se utilizan funciones de Business Server 2015 (y que no están) y también proporciona información sobre cuándo se utilizan estas características. Los datos de calidad de la experiencia permiten mantener un registro de la calidad de las llamadas de audio y vídeo realizadas en la organización e incluyen, entre otros, la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).
  
Si decide habilitar supervisión en Skype para Business Server 2015 puede habilitar supervisión de CDR y QoE supervisión, o bien puede optar por habilitar a un tipo de supervisión y dejar el otro tipo deshabilitado. Por ejemplo, supongamos que sus usuarios usan la mensajería instantánea y la transferencia de archivos, pero no las llamadas de audio o vídeo. En este caso, no tiene sentido habilitar la supervisión de QoE. Asimismo, Skype para Business Server 2015 facilita habilitar y deshabilitar el seguimiento después de haber implementado la supervisión. Por ejemplo, supongamos que decidió implementar la supervisión, pero con la supervisión de QoE inicialmente deshabilitada. Si los usuarios empiezan a tener problemas con las llamadas de audio o vídeo, puede habilitar la supervisión de QoE y usar los datos obtenidos para solucionar más fácilmente estos problemas.
  
No hay ninguna ventaja particular (o desventaja) para la instalación de supervisión al mismo tiempo que instalar Skype para Business Server 2015 frente a instalación de supervisión después de instalar Skype para Business Server 2015. Solo hay que tener en cuenta que, antes de instalar la supervisión, es preciso seleccionar un equipo para que hospede el almacén de supervisión de back-end y que ese equipo precisa tener una versión compatible de SQL Server instalada y configurada para poder usarlo en la supervisión. Si ya ha instalado a SQL Server en un equipo y está listo para usar ese equipo puede instalar supervisión al mismo tiempo que instalar Skype para Business Server 2015. Si no tiene un equipo de back-end preparado puede proceder a instalar Skype para Business Server 2015 por sí mismo luego instalar la supervisión cada vez que el equipo back-end está listo para su uso.
  
 **¿Cuántos back-end monitoreo de bases de datos necesita?** Se estimaba que una base de datos colocada para monitoreo y archiving podría admitir 240.000 Skype para los usuarios de Business Server 2015). Además, puede utilizarse una única base de datos de supervisión por varios grupos de servidores de Front-End; Si tiene tres grupos de Front-End de la organización se podían asociar los tres de esos grupos con el mismo almacén de back-end.
  
Para muchas organizaciones, la capacidad de la base de datos no será el factor determinante a la hora de establecer la cantidad de bases de datos de supervisión back-end que se necesitarán. En su lugar, es posible que se dé más importancia a la velocidad de red. Supongamos que tiene tres grupos de servidores front-end, pero uno de estos grupos de servidores se encuentra en una conexión de red lenta. En ese caso, puede que desee tener dos bases de datos de supervisión: una base de datos para los dos grupos de servidores con la conexión de red buena y otra base de datos para el grupo de servidores con la conexión de red más lenta.
  
También debe tener en cuenta que Skype para el año 2015 de Business Server admite el uso de bases de datos de reflejo. La creación de reflejo de la base de datos es una forma de mantener al mismo tiempo dos copias de una base de datos, cada una de ellas en un servidor diferente. Cada vez que se escriben datos en la base de datos principal, esos mismos datos se escriben en la base de datos reflejada. Si la base de datos principal debe fallar o dejan de estar disponible en caso contrario, puede "conmutar" a la base de datos reflejada utilizando un simple Skype Business Server 2015 PowerShell comando. Por ejemplo:
  
```
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

En términos de planeación, esto es importante, ya que será necesario duplicar la cantidad de bases de datos necesarias, ya que, aparte de cada base de datos principal, necesitará otra base de datos que haga de reflejo.
  
 **¿Su Skype para Business Server 2015 sitios necesitan sus propias configuraciones personalizadas de supervisión?** Al instalar Skype para Business Server 2015 también instalar colecciones globales de configuración de CDR y calidad; Estas colecciones globales le permiten aplicar la misma configuración de CDR y calidad de la experiencia a toda la organización. En muchos casos, será suficiente:-a menudo va a necesitar, digamos, tener CDR supervisión habilitada para todos los usuarios.
  
En cambio, en ocasiones querrá aplicar otras configuraciones en sitios diferentes. Por ejemplo, quizás quiera usar la supervisión de CDR y QoE en el sitio de Redmond, pero desee usar solo la supervisión de CDR en el sitio de Dublín. Igualmente, es posible que quiera conservar los datos de supervisión durante 60 días en el sitio de Redmond, y mantener ese mismo tipo de datos durante 30 días en el sitio de Dublín. Skype para el año 2015 de Business Server le permite crear colecciones separadas de los valores de configuración de CDR y calidad de la experiencia en el ámbito del sitio; que le permite administrar cada sitio de forma diferente. De esta forma, podrá administrar cada sitio de forma diferente (esto incluye la habilitación y la deshabilitación de la supervisión, así como también la configuración de las opciones de administración como, por ejemplo, cuánto tiempo se retendrán los datos).
  
Puede tomar esta decisión antes o después de implementar la supervisión. Por ejemplo, implemente la supervisión y administre toda la organización con la configuración global. Si más tarde cambia de opinión, cree una colección de opciones independiente para, por ejemplo, el sitio de Redmond y después use esta configuración para administrar la supervisión de Redmond. (La configuración aplicada en el ámbito de sitio siempre tiene preferencia sobre la configuración aplicada en el ámbito global). Si vuelve a cambiar de opinión, solo tiene que eliminar las opciones de configuración aplicadas al sitio de Redmond. Cuando se elimina una colección de opciones de configuración de un sitio, se aplica automáticamente la colección global de configuración al sitio.
  
## <a name="sql-requirements-for-monitoring"></a>Requisitos de SQL para la supervisión
<a name="topologies"> </a>

Cuando se habilita la supervisión, se instalan y activan automáticamente en cada servidor los agentes de recopilación de datos unificados. Tendrá que instalar y configurar una de las siguientes bases de datos para que actúe como almacén de datos back-end para los datos de la supervisión.
  
- Microsoft SQL Server 2008 R2 Enterprise Edition (edición de 64 bits)
    
- Microsoft SQL Server 2008 R2 Standard Edition (edición de 64 bits)
    
- Microsoft SQL Server 2012 Enterprise Edition (edición de 64 bits)
    
- Microsoft SQL Server 2012 Standard Edition (edición de 64 bits)
    
- Microsoft SQL Server 2014 Enterprise Edition (edición de 64 bits)
    
- Microsoft SQL Server 2014 Standard Edition (edición de 64 bits)
    
Las versiones de 32 bits de SQL Server no se pueden usar como almacén back-end. Skype para el año 2015 de Business Server no admite la Express ediciones de SQL Server 2008 o SQL Server 2012. Para obtener más información sobre los requisitos de la base de datos de Skype para Business Server 2015, vea el tema [Compatibilidad con Software de base de datos](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx).
  
Al supervisar los datos se puede compartir una instancia de SQL Server con otros tipos de datos. Generalmente, las bases de datos del registro detallado de llamadas (LcsCdr) y de la calidad de la experiencia (QoEMetrics) comparten la misma instancia de SQL. También es habitual que las dos bases de datos de supervisión se encuentren en la misma instancia de SQL que la base de datos de archivado (LcsLog). El único requisito real con relación a las instancias de SQL Server es que cada una de ellas se limite conforme a lo siguiente:
  
- Una instancia de la Skype para base de datos de back-end de Business Server 2015. Como norma general, no recomendamos que la base de datos de supervisión se encuentre en la misma instancia de SQL, ni siquiera en el mismo equipo, que la base de datos back-end. Aunque técnicamente es posible, corre el riesgo de que la base de datos de supervisión agote el espacio en disco que necesita la base de datos back-end. 
    
- Una instancia de la base de datos del registro detallado de llamadas.
    
- Una instancia de la base de datos de la calidad de la experiencia.
    
- Una instancia de la base de datos de archivado.
    
En otras palabras, no puede tener dos instancias de la base de datos LcsCdr en la misma instancia de SQL Server. Si necesita varias instancias de la base de datos LcsCdr, tendrá que configurar varias instancias de SQL Server.
  
## <a name="see-also"></a>Vea también
<a name="topologies"> </a>

#### 

[Implementación de la supervisión](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)


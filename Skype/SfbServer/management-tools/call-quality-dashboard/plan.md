---
title: Plan de panel de calidad de llamadas para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Resumen: Obtenga información sobre qué hay que tener en cuenta al planear el panel de calidad de llamadas.'
ms.openlocfilehash: c98828f8fed3567a892e20dcab8040bb731c91f2
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328442"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Plan de panel de calidad de llamadas para Skype empresarial Server 
 
**Resumen:** Más información sobre lo que hay que tener en cuenta al planear el panel de calidad de llamadas.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Información general del panel de calidad de llamadas de Skype empresarial Server

El panel de calidad de llamadas de Skype empresarial Server (CQD) es un nivel de informes que se encuentra en la parte superior de la base de datos de la calidad de la experiencia en el servidor de supervisión de Skype empresarial Server. El CQD usa Microsoft SQL Server Analysis Services para proporcionar información sobre la calidad de las llamadas y el uso agregado, así como para filtrar y dinamizar en el conjunto de datos. Entre las características del CQD se incluyen:
  
- **Almacenamiento de archivos de los datos de la calidad de la calidad mediante el componente de archivo QoE de CQD.** El componente de archivo QoE puede almacenar los datos de la calidad de la calidad durante mucho más tiempo que el servidor de supervisión. Esto permite la creación de tendencias y los informes de hasta siete meses de datos a la vez, con la capacidad de deslizar la ventana de informes hasta atrás, ya que hay datos.
- **Informes y análisis con la potencia y la velocidad de Microsoft SQL Server Analysis Services.** El CQD usa Microsoft SQL Analysis Services para proporcionar capacidades de Resumen, filtrado y dinamización rápidas para potenciar el panel a través de un cubo de análisis. La velocidad de ejecución de informes y la capacidad de profundizar en los datos puede reducir drásticamente el tiempo de análisis.
- **Nuevo esquema de datos optimizado para informes de calidad de las llamadas.** El cubo tiene un esquema diseñado para la creación de informes e investigaciones de calidad de voz. Los usuarios del portal pueden centrarse en las tareas de informes en lugar de averiguar cómo el esquema de base de datos de la calidad de la QoE se asigna a las vistas que necesitan. La combinación del archivo QoE y el cubo ofrece una abstracción que reduce la complejidad de la creación de informes y análisis a través del CQD. El esquema de la base de datos del archivo de calidad de la calidad también contiene tablas que se pueden rellenar con datos específicos de la implementación para mejorar el valor general de los datos.
- **El diseñador de informes integrado y la edición de informes en contexto.** El componente de portal viene con varios informes integrados modelados después de la metodología de calidad de las llamadas. Los usuarios del portal pueden modificar los informes y crear nuevos informes a través de la funcionalidad de edición del portal.
- **Acceso a la API Web para la estructura del informe y los datos del cubo de análisis.** El marco de informes de paneles no es la única forma de mostrar los datos del cubo. El CQD proporciona varios ejemplos de uso de HTML y JavaScript para recuperar datos de las API Web de CQD y representar los datos en un formato personalizado. La combinación del editor de informes y las API Web de CQD permiten el prototipo rápido de informes y el diseño personalizado de informes.

> [!NOTE]
> Un administrador puede administrar ahora Skype empresarial Server 2019 con el [CQD versión 3](https://cqd.teams.microsoft.com) (iniciar sesión con credenciales de administrador). Esto requiere una implementación híbrida y el uso del conector de datos de llamada (CDC). Consulte [plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) para obtener más información sobre cómo habilitar CDC. Para obtener la documentación de la versión 3 del CQD, consulte [activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype empresarial online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) para obtener más información sobre la versión 3 del CQD.

## <a name="cqd-design-goals"></a>Objetivos del diseño del CQD

El panel de calidad de llamadas permite a los profesionales de TI usar datos de agregados para identificar áreas en su entorno que estén experimentando problemas en la calidad de los medios. También les permite comparar estadísticas de diferentes grupos de usuarios, e identificar tendencias y patrones. No se centra en la solución de problemas con llamadas individuales, sino en la identificación de problemas y soluciones aplicables a muchos usuarios dentro de un entorno. 
  
## <a name="call-quality-dashboard-components"></a>Componentes del panel de calidad de llamadas

El panel de calidad de llamadas consta de varias bases de datos, trabajos de Microsoft SQL Agent, procesos y aplicaciones Web. Los trabajos del agente de Microsoft SQL periódicamente copian datos de la base de datos QoE Metrics a la base de datos de archivo de la calidad de archivo y procesa el cubo con los datos de la base de datos de archivo de calidad. La base de datos del depósito almacena las definiciones de los informes que encienden el portal. El portal proporciona acceso a los datos del cubo por explorador. 
  
Los componentes CQD, incluidas las bases de datos de archivo, cubo y repositorio de la calidad, se pueden instalar en el servidor de supervisión, instalarse en su propio servidor o instalarse en varios servidores. El método de instalación en particular depende de las demandas de rendimiento del CQD, así como del impacto en otros procesos en los mismos servidores. Para obtener más información, consulte la sección "componentes y topologías de CQD", más adelante en este artículo.
  
### <a name="architectural-overview"></a>Información general de la arquitectura

En Resumen, el CQD necesita los siguientes elementos:
  
- Dos bases de datos: una base de datos de archivo y una base de datos del depósito.
    
- Un cubo SSAS visualizar datos agregados 
    
- IIS hospeda el portal web de CQD
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La misma arquitectura de CQD es compatible con Lync Server 2013 y Skype empresarial. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD y Skype empresarial frente a Lync 2013

 En un entorno de Skype empresarial solamente, están disponibles las siguientes funciones:
  
- Informes de Wi-Fi sobre la intensidad de la señal
    
- Informes de los chipsets Wi-Fi
    
- Clasificar mis datos de llamadas 
    
## <a name="information-available-through-cqd"></a>Información disponible por el CQD

El CQD puede mostrar el recuento de transmisiones de audio, vídeo y uso compartido de aplicaciones de Skype empresarial Server y el recuento de llamadas buenas frente a las incorrectas, así como las proporciones de buenas llamadas. Las vistas se pueden segmentar y filtrar por muchas dimensiones diferentes. El CQD extrae los datos de la base de datos de la QoE Metrics en el servidor de supervisión. A continuación, los datos se fusionan con los datos proporcionados por el cliente, como la asignación de subred a edificio para que los informes, como "calidad de las llamadas por construcción", sean posibles. 
  
El CQD también abstrae muchas de las idiosincrasias de los datos de los QoE internos, como "llama" y "llama", de modo que el usuario puede centrarse en crear vistas informes en función de "servidor" y "cliente". Siguiendo la metodología de la calidad de las llamadas, el CQD se ha simplificado para ayudar a identificar las condiciones de las llamadas inadecuadas en común, uno de los principios para mejorar la calidad de las llamadas.
  
## <a name="viewing-data-in-cqd"></a>Visualización de datos en el CQD

Los datos del CQD pueden visualizarse a través del portal de CQD y acceder a ellos a través de llamadas de API de REST.
  
### <a name="cqd-portal"></a>Portal de CQD

El portal es la manera más rápida de ver los datos del cubo. El portal incluye varios informes incorporados que se pueden usar de inmediato. Los informes integrados están vinculados de forma estructurada para guiar al usuario en segmentos sucesivos más pequeños y pequeños de los datos de la llamada. Los informes integrados también resaltan las diferentes maneras en que se pueden mostrar los datos mediante la demostración de una combinación de gráficos y tablas con diferentes tablas dinámicas, filtros y medidas. Cada usuario que tiene acceso al portal puede tener su propio conjunto de informes que puede modificar y compartir. Para obtener más información sobre el uso del portal web de CQD, consulte [usar el panel de calidad de llamadas para Skype empresarial Server](use.md).
  
Sistemas operativos compatibles con el portal de CQD: Windows 8,1, Windows 8, Windows Server 2012 R2, Windows Server 2012 y Windows Server 2016 (solo para el CQD de Skype empresarial 2019 Server).
  
Exploradores admitidos para el portal de CQD: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>API de REST

También se puede acceder a los datos del cubo a través de llamadas API de REST. Los datos que se recuperan a través de las llamadas API de REST se pueden representar mediante páginas HTML. Los usuarios pueden aprovechar la velocidad de la consulta y el esquema de nivel alto del CQD mientras crean informes personalizados adaptados a las necesidades de su empresa. Para obtener más información sobre la API y los ejemplos, consulte [desarrollar el panel de calidad de llamadas para Skype empresarial Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definir los requisitos de la organización para el CQD

El CQD proporciona el archivado de datos de QoE y un análisis rápido y exhaustivo de los datos de calidad de las llamadas. La siguiente guía le ayuda a decidir cuándo y por qué implementar el CQD.
  
### <a name="when-to-deploy-cqd"></a>Cuándo implementar el CQD

 **El CQD puede implementarse para establecer una medida de calidad de llamada de línea base, incluso si una organización no experimenta problemas de calidad de las llamadas.** Establecer una medición de la calidad de una llamada base es importante porque todas las organizaciones tienen una combinación diferente de Wi-Fi en comparación con redes cableadas y remotas en comparación con trabajadores de oficina. Cuando se producen problemas con la calidad de las llamadas, las medidas de calidad de llamadas más recientes se pueden comparar con intervalos de tiempo anteriores. Las características de tendencias del CQD permiten detectar fácilmente los cambios en la calidad de las llamadas a lo largo del tiempo.
  
 **El CQD puede implementarse para encontrar de manera proactiva las áreas problemáticas que pueden afectar la calidad de las llamadas.** Incluso si la calidad media de las llamadas de una organización puede cumplir los objetivos establecidos por la organización, puede haber bolsillos problemas de calidad de llamadas que se hayan ocultado detrás del promedio de métricas. El CQD permite el desglose de la calidad de las llamadas en tablas dinámicas con muchas dimensiones en la base de datos QoEMetrics. La detección de valores atípicos en grupos de iguales es una forma rápida de encontrar problemas de calidad de las llamadas.
  
 **El CQD debe implementarse si hay problemas de calidad de las llamadas en la organización para reducir el tiempo necesario para solucionar problemas.** El CQD puede simplificar las investigaciones existentes de calidad de las llamadas al ofrecer un rápido rendimiento de creación de informes y capacidades de desglose dinámica. El CQD está diseñado para muchos tipos de flujos de trabajo en investigaciones de calidad de llamadas validación de reparaciones en el entorno.
  
### <a name="why-deploy-cqd"></a>Por qué implementar el CQD

 **El CQD debe implementarse si es necesario que los informes de hipótesis se realicen durante más de 3 meses de datos.** Los informes del servidor de supervisión y la base de datos de QoEMetrics están diseñados para retener y denunciar un pequeño conjunto de datos. La base de datos de la calidad de la QoE está optimizada para las inserciones rápidas y, por lo tanto, el rendimiento de la creación de informes de llamadas o de creación de informes de competir con la base de datos. La base de datos de archivos de calidad de la calidad del CQD brinda una segunda copia de los datos de la calidad de la QoE con capacidades de retención mucho más prolongadas. El portal también está optimizado para mostrar hasta 7 meses de datos a la vez y puede informar sobre todos los datos en el archivo de la calidad de la calidad según sea necesario.
  
 **El CQD debe implementarse si se necesitan informes de QoE personalizados.** El portal tiene una característica de editor de informes para crear y crear prototipos de informes de forma rápida y sencilla. También hace que las API de REST disponibles accedan mediante programación a los datos del cubo, lo que permite una presentación personalizada con HTML/JavaScript o muchos otros marcos. Ya no es necesario crear consultas SQL nuevas con el propósito de crear vistas de datos personalizadas para informes.
  
 **El CQD debe implementarse si la funcionalidad de reporting de QoE existente no cumple con la velocidad o profundidad requerida por la organización.** El CQD viene con muchos informes incorporados. Los informes son útiles inmediatamente y demuestran cómo llegar a los datos progresivamente puede ofrecer más información en cada nivel. La jerarquía de informes también ayuda a administrar los numerosos informes de forma lógica y fomenta la creación de muchos más informes que son fácilmente accesibles y comprensibles. El CQD no solo ofrece velocidad y flexibilidad, sino que también está optimizado para los flujos de trabajo desarrollados por la metodología de calidad de las llamadas.
  
## <a name="components-and-topologies-for-cqd"></a>Componentes y topologías del CQD

El CQD viene con varios componentes, y es útil comprender los requisitos de cada componente y su relación mutua para obtener la implementación más simple y de mejor rendimiento de la herramienta. En la siguiente tabla se describe el componente dependiente de cada componente de CQD.
  

|**Nombre del componente**|**Componente dependiente**|
|:-----|:-----|
|Archivo de QoE  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Servicios de información de Microsoft  <br/> |
|Servicio de repositorio (parte de la instalación del portal)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Para el archivo y el cubo de QoE, ciertas opciones de implementación requieren inteligencia empresarial o ediciones empresariales de Microsoft SQL Server. Para obtener más información, consulta la sección [requisitos de infraestructura de CQD](plan.md#Infrastructure_Req) a continuación.
  
![Componentes de CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuración de servidor único

Todos los componentes del CQD y los componentes dependientes se pueden instalar en un equipo. La configuración de un solo cuadro es la configuración más sencilla y permite que el CQD sea independiente. El CQD solo necesitaría acceder a la base de datos de la calidad de la calidad de la QoE en el servidor de supervisión. El servidor CQD puede ser un equipo independiente, una máquina virtual o incluso el servidor de supervisión, en función de los recursos disponibles de la máquina host y los requisitos de rendimiento. 
  
Durante la instalación, el usuario que realiza la instalación simplemente necesita proporcionar las instancias de Microsoft SQL Server y Microsoft SQL Server Analysis Services que se han configurado previamente en el equipo en el que se va a instalar el CQD. Para obtener más información, consulte [implementar el panel de calidad de llamadas de Skype empresarial Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configuración de multiservidor

En una configuración multiservidor, el archivo, el cubo y el portal de la calidad de la calidad pueden estar en diferentes equipos. Hay dos usos principales para la configuración multiservidor:
  
- Hospedar el portal web de CQD y el cubo CQD en servidores diferentes.
    
- Alojamiento de un portal de "desarrollo" independiente del portal de "producción". 
    
  **Hospedar el portal web de CQD y el cubo CQD en máquinas diferentes.** Las organizaciones que pueden tener requisitos para separar el portal de CQD de la instalación de SQL Server o que tal vez deseen combinar y comparar las ediciones de SQL Server para la instancia de SQL Server y la instancia de SQL Server Analysis Services pueden optar por instalar el portal de CQD y Cubo CQD en máquinas diferentes. El componente de archivo QoE también puede ser el único componente CQD instalado, si la organización simplemente desea tener un método sostenible para archivar los datos de la calidad de la calidad, sin alcanzar los límites de performance en el servidor de monitoreo.
  
![CQD de un único servidor](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Alojamiento de un portal de "desarrollo" independiente del portal de "producción".** Es posible que las organizaciones que desarrollan sus propios informes personalizados (a través de las API de REST) prefieran implementar instancias de portal adicionales junto al portal de producción a las que los usuarios habituales tienen acceso para realizar una evaluación o investigación de la calidad de las llamadas. El portal de desarrollo puede aislar las modificaciones en el portal del entorno de producción. Los portales web adicionales se pueden implementar en diferentes equipos (que se muestran a continuación) o implementar en diferentes directorios web de la misma máquina (no se muestra). Para ello, el portal web adicional de CQD debe copiarse manualmente en el equipo de producción porque el proceso de configuración del CQD siempre implementa el portal web del CQD en el sitio web predeterminado con nombres de aplicaciones Web predefinidos.
  
![Planificar varios servidores de CQD](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologías compatibles

El CQD no combina datos de varias bases de datos de QoEMetrics, como es el caso de que haya varias topologías de Skype empresarial Server, cada una con su propio servidor de supervisión. Cada instancia de CQD debe apuntar a una base de datos QoEMetrics. Sin embargo, dado que el CQD va a mover la mayor parte de la carga de trabajo de los informes del servidor de supervisión, las organizaciones grandes que necesitaban implementar un servidor de supervisión por topología de servidor de Skype empresarial deberían considerar el uso de un servidor de supervisión para todas las topologías.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisitos de infraestructura para el CQD
<a name="Infrastructure_Req"> </a>

El CQD, incluidos todos sus componentes y componentes dependientes, se puede implementar en una máquina virtual, en un solo equipo o en varios equipos. A continuación se enumeran los requisitos mínimos de software y hardware. La disponibilidad de los datos y el rendimiento de las consultas pueden variar de minutos a horas, según el número de usuarios y el hardware y la configuración activos de Skype empresarial, por lo que se proporcionan algunas medidas de rendimiento a continuación.
  
|||
|:-----|:-----|
|Para el CQD 2015 <br/> |  <br/> |
|Sistemas operativos compatibles  <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|SQL Server compatible  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Para el CQD 2019 <br/> |  <br/> |
|Sistemas operativos compatibles  <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|SQL Server compatible  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
El CQD usa Microsoft SQL Server, Microsoft SQL Server Analysis Services y Microsoft Internet Information Services, de modo que los requisitos mínimos de hardware y software del CQD son básicamente los mismos que los componentes dependientes. Sin embargo, en función de los requisitos de la organización sobre la actualización de los datos (que dependerá en parte del volumen de datos de QoE que genera la organización) y el costo de implementación, hay consideraciones adicionales de implementación.
  
El procesamiento de datos en el CQD se divide en dos etapas principales: 
  
- Proceso de archiving de QoE
    
- Procesamiento del cubo CQD
    
  **Procesamiento de archivo de QoE.** La tarea de procesamiento de archiving de QoE copia los datos de la base de datos de QoE Metrics del servidor de monitoreo a la base de datos de archivo de calidad. Hay dos situaciones en las que el tiempo de procesamiento de la tarea tendría características de rendimiento fundamentalmente diferentes. El primero es después de la instalación inicial del CQD. Cuando la tarea se ejecuta por primera vez después de una nueva instalación, la tarea de procesamiento de archiving de QoE copiará todos los datos que se encuentran en la base de datos de la calidad de la QoE en la base de datos de archivos de QoE. El segundo es el procesamiento periódico después de este redondeo inicial. La tarea de procesamiento de archiving de QoE se ejecutará cada 15 minutos y procesará los nuevos registros de calidad de la calidad que se encuentren en la base de datos de la calidad de la QoE. Por lo general, el tiempo de procesamiento inicial no es preocupante porque se ejecuta solo la primera vez, cuando está instalado el CQD. Sin embargo, si el servidor CQD tiene muy pocos problemas, esta tarea puede demorar varias horas. Consulte la tabla siguiente para obtener ejemplos iniciales de procesamiento de archivos de QoE.
  
  **Procesamiento del cubo CQD.** La tarea de procesamiento del cubo agrega los datos de la base de datos de archivo de calidad de archivo al cubo. El tiempo de procesamiento inicial del cubo y el tiempo de procesamiento del cubo posterior se determinan mediante la edición SQL Server Analysis Services usada para el cubo CQD. Si se usa la edición estándar, no hay diferencia entre el tiempo de procesamiento del cubo inicial y el tiempo de procesamiento del cubo subsiguiente porque cada vez que se actualizan los datos del cubo, siempre será un procesamiento completo de todos los datos disponibles. (Esto significa que el tiempo de procesamiento del cubo aumenta a medida que aumenta la cantidad de datos en la base de datos de archivo de QoE). Como Business Intelligence Edition y Enterprise Edition de SQL Server tienen compatibilidad con las particiones, si se usa cualquiera de las dos ediciones, solo la ejecución inicial procesará todos los datos de la base de datos de archivo de calidad. En ejecuciones posteriores, cuando la tarea se desencadena cada 15 minutos, la tarea solo procesará los nuevos registros agregados a la base de datos de archivo de calidad de archivo desde la última vez que se ejecutó la tarea. Una vez al día, también habrá un procesamiento completo en la partición que contiene los datos del mes en curso.
  
Las características de la máquina física pueden afectar al rendimiento del CQD, así como a las características de software que están disponibles en los componentes de SQL Server. El componente de archivo de calidad de servicio será más intensivo en comparación con otros componentes, mientras que el componente de cubo tendrá más CPU y mucha memoria. Todos estos factores contribuyen al tiempo total de procesamiento de datos del CQD, que afecta directamente a la actualización y disponibilidad de los datos. Las organizaciones deben tomar decisiones sobre el hardware y el software según las necesidades individuales de la organización. 
  
### <a name="tested-hardware-configurations"></a>Configuraciones de hardware probadas

En esta sección se supone que hay una sola base de QoEMetrics en el entorno. 
  
**Perfiles de equipo**

|**Equipo**|**Núcleos de la CPU**|**MEMORIAS**|**Archivo de QoE y cubo en el mismo disco**|**Archivo de QoE y base de datos Temp SQL en el mismo disco**|
|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |4  <br/> |7 GB  <br/> |Sí  <br/> |Sí  <br/> |
|4 núcleos  <br/> |4  <br/> |20 GB  <br/> |Sí  <br/> |No  <br/> |
|8 núcleos  <br/> |4,8  <br/> |32 GB  <br/> |Sí  <br/> |No  <br/> |
|16 núcleos  <br/> |apartado  <br/> |128 GB  <br/> |No  <br/> |No  <br/> |
   
**Resultados de rendimiento**

|**Equipo**|**Tamaño de BD de los indicadores QoE**|**Particiones SQL**|**Tipo de disco**|**Número de transmisiones**|**Proceso inicial de archivo**|**Proceso de cubo inicial**|**Proceso de archivo posterior**|**Proceso de cubo subsiguiente**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |900 MB  <br/> |Individual  <br/> |VHD (tamaño variable)  <br/> |0,5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Individual  <br/> |VHD (tamaño variable)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Individual  <br/> |VHD (tamaño fijo)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |MÁS DE 30 GB  <br/> |Individual  <br/> |VHD (tamaño fijo)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Individual  <br/> |Varios discos  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Multiple  <br/> |Varios discos  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 núcleos  <br/> |MÁS DE 30 GB  <br/> |Individual  <br/> |Varios discos  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 núcleos  <br/> |MÁS DE 30 GB  <br/> |Multiple  <br/> |Varios discos  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 núcleos  <br/> |200 GB  <br/> |Individual  <br/> |Varios discos  <br/> |125 M  <br/> |6 + días  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 núcleos  <br/> |500 GB  <br/> |Multiple  <br/> |Varios ejes  <br/> |250 M  <br/> |8 días  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*No se espera que se encuentren en implementaciones reales, ya que la base de datos de la calidad de la calidad de la QoE necesita tener 9 y 18 meses de datos, respectivamente, pero se proporcionan aquí para su integridad.
  
### <a name="service-account-requirements"></a>Requisitos de la cuenta de servicio

Necesitará una cuenta (con acceso de lectura a QoEMetrics) que el Agente SQL en el servidor CQD pueda usar para importar datos a la QoEArchiveDB.
  
Es posible que también tenga que configurar una cuenta independiente para que un trabajo de SSAS Extraiga datos de QoEArchiveDB (este es un proceso opcional).
  
Normalmente, IIS usa el servicio de red como identidad del grupo de aplicaciones, pero se puede configurar para una cuenta de servicio.
  
### <a name="portal-access-control"></a>Control de acceso al portal

De forma predeterminada, cualquier usuario autenticado tiene acceso. Esto se puede cambiar mediante el uso de reglas de autorización de IIS para restringir a un grupo específico.
  
### <a name="pre-install-requirements"></a>Requisitos previos a la instalación

En estas instrucciones se supone que ya se ha instalado una base de datos de QoE Metrics y que se está ejecutando en algún lugar de la topología de Skype empresarial Server.
  
#### <a name="hardware-requirements"></a>Requisitos de hardware

El CQD usa Microsoft SQL Server, Microsoft SQL Analysis Server y Microsoft Internet Information Server, de modo que los requisitos mínimos de hardware y software del CQD son básicamente los mismos que los componentes dependientes. Sin embargo, en función de los requisitos de la organización sobre la actualización de los datos (que dependerá en parte del volumen de datos de QoE que genera la organización) y el costo de implementación, hay consideraciones adicionales de implementación.
  
#### <a name="software-requirements"></a>Requisitos de software

Los siguientes sistemas operativos son necesarios para el CQD:
  
- Windows Server 2008 R2 con IIS 7,5
    
- Windows Server 2012 con IIS 8,0
    
- Windows Server 2012 R2 con IIS 8,5

- Windows Server 2016 con IIS 10,0 (solo para el CQD de Skype empresarial Server 2019)

- Windows Server 2019 (solo para el CQD de Skype empresarial Server 2019)
    
A continuación se indican los servicios de rol de IIS requeridos (en orden jerárquico):
  
- Servidor Web
    
  - Características HTTP comunes
    
  - Contenido estático
    
  - Documento predeterminado
    
  - Desarrollo de aplicaciones
    
  - ASP.NET
    
  - Filtros ISAPI
    
  - Diagnóstico &amp; de estado
    
  - Registro HTTP
    
  - Seguridad
    
  - Autorización de URL
    
  - Autenticación de Windows
    
  - Herramientas de administración
    
  - Consola de administración de IIS
    
> [!NOTE]
>  Tenga en cuenta lo siguiente para los requisitos mencionados: > 3,5 y 4,5 están disponibles las versiones de .NET Framework. Ambos son obligatorios (se necesita más específicamente, 3,5 SP1). > en algunos sistemas, si ASP.NET se configura antes de la instalación de IIS, es posible que ASP.NET no esté registrado en IIS. El problema se manifiesta en la ausencia de grupos de aplicaciones para la versión de .net correspondiente y, además, no se encuentra la versión de .NET CLR en la configuración de la agrupación de aplicaciones. Para corregir este problema en Windows Server 2008 R2, ejecute `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. En Windows Server 2012 y Windows Server 2012 R2, ejecútelo `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` y, después, quite el módulo "ServiceModel" del sitio web predeterminado en el administrador de IIS. las herramientas de administración de > son opcionales, pero se recomiendan.
  
Para instalar estos requisitos con PowerShell, ejecute lo siguiente:
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Se admiten las siguientes versiones de SQL Server:
  
- SQL Server 2012
    
- SQL Server 2014

- 2016 de SQL Server

- 2017 de SQL Server

- SQL Server 2019 (solo para el CQD de Skype empresarial Server 2019)
    
Se recomienda usar Business Intelligence o Enterprise Edition por razones de rendimiento. Estas ediciones permiten el uso de varios archivos de partición que se pueden procesar en paralelo, lo cual resulta ventajoso para procesar datos que abarcan varios meses o más. 
  
Aunque no se recomienda, la versión Standard Edition también es compatible. El procesamiento se limitará a una única partición (que debe configurarse durante la instalación). 
  
En todos los casos, debe instalarse "servicios de motor de base de datos" y "Analysis Services". Se recomienda, pero no es necesario, instalar también la característica "herramientas de Administración-completada", que agrega compatibilidad con SQL Server Management Studio para Analysis Services. La pantalla de selección de características debería tener un aspecto similar al de la ilustración.
  
![Requisitos de la característica de SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Al configurar la configuración de SSAS, en la configuración de Analysis Services, establezca "modo de servidor" en "modo de minería de datos y multidimensional". 
  
Para obtener más ayuda para instalar y configurar las características de inteligencia empresarial de SQL Server, consulte [instalar Analysis Services en modo multidimensional y de minería de datos](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Requisitos de la cuenta

Se recomiendan tres cuentas de servicio de dominio en el principio de privilegios mínimos: 
  
- Uno que ya tiene tanto un principio de seguridad de inicio de sesión para la base de datos de QoE Metrics (con el privilegio db_datareader) y un principio de seguridad de inicio de sesión en la instancia de archivo de SQL Server de QoE (necesario para crear un objeto de servidor vinculado durante la instalación). Esta cuenta se usará para ejecutar el paso "datos del archivo QoE" del trabajo del Agente SQL Server.
    
- Una que se usará para ejecutar el paso "procesar cubo" del trabajo del Agente SQL Server. El programa de instalación creará una entidad de seguridad de inicio de sesión para la base de datos de archivos de alta definición (con privilegio de lectura y escritura) y también crea un miembro en el rol de QoE (con privilegio de control total) para el cubo.
    
- Una que se usará para ejecutar el proceso de trabajo de IIS para los portales web y las API Web. El programa de instalación creará un principal de seguridad de inicio de sesión para la base de datos de archivos de alta definición (con privilegio de lectura), un principal de seguridad de inicio de sesión en la base de datos del repositorio (con privilegio de lectura y escritura) y un miembro de QoERole (con privilegio de control total) para el cubo. 
    
    > [!NOTE]
    > Cuando se hospedan en el mismo SQL Server una base de datos de archivo de calidad y la base de datos del repositorio, solo se crea una entidad principal de seguridad de inicio de sesión con dos asignaciones de usuario. 
  
Las dos primeras cuentas se pueden considerar lógicamente como "cuentas de servicio de back-end" y la última cuenta es una "cuenta de servicio front-end". Aunque no se recomienda, es posible usar una sola cuenta en todos los casos.
  
> [!NOTE]
> La cuenta de usuario que inicia la instalación también debe tener acceso de lectura a la BD de la métrica de QoE (además de contar con derechos de administrador de equipo en el servidor de bases de datos de archivo de QoE, donde debe tener lugar la instalación). 
  
## <a name="capacity-planning"></a>Planificación de capacidad
<a name="Infrastructure_Req"> </a>

El CQD está diseñado para un impacto mínimo en QoEMetrics: el código se ha optimizado para no bloquear datos y los trabajos de importación se pueden ajustar.
  
El tipo de hardware que se usará depende de los requisitos para la forma en que se deben ejecutar sincronizaciones rápidamente. El tamaño del disco es el siguiente:
  
- QoEArchive es ~ 1,5 x mayor que QoEMetrics DB al principio
    
- El cubo SSIS comprime los datos casi en comparación con la base de datos
    
- Los datos se dividen mensualmente; las particiones se pueden eliminar
    


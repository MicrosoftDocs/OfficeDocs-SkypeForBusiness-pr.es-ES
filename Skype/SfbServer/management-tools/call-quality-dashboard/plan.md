---
title: Planeación del panel de calidad de llamadas para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Resumen: Obtenga información sobre qué se debe tener en cuenta al planear el panel de calidad de llamadas.'
ms.openlocfilehash: 63b69d64624d13253badf1d3e6f44535afdc0993
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339445"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planeación del panel de calidad de llamadas para Skype empresarial Server 
 
**Resumen:** Obtenga información sobre qué tiene que tener en cuenta al planear el panel de calidad de llamadas.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Información general sobre el panel de calidad de llamadas de Skype empresarial Server

El panel de calidad de llamadas de Skype empresarial Server (CQD) es un nivel de informes que se encuentra en la parte superior de la base de datos de calidad de la experiencia en el servidor de supervisión en Skype empresarial Server. El CQD usa Microsoft SQL Server Analysis Services para proporcionar información sobre el uso agregado y la calidad de las llamadas, así como para filtrar y dinamizar en el conjunto de datos. Entre las características del CQD se incluyen:
  
- **Almacenamiento de archivado de los datos de QoE a través del componente de archivo de QoE del CQD.** El componente de archivo de QoE puede almacenar los datos de QoE durante un período de tiempo mucho mayor que el que puede hacerlo el servidor de supervisión. Esto permite la creación de tendencias y la generación de informes de hasta siete meses de datos a la vez, con la capacidad de deslizar la ventana de informes hasta el final de los datos.
- **Informes y análisis mediante la potencia y la velocidad de Microsoft SQL Server Analysis Services.** El CQD usa Microsoft SQL Analysis Services para proporcionar capacidades de Resumen, filtro y tablas dinámicas para poder alimentar el panel a través de un cubo de análisis. La velocidad de ejecución del informe y la capacidad de profundizar en los datos puede reducir drásticamente el tiempo de análisis.
- **Nuevo esquema de datos optimizado para informes de calidad de llamadas.** El cubo tiene un esquema diseñado para las investigaciones e informes de calidad de voz. Los usuarios del portal pueden centrarse en las tareas de informes en lugar de saber cómo el esquema de base de datos de calidad de la QoE se asigna a las vistas que necesitan. La combinación del archivo de QoE y el cubo ofrece una abstracción que reduce la complejidad de los informes y análisis a través del CQD. El esquema de la base de datos de archivo de QoE también contiene tablas que se pueden rellenar con datos específicos de la implementación para mejorar el valor general de los datos.
- **Diseñador de informes integrado y edición de informes en el tiempo.** El componente del portal incluye varios informes integrados que se basan en la metodología de calidad de la llamada. Los usuarios del portal pueden modificar los informes y crear nuevos informes mediante la funcionalidad de edición del portal.
- **Acceso a la API Web a la estructura del informe y a los datos del cubo de análisis.** El marco de informes del panel no es la única forma de mostrar los datos del cubo. El CQD proporciona varios ejemplos de cómo usar HTML y JavaScript para recuperar datos de las API Web Web del CQD y representar los datos en un formato personalizado. La combinación del editor de informes y las API Web de CQD permite un prototipo rápido de informes y el diseño de informes personalizados.

> [!NOTE]
> Ahora, un administrador puede administrar Skype empresarial Server 2019 con el [CQD versión 3](https://cqd.teams.microsoft.com) (iniciar sesión con credenciales de administrador). Esto requiere una implementación híbrida y el uso del conector de datos de llamada (CDC). Consulte [plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) para obtener más información sobre cómo habilitar CDC. Para la documentación de la versión 3 del CQD, consulte [activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype empresarial online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) para obtener más información acerca de la versión 3 del CQD.

## <a name="cqd-design-goals"></a>Objetivos del diseño del CQD

El CQD permite a los profesionales de TI usar datos agregados para identificar áreas de enfoque en su entorno que experimentan problemas de calidad de los medios. Permite a un profesional de ti comparar estadísticas para diferentes grupos de usuarios e identificar tendencias y patrones. No se centra en la solución de problemas de llamadas individuales, sino en la identificación de problemas y soluciones que se aplicarán a muchos usuarios en un entorno determinado. 
  
## <a name="call-quality-dashboard-components"></a>Componentes del panel de calidad de llamadas

El panel de calidad de llamadas consta de varias bases de datos, trabajos de Microsoft SQL Agent, procesos y aplicaciones Web. Los trabajos del agente de Microsoft SQL copian periódicamente datos de la base de datos de calidad de la QoE en la base de datos de archivo de QoE y procesan el cubo con los datos de la base de datos de archivo de QoE. La base de datos del repositorio almacena las definiciones de informe que encienden el portal. El portal proporciona acceso de explorador a los datos del cubo. 
  
Los componentes del CQD, incluidas las bases de datos de archivo, cubo y repositorio de QoE, se pueden instalar en el servidor de supervisión, instalar en su propio servidor o instalarse en varios servidores. El método de instalación concreto depende de las demandas de rendimiento del CQD, así como del impacto en otros procesos en los mismos servidores. Para obtener más información, consulte la sección "componentes y topologías de CQD" más adelante en este artículo.
  
### <a name="architectural-overview"></a>Descripción general de la arquitectura

En Resumen, el CQD requiere los siguientes elementos:
  
- Dos bases de datos: una base de datos de archivo y una base de datos de repositorio.
    
- Un cubo SSAS visualizar datos agregados 
    
- IIS hospeda el portal web de CQD
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La misma arquitectura del CQD admite Lync Server 2013 y Skype empresarial. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD y Skype empresarial en comparación con Lync 2013

 Solo en un entorno de Skype empresarial, están disponibles las siguientes capacidades:
  
- Informe de Wi-Fi sobre la intensidad de la señal
    
- Informes de Wi-Fi de controladores de chipset
    
- Clasificar mis datos de llamada 
    
## <a name="information-available-through-cqd"></a>Información disponible a través del CQD

El CQD puede mostrar los recuentos de secuencias de audio, vídeo y uso compartido de aplicaciones de Skype empresarial Server y el número de llamadas buenas frente a las incorrectas, así como las proporciones de llamadas malas y buenas. Las vistas se pueden segmentar y filtrar por muchas dimensiones diferentes. El CQD extrae los datos de la base de datos de calidad de la QoE en el servidor de supervisión. A continuación, los datos se combinan con los datos proporcionados por el cliente, como la asignación de subred de red a edificio para que los informes como "calidad de llamadas por edificio" sean posibles. 
  
El CQD también abstrae muchas de las idiosincrasias de datos de la QoE interna, como "autor de la llamada" y "autor de la llamada", de modo que el usuario pueda centrarse en crear vistas de informes alrededor de "servidor" y "cliente". Siguiendo la metodología de calidad de llamadas, el CQD se ha simplificado para ayudar a identificar las condiciones que los bolsillos de llamadas deficientes tienen en común: uno de los principios para mejorar la calidad de las llamadas.
  
## <a name="viewing-data-in-cqd"></a>Ver datos en el CQD

Los datos del CQD se pueden ver a través del portal de CQD y tener acceso a ellos a través de llamadas API de REST.
  
### <a name="cqd-portal"></a>Portal de CQD

El portal es la forma más rápida de ver los datos del cubo. El portal incluye varios informes integrados que pueden usarse inmediatamente. Los informes integrados están vinculados de forma estructurada para guiar al usuario a segmentos cada vez más pequeños y pequeños de los datos de la llamada. Los informes integrados también resaltan las distintas formas en que se pueden mostrar los datos mediante la demostración de una combinación de gráficos y tablas con diferentes tablas dinámicas, filtros y medidas. Cada usuario que tiene acceso al portal puede tener su propio conjunto de informes que puede modificar y compartir. Para obtener más información sobre el uso del portal web del CQD, consulte [usar el panel de calidad de llamadas para Skype empresarial Server](use.md).
  
Sistemas operativos compatibles para el portal de CQD: Windows 8,1, Windows 8, Windows Server 2012 R2, Windows Server 2012 y Windows Server 2016 (solo para Skype empresarial Server 2019 CQD).
  
Exploradores compatibles para el portal de CQD: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>API de REST

También se puede tener acceso a los datos del cubo a través de llamadas API de REST. Los datos recuperados mediante llamadas a la API de REST se pueden representar mediante páginas HTML. Los usuarios pueden aprovechar la velocidad de la consulta y el esquema de nivel alto del CQD y, al mismo tiempo, crear informes personalizados adaptados a sus necesidades empresariales. Para obtener más información sobre la API y los ejemplos, consulte [develop Call Quality Dashboard for Skype for Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definición de los requisitos de la organización para el CQD

El CQD proporciona el archivado de datos de QoE y un análisis rápido y detallado de los datos de calidad de la llamada. La siguiente guía le ayudará a decidir cuándo y por qué implementar el CQD.
  
### <a name="when-to-deploy-cqd"></a>Cuándo implementar el CQD

 **El CQD puede implementarse para establecer una medida de calidad de llamada de línea base, incluso si una organización no experimenta problemas de calidad de llamadas.** El establecimiento de una medida de la calidad de la llamada de línea base es importante, ya que cada organización tiene una combinación de Wi-Fi en comparación con los trabajadores por cable y remotas. Cuando surgen problemas con la calidad de las llamadas, las medidas de calidad de llamadas más recientes se pueden comparar con los intervalos de tiempo anteriores. Las características de tendencias del CQD permiten detectar fácilmente los cambios en la calidad de las llamadas a lo largo del tiempo.
  
 **El CQD se puede implementar para buscar de forma proactiva las áreas problemáticas que puedan afectar a la calidad de la llamada.** Incluso si la calidad media de llamada para una organización puede cumplir los objetivos establecidos por la organización, podrían existir problemas de calidad de llamadas ocultos tras las métricas medias. El CQD permite el desglose de la tabla dinámica similar a la de las métricas de calidad de las llamadas por muchas dimensiones en la base de datos de QoEMetrics. La detección de valores atípicos en grupos del mismo nivel es una forma rápida de localizar los problemas de calidad de las llamadas de forma proactiva.
  
 **El CQD debe implementarse si hay problemas de calidad de las llamadas en la organización para reducir el tiempo necesario para solucionar problemas.** El CQD puede simplificar las investigaciones de calidad de las llamadas existentes ofreciendo un rendimiento de informes rápido y capacidades de obtención de detalles dinámicas. El CQD está diseñado para muchos tipos de flujos de trabajo en investigaciones de calidad de llamadas validación de reparaciones en el entorno.
  
### <a name="why-deploy-cqd"></a>Por qué implementar el CQD

 **El CQD debe implementarse si es necesario que se produzcan informes de QoE durante más de 3 meses de datos.** Los informes de la base de datos de QoEMetrics y del servidor de supervisión están diseñados para retener e informar de un pequeño conjunto de datos. La base de datos de calidad de la calidad de la QoE está optimizada para inserciones rápidas y, por lo tanto, el rendimiento del informe puede verse obstaculizado por grandes volúmenes de llamadas o a la base de datos de creación de informes de competencia. La base de datos de archivo QoE del CQD proporciona una segunda copia de los datos de las métricas de QoE con capacidades de retención mucho más largas. El portal también está optimizado para mostrar hasta 7 meses de datos a la vez y puede informar sobre todos los datos en el archivo de QoE según sea necesario.
  
 **El CQD debe implementarse si se necesitan informes de QoE personalizados.** El portal tiene una característica editor de informes para crear y crear prototipos de informes de forma rápida y sencilla. También hace que las API de REST disponibles obtengan acceso mediante programación a los datos del cubo, lo que permite la presentación personalizada con HTML/JavaScript o muchos otros marcos. Ya no es necesario crear nuevas consultas SQL con el propósito de crear vistas de datos personalizadas para los informes.
  
 **El CQD debe implementarse si la funcionalidad de informes de QoE existente no cumple la velocidad o la profundidad que requiere la organización.** El CQD incluye varios informes integrados. Los informes son útiles inmediatamente y demuestran cómo profundizar progresivamente los datos pueden ofrecer información adicional en cada nivel. La jerarquía de informes también ayuda a administrar los numerosos informes de forma lógica y fomenta la creación de muchos más informes que son fácilmente accesibles y comprensibles. El CQD no solo ofrece la velocidad y la flexibilidad, sino que también está optimizada para los flujos de trabajo desarrollados por la metodología de calidad de llamadas.
  
## <a name="components-and-topologies-for-cqd"></a>Componentes y topologías del CQD

El CQD incluye varios componentes y ayuda a comprender los requisitos de cada componente y su relación entre sí para obtener la implementación más sencilla y con mejor rendimiento de la herramienta. En la tabla siguiente se describe el componente dependiente para cada componente del CQD.
  

|**Nombre del componente**|**Componente dependiente**|
|:-----|:-----|
|Archivo de QoE  <br/> |Microsoft SQL Server  <br/> |
|Cúbica  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Servicios de información de Microsoft  <br/> |
|Servicio de repositorio (parte de la instalación del portal)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Para el archivo y el cubo de QoE, algunas opciones de implementación requieren inteligencia empresarial o ediciones empresariales de Microsoft SQL Server. Para obtener más información, consulte la sección [requisitos de infraestructura para el CQD](plan.md#Infrastructure_Req) .
  
![Componentes de CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuración de un solo servidor

Todos los componentes del CQD y los componentes dependientes pueden instalarse en un solo equipo. La configuración de un único cuadro es la configuración más sencilla y permite que el CQD sea independiente. El CQD solo necesitaría tener acceso a la base de datos de la calidad de la QoE en el servidor de supervisión. El servidor CQD puede ser un equipo independiente, una máquina virtual o incluso el servidor de supervisión, en función de los recursos disponibles del equipo host y los requisitos de rendimiento. 
  
Durante la instalación, el usuario que realiza la instalación simplemente tiene que proporcionar las instancias de Microsoft SQL Server y Microsoft SQL Server Analysis Services que se han configurado previamente en el equipo en el que se instalará el CQD. Para obtener más información, consulte [implementar el panel de calidad de llamadas para Skype empresarial Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configuración multiservidor

En una configuración multiservidor, el archivo, el cubo y el portal de QoE pueden estar en equipos diferentes. Hay dos usos principales para la configuración de multiservidor:
  
- Hospedar el portal web del CQD y el cubo del CQD en servidores diferentes.
    
- Hospedar un portal de "desarrollo" independiente del portal de "producción". 
    
  **Hospedar el portal web del CQD y el cubo del CQD en diferentes equipos.** Las organizaciones que podrían tener requisitos para separar el portal de CQD de la instalación de SQL Server o que quieran mezclar y hacer coincidir las ediciones de SQL Server para la instancia de SQL Server y la instancia de SQL Server Analysis Services pueden elegir instalar el portal de CQD y Cubo del CQD en máquinas diferentes. El componente de archivo de QoE también puede ser el único componente de CQD instalado si la organización simplemente desea tener un método sostenible para archivar los datos de la QoE sin alcanzar los límites de rendimiento del servidor de supervisión.
  
![CQD de un solo servidor](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hospedar un portal de "desarrollo" independiente del portal de "producción".** Las organizaciones que desarrollan sus propios informes personalizados (a través de las API de REST) pueden preferir la implementación de instancias del portal adicionales (CQD) junto al portal de producción que tienen acceso a los usuarios habituales para la supervisión o investigación de la calidad de las llamadas. El portal de desarrollo puede aislar cualquier modificación del portal desde el entorno de producción. Los portales web adicionales se pueden implementar en diferentes equipos (que se muestran a continuación) o implementar en diferentes directorios web en el mismo equipo (no se muestra). Para lograr esto último, el portal web del CQD adicional debe copiarse manualmente en la máquina de producción, ya que el proceso de configuración del CQD siempre implementa el portal web del CQD en el sitio web predeterminado con nombres de aplicaciones Web predefinidos.
  
![Planear el servidor múltiple del CQD](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologías admitidas

El CQD no combina datos de varias bases de datos de QoEMetrics, como es el caso en el que hay varias topologías de Skype empresarial Server, cada una con su propio servidor de supervisión. Cada instancia del CQD debe apuntar a una base de datos de QoEMetrics. Sin embargo, como el CQD moverá gran parte de la carga de trabajo de informes del servidor de supervisión, las organizaciones grandes que necesitaban implementar un servidor de supervisión por topología de Skype empresarial Server deberían considerar el uso de un servidor de supervisión para todas las topologías.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisitos de infraestructura para el CQD
<a name="Infrastructure_Req"> </a>

El CQD, incluidos todos sus componentes y componentes dependientes, se puede implementar en una máquina virtual, en un solo equipo o en varios equipos. Los requisitos mínimos de software y hardware se enumeran a continuación. La disponibilidad de los datos y el rendimiento de las consultas pueden variar de minutos a horas, según el número de usuarios y el hardware y la configuración activos de Skype empresarial Server, por lo que se proporcionan algunas medidas de rendimiento a continuación.
  
|||
|:-----|:-----|
|Para el CQD 2015 <br/> |  <br/> |
|Sistemas operativos compatibles   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|SQL Server compatible  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Para el CQD 2019 <br/> |  <br/> |
|Sistemas operativos compatibles   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|SQL Server compatible  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
El CQD usa Microsoft SQL Server, Microsoft SQL Server Analysis Services y Microsoft Internet Information Services para que los requisitos mínimos de hardware y software del CQD sean básicamente los mismos que los componentes dependientes. Sin embargo, en función de los requisitos de la organización sobre la actualización de datos (que dependerá en parte del volumen de los datos de QoE que genera la organización) y el costo de implementación, se deben tener en cuenta otras consideraciones de implementación.
  
El procesamiento de datos en el CQD se divide en dos etapas principales: 
  
- Proceso de archivo de QoE
    
- Procesamiento del cubo CQD
    
  **Procesamiento del archivo QoE.** La tarea de procesamiento de archivos de QoE copia datos de la base de datos de QoE Metrics del servidor de supervisión a la base de datos de archivo de QoE. Hay dos situaciones en las que el tiempo de procesamiento de la tarea tendría características de rendimiento fundamentalmente diferentes. La primera se encuentra después de la instalación inicial del CQD. Cuando la tarea se ejecuta por primera vez después de una instalación nueva, la tarea de procesamiento de archivo de QoE copiará todos los datos que se encuentra en la base de datos de la actualización de QoE en la base de datos de archivo de QoE. El segundo es el procesamiento periódico después de este redondeo inicial. La tarea de procesamiento de archivos de QoE se ejecutará cada 15 minutos y procesará los nuevos registros de QoE que se encuentren en la base de datos de la calidad de la biométrica. Por lo general, el tiempo de procesamiento inicial no es un problema porque solo se ejecuta la primera vez, cuando se instala el CQD. Sin embargo, si el servidor CQD tiene muy pocos problemas, esta tarea puede durar varias horas. Consulte la tabla siguiente para obtener un ejemplo inicial de los tiempos de procesamiento del archivo QoE.
  
  **Procesamiento del cubo CQD.** La tarea de procesamiento del cubo agrega los datos de la base de datos de archivo de QoE al cubo. El tiempo de procesamiento inicial del cubo y el tiempo de procesamiento del cubo posterior se determinan mediante la edición de SQL Server Analysis Services usada para el cubo CQD. Si se usa la edición estándar, no hay ninguna diferencia entre el tiempo de procesamiento del cubo inicial y el tiempo de procesamiento del cubo posterior, ya que cada vez que se actualizan los datos del cubo, siempre será un procesamiento completo de todos los datos disponibles. (Esto significa que el tiempo de procesamiento del cubo aumenta a medida que aumenta la cantidad de datos en la base de datos de archivo de QoE.) Como Business Intelligence Edition y Enterprise Edition de SQL Server tienen compatibilidad con particiones, si se usa cualquiera de las dos ediciones, solo la ejecución inicial procesará todos los datos de la base de datos de archivo de QoE. En las ejecuciones siguientes, cuando la tarea se desencadene cada 15 minutos, la tarea sólo procesará los nuevos registros agregados a la base de datos de archivo de QoE desde la última vez que se ejecutó la tarea. Una vez al día, también habrá un procesamiento completo en la partición que contiene los datos del mes actual.
  
Las características de la máquina física pueden afectar al rendimiento del CQD, así como las características de software que están disponibles en los componentes de SQL Server. El componente de archivo de QoE tendrá un uso más intensivo del disco en comparación con otros componentes, mientras que el componente de cubos tendrá más CPU y mucha memoria. Todos estos factores contribuyen al tiempo total de procesamiento de los datos del CQD, que afecta directamente a la actualización y a la disponibilidad de los datos. Las organizaciones deben tomar decisiones sobre el hardware y el software en función de las necesidades individuales de la organización. 
  
### <a name="tested-hardware-configurations"></a>Configuraciones de hardware probadas

En esta sección se asume que hay una sola base de datos de QoEMetrics en el entorno. 
  
**Perfiles de equipo**

|**Equipo**|**Núcleos de CPU**|**Memoria RAM**|**Archivo de QoE y cubo en el mismo disco**|**Archivo de QoE y base de datos Temp SQL en el mismo disco**|
|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |4  <br/> |7 GB  <br/> |Sí  <br/> |Sí  <br/> |
|4 núcleos  <br/> |4  <br/> |20 GB  <br/> |Sí  <br/> |No  <br/> |
|8 núcleos  <br/> |8,5  <br/> |32 GB  <br/> |Sí  <br/> |No  <br/> |
|16 núcleos  <br/> |16   <br/> |128 GB  <br/> |No  <br/> |No  <br/> |
   
**Resultados de rendimiento**

|**Equipo**|**Tamaño de BD de la métrica de QoE**|**Particiones SQL**|**Tipo de disco**|**Número de transmisiones**|**Proceso inicial de archivo**|**Proceso inicial de cubo**|**Proceso de archivo subsiguiente**|**Proceso de cubo posterior**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |900 MB  <br/> |Simple  <br/> |VHD (tamaño variable)  <br/> |0,5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Simple  <br/> |VHD (tamaño variable)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Simple  <br/> |VHD (tamaño fijo)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |30 + GB  <br/> |Simple  <br/> |VHD (tamaño fijo)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Simple  <br/> |Varios discos  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Múltiple  <br/> |Varios discos  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 núcleos  <br/> |30 + GB  <br/> |Simple  <br/> |Varios discos  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 núcleos  <br/> |30 + GB  <br/> |Múltiple  <br/> |Varios discos  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 núcleos  <br/> |200 GB  <br/> |Simple  <br/> |Varios discos  <br/> |125 M  <br/> |6 + días  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 núcleos  <br/> |500 GB  <br/> |Múltiple  <br/> |Varios ejes  <br/> |250 M  <br/> |8 días  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*No se espera que se encuentren en implementaciones reales, ya que la base de datos de la calidad de la QoE debe tener 9 y 18 meses de datos, respectivamente, pero se proporcionan aquí para estar completos.
  
### <a name="service-account-requirements"></a>Requisitos de la cuenta de servicio

Necesitará una cuenta (con acceso de lectura a QoEMetrics) que el agente de SQL en el servidor CQD puede usar para importar datos a la QoEArchiveDB.
  
Es posible que también necesite configurar una cuenta independiente para que un trabajo de SSAS Extraiga datos de QoEArchiveDB (este es un proceso opcional).
  
Normalmente, IIS usa el servicio de red como identidad del grupo de aplicaciones, pero puede configurarse para una cuenta de servicio.
  
### <a name="portal-access-control"></a>Control de acceso al portal

De forma predeterminada, cualquier usuario autenticado tiene acceso. Esto puede cambiarse mediante el uso de reglas de autorización de IIS para restringir a un grupo específico.
  
### <a name="pre-install-requirements"></a>Requisitos previos a la instalación

En estas instrucciones se da por hecho que ya se ha instalado una base de datos de la métrica de QoE y que se está ejecutando en algún lugar de la topología de Skype empresarial Server.
  
#### <a name="hardware-requirements"></a>Requisitos de hardware

El CQD usa Microsoft SQL Server, Microsoft SQL Analysis Server y Microsoft Internet Information Server para que los requisitos mínimos de hardware y software del CQD sean básicamente los mismos que los componentes dependientes. Sin embargo, en función de los requisitos de la organización sobre la actualización de datos (que dependerá en parte del volumen de los datos de QoE que genera la organización) y el costo de implementación, se deben tener en cuenta otras consideraciones de implementación.
  
#### <a name="software-requirements"></a>Requisitos de software

Los siguientes sistemas operativos son necesarios para el CQD:
  
- Windows Server 2008 R2 con IIS 7,5
    
- Windows Server 2012 con IIS 8,0
    
- Windows Server 2012 R2 con IIS 8,5

- Windows Server 2016 con IIS 10,0 (solo CQD de Skype empresarial Server 2019)

- Windows Server 2019 (solo el CQD de Skype empresarial Server 2019)
    
Los siguientes son los servicios de rol de IIS necesarios (en orden jerárquico):
  
- Servidor web
    
  - Características HTTP comunes
    
  - Contenido estático
    
  - Documento predeterminado
    
  - Desarrollo de aplicaciones
    
  - ASP.NET
    
  - Filtros ISAPI
    
  - Diagnósticos de mantenimiento &amp;
    
  - Registro HTTP
    
  - Seguridad
    
  - Autorización de dirección URL
    
  - Autenticación de Windows
    
  - Herramientas de administración
    
  - Consola de administración de IIS
    
> [!NOTE]
>  Tenga en cuenta lo siguiente para los requisitos anteriores: > 3,5 y 4,5 están disponibles las versiones de .NET Framework. Se requieren ambos (más concretamente, se requiere 3,5 SP1). > en algunos sistemas, si ASP.NET se configura antes de instalar IIS, entonces ASP.NET puede no estar registrado en IIS. El problema manifiesta a través de la ausencia de grupos de aplicaciones para la versión de .net correspondiente y también falta la versión de .NET CLR en la configuración del grupo de aplicaciones. Para corregir este problema en Windows Server 2008 R2, ejecute `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. En Windows Server 2012 y Windows Server 2012 R2, ejecute `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` y, a continuación, quite el módulo "ServiceModel" del sitio web predeterminado en el administrador de IIS. > las herramientas de administración son opcionales, pero recomendadas.
  
Para instalar estos requisitos con PowerShell, ejecute lo siguiente:
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Se admiten las siguientes versiones de SQL Server:
  
|||
|:-----|:-----|
| CQD 2015 <br/> |  SQL Server 2012, SQL Server 2014, SQL Server 2016  |
|CQD 2019 <br/> |  SQL Server 2017, SQL Server 2019  |
    
Se recomienda usar Business Intelligence o Enterprise Edition por motivos de rendimiento. Estas ediciones permiten el uso de varios archivos de partición que se pueden procesar en paralelo, lo que resulta ventajoso para procesar datos que abarcan varios meses o más. 
  
Aunque no se recomienda, Standard Edition también es compatible. El procesamiento se limitará a una sola partición (que debe configurarse durante la instalación). 
  
En todos los casos, debe estar instalado "servicios de motor de base de datos" y "Analysis Services". Se recomienda, pero no es necesario, instalar también la característica "herramientas de administración completadas", que agrega la compatibilidad con SQL Server Management Studio para Analysis Services. La pantalla de selección de características debería tener un aspecto similar al de la figura.
  
![Requisitos de características de SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Cuando configure la configuración de SSAS, en la configuración de Analysis Services, establezca "modo de servidor" en "modo de minería de datos y multidimensional". 
  
Para obtener más información sobre la instalación y la configuración de las características de la inteligencia empresarial de SQL Server, vea [install Analysis Services in multidimensional and Data Mining Mode](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Requisitos de la cuenta

Se recomiendan tres cuentas de servicio de dominio en el principio de privilegios mínimos: 
  
- Uno que ya tiene una entidad de seguridad de inicio de sesión para la base de datos de QoE Metrics (con db_datareader privilegio) y una entidad de seguridad de inicio de sesión en la instancia de archivo de SQL Server de QoE (necesario para crear un objeto de servidor vinculado durante la instalación). Esta cuenta se utilizará para ejecutar el paso "datos del archivo QoE" del trabajo del Agente SQL Server.
    
- Una que se usará para ejecutar el paso "procesar cubo" del trabajo del Agente SQL Server. El programa de instalación creará una entidad de seguridad de inicio de sesión para la base de datos de archivo de QoE (con privilegio de lectura y escritura) y también crea un miembro en el rol de QoE (con control total) para el cubo.
    
- Una que se usará para ejecutar el proceso de trabajo de IIS para los portales web y las API Web. El programa de instalación creará una entidad de seguridad de inicio de sesión para la base de datos de archivo de QoE (con privilegio de lectura), una entidad de seguridad de inicio de sesión en la base de datos del repositorio (con privilegio de lectura y escritura) y un miembro de QoERole (con privilegio de control total) para el cubo. 
    
    > [!NOTE]
    > Cuando ambas bases de datos de archivo de QoE y de repositorio se hospedan en el mismo SQL Server, solo se crea una entidad de seguridad de inicio de sesión con dos asignaciones de usuario. 
  
Las dos primeras cuentas se pueden considerar lógicamente como "cuentas de servicio back-end" y la última cuenta es una "cuenta de servicio front-end". Aunque no se recomienda, es posible usar una sola cuenta en todos los casos.
  
> [!NOTE]
> La cuenta de usuario que inicia la instalación también debe tener acceso de lectura a la base de datos de la métrica de QoE (además de tener derechos de administrador de la máquina en el servidor de base de datos de archivo de QoE en el que debe tener lugar la instalación). 
  
## <a name="capacity-planning"></a>Planeamiento de la capacidad
<a name="Infrastructure_Req"> </a>

El CQD está diseñado para que tenga un impacto mínimo en la QoEMetrics: el código se ha optimizado para no bloquear datos y los trabajos de importación son ajustables.
  
El tipo de hardware que se va a usar depende de los requisitos de la velocidad con la que se deben ejecutar las sincronizaciones. El tamaño del disco es el siguiente:
  
- QoEArchive es ~ 1,5 x mayor que QoEMetrics DB inicial
    
- El cubo SSIS comprime los datos casi 10x en comparación con la base de datos
    
- Los datos se dividen mensualmente; las particiones se pueden eliminar
    


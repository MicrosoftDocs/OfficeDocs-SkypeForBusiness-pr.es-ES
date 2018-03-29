---
title: Plan para el panel de calidad de la llamada de Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/27/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Resumen: Conozca qué debe tener en cuenta al planear el panel calidad llamar.'
ms.openlocfilehash: 25438b759e367d70df6ae09b7d4a5cc093dc1e7a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server-2015"></a>Plan para el panel de calidad de la llamada de Skype para Business Server 2015
 
**Resumen:** Obtenga información sobre lo que debe tener en cuenta al planear el panel calidad llamar.
  
## <a name="overview-of-the-skype-for-business-server-2015-call-quality-dashboard"></a>Información general sobre el Skype para Business Dashboard de calidad de llamada Server 2015

El Skype para Business Server 2015 llamar calidad Dashboard (CQD) es una capa de informes sobre la calidad de experiencia de base de datos en el servidor de supervisión en Skype para Business Server 2015 y Lync Server 2013. CQD utiliza Microsoft SQL Server Analysis Services para proporcionar uso adicional y llamar a información de calidad, así como para el filtrado y la creación de tablas dinámicas en el conjunto de datos. CQD características incluyen:
  
- **Almacenamiento para archiving de datos de la calidad mediante el componente de archivo QoE de CQD.** El componente de archiving QoE puede almacenar datos de calidad para una duración mucho mayor que el servidor de supervisión puede. Esto permite tendencias e informes hasta siete meses de datos a la vez, con la capacidad de la diapositiva de la ventana de informes hasta donde hay datos.
    
- **Reporting y análisis con la potencia y la velocidad de Microsoft SQL Server Analysis Services.** CQD utiliza Analysis Services de Microsoft SQL para proporcionar un resumen rápido, filtrar y tablas dinámicas capacidades para encender la consola mediante un cubo de Analysis. Informes de velocidad de ejecución y la capacidad para profundizar en los datos pueden reducir los tiempos de análisis considerablemente.
    
- **Nuevo esquema de datos optimizada para informes de calidad de llamada.** El cubo tiene un esquema diseñado para informes de calidad de voz e investigaciones. Los usuarios del portal pueden centrarse en las tareas de informes en lugar de averiguar cómo las métricas de calidad base de datos esquema se asigna a las vistas que necesitan. La combinación del archivo QoE y cubo proporciona una abstracción que reduce la complejidad de los informes y análisis a través de CQD. El esquema de base de datos de archivo QoE también contiene tablas que pueden rellenarse con datos específicos de la implementación para mejorar el valor general de los datos.
    
- **Diseñador de informes integrado y edición de informes en el lugar.** El componente de Portal incluye varios informes integrados modelados la metodología de calidad llamar. Los usuarios del portal pueden modificar los informes y crear nuevos informes a través de la funcionalidad de edición del Portal.
    
- **Acceso Web API a la estructura de informe y análisis de datos del cubo.** El marco de informes de escritorio no es la única manera de mostrar los datos del cubo. CQD proporciona varios ejemplos del uso de HTML y JavaScript para recuperar datos de las API Web de CQD y presentar los datos en un formato personalizado. La combinación del Editor de informes y las API de Web CQD permite creación rápida de prototipos de informes y el diseño de informe personalizado.
    
## <a name="cqd-design-goals"></a>Objetivos de diseño CQD

El panel de calidad de llamadas permite a los profesionales de TI usar datos de agregados para identificar áreas en su entorno que estén experimentando problemas en la calidad de los medios. También les permite comparar estadísticas de diferentes grupos de usuarios, e identificar tendencias y patrones. No se centra en la solución de problemas con llamadas individuales, sino en la identificación de problemas y soluciones aplicables a muchos usuarios dentro de un entorno. 
  
## <a name="call-quality-dashboard-components"></a>Llamar a componentes de panel de calidad

El panel de calidad llamar consta de varias bases de datos, Microsoft SQL Agent trabajos, procesos y aplicaciones web. Los trabajos del Agente SQL de Microsoft copien periódicamente datos de la base de datos de métricas de calidad de la experiencia en la QoE Archivar base de datos y el cubo con los datos en la base de datos de archivo de calidad de procesos. La base de datos del depósito almacena las definiciones de informe que el Portal de la energía. El Portal proporciona acceso de explorador a los datos del cubo. 
  
Los componentes CQD, incluidas las bases de datos de archivo QoE, cubo y repositorio, se pueden instalados en el servidor de supervisión, instalados en su propio servidor o instalados en varios servidores. El método de instalación particular dependerá de las demandas de rendimiento de CQD, así como la repercusión a otros procesos en los mismos servidores. Para obtener más información, consulte la sección "Componentes y topologías para CQD" más adelante en este artículo.
  
### <a name="architectural-overview"></a>Introducción a la arquitectura

Para resumir, CQD requiere los elementos siguientes:
  
- Dos bases de datos: una base de datos de archivo y una base de datos.
    
- Un cubo de SSAS visualizar datos agregados 
    
- IIS aloja el Portal Web de CQD
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La misma arquitectura CQD admite Lync Server 2013 y Skype para el negocio. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD y Skype para negocio frente a Lync 2013

 En Skype en un sólo entorno de negocios, están disponibles las siguientes capacidades:
  
- Wi-Fi informes de intensidad de la señal
    
- Wi-Fi reporting de los controladores de Chipset
    
- Velocidad de datos de la llamada 
    
## <a name="information-available-through-cqd"></a>Información disponible a través de CQD

CQD puede mostrar Skype para Business Server audio, vídeo y aplicaciones compartir recuentos de secuencia y el número del bien contra el mal llamadas así como relaciones de llamadas incorrectos a una buena. Las vistas pueden rodajas y filtradas por muchas dimensiones diferentes. CQD extrae datos de la base de datos de métricas de calidad en el servidor de supervisión. A continuación, los datos se combinan con cualquier dato proporcionado por el cliente, como la asignación de creación de subred de red para que sea posible informes como "Llamar a calidad por edificios". 
  
CQD también muchas de las idiosincrasias de datos QoE internas como "llamador" y "destinatario" abstrae tal que el usuario pueda centrarse en la creación de vistas de informe alrededor de "servidor" y "cliente". Siguiendo la metodología de calidad llamar, CQD está optimizada para ayudar a identificar las condiciones que los focos de llamadas pobre tienen en común: uno de los principios para mejorar la calidad de las llamadas.
  
## <a name="viewing-data-in-cqd"></a>Ver datos de CQD

Los datos CQD pueden verse a través del Portal de CQD y se accede a través de llamadas de la API de REST.
  
### <a name="cqd-portal"></a>Portal CQD

El Portal es la forma más rápida de ver los datos del cubo. El Portal incluye varios informes integrados que se pueden usables inmediatamente. Los informes integrados están vinculados de forma estructurada para guiar al usuario a sectores sucesivamente más y más pequeños de los datos de llamada. Los informes integrados también resaltar las diferentes formas de que los datos se pueden mostrar con la demostración de una combinación de gráficos y tablas con diferentes pivotes, filtros y medidas. Cada usuario que acceda al Portal puede tener su propio conjunto de informes que él o ella puede modificar y compartir. Para obtener más información sobre el uso del Portal Web CQD, consulte [Panel de calidad llamar al uso de Skype para Business Server 2015](use.md).
  
Sistemas operativos compatibles para el Portal CQD: Windows 8.1, Windows 8, Windows Server 2012 R2 y Windows Server 2012.
  
Exploradores compatibles para CQD Portal: Internet Explorer 9, Internet Explorer 10 y 11 de Internet Explorer.
  
### <a name="rest-apis"></a>API del resto

También se pueden acceder a los datos del cubo mediante llamadas de API de REST. Los datos recuperados a través de las llamadas de API de REST se pueden representar a través de páginas HTML. Los usuarios pueden tomar ventaja de la velocidad de consulta y el esquema de alto nivel de CQD mientras sigue creando informes personalizados adecuados para sus necesidades empresariales. Para obtener más información sobre la API y ejemplos, vea [Desarrollar panel calidad llame para Skype para Business Server 2015](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definir los requisitos de su organización para CQD

CQD proporciona QoE archiving y rápidamente y profundo análisis de los datos de datos de calidad de la llamada. La siguiente guía le ayuda a decidir cuándo y por qué debería implementar CQD.
  
### <a name="when-to-deploy-cqd"></a>Cuándo desplegar CQD

 **CQD puede implementarse para establecer una medida de calidad básica llamada, incluso si una organización no experimenta problemas de calidad de la llamada.** Establecimiento de una medida de calidad básica llamada es importante porque cada organización tiene una combinación diferente de Wi-Fi frente a remoto frente a los trabajadores de oficina y por cable. Cuando surgen problemas de calidad de llamada, las mediciones de calidad de llamada más reciente pueden compararse a intervalos de tiempo anterior. Características de tendencias de CQD permiten facilita la detección de cambios en la calidad de las llamadas con el tiempo.
  
 **CQD se puede implementar para buscar áreas problemáticas que pueden afectar la calidad de las llamadas de manera preventiva.** Incluso si el promedio de llamadas calidad para una organización puede cumplir los objetivos establecidos por la organización, podría haber focos de problemas de calidad de la llamada que se ocultan detrás de métricas promedio. CQD permite desglose de similar a una tabla dinámica de la métrica de calidad de la llamada al número de dimensiones de la base de datos de QoEMetrics. Descubrir los valores atípicos en grupos del mismo nivel es una forma rápida de buscar proactivamente problemas de calidad de la llamada.
  
 **CQD debe implementarse si hay llamada problemas de calidad de la organización para reducir el tiempo necesario para solucionar problemas.** CQD puede simplificar las investigaciones de calidad de llamada existente al ofrecer informes rápido rendimiento y funciones de desglose dinámico. CQD está diseñado para muchos tipos de flujos de trabajo de validación de las investigaciones de llamada calidad de reparaciones en el entorno.
  
### <a name="why-deploy-cqd"></a>¿Por qué implementar CQD

 **Si reporting QoE debe ocurrir durante más de 3 meses de datos, se debe implementar CQD.** La base de datos de QoEMetrics y supervisión de informes de servidor están diseñados para conservar y notificar un pequeño conjunto de datos. La base de datos de métricas de calidad está optimizado para las inserciones rápidas y, por tanto, rendimiento de los informes puede verse obstaculizada por el gran volumen de llamadas o competencia acceso de informes a la base de datos. Base de datos de archivo de calidad de la experiencia del CQD proporciona una segunda copia de los datos de métricas de calidad de la experiencia con mucho más capacidades de retención. El Portal también está optimizado para mostrar hasta 7 meses de datos a la vez y puede informar sobre todos los datos en el archivo de calidad según sea necesario.
  
 **Si son necesarios informes de calidad personalizados debe implementar CQD.** El Portal tiene una función de Editor de informes para informes de prototipo y crear rápida y fácilmente. También facilita API resto disponibles para el acceso mediante programación a los datos del cubo, que permiten la presentación personalizada utilizando HTML/JavaScript o muchos otros marcos. Ya no es necesario crear nuevas consultas SQL con el fin de crear vistas de datos personalizadas para informes.
  
 **Si la funcionalidad de informes de calidad existente no cumple con la velocidad o la profundidad requerida por la organización, se debe implementar CQD.** CQD incluye muchos informes integrados. Los informes resultan de utilidad inmediata y demostrar cómo progresivamente en los datos de taladro puede ofrecer perspectivas adicionales en cada nivel. La jerarquía de informes también ayuda a administrar los numerosos informes de una manera lógica y fomenta la creación de muchos informes más fácilmente accesible y comprensible. CQD no sólo ofrece una velocidad y flexibilidad, pero también está optimizado para los flujos de trabajo desarrollados por la metodología de calidad llamar.
  
## <a name="components-and-topologies-for-cqd"></a>Componentes y topologías para CQD

CQD incluye varios componentes, y ayuda a entender los requisitos de cada componente y su relación entre sí para obtener la implementación más simple y con mejor performance de la herramienta. La tabla siguiente describe el componente dependiente para cada componente CQD.
  

|**Nombre de componente**|**Componente dependiente**|
|:-----|:-----|
|Archivo de calidad  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Servicios de información de Microsoft  <br/> |
|Servicio de repositorio (parte de la instalación de Portal)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Archivo de calidad de la experiencia y el cubo, algunas opciones de implementación requieren Business Intelligence o ediciones Enterprise de Microsoft SQL Server. Consulte la sección [requerimientos de infraestructura para CQD](plan.md#Infrastructure_Req) a continuación para obtener más detalles.
  
![Componentes de CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuración de servidor único

Todos los componentes CQD y dependientes puede instalarse en un equipo. La configuración de una caja es la configuración más sencilla y permite CQD a ser autónomos. CQD simplemente tendría acceso a la base de datos de métricas de calidad en el servidor de supervisión. El servidor de CQD puede ser un equipo independiente, una máquina virtual, o incluso puede ser el servidor de supervisión, según los recursos disponibles del equipo host y los requisitos de rendimiento. 
  
Durante la instalación, el usuario realiza que la instalación sólo tiene que proporcionar el Microsoft SQL Server y las instancias de Analysis Services de Microsoft SQL Server que previamente configuradas en el equipo donde se va a instalar el CQD. Consulte [Implementar panel calidad llame para Skype para Business Server 2015](deploy-0.md) para obtener más información.
  
### <a name="multiserver-configuration"></a>Configuración multiservidor

En una configuración multiservidor, The QoE Archive, cubo y Portal pueden estar en diferentes equipos. Existen dos usos principales para la configuración de varios servidores:
  
- Alojamiento de Portal Web de CQD y el cubo de CQD en servidores diferentes.
    
- Alojamiento de un Portal independiente de "producción" Portal "desarrollo". 
    
 **Alojamiento de Portal Web de CQD y CQD cubo en diferentes equipos.** Las organizaciones que pueden tener requisitos para separar el Portal CQD desde la instalación de SQL Server o que desee combinar y adecuar las ediciones de SQL Server para la instancia de SQL Server y la instancia de SQL Server Analysis Services pueden optar por instalar el Portal de CQD y Cubo de CQD en máquinas diferentes. El componente de archivo QoE también puede ser el único componente CQD que se instala si la organización desea simplemente tienen un método sostenible para archivar los datos de la calidad sin llegar a límites de rendimiento en el servidor de supervisión.
  
![CQD de un único servidor](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Alojamiento de un Portal independiente de "producción" Portal "desarrollo".** Las organizaciones que desarrollen sus propios informes personalizados (a través de las API de descanso) que prefiera implementar instancias adicionales de Portal (CQD) junto con la producción de Portal que tienen acceso los usuarios normales para la supervisión de la calidad en la llamada o investigaciones. El Portal de desarrollo puede aislar cualquier modificación en el Portal desde el entorno de producción. Los portales web adicionales se pueden implementar en equipos diferentes (mostrados más abajo) o implementados en directorios web diferentes en el mismo equipo (no se muestra). Para lograr este último, el portal web CQD adicional debe copiarse en el equipo de producción manualmente porque el proceso de instalación CQD siempre implementa el Portal Web de CQD en el sitio web predeterminado con nombres de aplicaciones web predefinidas.
  
![Planificar varios servidores de CQD](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologías compatibles

CQD no combina datos de varias bases de datos de QoEMetrics, como es el caso donde hay varios Skype para topologías de servidor de negocios, cada uno con su propio servidor de supervisión. Cada instancia CQD debe apuntar a una base de datos de QoEMetrics. Sin embargo, porque CQD pasará gran parte de la carga de trabajo de informes fuera del servidor de supervisión, deben considerar las grandes organizaciones que necesitan implementar un servidor de supervisión por Skype para la topología de servidores de negocios utilizando un servidor de supervisión para todas las topologías.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requerimientos de infraestructura para CQD
<a name="Infrastructure_Req"> </a>

CQD, incluidos todos sus componentes y dependientes, puede implementarse en una máquina virtual, un solo equipo, o en varios equipos. Continuación se enumeran los requisitos mínimos de hardware y software. Disponibilidad de los datos y consulta el rendimiento puede variar desde minutos a horas, dependiendo del número de activo Skype para los usuarios de Business Server y el hardware y la configuración, por lo que algunas medidas de rendimiento figuran debajo.
  
|||
|:-----|:-----|
|Sistemas operativos compatibles  <br/> |Windows Server 2008 R2, Windows Server 2012, R2 de Windows Server 2012  <br/> |
|SQL Server compatibles  <br/> |SQL Server 2008 R2, SQL Server 2012, SQL Server de 2014  <br/> |
   
CQD utiliza Microsoft SQL Server, Microsoft SQL Server Analysis Services y Microsoft Internet Information Services del CQD mínimo requisitos de hardware y software son básicamente igual que los componentes dependientes. Sin embargo, en función de los requisitos de la organización alrededor de frescura de los datos (que dependerá en parte el volumen de datos de que la organización genera la calidad) y el costo de implementación, las consideraciones de implementación adicionales se debió.
  
Procesamiento de datos en CQD se divide en dos fases principales: 
  
- Proceso de archivado de calidad
    
- Procesamiento de cubos CQD
    
 **QoE Archive de procesamiento.** La tarea de procesamiento de archivo QoE copia los datos de la base de datos de métricas de calidad en el servidor de supervisión de la base de datos de archivo de calidad. Existen dos situaciones donde el tiempo de procesamiento de la tarea tendría las características de rendimiento muy diferentes. La primera es después de la instalación inicial de CQD. Cuando la tarea se ejecuta por primera vez después de una instalación nueva, la tarea de procesamiento de archivo QoE copiará todos los datos que se encuentra en la base de datos de métricas de calidad de la experiencia en base de datos de archivo de calidad. El segundo es el procesamiento periódico después de esta fase inicial. El archivo QoE procesamiento tarea ejecutará cada 15 minutos y procesar todos los registros QoE nuevos que se encuentran en la base de datos de métricas de calidad. Generalmente, el tiempo de procesamiento inicial no es una preocupación porque se ejecuta sólo la primera vez, cuando se instala CQD. Sin embargo, si el servidor CQD es muy bajo con provisioning, esta tarea puede tardar varias horas. Consulte la tabla siguiente por ejemplo inicial QoE de contenedores tiempo de procesamiento.
  
 **Procesamiento de cubos CQD.** La tarea de procesamiento de cubo agrega los datos de la base de datos de archivo QoE en el cubo. El tiempo de procesamiento del cubo inicial y tiempo de procesamiento del cubo subsiguientes dependen de la edición de SQL Server Analysis Services utilizada el cubo de CQD. Si se utiliza la versión Standard edition, no hay diferencia entre el tiempo de procesamiento del cubo inicial y el cubo posterior, tiempo de procesamiento, porque cada vez que se actualizan los datos del cubo, siempre será un procesamiento completo de todos los datos disponibles. (Esto significa que aumenta el tiempo de procesamiento del cubo como la cantidad de datos en el archivo QoE aumenta la base de datos). Dado que el Business Intelligence Edition y Enterprise Edition de SQL Server tienen partición admite, si se utiliza cualquier edición, sólo la ejecución inicial procesará todos los datos en la base de datos de archivo de calidad. En las ejecuciones posteriores, cuando la tarea se activa cada 15 minutos, la tarea sólo procesará los nuevos registros que se agregan a la base de datos de archivo de calidad desde la última vez que se ejecutó la tarea. Una vez al día, también habrá un procesamiento completo de la partición que contiene los datos del mes actual.
  
Las características de la máquina física pueden afectar al rendimiento de CQD, así como las características de software que están disponibles en los componentes de SQL Server. El componente de archiving QoE será más-uso intensivo del disco en comparación con otros componentes, mientras que el componente de cubo será más CPU y memoria intensiva. Todos estos factores contribuyen al tiempo de procesamiento total de datos de CQD, que afecta directamente a la disponibilidad y la frescura de los datos. Las organizaciones deben tomar decisiones sobre el hardware y el software basado en las necesidades individuales de la organización. 
  
### <a name="tested-hardware-configurations"></a>Configuraciones de Hardware probado

Esta sección presupone que hay una sola base de datos de QoEMetrics en el entorno. 
  
**Perfiles de equipo**

|**Máquina**|**Núcleos de CPU**|**MEMORIA RAM**|**Archivo de calidad de la experiencia y el cubo en el mismo disco**|**Base de datos de SQL Temp en el mismo disco y el archiving de QoE**|
|:-----|:-----|:-----|:-----|:-----|
|Mmachine virtual  <br/> |4  <br/> |7 GB  <br/> |Sí  <br/> |Sí  <br/> |
|Llamar 4  <br/> |4  <br/> |20 GB  <br/> |Sí  <br/> |No  <br/> |
|núcleo 8  <br/> |8  <br/> |32 GB  <br/> |Sí  <br/> |No  <br/> |
|núcleo de 16  <br/> |16  <br/> |128 GB  <br/> |No  <br/> |No  <br/> |
   
**Resultados de rendimiento**

|**Máquina**|**Métricas de calidad tamaño de BD**|**Particiones SQL**|**Tipo de disco**|**Número de secuencias**|**Proceso de archivo inicial**|**Proceso inicial de cubo**|**Proceso posterior de archivado**|**Proceso subsiguiente de cubo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |900 MB  <br/> |Único  <br/> |VHD (tamaño variable)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m.  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Único  <br/> |VHD (tamaño variable)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m.  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Único  <br/> |VHD (tamaño fijo)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m.  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |MÁS DE 30 GB  <br/> |Único  <br/> |VHD (tamaño fijo)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|núcleo 8  <br/> |9 GB  <br/> |Único  <br/> |Varios discos  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|núcleo 8  <br/> |9 GB  <br/> |Varios  <br/> |Varios discos  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|núcleo 8  <br/> |MÁS DE 30 GB  <br/> |Único  <br/> |Varios discos  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m.  <br/> |20 m  <br/> |
|núcleo 8  <br/> |MÁS DE 30 GB  <br/> |Varios  <br/> |Varios discos  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|núcleo 4  <br/> |200 GB  <br/> |Único  <br/> |Varios discos  <br/> |125 M  <br/> |6 + días  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|núcleo de 16  <br/> |500 GB  <br/> |Varios  <br/> |Varios ejes  <br/> |250 M  <br/> |8 días  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*No se espera que se den en implementaciones reales, porque la base de datos de métricas de calidad tendría que tener 9 y 18 meses de datos, respectivamente, pero que se proporcionan aquí para integridad.
  
### <a name="service-account-requirements"></a>Requisitos de la cuenta de servicio

Se necesita una cuenta (con acceso de lectura a QoEMetrics) que el agente de SQL en el servidor de CQD puede utilizar para importar datos a la QoEArchiveDB.
  
También debe configurar una cuenta independiente para un trabajo de SSAS para extraer datos de QoEArchiveDB (Esto es un proceso opcional).
  
IIS normalmente utiliza el servicio de red como identidad del grupo de la aplicación, pero se puede configurar para una cuenta de servicio.
  
### <a name="portal-access-control"></a>Control de acceso al portal

De forma predeterminada, cualquier usuario autenticado tiene acceso. Esto puede cambiarse mediante reglas de autorización de IIS para restringir a un grupo específico.
  
### <a name="pre-install-requirements"></a>Requisitos de preinstalación

Estas instrucciones se supone que una base de datos de métricas de calidad de la experiencia ya ha sido instalado y se está ejecutando en algún lugar en el Skype para la topología de servidores de empresa.
  
#### <a name="hardware-requirements"></a>Requisitos de hardware

CQD utiliza Microsoft SQL Server, Microsoft SQL Analysis Server y Microsoft Internet Information Server del CQD mínimo requisitos de hardware y software son básicamente igual que los componentes dependientes. Sin embargo, en función de los requisitos de la organización alrededor de frescura de los datos (que dependerá en parte el volumen de datos de que la organización genera la calidad) y el costo de implementación, las consideraciones de implementación adicionales se debió.
  
#### <a name="software-requirements"></a>Requisitos de software

Los siguientes sistemas operativos son necesarios para CQD:
  
- Windows Server 2008 R2 con IIS 7.5
    
- Windows Server 2012 con IIS 8.0
    
- R2 de Windows Server 2012 con IIS 8.5
    
Los siguientes son los servicios de rol IIS necesarios (en orden jerárquico):
  
- Servidor Web
    
  - Características HTTP comunes
    
  - Contenido estático
    
  - Documento predeterminado
    
  - Desarrollo de aplicaciones
    
  - ASP.NET
    
  - Filtros ISAPI
    
  - Salud &amp; diagnóstico
    
  - Registro HTTP
    
  - Seguridad
    
  - Autorización de direcciones URL
    
  - Autenticación de Windows
    
  - Herramientas de administración
    
  - Consola de administración de IIS
    
> [!NOTE]
>  Tenga en cuenta lo siguiente para los requisitos anteriores: > 3.5 y las versiones de .net framework 4.5 están disponibles. Ambos son necesarios (más concretamente, 3.5 SP1 es necesario). > en algunos sistemas, si ASP.NET está configurado antes de instalar IIS, a continuación, ASP.NET puede no estar registrada en IIS. El problema se manifiesta a través de la ausencia de grupos de aplicaciones para la versión correspondiente de .net y también falta la versión de CLR de .NET en la configuración del grupo de la aplicación. Para corregir un problema en Windows Server 2008 R2, ejecutar `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. En Windows Server 2012 y Windows Server 2012 R2, ejecutar `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` seguido de la eliminación del módulo de "ServiceModel" desde el sitio Web predeterminado en IIS Manager. > herramientas de gestión es opcional, pero recomendado.
  
Para instalar estos requisitos con PowerShell, ejecute lo siguiente:
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Se admiten las siguientes versiones de SQL Server:
  
- SQL Server 2008 R2
    
- SQL Server 2012
    
- SQL Server 2014
    
Inteligencia empresarial o Enterprise edition se recomienda por motivos de rendimiento. Estas ediciones de permiten el uso de varios archivos de la partición que se puede procesar en paralelo, lo que es beneficioso para el procesamiento de datos que abarcan varios meses o más. 
  
Aunque no se recomienda, Standard edition es compatible también. Procesamiento se restringirse a una única partición (que debe configurarse durante la instalación). 
  
En todos los casos, deben instalarse "Servicios del motor de base de datos" y "Analysis Services". Se recomienda, aunque no es necesario instalar también la característica "Herramientas de administración - completa", que agrega compatibilidad con SQL Server Management Studio para Analysis Services. Pantalla de selección de función debería parecerse a la ilustración.
  
![Requisitos de la característica de SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Al configurar el programa de instalación SSAS, en la configuración de Analysis Services, establezca "Modo servidor" a "Multidimensional y minería de modo de datos". 
  
Para obtener ayuda adicional para instalar y configurar características de inteligencia empresarial de SQL Server, vea [Instalar Analysis Services en modo de minería de datos y Multidimensional](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Requisitos de la cuenta

En el principio de privilegio mínimo, se recomiendan tres cuentas de servicio de dominio: 
  
- Uno que ya tiene un principal de seguridad inicio de sesión de base de datos de métricas de calidad (con privilegios db_datareader) y una entidad de seguridad de inicio de sesión en QoE archivo SQL Server instancia (necesario para crear un objeto de servidor vinculado durante la instalación). Esta cuenta se utilizará para ejecutar el paso de "Datos de archivo de la calidad" del trabajo del agente de SQL Server.
    
- Uno que se utilizará para ejecutar el paso de "Procesar cubos" del trabajo del agente de SQL Server. El programa de instalación creará un inicio de sesión principal QoE Archivar base de datos de seguridad (con lectura y escritura de privilegio) y crear también un miembro de la función de calidad (con privilegios de control total) para el cubo.
    
- Uno que se utilizará para ejecutar el proceso de trabajo de IIS para los portales web y web API. El programa de instalación creará un inicio de sesión principal de seguridad de base de datos de archivo de calidad (con privilegios de lectura), una entidad de seguridad de inicio de sesión a la base de datos de repositorio (con lectura y escritura) y un miembro de QoERole (con privilegios de control total) para el cubo. 
    
    > [!NOTE]
    > Cuando la base de datos de archivo de calidad de la experiencia y base de datos se alojan en el mismo SQL Server, se crea sólo una seguridad de inicio de sesión principal con dos asignaciones de usuario. 
  
Las dos primeras cuentas pueden considerarse lógicamente como "cuentas de servicio de back-end" y la última cuenta es una "cuenta de servicio de front-end". Aunque no se recomienda, es posible utilizar una sola cuenta en todos los casos.
  
> [!NOTE]
> Inicio de la instalación de la cuenta de usuario debe tener acceso de lectura a la base de datos de métricas de calidad también (además de tener derechos de administrador de equipo en el servidor QoE archivo DB donde debe realizarse la instalación). 
  
## <a name="capacity-planning"></a>Planificación de la capacidad
<a name="Infrastructure_Req"> </a>

CQD está diseñado para minimizar el impacto en el QoEMetrics: el código se ha optimizado para no bloquear los datos y trabajos de importación son ajustables.
  
El tipo de hardware que utilice depende de los requisitos para la rapidez deben ejecutar sincronizaciones. Tamaño de disco es el siguiente:
  
- QoEArchive es mayor que QoEMetrics DB ~1.5x inicialmente
    
- Cubo de SSIS comprime los datos casi 10 x en comparación con DB
    
- Los datos se particiona mensualmente; se pueden eliminar particiones
    


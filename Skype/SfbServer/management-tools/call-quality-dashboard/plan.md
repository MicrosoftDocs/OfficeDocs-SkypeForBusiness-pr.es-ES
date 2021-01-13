---
title: Plan for Call Quality Dashboard for Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Resumen: obtenga información sobre lo que debe tener en cuenta al planear el Panel de calidad de llamadas.'
ms.openlocfilehash: 6a1fc39dd26f6c4e9e455babcecb124888629179
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803180"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Plan for Call Quality Dashboard for Skype for Business Server 
 
**Resumen:** Obtenga información sobre lo que debe tener en cuenta al planear el Panel de calidad de llamadas.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Información general sobre el panel de calidad de llamadas de Skype Empresarial Server

El Panel de calidad de llamadas (CQD) de Skype Empresarial Server es una capa de informes sobre la base de datos de calidad de la experiencia en el servidor de supervisión de Skype Empresarial Server. El CQD usa Microsoft SQL Server Analysis Services para proporcionar información de calidad de llamadas y uso agregado, así como para filtrar y pivotar sobre el conjunto de datos. Las características de CQD incluyen:
  
- **Almacenamiento de archivado de datos de QoE a través del componente de archivo QoE de CQD.** El componente de archivo de QoE puede almacenar datos de QoE durante mucho más tiempo que el servidor de supervisión. Esto permite crear tendencias e informes de hasta siete meses de datos a la vez, con la capacidad de deslizar la ventana de informes hasta llegar a los datos.
- **Informes y análisis con la potencia y la velocidad de Microsoft SQL Server Analysis Services.** CQD usa Microsoft SQL Analysis Services para proporcionar funcionalidades rápidas de resumen, filtro y control dinámico para encender el panel a través de un cubo de análisis. La velocidad de ejecución de los informes y la capacidad de explorar en profundidad los datos pueden reducir considerablemente los tiempos de análisis.
- **Nuevo esquema de datos optimizado para los informes de calidad de llamadas.** El cubo tiene un esquema diseñado para informes e investigaciones de calidad de voz. Los usuarios del portal pueden centrarse en las tareas de informes en lugar de averiguar cómo se asigna el esquema de la base de datos métricas de QoE a las vistas que necesitan. La combinación del archivo QoE y el cubo proporciona una abstracción que reduce la complejidad de los informes y el análisis a través del CQD. El esquema de base de datos de archivo qoE también contiene tablas que se pueden rellenar con datos específicos de la implementación para mejorar el valor general de los datos.
- **Diseñador de informes integrado y edición de informes en contexto.** El componente portal incluye varios informes integrados modelados después de la Metodología de calidad de llamadas. Los usuarios del portal pueden modificar los informes y crear nuevos informes a través de la funcionalidad de edición del portal.
- **Acceso de la API web a la estructura del informe y a los datos del cubo de análisis.** El marco de informes del panel no es la única forma de mostrar los datos del cubo. CQD proporciona varios ejemplos de uso de HTML y JavaScript para recuperar datos de las API web de CQD y representar los datos en un formato personalizado. La combinación del Editor de informes y las API web de CQD permite crear prototipos rápidos de informes y diseño de informes personalizados.

> [!NOTE]
> Ahora, un administrador puede administrar Skype Empresarial Server 2019 con [CQD versión 3](https://cqd.teams.microsoft.com) (iniciar sesión con credenciales de administrador). Esto requiere una implementación híbrida y el uso del conector de datos de llamadas (¡ENTE!). Vea [Plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) para obtener más información sobre la habilitación de SMTP. Para obtener más información sobre la versión 3 del CQD, vea Activar y usar el Panel de calidad de llamadas para Microsoft Teams y [Skype Empresarial Online.](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)

## <a name="cqd-design-goals"></a>Objetivos de diseño de CQD

El CQD permite a los profesionales de TI usar datos agregados para identificar áreas de foco en su entorno que experimentan problemas de calidad de medios. Permite a un profesional de TI comparar estadísticas de distintos grupos de usuarios e identificar tendencias y patrones. No se centra en resolver problemas de llamadas individuales, sino en identificar problemas y soluciones que se aplicarán a muchos usuarios de un entorno determinado. 
  
## <a name="call-quality-dashboard-components"></a>Componentes del Panel de calidad de llamadas

El Panel de calidad de llamadas consta de varias bases de datos, trabajos, procesos y aplicaciones web del Agente de SQL Microsoft. Los trabajos del Agente de SQL de Microsoft copian periódicamente datos de la base de datos métricas de QoE en la base de datos de archivo de QoE y procesa el cubo con los datos de la base de datos de archivo de QoE. La base de datos repositorio almacena las definiciones de informe que se han encendido el Portal. El portal proporciona acceso del explorador a los datos del cubo. 
  
Los componentes de CQD, incluidas las bases de datos de repositorio, cubo y archivo QoE, se pueden instalar en el servidor de supervisión, instalarse en su propio servidor o instalarse en varios servidores. El método de instalación específico depende de las demandas de rendimiento del CQD, así como del impacto en otros procesos en los mismos servidores. Para obtener más información, consulte la sección "Componentes y topologías para CQD" más adelante en este artículo.
  
### <a name="architectural-overview"></a>Descripción general de la arquitectura

En resumen, el CQD requiere los siguientes elementos:
  
- Dos bases de datos: una base de datos de archivo y una base de datos de repositorio.
    
- Un cubo SSAS que visualiza los datos agregados 
    
- IIS hospeda el portal web CQD
    
![Componentes de CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La misma arquitectura de CQD admite Lync Server 2013 y Skype Empresarial. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD y Skype Empresarial frente a Lync 2013

 Solo en un entorno de Skype Empresarial, están disponibles las siguientes funcionalidades:
  
- Wi-Fi informes de intensidad de señal
    
- Wi-Fi informes de controladores de conjunto de chips
    
- Calificar mis datos de llamada 
    
## <a name="information-available-through-cqd"></a>Información disponible a través de CQD

El CQD puede mostrar recuentos de secuencias de audio, vídeo y uso compartido de aplicaciones de Skype Empresarial Server, así como el recuento de llamadas buenas frente a llamadas mal llamadas, así como relaciones de llamadas buenas y mal llamadas. Las vistas se pueden segmentar y filtrar por muchas dimensiones diferentes. El CQD dibuja datos de la base de datos métricas de QoE en el servidor de supervisión. A continuación, los datos se combinan con cualquier dato proporcionado por el cliente, como la asignación de subred a edificio de red para hacer posibles informes como "Calidad de llamadas por edificio". 
  
El CQD también abstrae muchas de las idiosincrasias internas de datos de QoE, como "autor de la llamada" y "destinatario de la llamada", de modo que el usuario pueda centrarse en crear vistas de informes en torno a "servidor" y "cliente". Siguiendo la metodología de calidad de llamadas, el CQD se simplifica para ayudar a identificar las condiciones que tienen en común los bolsillos de llamadas deficientes, uno de los principios para mejorar la calidad de las llamadas.
  
## <a name="viewing-data-in-cqd"></a>Visualización de datos en CQD

Los datos de CQD se pueden ver a través del portal de CQD y se puede acceder a él a través de llamadas a la API de REST.
  
### <a name="cqd-portal"></a>CQD Portal

El portal es la forma más rápida de ver los datos en el cubo. El portal incluye varios informes integrados que se pueden abrir de inmediato. Los informes integrados se vinculan de forma estructurada para guiar al usuario a segmentos sucesivamente más pequeños y pequeños de los datos de llamada. Los informes integrados también resaltan las distintas formas en que se pueden mostrar los datos mostrando una combinación de gráficos y tablas con diferentes tablas dinámicas, filtros y medidas. Cada usuario que tiene acceso al Portal puede tener su propio conjunto de informes que puede modificar y compartir. Para obtener más información sobre el uso del portal web de CQD, vea Usar el panel de calidad de llamadas [para Skype Empresarial Server.](use.md)
  
Sistemas operativos compatibles con el portal CQD: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 y Windows Server 2016 (solo CQD de Skype Empresarial Server 2019).
  
Exploradores compatibles con el portal CQD: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>API de REST

También se puede tener acceso a los datos del cubo a través de llamadas a la API de REST. Los datos recuperados a través de las llamadas a la API de REST se pueden representar a través de páginas HTML. Los usuarios pueden aprovechar la velocidad de consulta y el esquema de alto nivel del CQD a la vez que crean informes personalizados adecuados para sus necesidades empresariales. Para obtener más información sobre la API y los ejemplos, consulte [Desarrollar panel de calidad de llamadas para Skype Empresarial Server.](develop.md) 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definir los requisitos de la organización para el CQD

El CQD proporciona archivado de datos de QoE y un análisis rápido y profundo de los datos de calidad de llamadas. La siguiente guía le ayuda a decidir cuándo y por qué implementaría el CQD.
  
### <a name="when-to-deploy-cqd"></a>Cuándo implementar el CQD

 **El CQD se puede implementar para establecer una medida de calidad de llamada de línea base, incluso si una organización no experimenta problemas de calidad de llamadas.** Establecer una medición de calidad de llamada de línea base es importante porque cada organización tiene una mezcla diferente de Wi-Fi frente a trabajadores de oficina con cable y remotos. Cuando surgen problemas de calidad de llamadas, las mediciones de calidad de llamadas más recientes se pueden comparar con intervalos de tiempo anteriores. Las características de tendencias del CQD permiten detectar fácilmente los cambios en la calidad de las llamadas con el tiempo.
  
 **El CQD se puede implementar para encontrar de forma proactiva áreas problemáticas que pueden afectar a la calidad de las llamadas.** Incluso si la calidad de llamada promedio de una organización puede cumplir los objetivos establecidos por la organización, podría haber bolsillos de problemas de calidad de llamadas que se ocultan detrás de las métricas promedio. El CQD permite desglosar las métricas de calidad de llamadas en tablas dinámicas en muchas dimensiones en la base de datos QoEMetrics. Detectar valores atípicos en grupos del mismo nivel es una forma rápida de localizar de forma proactiva problemas de calidad de llamadas.
  
 **El CQD debe implementarse si hay problemas de calidad de llamadas en la organización para reducir el tiempo necesario para solucionar problemas.** El CQD puede simplificar las investigaciones de calidad de llamadas existentes al ofrecer un rendimiento rápido de los informes y capacidades de obtención de detalles dinámicos. El CQD está diseñado para muchos tipos de flujos de trabajo en investigaciones de calidad de llamadas de validación de las reparaciones en el entorno.
  
### <a name="why-deploy-cqd"></a>Por qué implementar CQD

 **El CQD debe implementarse si los informes de QoE deben producirse durante más de 3 meses de datos.** La base de datos QoEMetrics y los informes del servidor de supervisión están diseñados para conservar e informar de un pequeño conjunto de datos. La base de datos métricas de QoE está optimizada para inserciones rápidas y, por lo tanto, el rendimiento de los informes se puede ver obstaculizado por un gran volumen de llamadas o el acceso de informes de la competencia a la base de datos. La base de datos de archivo QoE de CQD proporciona una segunda copia de los datos de métricas de QoE con capacidades de retención mucho más largas. El portal también está optimizado para mostrar hasta 7 meses de datos a la vez y puede informar sobre todos los datos del archivo QoE según sea necesario.
  
 **El CQD debe implementarse si se necesitan informes de QoE personalizados.** El portal tiene una característica del Editor de informes para crear y crear prototipos de informes de forma rápida y sencilla. También pone a disposición las API de REST para el acceso mediante programación a los datos del cubo, lo que permite la presentación personalizada mediante HTML/JavaScript o muchos otros marcos. Ya no es necesario crear nuevas consultas SQL con el fin de crear vistas de datos personalizadas para los informes.
  
 **El CQD debe implementarse si la funcionalidad de informes de QoE existente no cumple la velocidad o profundidad requerida por la organización.** El CQD incluye muchos informes integrados. Los informes son útiles inmediatamente y muestran cómo la exploración en profundidad progresiva de los datos puede ofrecer información adicional en cada nivel. La jerarquía de informes también ayuda a administrar los numerosos informes de forma lógica y fomenta la creación de muchos más informes que son fáciles de obtener y comprender. El CQD no solo ofrece velocidad y flexibilidad, sino que también está optimizado para los flujos de trabajo desarrollados por la Metodología de calidad de llamadas.
  
## <a name="components-and-topologies-for-cqd"></a>Componentes y topologías para CQD

El CQD incluye varios componentes y ayuda a comprender los requisitos de cada componente y su relación entre sí para obtener la implementación más sencilla y con mejor rendimiento de la herramienta. En la tabla siguiente se describe el componente dependiente de cada componente de CQD.
  

|**Nombre del componente**|**Componente dependiente**|
|:-----|:-----|
|Archivo QoE  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Microsoft Information Services  <br/> |
|Servicio de repositorio (parte de la instalación del portal)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Para el archivo QoE y el cubo, determinadas opciones de implementación requieren business intelligence o ediciones Enterprise de Microsoft SQL Server. Consulta la sección [Requisitos de infraestructura para CQD](plan.md#Infrastructure_Req) a continuación para obtener más información.
  
![Componentes de CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuración de servidor único

Todos los componentes CQD y componentes dependientes se pueden instalar en un equipo. La configuración de cuadro único es la configuración más sencilla y permite que el CQD sea autocontenido. El CQD solo necesita tener acceso a la base de datos de métricas de QoE en el servidor de supervisión. El servidor CQD puede ser una máquina independiente, una máquina virtual o incluso el servidor de supervisión, según los recursos disponibles del equipo host y los requisitos de rendimiento. 
  
Durante la instalación, el usuario que realiza la instalación simplemente necesita proporcionar las instancias de Microsoft SQL Server y Microsoft SQL Server Analysis Services que se han configurado previamente en el equipo donde se instalará el CQD. Consulte Deploy [Call Quality Dashboard for Skype for Business Server](deploy-0.md) para obtener más información.
  
### <a name="multiserver-configuration"></a>Configuración multiservidor

En una configuración multiservidor, el archivo QoE, el cubo y el portal pueden estar en diferentes equipos. Hay dos usos principales para la configuración multiservidor:
  
- Hospedar el portal web CQD y el cubo CQD en servidores diferentes.
    
- Hospedar un portal de "desarrollo" independiente del portal de "producción". 
    
  **Hospedar el portal web de CQD y el cubo CQD en diferentes equipos.** Las organizaciones que pueden tener requisitos para separar el portal de CQD de la instalación de SQL Server o que quieran mezclar y hacer coincidir ediciones SQL Server para la instancia de SQL Server y la instancia de SQL Server Analysis Services pueden elegir instalar el portal CQD y el cubo CQD en diferentes equipos. El componente de archivo qoE también puede ser el único componente de CQD que se instala si la organización simplemente desea tener un método sostenible para archivar los datos de QoE sin alcanzar los límites de rendimiento en el servidor de supervisión.
  
![CQD de servidor único](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hospedar un portal de "desarrollo" independiente del portal de "producción".** Las organizaciones que desarrollan sus propios informes personalizados (a través de las API de REST) pueden preferir implementar instancias adicionales del portal (CQD) junto con el portal de producción al que los usuarios normales tienen acceso para investigaciones o supervisión de calidad de llamadas. El portal de desarrollo puede aislar cualquier modificación del portal desde el entorno de producción. Los portales web adicionales se pueden implementar en diferentes máquinas (que se muestran a continuación) o implementarse en diferentes directorios web en el mismo equipo (no se muestra). Para ello, el portal web de CQD adicional debe copiarse manualmente en el equipo de producción porque el proceso de configuración de CQD siempre implementa el portal web de CQD en el sitio web predeterminado con nombres de aplicación web predefinidos.
  
![Planear CQD Multi Server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologías admitidas

El CQD no combina datos de varias bases de datos QoEMetrics, como es el caso en el que hay varias topologías de Skype Empresarial Server, cada una con su propio servidor de supervisión. Cada instancia de CQD debe apuntar a una base de datos QoEMetrics. Sin embargo, dado que el CQD sacará gran parte de la carga de trabajo de informes del servidor de supervisión, las grandes organizaciones que necesitaban implementar un servidor de supervisión por topología de Skype Empresarial Server deben considerar el uso de un servidor de supervisión para todas las topologías.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisitos de infraestructura para CQD
<a name="Infrastructure_Req"> </a>

El CQD, incluidos todos sus componentes y componentes dependientes, se puede implementar en una máquina virtual, en una sola máquina o en varias máquinas. A continuación se enumeran los requisitos mínimos de software y hardware. La disponibilidad de los datos y el rendimiento de las consultas pueden variar de minutos a horas, según el número de usuarios activos de Skype Empresarial Server y el hardware y la configuración, por lo que a continuación se indican algunas medidas de rendimiento.
  
|||
|:-----|:-----|
|Para CQD 2015 <br/> |  <br/> |
|Sistemas operativos compatibles   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|Compatible SQL Server  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Para CQD 2019 <br/> |  <br/> |
|Sistemas operativos compatibles   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|Compatible SQL Server  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
CQD usa Microsoft SQL Server, Microsoft SQL Server Analysis Services y Microsoft Internet Information Services para que los requisitos mínimos de hardware y software del CQD sean básicamente los mismos que los componentes dependientes. Sin embargo, en función de los requisitos de la organización en torno a la actualización de datos (que dependerá en parte del volumen de datos de QoE que genera la organización) y el costo de implementación, deben tenerse en cuenta otras consideraciones de implementación.
  
El procesamiento de datos en el CQD se divide en dos fases principales: 
  
- Proceso de archivo QoE
    
- Procesamiento del cubo CQD
    
  **Procesamiento de archivo QoE.** La tarea de procesamiento de archivo QoE copia datos de la base de datos métricas de QoE en el servidor de supervisión a la base de datos de archivo de QoE. Hay dos situaciones en las que el tiempo de procesamiento de la tarea tendría características de rendimiento fundamentalmente diferentes. La primera es después de la instalación inicial del CQD. Cuando la tarea se ejecuta por primera vez después de una instalación nueva, la tarea de procesamiento de archivo de QoE copiará todos los datos que se encuentra en la base de datos de métricas de QoE en la base de datos de archivo de QoE. El segundo es el procesamiento periódico después de esta ronda inicial. La tarea de procesamiento de archivo de QoE se ejecutará cada 15 minutos y procesará los nuevos registros de QoE que se encuentran en la base de datos de métricas de QoE. Por lo general, el tiempo de procesamiento inicial no es un problema porque se ejecuta solo la primera vez, cuando se instala el CQD. Sin embargo, si el servidor CQD no está aprovisionado correctamente, esta tarea puede tardar varias horas. Consulte la tabla siguiente para ver los tiempos de procesamiento iniciales de QoE Archive.
  
  **Procesamiento del cubo CQD.** La tarea de procesamiento de cubo agrega los datos de la base de datos de archivo de QoE al cubo. El tiempo de procesamiento del cubo inicial y el tiempo de procesamiento posterior del cubo están determinados por la edición SQL Server Analysis Services usada para el cubo CQD. Si se usa la edición Standard, no hay diferencia entre el tiempo de procesamiento del cubo inicial y el tiempo de procesamiento del cubo posterior, ya que cada vez que se actualizan los datos del cubo, siempre será un procesamiento completo de todos los datos disponibles. (Esto significa que el tiempo de procesamiento del cubo aumenta a medida que aumenta la cantidad de datos en la base de datos de archivo QoE). Dado que Business Intelligence Edition y Enterprise Edition de SQL Server admiten particiones, si se usa alguna de las dos ediciones, solo la ejecución inicial procesará todos los datos de la base de datos de archivo QoE. En ejecuciones posteriores, cuando la tarea se desencadena cada 15 minutos, la tarea solo procesará los nuevos registros agregados a la base de datos de archivo de QoE desde la última vez que se hizo la tarea. Una vez al día, también habrá un procesamiento completo en la partición que contiene los datos del mes actual.
  
Las características de la máquina física pueden afectar al rendimiento del CQD, así como a las características de software que están disponibles en los SQL Server componentes. El componente de archivo qoE hará un uso más intensivo del disco en comparación con otros componentes, mientras que el componente cubo será más intensivo en CPU y memoria. Todos estos factores contribuyen al tiempo total de procesamiento de datos del CQD, lo que afecta directamente a la actualización y disponibilidad de los datos. Las organizaciones deben tomar decisiones sobre el hardware y el software en función de las necesidades individuales de la organización. 
  
### <a name="tested-hardware-configurations"></a>Configuraciones de hardware probadas

En esta sección se presuposición de que hay una única base de datos QoEMetrics en el entorno. 
  
**Perfiles de equipo**

|**Equipo**|**Núcleos de CPU**|**RAM**|**Archivo qoE y cubo en el mismo disco**|**Archivo qoE y SQL base de datos temporal en el mismo disco**|
|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |4   <br/> |7 GB  <br/> |Sí  <br/> |Sí  <br/> |
|4 núcleos  <br/> |4   <br/> |20 GB  <br/> |Sí  <br/> |No  <br/> |
|8 núcleos  <br/> |8   <br/> |32 GB  <br/> |Sí  <br/> |No  <br/> |
|16 núcleos  <br/> |16   <br/> |128 GB  <br/> |No  <br/> |No  <br/> |
   
**Resultados de rendimiento**

|**Equipo**|**Tamaño de base de datos de métricas de QoE**|**SQL de datos**|**Tipo de disco**|**Número de secuencias**|**Proceso de archivo inicial**|**Proceso de cubo inicial**|**Proceso de archivo posterior**|**Proceso de cubo posterior**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |900 MB  <br/> |Simples  <br/> |VHD (tamaño variable)  <br/> |0,5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Simples  <br/> |VHD (tamaño variable)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Simples  <br/> |VHD (tamaño fijo)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |Más de 30 GB  <br/> |Simples  <br/> |VHD (tamaño fijo)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Simples  <br/> |Varios discos  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Múltiples  <br/> |Varios discos  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 núcleos  <br/> |Más de 30 GB  <br/> |Simples  <br/> |Varios discos  <br/> |20 m  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 núcleos  <br/> |Más de 30 GB  <br/> |Múltiples  <br/> |Varios discos  <br/> |20 m  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 núcleos  <br/> |200 GB  <br/> |Simples  <br/> |Varios discos  <br/> |125 M  <br/> |Más de 6 días  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 núcleos  <br/> |500 GB  <br/> |Múltiples  <br/> |Ejes múltiples  <br/> |250 M  <br/> |8 días  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*No se espera que se encuentren en implementaciones reales porque la base de datos métricas de QoE tendría que tener 9 y 18 meses de datos, respectivamente, pero se proporcionan aquí para completarse.
  
### <a name="service-account-requirements"></a>Requisitos de la cuenta de servicio

Necesitará una cuenta (con acceso de lectura a QoEMetrics) que el agente de SQL en el servidor CQD pueda usar para importar datos a QoEArchiveDB.
  
Es posible que también deba configurar una cuenta independiente para que un trabajo de SSAS extraiga datos de QoEArchiveDB (este es un proceso opcional).
  
IIS usa normalmente el servicio de red como identidad del grupo de aplicaciones, pero se puede configurar para una cuenta de servicio.
  
### <a name="portal-access-control"></a>Control de acceso del portal

De forma predeterminada, cualquier usuario autenticado tiene acceso. Esto se puede cambiar mediante el uso de reglas de autorización de IIS para restringir a un grupo específico.
  
### <a name="pre-install-requirements"></a>Requisitos previos a la instalación

En estas instrucciones se supone que ya se ha instalado una base de datos de métricas de QoE y que se está ejecutando en algún lugar de la topología de Skype Empresarial Server.
  
#### <a name="hardware-requirements"></a>Requisitos de hardware

CQD usa Microsoft SQL Server, Microsoft SQL Analysis Server y Microsoft Internet Information Server para que los requisitos mínimos de hardware y software del CQD sean básicamente los mismos que los componentes dependientes. Sin embargo, en función de los requisitos de la organización en torno a la actualización de datos (que dependerá en parte del volumen de datos de QoE que genera la organización) y el costo de implementación, deben tenerse en cuenta otras consideraciones de implementación.
  
#### <a name="software-requirements"></a>Requisitos de software

Se requieren los siguientes sistemas operativos para el CQD:
  
- Windows Server 2008 R2 con IIS 7.5
    
- Windows Server 2012 con IIS 8.0
    
- Windows Server 2012 R2 con IIS 8.5

- Windows Server 2016 con IIS 10.0 (solo CQD de Skype Empresarial Server 2019)

- Windows Server 2019 (solo CQD de Skype Empresarial Server 2019)
    
Los siguientes son los servicios de rol de IIS necesarios (en orden jerárquico):
  
- Servidor web
    
  - Características HTTP comunes
    
  - Contenido estático
    
  - Documento predeterminado
    
  - Desarrollo de aplicaciones
    
  - ASP.NET
    
  - Filtros ISAPI
    
  - Diagnósticos &amp; de estado
    
  - Registro HTTP
    
  - Seguridad
    
  - Autorización de url
    
  - Autenticación de Windows
    
  - Herramientas de administración
    
  - Consola de administración de IIS
    
> [!NOTE]
>  Tenga en cuenta lo siguiente para los requisitos anteriores: > disponibles las versiones 3.5 y 4.5 de .Net Framework. Ambos son necesarios (más concretamente, se requiere 3.5 SP1).> En algunos sistemas, si ASP.NET está configurado antes de la instalación de IIS, es posible que ASP.NET no esté registrado en IIS. El problema se muestra a través de la ausencia de grupos de aplicaciones para la versión correspondiente de .Net y también falta la versión de .NET CLR en la configuración del grupo de aplicaciones. Para corregir este problema en Windows Server 2008 R2, ejecute `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` . En Windows Server 2012 y Windows Server 2012 R2, ejecutar seguido de quitar el módulo "ServiceModel" del sitio web predeterminado en las herramientas de administración de IIS Manager.> es opcional, pero se  `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` recomienda.
  
Para instalar estos requisitos con PowerShell, ejecute lo siguiente:
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Se admiten las SQL Server siguientes:
  
|||
|:-----|:-----|
| CQD 2015 <br/> |  SQL Server 2012, SQL Server 2014, SQL Server 2016  |
|CQD 2019 <br/> |  SQL Server 2017, SQL Server 2019  |
    
Se recomienda Business Intelligence o Enterprise Edition por motivos de rendimiento. Estas ediciones permiten el uso de varios archivos de partición que se pueden procesar en paralelo, lo que es beneficioso para el procesamiento de datos que abarcan varios meses o más. 
  
Aunque no se recomienda, la edición Standard también es compatible. El procesamiento se restringirá a una sola partición (que debe configurarse durante la instalación). 
  
En todos los casos, deben instalarse "Servicios del motor de base de datos" y "Analysis Services". Se recomienda, pero no es necesario, instalar también la característica "Herramientas de administración- Completa", que agrega SQL Server Management Studio compatibilidad con Analysis Services. La pantalla de selección de características debe ser como la figura.
  
![SQL Server requisitos de características](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Al configurar la configuración de SSAS, en la configuración de Analysis Services, establezca "Modo de servidor" en "Modo multidimensional y de minería de datos". 
  
Para obtener ayuda adicional para instalar y configurar SQL Server de inteligencia empresarial, vea Instalar Analysis Services en modo multidimensional y de [minería de datos.](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx)
  
#### <a name="account-requirements"></a>Requisitos de la cuenta

Se recomiendan tres cuentas de servicio de dominio en el principio de privilegios mínimos: 
  
- Una que ya tiene una entidad de seguridad de inicio de sesión para la base de datos de métricas de QoE (con privilegios de db_datareader) y una entidad de seguridad de inicio de sesión en la instancia de SQL Server de archivo de QoE (necesaria para crear un objeto de servidor vinculado durante la instalación). Esta cuenta se usará para ejecutar el paso "Datos de archivo qoE" del trabajo SQL Server agente.
    
    > [!NOTE]
    > Si está trabajando en un entorno muy bloqueado, debe comprobar que a esta cuenta de servicio se le conceden efectivamente los derechos de usuario "Inicio de sesión como un trabajo por lotes" y "Permitir inicio de sesión local" tanto en la base de datos de supervisión de métricas de QoE SQL Server como en la base de datos de archivo de QoE SQL Server.
    
- Uno que se usará para ejecutar el paso "Cubo de proceso" del trabajo SQL Server agente. El programa de instalación creará una entidad de seguridad de inicio de sesión en la base de datos de archivo qoE (con privilegios de lectura y escritura) y también creará un miembro en el rol QoE (con privilegios de control total) para el cubo.
    
- Uno que se usará para ejecutar el proceso de trabajo de IIS para los portales web y las API web. El programa de instalación creará una entidad de seguridad de inicio de sesión en la base de datos de archivo QoE (con privilegios de lectura), una entidad de seguridad de inicio de sesión para la base de datos de repositorio (con privilegios de lectura y escritura) y un miembro de QoERole (con privilegios de control total) para el cubo. 
    
    > [!NOTE]
    > Cuando la base de datos de archivo de QoE y la base de datos de repositorio se hospedan en el mismo SQL Server, solo se crea una entidad de seguridad de inicio de sesión con dos asignaciones de usuario. 
  
Las dos primeras cuentas se pueden considerar lógicamente como "cuentas de servicio back-end" y la última cuenta es una "cuenta de servicio front-end". Aunque no se recomienda, es posible usar una sola cuenta en todos los casos.
  
> [!NOTE]
> La cuenta de usuario que inicia la instalación también debe tener acceso de lectura a la base de datos de métricas de QoE (además de tener derechos de administrador del equipo en el servidor de base de datos de archivo de QoE donde debe realizarse la instalación). 
  
## <a name="capacity-planning"></a>Planeamiento de la capacidad
<a name="Infrastructure_Req"> </a>

El CQD está diseñado para un impacto mínimo en QoEMetrics: el código se ha optimizado para no bloquear datos y los trabajos de importación son ajustables.
  
El tipo de hardware que se va a usar depende de los requisitos para la rapidez con la que se deben ejecutar las sincronizaciones. El tamaño del disco es el siguiente:
  
- QoEArchive es ~1,5x más grande que QoEMetrics DB inicialmente
    
- El cubo SSIS comprime los datos casi 10 veces en comparación con la base de datos
    
- Los datos se particiona mensualmente; se pueden eliminar las particiones
    


---
title: Calidad de la experiencia de guía de revisión de equipos de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guía para analizar el rendimiento de los medios de comunicación en tiempo real para Microsoft Teams utilizando el panel de calidad llamar (CQD).
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42af71e9062b68da6e9d3bc77a6c067eee35ec92
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="quality-of-experience-review-guide"></a>Calidad de la Guía de revisión de experiencia

Esta guía es acerca de la fase de valor de la unidad de Teams de Microsoft y Skype para los negocios en línea. Puede [descargar una versión en Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) de esta guía.

## <a name="introduction"></a>Introducción

Para tener mayor impacto sobre la mejora de la experiencia del usuario, las organizaciones necesitan que controle las áreas clave que se muestran en la figura siguiente.
Áreas adicionales incluyen la identificación de las tareas operativas, estableciendo objetivos para la métrica de calidad, determinar las métricas a utilizar para medir el éxito organizativo y áreas de investigación de restricción según sea necesario.

![Áreas clave para la calidad de la experiencia del usuario incluyen audio, confiabilidad, encuestas al usuario, los dispositivos y clientes.](media/quality-of-experience-review-guide-image1.png)

_Figura 1 - áreas operativas clave tratadas a lo largo de este documento_

Continuamente evaluar y remediar las zonas descritas en este documento, podrá reducir su potencial de afectar negativamente a la calidad de la experiencia de los usuarios. Problemas de experiencia de usuario más encontrados en una implementación pueden agruparse en las siguientes categorías:

-   Configuración de firewall o proxy incompleto

-   Mala cobertura Wi-Fi

-   No hay suficiente ancho de banda

-   VPN

-   Versiones de cliente anticuado o incompatible

-   Dispositivos de audio integrados o no optimizados

-   Subredes problemáticas o dispositivos de red

A través de una planificación adecuada y diseño antes de implementar los equipos o Skype para los negocios en línea, puede reducir la cantidad de esfuerzo que será necesario mantener experiencias de alta calidad.

Esta guía se centra en usar panel de calidad llamar (CQD) en línea como herramienta principal para informar e investigar cada área, con especial énfasis en audio para maximizar la adopción y el impacto. Todas las mejoras realizadas a la red para mejorar la experiencia de audio se traducirán directamente a mejoras en el uso compartido de escritorio y vídeo.

Para acelerar la evaluación, se incluyen dos plantillas CQD comisariadas: uno para administrar todas las redes y la otra se filtra para administrado sólo redes (internas). Aunque los informes de la plantilla de todas las redes están configurados para mostrar la información de red y la creación, aún puede utilizarse mientras trabaje para recopilar y carga de información de edificio. Cargando información en CQD de compilación permite al servicio mejorar el reporting al agregar información personalizada de edificio, la red y la ubicación al diferenciar interno de subredes externas. Para obtener más información, consulte [asignación de edificio](#building-mapping) más adelante en este documento.

### <a name="what-is-the-cqd"></a>¿Qué es el CQD?

Utilice el panel de calidad llamar (CQD) para obtener información sobre la calidad de las llamadas realizadas mediante el uso de equipos y Skype para servicios de negocios. CQD está diseñado para ayudar a Skype para los administradores de negocios y los equipos y los ingenieros de red optimizan la red. CQD examina la información agregada para toda una organización donde patrones generales pueden ponerse de manifiesto, permitiendo que el personal realizar evaluaciones informadas de la calidad de las llamadas. CQD proporciona informes de métricas de llamada que brindar información sobre la calidad general de las llamadas, llamada confiabilidad y experiencia del usuario.

> [!NOTE]
> CQD no contiene ninguna información personalmente identificable (PII). PII es información que puede utilizarse por sí solo o junto con otra información para identificar, ponerse en contacto con o busque a una sola persona, o para identificar a un individuo en contexto. 

### <a name="intended-audience"></a>Audiencia objetivo

Este documento está pensado para ser utilizado por los participantes de clientes y socios con funciones como arquitecto y principal de colaboración, consultor, especialista en administración y adopción de cambio, soporte/Help Desk conducir, red llevar, conducir de escritorio y Administrador de TI.

Este documento también está pensado para ser utilizado por el Campeón de calidad designado.
Para obtener más información, vea [la función Campeón de calidad](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Requisitos previos

Antes de utilizar a esta guía, asegúrese de que tiene los inquilinos adecuados [roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) asignados para que puedan acceder CQD.

-   **Función de administrador Global de office 365:** Tiene acceso a todas las funciones administrativas en el paquete Office 365 de servicios en el plan, incluyendo Skype para el negocio.

-   **Skype para la función de administrador de empresa:** Configura Skype para el negocio de la organización y es capaz de ver todos los [informes de actividad](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración de Office 365. Esta función es necesaria incluso si se implementación sólo equipos.

Como alternativa, puede asignar la siguiente función a una cuenta de usuario de Office 365 para permitir el acceso a las características de informes sólo.

-   **Lector de informes:** Puede ver todos los [informes de actividad](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración de Office 365, los informes desde el [paquete de contenido de Office 365 adopción](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)e informes CQD.

Comprender los conceptos clave de CQD ayuda a maximizar el impacto que puede hacer para mejorar la experiencia de los usuarios con equipos o Skype para los negocios en línea.
Encontrará recursos adicionales en el [Apéndice](#other-resources).

## <a name="what-is-quality"></a>¿Cuál es la calidad?

Cuando se habla de calidad en equipos y Skype para el negocio, es importante definir el término para lograr una comprensión común. Calidad, tal como se define aquí, es una combinación de servicio métricas y experiencia del usuario.

![Métricas de servicio se componen de las versiones de llamada mala relación, confiabilidad, extremos y dispositivos y cliente. Experiencia del usuario final se compone de la percepción del usuario de la calidad del servicio.](media/quality-of-experience-review-guide-image2.png)

_Figura 2 - ¿cuál es la calidad?_

### <a name="define-your-target-metrics"></a>Definir la métrica del objetivo

Esta sección describe las métricas de servicio de núcleo que utilizamos para evaluar cómo servicios experiencia de salud. Al continuamente evaluar y conducir los esfuerzos para mantener estas métricas debajo de destino, ayudaremos a garantizar la que calidad de las llamadas consistente y fiable de experiencia de los usuarios. Para comenzar, se proporcionan los siguientes destinos.
Vamos a explicar brevemente la diferencia entre una red administrada y no administrados:

-   Una red *administrada* puede ser influenciada y controlada por la organización.
    Esto incluye la LAN interna, WAN remoto y VPN.

-   Una red *no administrada* no puede ser influenciada o controlada por la organización. Un ejemplo de una red no administrada es una red de hotel o un aeropuerto.

_Tabla 1: medidas de evaluación de estado de destino principales_

|               | Calidad para redes administradas | Confiabilidad para redes administradas |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Nombre métrica   | Audio deficiente llamar % coeficiente      | Configuración de la llamada % de errores            | Llamar a colocar % de errores |
| Destino de ejemplo | \<3%                         | \<% 1                             | \<4%                 |

Es importante analizar y definir los objetivos de la organización para cumplir los objetivos de su negocio. Idealmente, debe identificar estos destinos antes de la implementación.

#### <a name="audio-pcr-"></a>% De audio PCR 

Audio deficiente llame al cociente (PCR) representa el porcentaje global de la organización de las llamadas que tienen una calidad de audio deficiente. Esta métrica está pensada para resaltar las áreas donde la organización puede centrarse en que el impacto más fuerte hacia reduce este valor y mejorando la experiencia del usuario, lo que redes administradas son el enfoque principal cuando se mira la PCR. Los usuarios externos también son importantes, pero difiere de las investigaciones sobre una base organizativa y usuario.
Considere proporcionar recomendaciones para los usuarios externos y mirar las llamadas externas independientemente de la organización global.

#### <a name="call-setup-failures-"></a>Configuración de la llamada % de errores 

Esto representa cualquier sesión de medios que no se ha podido establecer. Dada la gravedad del impacto en la experiencia del usuario mide aquí, el objetivo es reducir este valor a como cerca de cero como sea posible. Un valor alto de esta métrica es más común en nuevas implementaciones de reglas del cortafuegos incompleto que una implementación madurada, pero sigue siendo importante inspeccionar de forma regular. A medida que crezca su rigor operacional, puede expandir esta métrica para incluir las cargas de trabajo de vídeo y uso compartido de escritorio.

#### <a name="call-drop-failures-"></a>Llamar a colocar % de errores 

Esto se aplica a una carga de trabajo de audio en la sesión terminó inesperadamente. A medida que crezca su rigor operacional, puede expandir esta métrica para incluir las cargas de trabajo de vídeo y uso compartido de escritorio.

### <a name="service-metrics"></a>Medidas de servicio

Objetivos de métricas de servicio constan de las medidas específicas basadas en cliente.

#### <a name="pcr"></a>PCR

La base para determinar si una llamada se clasifica como pobre es mediante la relación llamada deficiente (PCR). PCR se compone de las cinco métricas de red que se describe en la tabla siguiente. Para que una llamada a ser clasificado como deficiente, sólo una métrica debe superar el umbral definido. Para obtener más información acerca del proceso de clasificación de llamadas, consulte [esta entrada de blog](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tabla 2 - métrica llamada deficiente del servicio_

| Métrica                                           | Descripción                                                                                                                                                                                                                                                                                                                                                                  | Experiencia de usuario                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Vibración \>30 ms                                   | Éste es el cambio promedio de retardo entre envíos sucesivos de paquetes. Equipos y Skype para empresas pueden adaptarse a algunos niveles de vibración mediante el almacenamiento en búfer. Es sólo cuando la variación supera el búfer que un participante avisos de los efectos de vibración.                                                                                                                         | Los paquetes que llegan a diferentes velocidades de causan del locutor sonido robótico.                                                                                       |
| Velocidad de pérdida de paquetes \>0,1 o 10%                    | Esto a menudo se define como un porcentaje de paquetes que se pierden. Pérdida de paquetes directamente afecta a la calidad de audio, desde pequeñas, individuo los paquetes perdidos que casi no afectan a las pérdidas de ráfagas de extremo a extremo que causa el audio para cortar completamente.                                                                                                                               | Los paquetes se perdidos y que no llegan a su destino provocarán lagunas en los medios de comunicación, resultante en palabras y sílabas perdidas y entrecortado vídeo y uso compartidos. |
| Tiempo de ida y vuelta \>500 ms.                         | Esto es el tiempo que se tarda en obtener un paquete IP desde el punto al punto B y vuelve al punto A. Este retraso de propagación de la red está ligado a la distancia física entre los dos puntos y la velocidad de la luz e incluye una sobrecarga adicional adoptada por los diversos dispositivos en la ruta de acceso de red.                                                                                  | Los paquetes que tarda demasiado tiempo en llegar a su destino provocarán un efecto transmisor-receptor portátil.                                                                                 |
| Promedio de degradación NMOS \> 1.0                  | Uno o más de estas métricas de la red, aunque individualmente no eran defectuosas, causado conjuntamente la red [Significa la puntuación de opinión](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) (NMOS) para colocar por más de un punto. Esto no significa necesariamente la conexión de red es deficiente, pero suficiente problemas ocurrieron durante la llamada que se ha reducido la calidad. | Es una combinación de vibración, la pérdida de paquetes, y, en menor grado, aumenta el tiempo de ida y vuelta. El usuario puede estar experimentando una combinación de estos síntomas.          |
| Promedio de muestras ocultas \> 7% o 0.07 | Uno o más de estas métricas de la red, aunque individualmente no eran defectuosas, provocó el cliente para repararse a sí mismo los medios de comunicación. Una muestra de audio oculta es una técnica utilizada para suavizar la transición abrupta que normalmente estaría causada por paquetes de red perdidos.                                                                                                                | Valores altos indican que niveles significativos de encubrimiento de la pérdida se aplica y resultó en audio distorsionado o perdido.                                                  |

#### <a name="client-and-device-readiness"></a>Preparación del cliente y el dispositivo

Necesita una estrategia sólida de cliente y el dispositivo para garantizar que los usuarios tengan una experiencia de usuario coherente y positiva. Cada estrategia de preparación de unidad algunos principios clave.

##### <a name="client-readiness"></a>Preparación del cliente

Una estrategia de preparación del cliente seguro garantiza que los usuarios están ejecutando la versión más reciente del cliente mientras que goza de la mejor experiencia posible.
Microsoft parches rutinariamente el Skype para cliente de negocios; asegurar que la mantenga actualizada en su entorno es vital para el éxito general.

Se recomienda que no permita que sus versiones cliente retrasarse por más de seis meses. Si utilizas Office Click-to-Run, usted está ya siendo actualizados por el servicio. Utilice el incluye [Un informe de cliente](#determine-client-versions), tal como se describe más adelante en esta guía, para ayudarle con este proceso. También puede aprovechar los informes de ejemplo llame a Mi velocidad para mejorar su estrategia de preparación del cliente.

> [!IMPORTANT]
> Actualmente, los clientes de equipos distribuidos y actualizan automáticamente a través de la red de entrega de contenido de Azure y se mantendrán actualizados por el servicio. Preparación del cliente y las actividades de investigación no son aplicables a los equipos.


##### <a name="device-readiness"></a>Preparación del dispositivo

No hay una estrategia única puede afectar a la experiencia del usuario más de su estrategia de preparación del dispositivo. La mayoría de las organizaciones están encantadas de quitar los dispositivos innecesarios de los usuarios (por ejemplo, los teléfonos de escritorio u otros dispositivos de audio dedicados) y suele ser una justificación del negocio principales para cambiar a los equipos o Skype para el negocio. Sin embargo, esas mismas organizaciones a veces dudan en proporcionar dispositivos de sustitución, incluso si los dispositivos son menos costosos. Hoy en día los equipos portátiles y PCs, aunque equipados con micrófono incorporado y altavoces, no están optimizados para voz de clase empresarial sobre IP (VoIP). A menudo esto crea una experiencia deficiente para todos los participantes, especialmente si el altavoz está en un entorno ruidoso. Programa de certificación de dispositivo de Microsoft garantiza que cuando un usuario participa en una llamada de teléfono mediante el uso de cualquier dispositivo certificado para equipos o Skype para empresas, produce una experiencia que es superior de un dispositivo no certificados.

Recomendamos siempre que equipos y Skype para usuarios de negocios utilizan un certificadas auriculares o altavoces al participar en una llamada de voz utilizando un cliente de escritorio.
Para obtener más información acerca de dispositivos con certificado de Microsoft, revise este [artículo acerca de los teléfonos y dispositivos calificados](https://technet.microsoft.com/office/dn788944.aspx). Utilice el [Dispositivo informe](#devices-investigations), más adelante en esta guía para obtener ayuda con la administración de los dispositivos. También puede utilizar los informes de ejemplo llame a Mi velocidad para mejorar su estrategia de preparación del dispositivo.

### <a name="user-experience"></a>Experiencia de usuario

Análisis de la experiencia del usuario es más que la ciencia, porque las métricas obtenidas aquí no siempre significa que hay un problema con la red o servicio, pero en su lugar, indican que el usuario percibe un problema. Microsoft ofrece un mecanismo de encuesta integrada, conocida como velocidad de mi llamar (RMC), para ayudar a medir la experiencia global del usuario. RMC le ayudará a responder las preguntas siguientes desde la perspectiva de los usuarios:

-   ¿Sé cómo utilizar la solución?

-   ¿Es la solución intuitiva y fácil de usar y compatible con mis necesidades de comunicación diaria?

-   ¿La solución ayudarme a realizar mi trabajo?

-   ¿Cuál es mi percepción general de la solución?

-   ¿Puedo utilizar la solución en cualquier punto en el tiempo, independientemente de donde estoy?

-   ¿Puedo configurar y mantener una llamada?

#### <a name="rmc"></a>RMC

RMC está integrado en los equipos y Skype para el negocio y se configura automáticamente para que se muestre después de que uno de cada 10 llamadas o 10 por ciento de todas las llamadas. Esta breve encuesta pregunta al usuario para valorar la llamada y proporcionar un contexto poco de por qué la calidad de la llamada podría haber sido pobre. Una clasificación de uno o dos se considere baja, es bueno tres o cuatro y cinco es excelente. Aunque es un poco de un indicador de revestimiento, esta es una métrica útil para descubrir problemas que pueden faltar las métricas de servicio.

> [!NOTE]
> Hasta que se indique los usuarios responder a encuestas RMC dando buena retroalimentación además respuestas incorrectos, normalmente regresar como muy negativos. La mayoría de usuarios sólo responde cuando es mala calidad de la llamada. Por este motivo, los informes RMC podrían sesgar al lado deficiente aunque métricas de servicio son buenos. 


Puede utilizar CQD para informar sobre las respuestas del usuario RMC y se incluyen ejemplos de informes en la plantilla CQD. Sin embargo, no se abordó en detalle en esta guía. Para obtener más información acerca de RMC en Skype para los negocios en línea y orientación para educar a los usuarios dar respuestas útiles de RMC, consulte este [blog post](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Categorías de calidad

El éxito de una implementación de alta calidad y confiable en marcha depende de su rigor operacional del edificio. En concreto, preste especial atención a las tres categorías que se ilustra en la figura siguiente; Estos son el enfoque de esta guía:

-   **Red:** Calidad de audio centrado en la métrica PCR, el uso TCP, subredes con cables e inalámbricas e identificar el uso de servidores proxy HTTP y VPN.

-   **Extremos:** Dispositivos de audio y la versión del cliente (Skype para empresas sólo).

-   **Administración de servicios:** Esta categoría consta de dos partes:

    -   En primer lugar es responsabilidad de Microsoft para administrar y mantener los equipos y Skype para servicios empresariales en línea.

    -   En segundo lugar son tareas que debe administrar su organización para garantizar el acceso confiable al servicio, como actualizar la información de creación y mantenimiento de firewalls para nuevas direcciones IP de Office 365 como infraestructura se agrega al servicio.

![Las categorías de calidad en una organización: administración, extremos y la red de servicio.](media/quality-of-experience-review-guide-image3.png)

_Figura 3 - categorías críticas para los equipos y Skype para la implementación de los negocios en línea_

El gráfico siguiente describe las tareas que debe ejecutar para cada categoría. Recomendamos que ejecute estas tareas una vez por semana, como mínimo.

La primera vez que realice estas tareas tendrá más esfuerzo que las iteraciones posteriores, ya que muchas de estas categorías requieren que valide sus configuraciones de implementación. Una vez que haya alcanzado el estado que desee, cumpliendo los objetivos que ha definido, estas tareas le ayudará a mantener ese estado.

#### <a name="service-management-tasks"></a>Tareas de administración de servicio

En un mundo de la nube en primer lugar, debe realizar ciertas tareas de administración de servicios para mantener experiencias de usuario de alta calidad. Estas tareas van desde asegurar que hay suficiente ancho de banda para alcanzar el servicio sin saturar los vínculos de internet, validando que la calidad de servicio (QoS) está implementada en todas las áreas de la red gestionada, y, por último, permanecer en la cima [Office 365 IP rangos en los servidores de seguridad](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Tareas de red

Existen dos categorías de tareas de red: calidad y confiabilidad. Confiabilidad se centra en medir la capacidad del usuario para hacer llamadas con éxito y permanecer conectado. Calidad se centra en la telemetría agregada enviada a equipos y Skype para los negocios en línea por el cliente del usuario durante y después de la llamada ha finalizado.

Dado el impacto crítico con fiabilidad en la experiencia del usuario, empezar a evaluar e investigar esas métricas antes de profundizar en la calidad.

#### <a name="endpoints-tasks"></a>Tareas de extremos

La tarea principal de esta categoría es validar las versiones de cliente están ejecutando Skype para el negocio en generaciones de escritorio de los últimos seis meses para asegurarse de que los usuarios están obteniendo los beneficios de las optimizaciones continuas realizadas para el Skype para el cliente de escritorio de negocios. Además, esto simplifica las tareas generales de administración del cliente y proporciona una experiencia de usuario coherente.

La otra área importante es supervisar los dispositivos que prevalecen en la implementación e impulsar el uso de dispositivos certificados para proporcionar la mejor experiencia de usuario.

> [!IMPORTANT]
> Actualmente, los clientes de equipos distribuidos y actualizan automáticamente a través de la red de entrega de contenido de Azure y se mantendrán actualizados por el servicio. Preparación del cliente y las actividades de investigación no son aplicables a los equipos.


## <a name="using-the-reports"></a>Uso de los informes

Esta sección describe los conceptos básicos del trabajo con CQD. Se proporcionan directrices para los siguientes temas:

-   Buscar el ID de inquilinos

-   Informar sobre los equipos frente a Skype para empresas

-   En primer lugar frente a las clasificaciones de segundo

-   Dimensiones, medidas y filtros

-   Secuencias frente a llamadas

-   Buenas, pobre y sin clasificar las llamadas

-   Introducción a CQD

-   Editar informes en CQD

-   Informes de filtrado de CQD

Para obtener información más detallada formación y recursos, consulte el [Apéndice](#other-resources).

### <a name="tenant-id"></a>Id. de inquilinos

Algunos informes CQD requieren que incluyen un filtro para el ID de inquilinos. Debido a la forma que CQD agrega datos, telemetría participante federado está incluido.
Aunque esto puede resultar valiosa al analizar las métricas de llamada deficiente, informes de cliente y dispositivos requieren el filtrado de datos para un arrendatario específico para excluir la telemetría participante federado. Si no conoce el identificador de inquilinos, puede utilizar uno de los métodos siguientes para encontrarlo.

Requisitos de permiso

-   Función de administrador global

-   Skype para la función de administrador de empresa

#### <a name="azure-ad-portal"></a>Portal de Azure AD

1.  Iniciar sesión en el portal de Azure de Microsoft:<https://portal.azure.com>

2.  Seleccione **Active Directory Azure**.

3.  En **Administrar**, seleccione **Propiedades**. El identificador de inquilinos se muestra en el cuadro **Identificador de directorio** .

#### <a name="azure-powershell"></a>PowerShell de Azure

1.  [Instalar el módulo de administración de servicios de PowerShell de Microsoft Azure](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Abra una ventana de comandos de PowerShell de Azure y ejecute el siguiente script, escribir las credenciales de Office 365 cuando se le solicite:  
    **Inicio de sesión AzureRmAccount**

3.  El identificador de inquilinos se muestra en la salida.

#### <a name="skype-for-business-online-admin-center"></a>Skype para el centro de administración de negocios en línea

1.  Vete a<https://portal.office.com>

2.  Inicie sesión con su cuenta organizativa del Administrador de inquilinos.

3.  Seleccione **Skype para los negocios** en **Centros de Admin**.

4.  El ID de inquilinos aparece como el **ID de la organización** en la página de bienvenida.

#### <a name="skype-for-business-online-using-powershell"></a>Skype para los negocios en línea con PowerShell

1.  [Conectarse a Skype para el negocio en línea a través de PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Ejecute el siguiente comando:  
    **.Tenantid (get-cstenant)**

3.  Se muestra el ID de inquilinos como un GUID.

### <a name="teams-vs-skype-for-business"></a>Los equipos frente a Skype para empresas

CQD puede informar sobre equipos y Skype para telemetría de negocio. Sin embargo, puede haber ocasiones cuando desea desarrollar un informe que mirar la telemetría equipos independiente de Skype para el negocio.

#### <a name="summary-reports"></a>Informes de resumen

Para modificar la página de informes de resumen para mirar sólo equipos o Skype para el negocio, seleccione el menú desplegable de **Filtro de producto** en la parte superior de la pantalla y, a continuación, seleccione el producto que desee.

![Captura de pantalla del panel de calidad llamar al reflejar un menú desplegable menú que muestra la opción de filtrar por carga de trabajo.](media/quality-of-experience-review-guide-image4.png)

_Figura 4 - Seleccione un filtro de producto_

#### <a name="detailed-reports"></a>Informes detallados

Para filtrar un informe detallado, agregue el filtro **Es equipos** al informe y establézcala en True o False. Para obtener más información, consulte [modificar informes](#editing-reports) más adelante en esta sección.

![Captura de pantalla del panel de calidad llame que representan el sistema de almacenamiento que se puede agregar a un informe detallado.](media/quality-of-experience-review-guide-image5.png)

_Figura 5: agregar un filtro de Teams de Microsoft a un informe_

### <a name="dimensions-measures-and-filters"></a>Dimensiones, medidas y filtros

Una consulta CQD correcta contiene tres de los siguientes parámetros:

-   **Dimensión:** ¿Cómo deseo en los datos de tabla dinámica.

-   **Medida:** Lo que quiero informar sobre.

-   **Filtro:** ¿Cómo desea reducir el conjunto de datos que devuelve la consulta.

Otra forma de analizar esto es una dimensión es la función de agrupación, una medida es que los datos que me interesa y un filtro es cómo limitar los resultados a aquellos que son relevantes para la consulta.

Un ejemplo de una consulta correcto es "Mostrarme pobre secuencias [medida] por subred [dimensión] para generar 6 [filtro]."

Para obtener más información, consulte [dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm).

Para dimensiones, medidas y filtros para los informes que se utilizan en las plantillas CQD, consulte el [Apéndice](#CQD-training).

### <a name="first-vs-second"></a>Primero y segundo 

Muchas de las dimensiones y medidas en CQD se clasifican como primera o segunda.
CQD no utilice campos de llamador y destinatario: estos han sido ha cambiado el nombre _primero_ y _segundo_ porque hay pasos intermedios entre el llamador y el destinatario. La siguiente lógica determina qué punto de conexión implicado en la transmisión o la llamada se etiqueta como primero:

-   En primer lugar siempre será un extremo de servidor (servidor de conferencias, servidor de mediación etc.) si un servidor está involucrado en la secuencia o la llamada.

-   En segundo lugar siempre será un extremo de cliente a menos que la secuencia es entre dos extremos de servidor.

-   Si ambos extremos son del mismo tipo, la decisión de cuál es el primera se basa en el orden interno de la categoría de agente de usuario. De este modo se asegura que el orden es coherente.

Para obtener más información acerca de cómo determinar el primer o el segundo extremo cuando son iguales, consulte [dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Flujo frente a llamada

Es necesario comprender la diferencia entre una llamada y una secuencia para elegir correctamente qué dimensiones o medidas que se utilizan en CQD.

**Secuencia:** Existe una secuencia entre dos extremos. Hay sólo una secuencia para cada dirección, y dos secuencias son necesarios para la comunicación. Secuencias son útiles para analizar redes o edificios. En algunos casos, la llamada y secuencia se utilizan en el nombre (por ejemplo, llamada secuencia de instalación o secuencia de texto de llamada).
Estos aún se clasifican como secuencias solo.

**Llamar:** Una llamada es una agrupación de todas las secuencias de todos los participantes. Consiste en una llamada — como mínimo — dos secuencias. Una sola llamada tendrá dos participantes con un mínimo de una secuencia. Llamadas son útiles para analizar las tendencias en el tiempo.

Para mayor información sobre si la medida o dimensión hace referencia a una llamada o una secuencia, consulte [dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Buenas, pobre y sin clasificar las llamadas

Una llamada se clasifica como buena, deficiente o sin clasificar. Dediquemos un momento a hablar sobre cada una de ellas con más detalle.

**Bueno o malo:** Una llamada buena o mala consta de una llamada que contiene un conjunto completo de métricas de servicio, para el que se generó un informe completo de la calidad de la experiencia.
Determinar si una llamada es bueno o malo es descrito [anteriormente en esta guía](#pcr).

**Sin clasificar:** Una llamada sin clasificar no contiene un conjunto completo de métricas de servicio. A menudo son llamadas de cortas duración, normalmente menos de 60 segundos, donde no se ha podido calcular promedios y no se genera un informe de calidad.

### <a name="access-cqd-online"></a>Acceso en línea CQD

Puede tener acceso a CQD de dos maneras.

-   Vaya a <https://cqd.lync.com>.

-   Vaya a **Skype para el centro de administración de negocios** \> **Herramientas**y seleccione el vínculo a CQD, como se muestra a continuación.

![Captura de pantalla mostrando seleccionados en el panel de la barra de navegación izquierda y el vínculo a "Skype para negocios en línea llame al panel de calidad" seleccionado "herramientas".](media/quality-of-experience-review-guide-image6.png)

_Figura 6 – acceso a CQD a través del Skype para el centro de administración de negocios_

### <a name="getting-started"></a>Introducción

Cuando explore en primer lugar a CQD, verá la página de informes de resumen. La mayoría de los informes descritos en esta guía son informes detallados personalizados. Para empezar a usar los informes detallados, seleccione **Informes de resumen** en la parte superior de la página y, a continuación, elija **Informes detallados**.

![Captura de pantalla de la depcting panel de calidad llamar a los distintos tipos de informes que están disponibles.](media/quality-of-experience-review-guide-image7.png)

_Figura 7 - explorar informes detallados_

La página de informes detallados de CQD aspecto de la figura que se muestra a continuación.

![Captura de pantalla de la página de informe detallado de CQD y los distintos elementos que componen un informe.](media/quality-of-experience-review-guide-image8.png)

_Figura 8 - página de informes detallados_

1.  El panel de resumen muestra el contexto para el conjunto de informes que aparece a la derecha.

2.  Puede seleccionar **Editar** en el panel Resumen para establecer las propiedades de informe – nivel (incluyendo la altura del eje y).

3.  La ruta de exploración ayuda a los usuarios a identificar su ubicación actual en la jerarquía del conjunto de informe.

4.  Informes que tienen informes secundarios se muestran con un enlace. Al seleccionar el vínculo, puede desglosar los informes secundarios.

Seleccione los gráficos de barras y líneas de tendencia para mostrar valores detallados. El informe que tiene el foco mostrará el menú de acción: **Editar**, **Clone**, **Eliminar**, **Descargar**y **Exportar el árbol de informes**.

### <a name="editing-reports"></a>Editar informes

Al seleccionar **Editar** en el menú de acción de un informe, abra Editor de consultas. Cada informe está respaldada por una consulta. Un informe es una visualización de los datos devueltos por su consulta. El Editor de consultas es una interfaz de usuario para la edición de estas consultas, además de las opciones de visualización para el informe, como se ilustra en la figura siguiente.

![Captura de pantalla de la página de informe detallado de CQD y los distintos elementos que componen un informe cuando el informe se está editando.](media/quality-of-experience-review-guide-image9.png)

_Figura 9: Editor de informes_

1.  Elija filtros, medidas y dimensiones del panel izquierdo. Señala a un valor existente, muestra un botón Cerrar (**X**) puede seleccionar Quitar el valor.

    1.  Seleccionando la dimensión o medida, puede cambiar el título, editando el campo **título** . También puede cambiar el orden seleccionando el azul hacia arriba o hacia abajo las flechas en el panel superior.

    2.  Seleccionar (**+**) junto al encabezado de abre el cuadro de diálogo para agregar una nueva dimensión, medida o filtro.

    3.  Escriba las primeras letras de la dimensión, una medida o un filtro en la **Buscar un** campo para filtrar la lista facilita la búsqueda.

2.  El panel superior muestra las opciones de personalización de gráficos.

3.  El Editor de consultas, se muestra una vista previa del informe.

4.  Utilice el cuadro de **Edición** en la parte inferior de la pantalla para crear o editar una descripción detallada del informe.

### <a name="filtering-reports"></a>Filtrado de informes

Las plantillas proporcionadas incluye varias consultas integradas y filtros de informe. Las secciones siguientes describen los filtros más comunes utilizados en las plantillas.

#### <a name="cqd-filter"></a>Filtro CQD

Puede utilizar el filtro CQD, o el filtro de URL para filtrar temporalmente cada consulta de informe. Es el filtro CQD más comunes que va a utilizar filtrar los informes para excluir la telemetría participante federado. Se recomienda marcar este filtro para que se convierta en la vista predeterminada. Excluir datos federados de informes CQD es útil cuando está remediar administrados edificios o redes donde pueden influir en su informe datos federados.

Para implementar un filtro CQD, en la barra de direcciones del explorador, añada lo siguiente al final de la dirección URL:

/Filter/ [AllStreams]. [Segundo inquilino Id] \|[El INQUILINO ID aquí]

**Ejemplo:**  
https://cqd.lync.com/cqd/\#/ 02-1234567/2018/filtro / [AllStreams]. [Segundo inquilino Id] \|[TENANTID] & inquilinos = TENANTID

> [!NOTE]
> El ejemplo de dirección URL anterior es para obtener únicamente la representación visual. Utilice el vínculo CQD predeterminado de <https://cqd.lync.com>.

#### <a name="query-filters"></a>Filtros de consulta

Filtros de consulta se implementan mediante el Editor de informes. Estos filtros se utilizan para reducir el número de registros devueltos por CQD, minimizando así el tamaño general del informe. Esto es especialmente útil para el filtrado de redes no administradas.
Los filtros siguientes usan expresiones regulares (RegEx).

_Tabla 3 - filtros de consulta_

| Filtro               | Descripción          | Ejemplo de filtro de consulta CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Valores en blanco         | Algunos filtros no tienen la opción para filtrar los valores en blanco. Para filtrar manualmente valores en blanco, utilice la expresión en blanco y establezca el filtro igual a o no igual a, dependiendo de sus necesidades.                                                                                                                             | Nombre del segundo edificio \< \> \^ \\s\*\$                       |
| Subredes domésticas populares | Sin un archivo válido del edificio para separar administrado desde redes no administradas, obtener incluirá redes domésticas en los informes. Estas subredes domésticas quedan fuera del alcance de su control y pueden excluirse rápidamente de un informe. Subredes domésticas popular, tal como se define en esta guía son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | La segunda subred \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Dentro y fuera   | Se utiliza para filtrar un informe de (interior) administrado o no administrado (fuera). La plantilla CQD administrada ya está preconfigurada con estos filtros.                                                                                                                                                                                | En segundo lugar dentro de Corp = dentro de                               |

#### <a name="report-filters"></a>Filtros de informe

Filtros de informe se implementan agregando un filtro en el informe representado, ya sea en el Editor de informes o directamente en el informe. Los filtros de informes siguientes se utilizan en la plantilla.

_Tabla 4 - filtro de informe_

| Filtro     | Descripción                            | Ejemplo de filtro de informe CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Iniciar con el año primero, después el mes. | 2017-10                           |
| Alfabético | Filtros para los caracteres alfabéticos. | [a-z]                             |
| Numérico    | Filtros para cualquier carácter numérico.    | [0-9]                             |
| Porcentaje | Filtra por un porcentaje.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importar las plantillas CQD

Esta guía incluye [dos plantillas CQD comisariadas](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Estas plantillas aceleran el uso de CQD y proporcionan una oportunidad de aprovechar rápidamente las capacidades del CQD para hacer un impacto en los usuarios equipos o Skype para la experiencia del negocio. La plantilla de todas las redes, aunque optimizado para trabajar con un edificio del archivo de datos, pueden utilizarse mientras trabaje para recopilar y carga de información de edificio en CQD, como se describe en la sección siguiente.

**Para importar las plantillas (. CQDX) en CQD en línea**

1.  Vaya a <https://cqd.lync.com>.

2.  Autenticarse utilizando las credenciales administrativas de Office 365.

> [!NOTE]
> Debe tener Office 365 administrador Global, Skype para el Administrador corporativo o función de lectores de informes obtener acceso a CQD. 


3.  Seleccione el menú de **Informes de resumen** en la parte superior de la página y, a continuación, elija **Informes detallados**.

4.  En el panel Resumen, seleccione **Importar**. Ir a la CQDX ubicación de guardado, seleccione la plantilla CQDX y, a continuación, seleccione **Abrir**.

5.  Después de carga la plantilla, una ventana emergente mostrará el mensaje "Importar informe tuvo éxito". Seleccione **OK.**

![Captura de pantalla de una ventana emergente que notifica al usuario que la plantilla se ha importado correctamente.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Repita los pasos 4 y 5 para la segunda plantilla CQD.

> [!NOTE]
> Se importaron las plantillas CQD por usuario. Si necesitan utilizar el informe usuarios adicionales, debe iniciar una sesión en e importar las plantillas en su instancia CQD. 


## <a name="building-mapping"></a>Asignación de creación

En un equipo o Skype para la implementación de los negocios en línea, todos los clientes externos.
Que tiene la implicación que de forma predeterminada, todos los clientes son notificados como fuera de CQD en línea, independientemente de si el cliente se ha conectado en una red corporativa interna.

Cuando se trabaja con la calidad de las llamadas, debe conocer la ubicación de un cliente y si estaba conectado a una red puede administrar o una red que no puede administrar: la hipótesis que sólo puede mejorar las redes puede administrar.
Cargando información de creación y red CQD Online, habilitar CQD determinar si un cliente se conecta a una red interna corporativa o administrado o a una red externa y no administrado.

### <a name="building-data-file-structure"></a>Estructura de archivos de datos de creación

El formato del archivo de datos que carga debe cumplir los siguientes requisitos para pasar la comprobación de validación antes de cargar.

-   El archivo debe ser un archivo TSV, lo que significa que para cada fila, cada columna está separada por un carácter de tabulación, o un archivo CSV en el que cada columna está separada por una coma.

-   El archivo no puede ser superior a 50 MB.

-   El contenido de los datos del archivo *no debe incluir encabezados de tabla*. En otras palabras, la primera línea del archivo de datos debe ser datos reales, no los encabezados de columna como "Red".

-   Para cada columna, el tipo de datos sólo puede ser cadena, número o Bool. Si el tipo de datos es número, el valor debe ser un valor numérico; Si es Bool, el valor debe ser 0 o 1.

-   Para cada columna, si el tipo de datos es String, los datos pueden estar vacíos (pero todavía deben estar separados por un delimitador adecuado, que es un carácter de tabulación o una coma). Esto simplemente asigna ese campo un valor de cadena vacía.

-   Debe haber 14 columnas para cada fila. Cada columna debe tener el tipo de datos que se describen en la siguiente tabla y las columnas deben estar en el orden indicado en la tabla.

_Tabla 5: creación de la estructura de archivos_

| Nombre de la columna        | Tipo de datos | Ejemplo                   | Orientación    |
|--------------------|-----------|---------------------------|-------------|
| Red            | Cadena    | 192.168.1.0               |  Obligatorio    |
| NetworkName        | Cadena    | USA/Seattle/SEATTLE-mar-1 | Obligatorio\*  |
| NetworkRange       | Número    | 26                        |  Obligatorio    |
| Nombredeedificio       | Cadena    | SEATTLE-MAR-1             | Obligatorio\*  |
| OwnershipType      | Cadena    | Contoso                   | Opcional     |
| BuildingType       | Cadena    | Terminación de TI            | Opcional     |
| BuildingOfficeType | Cadena    | De ingeniería               | Opcional     |
| Ciudad               | Cadena    | Seattle                   | Recomendado |
| Código postal            | Cadena    | 98001                     | Recomendado |
| País            | Cadena    | NOSOTROS                        | Recomendado |
| Estado              | Cadena    | WA                        | Recomendado |
| Region             | Cadena    | MSUS                      | Recomendado |
| InsideCorp         | Booleano      | 1                         |  Obligatorio    |
| ExpressRoute       | Booleano      | 0                         |  Obligatorio    |

\*Aunque no es necesario por CQD, las plantillas están configuradas para mostrar el edificio y red nombre.

#### <a name="supernetting"></a>Creación de superredes

Puede utilizar la creación de superredes, comúnmente llamada Classless Inter-Domain Routing (CIDR), en lugar de definir cada subred. Una *supernet* es una combinación de varias subredes que comparten un solo prefijo de enrutamiento. En lugar de agregar una entrada para cada subred, puede utilizar la dirección CIDR/superredes. Se admite la creación de superredes, pero no es recomendable utilizarlo.

Por ejemplo, la creación de marketing de Contoso se compone de las siguientes subredes:

-   10.1.0.0/24 – primer piso

-   10.1.1.0/24 – segundo piso

-   10.1.2.0/24: tercer piso

-   10.1.3.0/24 – cuarto piso

En lugar de agregar una entrada para cada subred, puede utilizar la dirección de superredes/CIDR: en este ejemplo, 10.1.0.0/22.

-   Red = red dividida 10.1.0.0

-   Intervalo de red = 22

Aquí están algunas cosas a considerar antes de implementar la creación de superredes:

-   Creación de superredes tarda menos por adelantado, pero viene a costa de la reducción de la riqueza de los datos. Supongamos que hay un problema de calidad que implique subred 200.1.2.0. Si implementa la creación de superredes, no sabrá dónde se encuentra la subred en el edificio o qué tipo de red es (por ejemplo, un laboratorio). Si se hubiera definido todas las subredes de un edificio y cargar la información de la ubicación de planta, podrá ver esa distinción.

-   Es importante asegurarse de que la dirección de superredes/CIDR es correcta y no detectar subredes no deseadas.

-   Creación de superredes se puede utilizar en una asignación de edificio con máscara de bits de 8 a 28 bits.

-   Es bastante frecuente encontrar 192.168.0.0 en datos. Para muchas organizaciones, esto indica que el usuario está en casa. Para otros, se trata de la combinación de dirección IP para una oficina satélite. Si su organización dispone de oficinas que utiliza esta configuración, no incluirlo en el archivo de creación ya que es difícil distinguir entre las redes domésticas e internas utilizando subredes comunes.

> [!IMPORTANT]
> El intervalo de red puede utilizarse para representar una supernet. Creación de todas las nuevas cargas de archivos de datos se comprobarán para los rangos superpuestos. Si previamente se ha cargado un archivo de creación, debe descargar el archivo actual y cargar de nuevo para identificar las superposiciones y corregir el problema. Las asignaciones incorrectas de subredes para edificios en los informes puede provocar cualquier superposición en archivos cargados previamente. 


#### <a name="vpn"></a>VPN

La calidad de los datos de la experiencia (QoE) que los clientes envían a Office 365, que es de donde proceden los datos CQD, incluye un indicador VPN. Sin embargo, este indicador se basa en proveedores de VPN informar a Windows de que el adaptador de red VPN registrado es un adaptador de acceso remoto. No todos los proveedores de VPN registrar correctamente los adaptadores de acceso remoto. Debido a esto, podría no ser capaz de utilizar los filtros integrados de consulta VPN. Hay dos enfoques para acomodar las subredes VPN en el edificio archivo de información.

-   Defina un **Nombre de red** utilizando el texto "VPN" en este campo para las subredes VPN.

![Captura de pantalla de un informe en el panel de calidad llame que define cómo crear una subred VPN](media/quality-of-experience-review-guide-image10.png)

_Figura 10 - VPN mediante el nombre de red_

-   Defina un **Nombre del edificio** utilizando el texto "VPN" en este campo para las subredes VPN.

![Captura de pantalla de un informe en el panel de calidad llame que define cómo crear una definición de edificio que consta de una subred de la VPN.](media/quality-of-experience-review-guide-image11.png)

_Figura 11 - VPN mediante el nombre del edificio_

> [!IMPORTANT]
> Ciertas implementaciones de VPN no notificar con precisión la información de la subred. Si esto se produce en los informes, que se recomienda que cuando se agrega una subred VPN para el archivo de edificio, en lugar de una entrada para la subred, agregar entradas independientes para cada dirección de la subred VPN como una red independiente de 32 bits. Cada fila puede tener los mismos metadatos de creación. Por ejemplo, en lugar de una fila por 172.16.18.0/24, tiene 253 filas, con una fila para cada dirección de 172.16.18.1/32 a 172.16.18.254/32, ambos inclusive.


> [!NOTE]
> Se sabe que las conexiones VPN identificar incorrectamente la conexión de red como por cable cuando la conexión a internet subyacente es inalámbrica. Cuando se mira calidad sobre conexiones VPN, no puede suponer que el tipo de conexión se ha identificado con precisión.

### <a name="uploading-building-information"></a>Cargando información del edificio

El tablero de mandos de los informes de resumen de CQD incluye una página de **Inquilinos al cargar los datos** , acceso, seleccione la etiqueta de vínculo **Arrendatario al cargar los datos** en la esquina superior derecha (busque el icono del engranaje). Esta página se utiliza para los administradores para cargar su propia información, como la asignación de dirección IP y la información geográfica, asignación de cada punto de acceso inalámbrico y su dirección MAC y así sucesivamente.

1.  Vaya a CQD en línea a través de <https://cqd.lync.com>.

2.  Seleccione el icono del engranaje en la esquina superior derecha y elija el **Inquilino al cargar los datos** desde la página **Informes de resumen** .

![Captura de pantalla de un cuadro de diálogo en el panel de calidad llame que aparece mientras se está cargando datos.](media/quality-of-experience-review-guide-image12.png)

_Figura 12 - menú cargar datos de inquilinos_

1.  O bien, si es la primera vez que visita CQD, usted se pedirá para cargar datos del edificio. Puede seleccionar **Cargar ahora** para desplazarse rápidamente a la página de **Carga de datos de inquilinos** .

![Captura de pantalla de una pancarta en el panel de calidad llame que notifica a un usuario para cargar datos del edificio.](media/quality-of-experience-review-guide-image13.png)

_Figura 13 - creación de banner de carga de datos_

1.  En la página de **Carga de datos de inquilinos** , seleccione **Examinar** para elegir un archivo de datos.

2.  Después de seleccionar un archivo de datos, especifique la **fecha de inicio** y, opcionalmente, especifique una fecha final.

3.  Después de seleccionar la **fecha de inicio**, seleccione **cargar** para cargar el archivo en el CQD. <br><br>Antes de cargar el archivo, se valida. Si se produce un error en la validación, se muestra un mensaje de error solicitando que corrija el archivo. La siguiente figura muestra un error que se produce cuando el número de columnas del archivo de datos es incorrecto.

![Captura de pantalla de un cuadro de diálogo en el panel de calidad llame que describe un mensaje de error al importar datos de construcción.](media/quality-of-experience-review-guide-image14.png)

_Figura 14 - errores de carga de datos_

4.  Si no se producen errores durante la validación, la carga de archivos se realizará correctamente. A continuación, puede ver el archivo de datos cargado en la tabla **Mis archivos** , que muestra la lista completa de todos los archivos cargados por el arrendatario en la parte inferior de la página actual.

> [!NOTE]
> Puede tardar hasta cuatro horas para finalizar el proceso de creación del archivo. <br><br> Si ya se ha cargado un archivo edificio y necesita agregar subredes que podrían se han perdido o excluidos, modifique el archivo original agregando las subredes nuevo, quite el archivo actual y volver a cargar el archivo recién modificado. Puede haber sólo un edificio active el archivo de datos en CQD. 

### <a name="missing-subnets"></a>Falta de subredes

Después de cargar la información de creación de redes administradas, cada red gestionada debe tener una asociación del edificio. Sin embargo, esto no siempre es el caso; Normalmente, se pierden algunas subredes. Esta sección describe cómo validar esas redes faltantes.

Vaya a la página de **Informes detallados** de CQD en línea y navegar hasta el **Informe falta de subred** incluidas en las plantillas CQD. Todas las subredes con 10 o más audio secuencias que no están definidos en el edificio, presenta el archivo de datos. Asegúrese de que no hay ninguna red administrada en esta lista. Si faltan las subredes, actualizar el edificio original de archivos de datos y volver a cargarlo en CQD.

> [!IMPORTANT]
> Debe agregar su ID de inquilinos como un filtro de consulta para el **Segundo ID de inquilinos** a este informe para filtrar el informe para ver sólo los datos de inquilinos de la organización. De lo contrario, el informe mostrará las subredes federadas.

> [!NOTE] 
> Asegúrese de ajustar el filtro de informe de año mes al mes actual. Seleccione **Editar**y ajuste el filtro de informe del **Mes año** para guardar el nuevo mes predeterminado.                                                  |

![Informe que muestra no incluidas en el archivo de datos de CQD creación de subredes que muestran el uso.](media/quality-of-experience-review-guide-image15.png)

_Figura 15: informe de edificio que falta_

## <a name="reliability-investigations"></a>Investigaciones de confiabilidad

Es el primer paso para mejorar la calidad evaluar el estado de audio confiabilidad en toda la organización. Porque el audio confiabilidad es vital para una experiencia de usuario positiva, empezamos con los dos componentes que miden la confiabilidad:

1.  **Llamar a errores en la instalación:** No se puede establecer la sesión.

2.  **Llamar a colocar errores:** Sesión fue establecida y finalizada de forma inesperada

En esta sección, analizaremos métodos para investigar en ambas áreas.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía. Consulte la descripción del informe individuales para obtener más información.


### <a name="call-setup"></a>Configuración de llamada

En primer lugar, dar prioridad a reparar errores en la instalación llamada en esta área porque estos errores tienen un impacto negativo significativo en la experiencia del usuario.

Comenzar la investigación evaluando el porcentaje de errores de configuración de llamada general para la organización y dar prioridad a áreas de investigación basada en el porcentaje más alto de generación o la red.

#### <a name="call-setup-failures-overall"></a>Llamar a errores en la instalación generales

Este informe gráfico muestra la cantidad total de llamada correcta, configurar y llamar a errores en la instalación con el tiempo. Seleccione cualquiera de las columnas para mostrar los valores individuales, como se muestra en la figura siguiente.

![Captura de pantalla de un gráfico que muestra el porcentaje de error de instalación de secuencia llamar a Audio](media/quality-of-experience-review-guide-image16.png)

_Figura 16 - fiabilidad Audio - llamada secuencia errores en la instalación_

##### <a name="analysis"></a>Análisis

Este informe muestra los errores y el uso de la instalación de llamada de audio de su organización con el tiempo. Mediante este informe, puede responder a las preguntas siguientes y determinar el siguiente curso de acción:

1.  ¿Cuál es el porcentaje de error de instalación de llamada total para el mes actual?

2.  ¿Es el porcentaje de error de instalación llamada total por debajo o por encima de la métrica de objetivo definido?

3.  ¿Es la tendencia de error peor o mejor que el mes anterior?

4.  ¿La tendencia de errores aumenta, constante, o disminuye?

La información presentada en este informe a contar la historia de ¿con qué frecuencia se producen errores en sus instalaciones de llamada general en toda la organización.

Independientemente de las respuestas anteriores, tómese su tiempo para investigar más utilizando los informes secundarios incluidos para buscar los edificios individuales o redes que necesiten corrección. Aunque la tasa de error global podría ser por debajo de la métrica de objetivo, a menudo las tasas de error para uno o varios edificios o redes están por encima de la métrica y necesiten corrección.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Llamar a errores en la instalación mediante la creación y la subred 

Este informe de tabla se utiliza para descubrir y aislar las redes que necesiten corrección o edificios.

> [!NOTE]
> Asegúrese de ajustar el filtro de informe de año mes al mes actual. Seleccione **Editar**y ajuste el filtro de informe del **Mes año** para guardar el nuevo mes predeterminado.


![Informe que listas de llamada instalación error razones, organizados por generar, red y subred por mes.](media/quality-of-experience-review-guide-image17.png)

_Figura 17 - errores en la instalación de Audio mediante la creación o subred_

##### <a name="remediation"></a>Corrección 

Centrar sus esfuerzos de reparación en edificios o subredes que tienen el mayor volumen de errores en primer lugar, ya que se maximice el impacto de la experiencia del usuario y ayudan a reducir rápidamente los errores de configuración organizativa llamada.
La tabla siguiente muestra las dos razones para errores en la instalación llamada notifica CQD.

_Tabla 6: razones para errores de configuración de llamada_

| Llamar a causa de errores en la instalación                       | Causa habitual                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Falta la regla de exención de inspección profunda del paquete FW | Indica que a lo largo de la ruta de acceso del equipo de red impide que la ruta de acceso de medios se establece debido a reglas de inspección profunda del paquete. Esto es probablemente debido a las reglas de firewall no está configuradas correctamente. En este caso se realizó correctamente el protocolo de enlace TCP pero no el protocolo de enlace SSL.               |
| Falta la regla de excepción de bloqueo IP FW               | Indica que a lo largo de la ruta de acceso del equipo de red impide que la ruta de medios está establecida a la red de Office 365. Esto podría deberse a que las reglas de proxy o firewall no está configuradas correctamente para permitir el acceso a direcciones IP y puertos utilizados para los equipos y Skype para tráfico del negocio. |

Ahora para comenzar su corrección, puede Centrar los esfuerzos en un determinado edificio o subred. Como se muestra en la tabla anterior, estos problemas son debido a configuraciones de firewall o proxy. Revise las opciones en la tabla siguiente para las acciones de corrección.

_Tabla 7: corrección de errores de instalación de pasos a seguir para la llamada_

| Corrección           | Orientación     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar servidores | Trabaje con su equipo de la red y comprobar la configuración de servidores contra [la lista de direcciones IP de Office 365](https://aka.ms/o365ips). Compruebe que las [subredes de los medios de comunicación](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) y puertos están incluidos en las reglas de firewall. Compruebe que los puertos TCP y UDP necesarios se abren en el servidor de seguridad. Los medios de comunicación prefieren UDP sobre TCP. TCP se considera un protocolo de conmutación por recuperación.<br><ul><li>**TCP:** puerto 443</li><li>**UDP:** puertos 3481: 3478</li><ul> |
| Comprobar                | Aproveche la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar la conectividad desde el edificio afectado o subred utilizando la función de comprobación de conectividad.    |


### <a name="call-drop"></a>Llamada de colocación

A diferencia de los errores de configuración de llamada, no hay ningún código de razón para indicar por qué interrumpe errores de llamada se produjo, lo que dificulta aislar una causa concreta. Para una mejor clasificación llamadas interrumpidas, utilice un enfoque inferido. Por remediar las áreas de interés para el audio, revisión de clientes y conducir el uso de dispositivos certificados para equipos y Skype para empresas, cabría esperar errores de llamada cayó a rechazar.

#### <a name="call-drop-failures-overall"></a>Llamar a errores de colocación global

Este informe gráfico muestra la cantidad total de secuencias de audio, secuencias de audio total caídos, y eliminan de flujo total porcentaje. Seleccione cualquiera de las columnas para mostrar sus valores, como se muestra en la figura siguiente.

![Captura de pantalla de un gráfico que muestra el porcentaje de quitar secuencias de Audio llamar](media/quality-of-experience-review-guide-image18.png)

_Figura 18 - llamada Total cayó porcentaje de error_

##### <a name="analysis"></a>Análisis

Este informe gráfico muestra errores y el uso de su organización con el tiempo relacionado con llamar a caídas. Mediante este informe, puede responder las siguientes preguntas:

1.  ¿Qué es la llamada actual total cayó porcentaje?

2.  ¿Es el porcentaje de entrega total por debajo de la métrica de objetivo definido?

3.  ¿Es la tendencia de error peor o mejor que el mes anterior?

4.  ¿La tendencia de errores aumenta, constante, o disminuye?

La información presentada en este informe puede contar la historia de la frecuencia con las gotas de llamada general se producen en toda la organización.

Independientemente de las respuestas a las preguntas anteriores, tómese su tiempo para investigar utilizando los subinformes para buscar los edificios o redes que necesiten corrección. Aunque la tasa global de entrega puede ser por debajo de la métrica de objetivo, a menudo la tasa de entrega de edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Llamar a colocar errores por edificio o subred

Errores en este informe de tabla indican que la llamada se eliminan inesperadamente y dio lugar a una experiencia negativa de los usuarios. Existen dos informes de la tabla incluidos en la plantilla, uno para investigar las conferencias y la otra para las dos partes.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajuste **Mes año** para guardar el nuevo mes predeterminado.


![Informe que número de listas y el porcentaje de llamadas interrumpidas, organizados por construcción, red y subred por mes.](media/quality-of-experience-review-guide-image19.png)

_Figura 19: llamada de Audio quitar errores por edificio o subred_

##### <a name="remediation"></a>Corrección

Con el informe de la tabla anterior, se pueden aislar "puntos calientes" en la red gestionada donde tienen lugar llamada gotas sobre la métrica de destino definido. Centrar sus esfuerzos de reparación en edificios o redes que tienen el recuento total de secuencia más alto en primer lugar, para obtener el mayor impacto.

Causas comunes de las caídas de llamada:

-   Aprovisionado en red o internet de salida

-   Sin QoS configurado en redes restringidas

-   Versiones anteriores de cliente

-   Comportamiento de los usuarios

Después de descubrir puntos calientes, puede aprovechar [Analytics llame](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) para revisar más los usuarios de dicho edificio para problemas específicos. Análisis de llamada contiene datos PII y pueden ser útil para aislar aún más los posibles motivos de las gotas de llamada.

Independientemente del siguiente paso, es una buena práctica para notificar que el departamento de soporte que se ha descubierto un problema con edificios específicos o subredes. De este modo, rápidamente pueden responder a las llamadas entrantes y clasifique los usuarios más eficientemente. Los usuarios marcados se pueden, a continuación, notificar al equipo de ingeniería para una mayor investigación.

La tabla siguiente enumeran algunos métodos comunes para administrar y solucionar las caídas de llamada.

_Tabla 9 - corrección de drop de pasos a seguir para la llamada_

| Corrección                              | Orientación     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Red/internet                         | Ahora que sabe que el edificio se ve afectado, trabajar con su equipo de red para supervisar el ancho de banda de dicho edificio para determinar si hay problemas con sobreutilización. Si se descubre el problema a estar relacionados con la congestión de la red, considere la posibilidad de aumentar ancho de banda de dicho edificio. <br><br>**QoS:** Si el aumento del ancho de banda es imposible o de costo prohibitivo, considere la implementación de QoS. Esto garantizará que se asignan prioridades a los paquetes de multimedia en la red gestionada por encima del tráfico de medios no. Si no hay ninguna evidencia clara que ancho de banda es el culpable, tenga en cuenta estas soluciones:<br><ul><li>[Guía de QoS de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para QoS dirección del negocio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Realizar una evaluación de disponibilidad de red:** Una evaluación de la red proporciona detalles acerca del uso de ancho de banda esperado, cómo lidiar con ancho de banda y de red cambia y recomendaciones de red para equipos y Skype para el negocio. Con la tabla anterior como su origen, tiene una lista de los edificios o subredes que son candidatos excelentes para una evaluación. <br><ul><li>[Evaluación de disponibilidad de la red de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para evaluación de disponibilidad de red empresarial](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Herramienta de evaluación de la red de Microsoft:** Utilice esta herramienta para una simple prueba de rendimiento de la red para determinar qué tan bien se realizaría la red para los equipos de una o de Skype para llamadas de negocios en línea. La herramienta le ayuda a evaluar el rendimiento de una subred y validar la disponibilidad de la red frente a [requisitos](https://aka.ms/performancerequirements)de rendimiento de Microsoft.<ul><li>[Descargue la herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Clientes (Skype para empresas sólo en línea) | Han conocido algunos de los clientes más antiguos, documentaban los problemas con la confiabilidad de los medios de comunicación. Revisar los informes de análisis llame desde varios usuarios afectados o crear un informe de tabla de versión de cliente personalizado en CQD filtrado a edificios específicos o subredes con medida de error llame al quitar Total %. Esta información le ayudará a comprender si existe una relación entre la llamada gotas de dicho edificio específico y una versión específica del cliente.                                                                                                                                                              |
| Dispositivos                                  | La mayoría de los errores del dispositivo son debido al uso de dispositivos que no están certificados para equipos o Skype para el negocio. Errores suelen adoptan la forma de los altavoces integrados o micrófonos que se utilizan combinaciones de audífono y micrófono están conectados a la toma de audio de 3,5 mm en un dispositivo. Recomendación actual de Microsoft es que todos los usuarios que están experimentando llamar a caídas — o mala llama en general — y están utilizando dispositivos integrados o controladores debe ser aprovisionado un [certificado auricular o del altavoz](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). |
| Comportamiento de los usuarios                            | Si determina que la red, dispositivos ni los clientes son el problema, considere contratar [Mi asesor](https://aka.ms/myadvisor) de orientación en el desarrollo de una estrategia de adopción de usuario para educar a los usuarios la mejor combinación y salir de las reuniones. Un equipo más inteligente y usuario de Skype producirá una mejor experiencia de usuario para todos los participantes de la reunión. Un usuario que pone su equipo portátil en modo de suspensión (cerrando la tapa) sin salir de la reunión se clasifica como una gota llamada inesperada.     |

## <a name="quality-investigations"></a>Investigaciones de calidad

El siguiente paso para evaluar el estado de la calidad de audio a través de la implementación es investigar el uso de proxy, TCP y Audio deficiente llame al cociente (PCR). Es importante recordar que los datos CQD no proporcionan una causa concreta, pero proporciona áreas de problema probablemente para iniciar una conversación de colaboración con los equipos adecuados para las actividades de recuperación.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía. Consulte la descripción del informe individuales para obtener más información. 


### <a name="investigate-call-quality"></a>Investigar la calidad de las llamadas

El porcentaje global de PCR se utiliza principalmente para indicar si la organización cumple los objetivos de métricas audio definidos. Es importante destacar que aunque el porcentaje general es dentro de destino, algunas subredes o edificios podrían no cumplir los objetivos definidos y, por tanto, necesitan más investigación. Por ejemplo, si el porcentaje PCR audio organizativo es 3 por ciento en diciembre, que cumple el objetivo del ejemplo, edificios específicos podría estar teniendo una mala experiencia, dependiendo de la distribución de ese 3 por ciento.

#### <a name="overall-organizational-poor-call-percentage"></a>Porcentaje de llamadas pobres organizativa general

Evaluar el porcentaje global de las llamadas para el uso de la organización el informe del plan general de calidad deficientes.

![Captura de pantalla de un gráfico que muestra el porcentaje de llamadas de mala calidad](media/quality-of-experience-review-guide-image20.png)

_Figura 20: calidad de Audio - general_

##### <a name="investigation"></a>Investigación

Este informe gráfico muestra PCR y uso de su organización con el tiempo. Mediante este informe, puede responder las siguientes preguntas:

1.  ¿Qué es la PCR total para el mes actual?

2.  ¿Es la PCR por debajo de la métrica de objetivo definido?

3.  ¿Es la tendencia de error peor o mejor que el mes anterior?

4.  ¿La tendencia de errores aumenta, constante, o disminuye?

Independientemente de las respuestas a las preguntas anteriores, tómese su tiempo para investigar utilizando los subinformes para buscar los edificios o redes que puedan necesitar investigación. Aunque podría ser la PCR general por debajo de la métrica de objetivo, a menudo lo PCR para uno o varios edificios o redes está por encima de la métrica y necesita más investigación.

#### <a name="audio-quality-overall"></a>Calidad de audio general

Hay dos árboles de informes incluidos en las plantillas para calidad de audio, uno para investigar las conferencias y la otra para las llamadas de dos partes. Efectos de corrección de calidad, el proceso de investigación es el mismo, así que nos concentraremos aquí en la conferencia. Mejoras en la calidad de la conferencia positivamente también afectará a la calidad de las llamadas de dos partes. También se incluyen para Wi-Fi y la calidad de audio para conferencias y dos partes por cable a la vista Informes.

> [!NOTE]
> Investigando dos partes defectuosas llamadas es similar a investigar las llamadas de conferencia. La tarea es identificar los edificios o subredes que tengan menor calidad para validar si hay un patrón de llamadas deficientes con otro edificio o subred. 

![Captura de pantalla de la calidad de Audio - informe de conferencia en el panel de calidad llamar.](media/quality-of-experience-review-guide-image21.png)

_Figura 21: calidad de Audio - conferencia_

##### <a name="investigation"></a>Investigación

Este informe gráfico muestra las conferencias de la organización o el uso de dos partes y PCR con el tiempo. Mediante este informe, puede responder las siguientes preguntas:

1.  ¿Qué es la PCR total para el mes actual?

2.  ¿Es la PCR por debajo de la métrica de objetivo definido?

3.  ¿Es PCR peor o mejor que el mes anterior?

4.  ¿La tendencia PCR aumenta, constante, o disminuye?

Independientemente de las respuestas a las preguntas anteriores, tómese su tiempo para investigar utilizando los subinformes para buscar los edificios o redes que necesiten la investigación. Aunque podría ser la PCR general por debajo de la métrica de objetivo, a menudo lo PCR para uno o varios edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Secuencia de audio deficiente creando y subred

Este informe de tabla proporciona información adicional sobre qué contribuyó las llamadas que se clasifican como pobres y ayuda a aislar las zonas activas en la red gestionada.

Distingue el detalle de conexión por cable y Wi-Fi e incluye vibración, pérdida de paquetes y las mediciones de tiempo de ida y vuelta (RTT). Un informe similar también existe en los informes de dos partes y se utiliza para aislar las llamadas de dos partes de la red gestionada.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajuste **Mes año** para guardar el nuevo mes predeterminado. 

> [!TIP]
> Redes domésticas comunes son difíciles de clasificación debido a su utilización generalizada. Un informe independiente que utiliza la dirección IP de servidor de seguridad se ha agregado a la plantilla de todas las redes para ayudar con oficinas adecuadas que utilizan las redes comunes.

![Informe que muestra los tipos de conexión, tipos de transporte y PCR superior al 3%, junto con las diversas razones mala calidad organizados por construcción, red y subred por mes.](media/quality-of-experience-review-guide-image22.png)

_Figura 22 - resumen de la secuencia de Audio deficiente creando - y subred conferencia_

##### <a name="remediation"></a>Corrección

Centrar sus esfuerzos de reparación en edificios o redes que tienen el mayor volumen de secuencias de audio, ya que se maximice el impacto y ayudar a mejorar el usuario experimentan rápidamente. Utilice la vibración, la pérdida del paquete y medidas de RTT para comprender lo que está contribuyendo a la calidad deficiente de llamada. Es posible que exista más de un problema:

-   **De vibración:** Paquetes de Media llegan a diferentes velocidades, que hace que un altavoz de sonido robótico.

-   **Pérdida de paquetes:** Se está eliminando paquetes de Media que crea el efecto de la falta de palabras o sílabas.

-   **RTT:** Paquetes de Media tardan mucho tiempo en llegar a su destino, lo que crea un efecto de transmisor-receptor portátil.

Aunque ninguna fuente única de verdad representa lo que puede producir una llamada deficiente, varios métodos comunes pueden ayudarle a tratar con anomalías de la red.

Para facilitar la investigación de problemas de calidad, puede aprovechar [Llamar Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).
Con llamar a Analytics, puede mirar una conferencia específica o informe de llamada detallada de los usuarios. Este informe contendrá datos PII y resulta útil al intentar discernir el motivo de los errores. Una vez que sepa qué edificio se ve afectado, localizar usuarios en que el edificio debe ser sencillo.

No olvide que el helpdesk sepan que estas redes están experimentando problemas de calidad, para poder evaluar rápidamente y responder a las llamadas entrantes.

_Tabla 9 - colaboradores comunes a la PCR alta_

| Corrección                              | Orientación       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Redes                                 | Una red sobreutilizada o aprovisionados bajo puede causar problemas con calidad media. Trabajo con el equipo de red para determinar si las conexiones de red del usuario a la salida de internet señalan tiene suficiente ancho de banda para soportar los medios de comunicación. **Realizar una evaluación de disponibilidad de red:** Una evaluación de la red proporciona detalles acerca del uso de ancho de banda esperado, cómo lidiar con ancho de banda y de red cambia y recomendaciones de red para equipos y Skype para el negocio. Con la tabla anterior como su origen, tiene una lista de los edificios o subredes que son candidatos excelentes para una evaluación.<br><ul><li>[Evaluación de disponibilidad de la red de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para evaluación de disponibilidad de red empresarial](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Herramienta de evaluación de la red de Microsoft:** Utilice esta herramienta para una simple prueba de rendimiento de la red para determinar qué tan bien se realizaría la red para los equipos de una o de Skype para llamadas de negocios en línea. Esta herramienta le ayuda a evaluar el rendimiento de una subred y validar la disponibilidad de la red frente a los de rendimiento [requisitos](https://aka.ms/performancerequirements)de Microsoft.<br><ul><li>[Descargue la herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Calidad de servicio (QoS)                 | QoS es un método probado para dar prioridad a los paquetes de una red para asegurarse de que llegan a su destino intacta y el tiempo. Considere la implementación de QoS en toda la organización para maximizar la calidad de la experiencia del usuario donde el ancho de banda está limitada o restringida. QoS le ayudará a solucionar problemas asociados típicamente con niveles altos de pérdida de paquetes, y, en menor grado, tiempos de vibración y de ida y vuelta. <br><ul><li>[Guía de QoS de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para QoS dirección del negocio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi puede tener un impacto significativo en la calidad de las llamadas. Diseño de Wi-Fi normalmente no tiene en consideración los requisitos de red para servicios de VoIP y a menudo es una fuente de mala calidad. **QoS:** Redes inalámbricas modernas deben ser compatible con muchos dispositivos. Estos dispositivos compiten por el ancho de banda y pueden conducir a problemas de calidad de servicios VoIP donde la velocidad y latencia son vitales. Consulte a su proveedor inalámbrico para obtener información específica y considerar la implementación de QoS en la red inalámbrica para dar prioridad a Skype para medios de negocio y equipos. **Densidad AP:** Puntos de acceso (AP) podrían estar demasiado alejados o no en una situación ideal. Para minimizar posibles interferencias, coloque los puntos de acceso adicionales en salas de conferencia y en ubicaciones que no están obstruidas por paredes u otros objetos. **2,4 GHz y 5 GHz:** 5 GHz proporciona menos interferencias de fondo y velocidades superiores y se debe asignar prioridad al implementar VoIP a través de Wi-Fi. Sin embargo, 5 GHz no es tan fuerte como 2,4 GHz y no penetrar en las paredes tan fácilmente. Revise el diseño del edificio para determinar la frecuencia en que se puede depender de la mejor conexión. **Fuerza de señal:** Tradicionalmente se mide en dBm (proporción de potencia en decibelios), mide la fuerza de la señal inalámbrica. Después de que un dispositivo está conectado a un punto de acceso, no quiere dejar ir fácilmente. Medida que el dispositivo se aleja del punto de acceso, la intensidad de la señal disminuye hasta un punto que induce a una mala conexión aunque PA otra, más cerca está disponible. Si es posible, trabaje con su proveedor para asegurarse de que los puntos de acceso están configurados para colocar un dispositivo cuando la intensidad de la señal cae por debajo de un nivel aceptable. Esto asegurará que el dispositivo no se bloquee un punto de acceso débil. Esto es una buena solución cuando no se puede agregar fácilmente más puntos de acceso. **Controlador de wireless:** Cuando todo lo demás falla, asegúrese de que los controladores inalámbricos están actualizados. Esto le ayudará a mitigar cualquier experiencia de usuario pobre relacionado con un controlador anticuado. |
| Dispositivo de red                           | Las organizaciones más grandes podrían tener cientos de dispositivos repartidos por la red. Trabajo con su equipo de red para asegurarse de los dispositivos de red a internet del usuario se conservan y actualizado.     |
| VPN                                      | Ha sido bien documentado que los dispositivos VPN tradicionalmente no están diseñadas para manejar cargas de trabajo de los medios de comunicación en tiempo real. Algunas configuraciones de VPN prohíban el uso de UDP (que es el protocolo preferido para el audio) y sólo se basan en TCP. Puede implementar una [solución VPN de túnel dividido](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) para reducir VPN como una fuente de mala calidad.        |
| Clientes (Skype para empresas sólo en línea) | Los clientes más antiguos se han sabido para causar problemas con los medios de comunicación. Asegúrese de que los clientes se se revisen dentro de seis meses a partir de la versión. Aproveche [MyAdvisor](https://aka.ms/myadvisor) para obtener consejos sobre el desarrollo de una estrategia de preparación del cliente e implementar [Hacer clic en ejecutar](https://technet.microsoft.com/library/jj219427.aspx).      |
| Dispositivos                                  | El uso de [optimizado de dispositivos](https://partnersolutions.skypeforbusiness.com/solutionscatalog) puede ayudar a mejorar significativamente la experiencia del usuario. Con todos los componentes iguales, optimizados dispositivos están diseñados para maximizar la experiencia del usuario con los equipos y Skype para el negocio y producir una calidad superior. Aproveche [MyAdvisor](https://aka.ms/myadvisor) para obtener consejos sobre el desarrollo de una estrategia de preparación del dispositivo.   |


### <a name="investigate-tcp-audio-sessions"></a>Investigar las sesiones de audio TCP

TCP se considera un transporte de failback y no el transporte principal que desee para los medios de comunicación en tiempo real. La razón es un transporte de recuperación tras error es debido a la naturaleza con estado de TCP. Por ejemplo, si se realiza una llamada en una red latente y paquetes de media se retrasan, entonces los paquetes desde hace unos segundos — que ya no son útiles, compiten por el ancho de banda llegar al receptor, que puede empeorar una mala situación. Esto hace la unión sanador audio y audio stretch, dando como resultado artefactos audibles a menudo en forma de vibración.

Los informes de esta sección no hacen una distinción entre las llamadas buenas y mala. Dado que UDP es preferido, busquen los informes para el uso de TCP para el audio. Esto ocurre principalmente por las reglas de firewall incompleta. Para obtener más información acerca de las reglas de firewall para los equipos y Skype para los negocios en línea, vea [direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips).

> [!IMPORTANT]
> Se recomienda el tener un válido [Generar archivo](#building-mapping) cargado para poder distinguir rápidamente dentro de secuencias de audio externos cuando se mira el uso TCP. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Secuencias de audio con el uso TCP general

Este informe indica el uso global de TCP para audio durante los últimos siete meses, tal como se muestra a continuación.

Todos los otros informes de esta sección se centrarán en edificios específicos y subredes donde TCP es más frecuente de restricción. Más subinformes descomponen el uso TCP, conferencias y llamadas de dos partes.

![Captura de pantalla de un gráfico que muestra el número de secuencias de audio TCP por mes](media/quality-of-experience-review-guide-image23.png)

_Figura 23 – secuencias de Audio con el uso TCP_

##### <a name="investigation"></a>Investigación

Este informe de gráfico muestra el uso TCP global de su organización. Mediante este informe, puede responder las siguientes preguntas:

1.  ¿Cuál es el volumen total de llamadas TCP para el mes actual?

2.  ¿Es mejor que el mes anterior o peor?

3.  ¿La tendencia del uso TCP aumenta, constante, o disminuye?

Si observa que la tendencia del uso TCP aumenta, o por encima de uso mensual normal, tómese su tiempo para investigar utilizando los subinformes para buscar los edificios o redes que necesiten corrección. Lo ideal es que desee tan sólo sesiones de audio basados en TCP como sea posible en la red gestionada.

#### <a name="tcp-vs-udp"></a>TCP y UDP

Este informe de tabla identifica el volumen de TCP en comparación con el uso UDP reporting en el mes más reciente para conferencias de audio, vídeo y vídeo pantalla compartida (VBSS).

![Informe que muestra el volumen de TCP frente a transmisiones UDP conferencia con PCR se muestra para la comparación](media/quality-of-experience-review-guide-image24.png)

_Figura 24: TCP y UDP - conferencia_

##### <a name="analysis"></a>Análisis

Aunque desea que el uso TCP para ser lo más baja posible, puede que vea un poco de uso TCP en una implementación de otra manera sana. Para comparar UDP con el uso TCP, dividir secuencias de audio TCP por secuencias de audio de UDP para determinar un porcentaje. Un valor más del 1 por ciento tiene que investigar más.

En el ejemplo anterior, tomamos 1.806 secuencias TCP divididos por secuencias UDP 10,481 para llegar a un valor de 17.2%. Este valor está muy por encima de 1 por ciento y nos dice que debemos continuar con nuestra investigación para determinar dónde se está produciendo el uso TCP.

También se incluyen en el informe es el porcentaje de Audio deficiente. Esto proporciona una vista en la comparación de la calidad de las llamadas entre UDP y TCP para ayudar a ver cómo TCP está afectando la calidad de las llamadas overcall.

Así que ahora que ha determinado que hay un uso intensivo de audio basados en TCP en su organización, ¿qué hace a continuación? Ir a los informes de **secuencias TCP mediante la creación y la subred** para desglosar el uso TCP por el edificio y subredes.

#### <a name="tcp-streams-by-building-and-subnet"></a>Secuencias TCP mediante la creación y la subred

En las plantillas proporcionadas CQD, vaya a las secuencias TCP por subred y creación de informes de tabla mediante el uso de los recursos administrados o plantilla de todas las redes. Existen tres informes que se incluye en la plantilla, uno para investigar la conferencia, con y sin información de retransmisión de Microsoft y uno para investigar las llamadas de dos partes. Con el fin de investigar el uso TCP, el proceso es el mismo, así que nos concentraremos la discusión aquí sólo conferencias.

> [!IMPORTANT]
> Se recomienda el tener un válido [Generar archivo](#building-mapping) cargado para poder distinguir rápidamente dentro de secuencias de audio externos cuando se mira el uso TCP. 

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajuste **Mes año** para guardar el nuevo mes predeterminado.                                  |

![Informe que muestra secuencias TCP, organizadas por el edificio, la red y subred por mes.](media/quality-of-experience-review-guide-image25.png)

_Figura 25 – secuencias TCP creando - y subred conferencia_

##### <a name="remediation"></a>Corrección

Este informe identifica los edificios específicos y subredes que contribuyen al volumen del uso TCP. También se incluye un informe adicional para identificar la IP de retransmisión de Microsoft que utilizó en la llamada para ayudar a aislar las reglas de firewall que faltan. Centrar los esfuerzos de corrección en los edificios que tienen el mayor volumen de secuencias de audio para maximizar el impacto.

La causa más común del uso TCP falta reglas de excepción de firewalls o servidores proxy. Estaremos hablando de servidores proxy en la sección siguiente, así que por ahora concentrar sus esfuerzos en los servidores de seguridad. Mediante la creación o subred proporcionada, puede determinar qué servidor de seguridad debe actualizarse.

_Tabla 10 - corrección * orientación para secuencias TCP mediante la creación y la subred_

| Corrección        | Orientación     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar firewall | Compruebe [las direcciones y puertos IP de Office 365](https://aka.ms/o365ips) se excluyen desde el servidor de seguridad. Aunque hay muchas direcciones IP y los puertos que deben estar abiertos, para problemas relacionados con los medios de comunicación TCP, concentrar sus esfuerzos iniciales en lo siguiente: Compruebe las siguientes [subredes de medios](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) en las reglas del cortafuegos. En la tabla de información de la subred de medios específicos, consulte la fila 4. [Puertos UDP 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): estos puertos son los puertos de medios preferido y deben abrirse, de lo contrario se producirá un error del cliente al puerto TCP 443. |
| Comprobar             | Utilice la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si hay problemas de conectividad a determinadas direcciones IP de Office 365 y puertos del edificio afectado o subred.    |

### <a name="investigate-http-proxy-usage"></a>Investigar el uso de proxy HTTP

Los proxies HTTP no son la ruta preferida para establecer sesiones de medio para una multitud de razones. Muchos contienen características de inspección profunda del paquete que pueden impedir conexiones con el servicio de que se complete e introducir las interrupciones. Además, servidores proxy podría forzar TCP en lugar de Permitir UDP, lo que se recomienda para una calidad de audio óptima.

Siempre es la recomendación de Microsoft para configurar el cliente para conectarse directamente a los equipos y Skype para servicios de negocios. Esto es especialmente importante para el tráfico de medios.

> [!IMPORTANT]
> Tener un válido [Generar archivo](#building-mapping) cargado facilita distinguir correctamente dentro de secuencias de audio externos al analizar el uso de proxy. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Secuencias de audio con el uso de proxy HTTP global

Este informe describe el uso de proxy en el tiempo en una escala mensual. El informe de flujo de proxy HTTP en esta sección de la plantilla es muy similar a los informes TCP. No tiene el aspecto si las llamadas son buena o mala, pero si la llamada está conectada a través de HTTP.

![Captura de pantalla de las secuencias de Audio con el informe de uso de Proxy HTTP en el panel de calidad llamar.](media/quality-of-experience-review-guide-image26.png)

_Figura 26 – secuencias de Audio con el uso de Proxy HTTP_

##### <a name="analysis"></a>Análisis

Si ve un gran volumen de uso HTTP, consulte a su equipo de red para asegurarse de que son las exclusiones adecuadas en el lugar para que los clientes directamente enruta a los equipos o Skype para las subredes de los negocios en línea media. Idealmente, no debería haber ningún uso de HTTP que se muestra aquí.

Si tiene sólo un servidor proxy de internet de su organización, compruebe la correcta [las direcciones URL de Office 365 y exclusiones de intervalo de direcciones IP](https://aka.ms/o365ips). Si más de un proxy de internet está configurado en su organización, aprovechar el HTTP subregional informar a aislar que el edificio o subred se ve afectada.

Para las organizaciones que no pueden omitir al servidor proxy, asegúrese de que el Skype para Business client está configurado para iniciar sesión correctamente cuando se encuentra detrás de un proxy tal como se describe en el artículo [Skype para empresa debe utilizar el servidor proxy para iniciar una sesión en lugar de tratar directamente conexión](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>Secuencias de proxy HTTP creando y subred

Este informe identifica los edificios específicos y subredes que contribuyen al uso HTTP.

> [!IMPORTANT]
> Tener un válido [Generar archivo](#building-mapping) cargado facilita distinguir correctamente dentro de secuencias de audio externos al analizar el uso de proxy.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajuste **Mes año** para guardar el nuevo mes predeterminado.                        |

![Captura de pantalla del uso del Proxy de HTTP por subred y generar informe en el panel de calidad llamar.](media/quality-of-experience-review-guide-image27.png)

_Figura 27: uso de Proxy HTTP creando y subred_

##### <a name="remediation"></a>Corrección

Centrar los esfuerzos de corrección en los edificios o subredes que tienen uso de proxy HTTP. La causa más común de uso HTTP falta reglas de excepción de los servidores proxy. Mediante la creación o subred proporcionada, puede determinar qué servidor proxy debe actualizarse.

Compruebe que los requiere [Office 365 FQDN](https://aka.ms/o365ips) se excluyen de su proxy.

## <a name="endpoint-investigations"></a>Investigaciones de extremo

En esta sección se centra en las tareas de reporting de Skype para versiones de cliente específicos de la empresa y el uso de dispositivos certificados.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía. Consulte la descripción del informe individuales para obtener más información. 


### <a name="determine-client-versions"></a>Determinar las versiones de cliente

El informe en este espacio se centra en la identificación de Skype para las versiones de cliente de empresa en uso y su volumen relativo en el entorno.

> [!IMPORTANT]
> Actualmente, los clientes de equipos distribuidos y actualizan automáticamente a través de Azure Content Delivery Network (CDN) y se mantendrán actualizados por el servicio. Preparación del cliente y las actividades de investigación no son aplicables a los equipos.

Números de versión de Skype para negocios 2015 y 2016 pueden encontrarse a través de los vínculos siguientes:

-   [Versiones de canal de actualización de cliente de Office 365](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Números de versión y de compilación de Office 365, haga clic en ejecutar](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype para negocios descargas y actualizaciones](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajuste **Mes año** para guardar el nuevo mes predeterminado.  

> [!IMPORTANT]
> Los informes de cliente requieren excluir datos participantes federados. Para excluir los datos de los participantes federados, debe agregar un filtro de consulta para el **Segundo identificador de inquilinos** definido como [ID del inquilino](#tenant-id)de su organización. |

![Captura de pantalla del informe en el panel de calidad llamar al cliente y dispositivos.](media/quality-of-experience-review-guide-image28.png)

_Figura 28 - informe de la versión de cliente_

#### <a name="remediation"></a>Corrección

Una parte fundamental de la conducción de experiencias de usuario de alta calidad es garantizar que los clientes administrados están ejecutando versiones actualizadas de Skype para empresas. Esto proporciona varias ventajas, entre ellas:

-   Es más fácil administrar algunas versiones frente a muchas versiones.

-   Proporciona un nivel de coherencia de la experiencia.

-   Resulta más fácil de solucionar problemas relacionados con la facilidad de uso y calidad de llamadas.

-   Microsoft realiza continuamente optimizaciones y mejoras generales en todo el producto. Para que los usuarios reciban estas actualizaciones, reduce su riesgo de tener un problema que ya se ha resuelto.

Limitar la implementación a las versiones de cliente que son menos de seis meses mejorará la experiencia general del usuario y mejorar la administración en comparación a tener grandes cantidades de diferentes versiones del cliente en el mismo entorno.

Si utiliza sólo Office Click-to-Run, estarás automáticamente dentro de la ventana de seis meses. No es necesaria realizar ninguna otra acción.

Si, como la mayoría de las organizaciones, tiene una combinación de paquetes de hacer clic en ejecutar y installer (MSI), puede utilizar el informe para comprobar que se actualizan con regularidad los clientes MSI. Concentrar sus esfuerzos en aquellos clientes donde está el volumen por encima del promedio. Si observa que los clientes se están quedando atrás, trabaje con el equipo responsable de administrar las actualizaciones de Office y asegúrese de que están aprobando y distribuir revisiones de cliente con regularidad.

### <a name="devices-investigations"></a>Investigaciones de dispositivos

Para hacer uso del informe del siguiente dispositivo, lo que es mejor para comprender el concepto de la opinión de Media puntuación (MOS). MOS es la medida estándar de oro para medir la calidad percibida de audio. Se representa como una clasificación de número entero de 0 a 5.

La base de todas las medidas de calidad de voz es cómo una persona percibe la calidad de la voz. Como se ve afectada por la percepción humana, es inherentemente subjetiva. Hay varias metodologías distintas para probar subjetiva.
Mayoría de las medidas de calidad de voz se basa en una escala de calificación (ACR) de categorización absoluta.

En una prueba subjetiva ACR, un número estadísticamente significativo de personas valora la calidad de su experiencia en una escala del 1 (malo) a 5 (excelente). El promedio de las puntuaciones es el MOS. La OP resultante depende de la gama de experiencias que fueron expuestos al grupo y al tipo de experiencia que se considera.

Dado que no resulta práctico para realizar pruebas subjetivas de la calidad de la voz de un sistema de comunicación en vivo, equipos y Skype para empresas generan valores MOS utilizando algoritmos avanzados para predecir objetivamente los resultados de una prueba subjetiva.

El conjunto disponible de MOS y medidas asociadas proporcionan una vista a la calidad de la experiencia que se envía a los usuarios.

Al ofrecer a los usuarios con los dispositivos certificados para equipos y Skype para el negocio, se reduce la probabilidad de que se produzcan experiencias negativas por el propio dispositivo (que es más probable que, por ejemplo, con micrófonos y altavoces integrados para equipos portátiles). Para obtener más información, consulte [los teléfonos y dispositivos de Skype para el negocio](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Uso de dispositivos de captura (micrófonos) por volumen para la organización

Este informe se utiliza para evaluar el uso de micrófono por volumen y puntuación MOS y puede encontrarse en las plantillas de acompañamiento en los clientes y dispositivos*.*

> [!IMPORTANT]
> Informes de dispositivo requieren excluir datos participantes federados. Para excluir los datos de los participantes federados, debe agregar un filtro de consulta para el **Segundo identificador de inquilinos** definido como [ID del inquilino](#tenant-id)de su organización. 

> [!NOTE] 
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajuste **Mes año** para guardar el nuevo mes predeterminado.<br><br> Puede observar al ver este informe que verá el mismo dispositivo informó varias veces. Esto es debido a la forma en que el dispositivo aparece notifica al CQD. Diferencias en el hardware y la configuración regional de sistema operativo notificar datos del dispositivo de forma diferente.

![Captura de pantalla del informe en el panel de calidad llamar a dispositivos (micrófono).](media/quality-of-experience-review-guide-image29.png)

_Figura 29 - – informe de dispositivo (micrófono)_

##### <a name="remediation"></a>Corrección

La primera tarea consiste en determinar el destino MOS que le gustaría alcanzar. MOS las puntuaciones van del 1 al 5, con 5 es la mejor. Elija un destino razonable basándose en su entorno y los resultados de la consulta. En el ejemplo siguiente, el objetivo es una puntuación de MOS de 3.6 o superior para todos los dispositivos que tienen más de 100 secuencias. Obtendrá la calidad de los dispositivos de destino cuando:

-   Resultados de la consulta de dispositivo devuelven MOS \> 3.6 para NumStreams \> 100

Normalmente, necesitará reemplazar dispositivos de bajo rendimiento con dispositivos certificados. Algunas consideraciones al revisar el informe del dispositivo incluyen:

-   ¿Son los dispositivos certificados o conocidos para ser buenas en su entorno? Si un dispositivo certificado o bien se devuelve en la consulta con una puntuación de MOS inferior a la línea de base, puede ser desconocidos factores adicionales (como una red deficiente o suficientemente potente pc) está contribuyendo a la baja calificación.
    Se requerirá una investigación adicional.

-   Puede identificar los usuarios de un dispositivo a través del [Análisis de llamar](#call-analytics-training). Compruebe para asegurarse de que tienen los controladores de dispositivo más recientes y que su dispositivo no está conectado a través de un concentrador USB.

-   Compruebe si hay una correlación entre los dispositivos mal y creación de un sistema concreto y modelo. Si es así, el dispositivo podría ser incompatibles o necesitan actualizaciones del controlador.

La segunda tarea consiste en determinar el uso general de dispositivos no certificados. Recomendamos que al menos el 80 por ciento de todas las secuencias de audio utilice un dispositivo certificado.
Esto se consigue mejor el informe dispositivos a exportar a Excel y calcular manualmente el uso de dispositivos aprobados o no certificados. Las organizaciones suelen mantener una lista de todos los dispositivos aprobados, para filtrar y ordenar los datos deben ser sencilla.

## <a name="appendix-a-lync-networking-guide"></a>Guía de redes del apéndice Lync r.

Para obtener más información sobre los equipos y Skype para conceptos de redes de negocios y la lógica tras su importancia para la calidad, la [Guía de redes de Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) sigue siendo aplicable.

## <a name="appendix-b-network-performance-requirements"></a>Requisitos de rendimiento de red B. apéndice

La calidad de la conectividad de red end-to-end depende en gran medida la calidad de multimedia en tiempo real (audio, vídeo y uso compartido de aplicaciones) a través de IP. Óptima equipos o Skype para calidad de media Business, de la red debe cumplir las siguientes métricas de rendimiento de red.

_Tabla 11 - requisitos de rendimiento de red_

| Métrica                           | Cliente a Microsoft Edge           | Perímetro de cliente a Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Latencia (unidireccional)                | \<50 ms                            | \<30 ms                            |
| Latencia (RTT o tiempo de ida y vuelta) | \<100 ms                           | \<60 ms                            |
| Pérdida de paquetes ráfaga                | \<10% durante cualquier intervalo de 200 ms   | \<1% durante cualquier intervalo de 200 ms    |
| Pérdida de paquetes                      | \<1% durante cualquier intervalo de 15 seg    | \<0,1% durante cualquier intervalo de 15 seg  |
| Vibración de llegada entre paquetes      | \<30 ms durante cualquier intervalo de 15 seg | \<15 ms durante cualquier intervalo de 15 seg |
| Reaprovisionamiento de paquete                   | \<paquetes de salida de la orden de 0,05%       | \<paquetes de salida de la orden de 0,01%      |

Para obtener más información, consulte el siguiente artículo acerca del [rendimiento de red y de calidad media](https://aka.ms/performancerequirements) para los equipos y Skype para los negocios en línea.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Apéndice C. Otros recursos

### <a name="building-data-file"></a>Archivo de datos de creación

-   [Activar y utilizar CQD en Skype para los negocios en línea](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>Formación de CQD

-   <https://aka.ms/sof-cqd>

-   Taller y Guía de [Introducción a CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) .

-   [Guía en línea CQD dimensiones y medidas](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Capacitación de análisis de llamada

-   [Presentación de llamada Analytics](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar el análisis de llamadas de Skype Empresarial](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [Diferencia entre el análisis de llamadas y el Panel de calidad de llamadas](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Usar el análisis de llamadas para solucionar problemas de mala calidad de llamada en Skype Empresarial](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Llame al soporte de análisis

-   Comunidad: [Skype para el programa de vista previa del negocio](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Para obtener soporte, iniciar sesión en nuestro portal [www.skypepreview.com](http://www.skypepreview.com)de vista previa, seleccione **informe de un problema**y utilice la opción de **Crear un nuevo error** para informar de un problema. Tenga en cuenta que los ingenieros de soporte están disponibles para proporcionar soporte técnico del lunes al viernes, entre las horas de 6 A.M. a 9 P.M. EST. Las solicitudes fuera de esas horas se evaluar el día siguiente.

### <a name="devices"></a>Dispositivos

-   [Skype para Business Solutions catálogo PCs y periféricos personales](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Informes de inquilinos

-   [Paquete de contenido de adopción de Office 365](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Creación de informes en Skype Empresarial Online](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Teams Microsoft reporting](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)

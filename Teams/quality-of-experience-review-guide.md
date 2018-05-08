---
title: Calidad de experiencia consulte la guía para los equipos de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guía para analizar el rendimiento de medios en tiempo real para Microsoft Teams utilizando el panel de calidad de llamadas (CQD).
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b5322d6c660e5f8dbb0e18bc052fafbd7a1b69f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="quality-of-experience-review-guide"></a>Calidad de experiencia consulte la Guía

Esta guía es acerca de la fase de valor de unidad para Microsoft Teams y Skype para profesionales en línea. Puede [descargar una versión de Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) de esta guía.

## <a name="introduction"></a>Introducción

Para que el mayor impacto sobre cómo mejorar la experiencia del usuario, las organizaciones necesitan que controle las áreas clave que se muestran en la ilustración siguiente.
Áreas adicionales incluyen la identificación de las tareas operativas, establecimiento de los objetivos de métricas de calidad, determinar las métricas para utilizar para medir el éxito organizativo y áreas de investigación de restricción según sea necesario.

![Áreas clave para la calidad de la experiencia de usuario incluyen audio, confiabilidad, encuestas al usuario, dispositivos y clientes.](media/quality-of-experience-review-guide-image1.png)

_En la figura 1 - áreas operativas clave tratadas a lo largo de este documento_

Al continuamente evaluar y solucionar relativos a las áreas que se describen en este documento, puede reducir su potencial de afectar negativamente a la calidad de la experiencia de los usuarios. Mayoría de experiencia de usuario los problemas encontrada en una implementación puede agruparse en las siguientes categorías:

-   Configuración de firewall o proxy incompleto

-   Cobertura Wi-Fi deficiente

-   Ancho de banda insuficiente

-   VPN

-   Versiones de cliente incoherentes o no actualizada

-   Dispositivos de audio integrados o no optimizados

-   Subredes problemáticas o dispositivos de red

A través de planear y diseñar correctamente antes de implementar los equipos o Skype para profesionales en línea, puede reducir la cantidad de esfuerzo que será necesarios para mantener experiencias de alta calidad.

Esta guía se centra en usar el panel de calidad de llamadas (CQD) Online como la principal herramienta para notificar e investigar cada área, con especial hincapié en audio para maximizar la adopción y el impacto. Todas las mejoras realizadas a la red para mejorar la experiencia de audio traducirá también directamente a las mejoras en uso compartido de escritorio y de vídeo.

Para acelerar la evaluación, se proporcionan dos plantillas CQD curated: uno para administrar todas las redes y la otra se filtra como administrado sólo redes (internas). Aunque los informes de la plantilla de todas las redes están configurados para mostrar la creación y la información de red, aún puede usarse mientras trabaja hacia la recopilación y la carga de información de creación. Cargar información en CQD de compilación, habilita el servicio mejorar la creación de informes mediante la adición de información de creación, la red y la ubicación personalizada mientras diferenciar interno de subredes externas. Para obtener más información, vea [asignación de creación](#building-mapping) más adelante en este documento.

### <a name="what-is-the-cqd"></a>¿Qué es la CQD?

Use el panel de calidad de llamadas (CQD) para obtener información sobre la calidad de las llamadas realizadas mediante el uso de los equipos y Skype para servicios de negocios. CQD está diseñado para ayudar a Skype para profesionales y los equipos de los administradores y los ingenieros de red optimizan la red. CQD busca agregada información para una organización completa donde patrones generales pueden convertirse en evidentes, lo que permite personal realizar las evaluaciones informadas de calidad de la llamada. CQD proporciona informes de métricas de llamada que brindar información sobre la calidad general de las llamadas, llamada de confiabilidad y experiencia del usuario.

> [!NOTE]
> CQD no contiene información de identificación personal (PII). PII es información que puede usar en su propio o con otra información para identificar, póngase en contacto con o busque a una sola persona, o para identificar a un individuo en contexto. 

### <a name="intended-audience"></a>Público objetivo

Este documento está destinado a ser utilizado por las partes interesadas de clientes y socios con funciones como arquitecto o jefe de colaboración, consultor, especialista en administración y adopción de cambio, jefe de soporte técnico y ayuda de asistencia al cliente, potenciales de red, potenciales de escritorio y Admin de TI.

Este documento también está pensada para usarse por la champion(s) calidad designada.
Para obtener más información, vea [la función de los pesos pesados calidad](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Requisitos previos

Antes de usar a esta guía, asegúrese de que tiene el inquilino adecuados [roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) asignados por lo que puede tener acceso a CQD.

-   **Función de administrador Global de office 365:** Tiene acceso a todas las características administrativas en el conjunto de aplicaciones de Office 365 de servicios en el plan, incluyendo Skype para la empresa.

-   **Skype para el rol de administrador empresarial:** Configura Skype para la empresa para su organización y puede ver todos los [informes de actividad](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración de Office 365. Esta función es necesaria, incluso si se implementación sólo los equipos.

Como alternativa, puede asignar la siguiente función a una cuenta de usuario de Office 365 para permitir el acceso a sólo las características de informes.

-   **Lector de informes:** Puede ver todos los [informes de actividad](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración de Office 365, los informes desde el [paquete de contenido de Office 365 adopción](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)e informes CQD.

Descripción de los conceptos clave de CQD ayuda a maximizar el impacto que puede realizar en la mejora de la experiencia de los usuarios con los equipos o Skype para profesionales en línea.
Recursos adicionales pueden encontrarse en el [Apéndice](#other-resources).

## <a name="what-is-quality"></a>¿Qué es la calidad?

Al hablar de calidad en los equipos y Skype para la empresa, es importante definir el término para lograr una comprensión común. Calidad, tal como se define aquí, es una combinación de la experiencia de usuario y las métricas de servicio.

![Métricas de servicio se componen de las versiones de relación, confiabilidad, extremos y a los dispositivos y cliente de llamadas deficientes. Experiencia del usuario final se compone de la percepción del usuario de la calidad de servicio.](media/quality-of-experience-review-guide-image2.png)

_La figura 2: ¿qué es la calidad?_

### <a name="define-your-target-metrics"></a>Definir las métricas de destino

En esta sección se describe las métricas de servicio principal que usamos para evaluar cómo servicios experimentan mantenimiento. Al continuamente evaluar y que dirigen los esfuerzos para mantener estas métricas debajo de destino, ayudaremos a garantizar la que calidad de la llamada coherente y confiable de experiencia de los usuarios. Para comenzar, se proporcionan los siguientes objetivos.
Vamos a explicar brevemente la diferencia entre una red administrada y no administrada:

-   Una red *administrada* puede ser influenciada y controlada por la organización.
    Esto incluye la LAN interna, WAN remoto y VPN.

-   Una red *no administrada* no se puede ser influenciada o controlada por la organización. Un ejemplo de una red no administrada es una red de hotel o un aeropuerto.

_Tabla 1 - medidas de evaluación de estado de destino principales_

|               | Calidad para redes administradas | Confiabilidad para redes administradas |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Nombre de la métrica   | Relación entre % de llamadas de audioconferencias deficientes      | Configuración de la llamada % de errores            | Llamar a colocar % de errores |
| Destino de ejemplo | \<% 3                         | \<% 1                             | \<% 4                 |

Es importante discutir y definir los objetivos de la organización para cumplir los objetivos del negocio. Idealmente, debe identificar estos destinos antes de la implementación.

#### <a name="audio-pcr-"></a>% De audio PCR 

Audio deficiente llamar proporción (PCR) representa el porcentaje general de la organización de las llamadas que tengan la mala calidad de audio. Esta métrica está diseñada para resaltar las áreas donde la organización puede centrarse en tener el impacto más sólido hacia reducir este valor y mejora de la experiencia del usuario, lo que las redes administradas son el foco principal cuando se mira PCR. Los usuarios externos son importantes demasiado, pero difiere de investigaciones de forma organizativa y usuario.
Considere la posibilidad de proporcionar procedimientos recomendados para los usuarios externos y fíjese en las llamadas externas independientemente de la organización global.

#### <a name="call-setup-failures-"></a>Configuración de la llamada % de errores 

Esto representa cualquier sesión de medios que no se ha podido establecerse. Dada la gravedad del impacto en la experiencia del usuario que se mide aquí, el objetivo es reducir este valor para como cercanos a cero como sea posible. Un valor alto para que esta métrica es más frecuente en las nuevas implementaciones con reglas de firewall incompletos que una implementación consolidada, pero sigue siendo importante inspeccionar de forma regular. A medida que crezca su exactitud operativa, puede expandir esta métrica para incluir las cargas de trabajo de vídeo y uso compartido de escritorio.

#### <a name="call-drop-failures-"></a>Llamar a colocar % de errores 

Esto se aplica a una carga de trabajo de audio donde finalizó la sesión de forma inesperada. A medida que crezca su exactitud operativa, puede expandir esta métrica para incluir las cargas de trabajo de vídeo y uso compartido de escritorio.

### <a name="service-metrics"></a>Métricas de servicio

Los objetivos de métricas de servicio constan de las medidas específicas basadas en cliente.

#### <a name="pcr"></a>PCR

La base para determinar si una llamada se clasificó como deficiente es mediante el uso de la relación de llamada deficiente (PCR). PCR se compone de las cinco métricas de red que se describen en la siguiente tabla. Para que una llamada se clasifican como deficiente, sólo una métrica necesita supere el umbral definido. Para obtener más información acerca del proceso de clasificación de llamadas, vea [esta entrada de blog](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tabla 2 - métricas de servicio de llamadas deficientes_

| Métrica                                           | Descripción                                                                                                                                                                                                                                                                                                                                                                  | Experiencia de usuario                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Vibración \>30 ms                                   | Éste es el cambio promedio de retraso entre envíos sucesivos de paquetes. Los equipos y Skype para la empresa pueden adaptarse a algunos niveles de vibración a través de almacenamiento en búfer. Es sólo cuando la vibración supera el almacenamiento en búfer que un participante avisos de los efectos de vibración.                                                                                                                         | Los paquetes que llegan a diferentes velocidades provocarán voz de un altavoz se oye robótica.                                                                                       |
| Tasa de pérdida de paquetes \>0,1 o 10%                    | A menudo se define como un porcentaje de paquetes que se pierden. Pérdida de paquetes afecta directamente a la calidad de audio: desde pequeñas, individual los paquetes perdidos que no tienen casi afectar a las pérdidas de ráfagas opuesta que causa el audio para recortar completamente.                                                                                                                               | Los paquetes se perdidos y que no llegan a su destino previsto provocarán diferencias en los medios, resultantes en palabras y sílabas perdidas y entrecortados vídeo y uso compartidos. |
| Tiempo de ida y vuelta \>500 ms                         | Esto es el tiempo necesario para obtener un paquete IP de punto A punto b y volver al punto A. Este retraso de propagación de red está asociado a la distancia física entre los dos puntos y la velocidad de la luz e incluye una sobrecarga adicional realizada por los diversos dispositivos en la ruta de acceso de red.                                                                                  | Los paquetes tarda mucho tiempo para llegar a su destino causar un efecto transmisor-receptor portátil.                                                                                 |
| Promedio de degradación de NMOS \> 1.0                  | Una o varias de estas métricas de red, aunque individualmente no estaban deficiente, juntos deberse a que la [Media de puntuación de opinión](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) de red (NMOS) para colocar más de un punto. Esto no significa necesariamente la conexión de red es deficiente, pero se han producido suficiente problemas durante la llamada que se ha reducido la calidad. | Esto es una combinación de vibración, la pérdida de paquetes, y, en menor grado, aumenta el tiempo de ida y vuelta. El usuario puede haber una combinación de estos síntomas.          |
| Relación media de muestras ocultas \> 7% o 0,07 | Una o varias de estas métricas de red, aunque individualmente no estaban deficiente, causó el cliente para resolver problemas de los medios. Un ejemplo de audio oculto es una técnica que se utiliza para emparejar la abrupta transición que normalmente podría deberse a paquetes de red perdidos.                                                                                                                | Valores altos indican que se han aplicado niveles significativos de ocultación de pérdida y esperó audio distorsionado o pierden.                                                  |

#### <a name="client-and-device-readiness"></a>Preparación de clientes y dispositivos

Se necesita una estrategia de cliente y dispositivo sólida para asegurarse de que los usuarios tengan una experiencia de usuario coherente y positiva. Unos principios claves de cada estrategia de preparación para la unidad.

##### <a name="client-readiness"></a>Preparación del cliente

Una estrategia de preparación de cliente seguro garantiza que los usuarios están ejecutando la versión más reciente del cliente disfrutando de la mejor experiencia posible.
Microsoft revisiones rutinariamente el Skype para clientes empresariales; asegurarse de que la mantenga actualizados en su entorno es vital para el éxito general.

Se recomienda que no permita que sus versiones de cliente se dividen por más de seis meses. Si está utilizando Office Click-to-Run, está ya que se mantiene actualizados por el servicio. Use el incluye [Un informe de cliente](#determine-client-versions), tal como se describe más adelante en esta guía, para ayudarle con este proceso. También puede aprovechar los informes de ejemplo tasa Mis llamadas para mejorar aún más la estrategia de preparación del cliente.

> [!IMPORTANT]
> Actualmente, los clientes de los equipos se distribuye y se actualizan automáticamente a través de la red de entrega de contenido de Azure y se mantengan actualizados por el servicio. Preparación de cliente y las actividades de investigación no son aplicables a los equipos.


##### <a name="device-readiness"></a>Preparación de dispositivo

No hay una estrategia de único puede afectar a la experiencia del usuario más que la estrategia de preparación del dispositivo. Mayoría de las organizaciones es feliz quitar los dispositivos innecesarios de los usuarios (por ejemplo, teléfonos de escritorio u otros dispositivos de audioconferencias dedicados) y, a menudo, esto es una justificación del negocio principales para cambiar a los equipos o Skype para la empresa. Sin embargo, esas organizaciones mismas dudan a veces para proporcionar dispositivos de sustitución, incluso si esos dispositivos son menos costosas. Equipos portátiles moderna y PCs, aunque dispongan de micrófono y altavoz, no están optimizados para voz de clase empresarial sobre IP (VoIP). A menudo esto crea una mala experiencia para todos los participantes, especialmente si el altavoz está en un entorno con mucho ruido. Programa de certificación de dispositivo de Microsoft se asegura de que, cuando un usuario participa en una llamada telefónica mediante el uso de cualquier dispositivo certificado para los equipos o Skype para la empresa, genera una experiencia que es superior de un dispositivo no certificados.

Siempre se recomienda que los equipos y Skype para usuarios profesionales usar un certificado de auriculares con micrófono o altavoz cuando participa en una llamada de voz mediante el uso de un cliente de escritorio.
Para obtener más información acerca de los dispositivos de certificación de Microsoft, revise este [artículo sobre teléfonos y dispositivos compatibles](https://technet.microsoft.com/office/dn788944.aspx). Use el [Informe de dispositivos](#devices-investigations), más adelante en esta guía, para obtener ayuda con la administración de los dispositivos. También puede usar los informes de ejemplo tasa Mis llamadas para mejorar aún más la estrategia de preparación del dispositivo.

### <a name="user-experience"></a>Experiencia de usuario

Análisis de la experiencia del usuario es más que science, debido a que las métricas se recopilan aquí no siempre significa que hay un problema con la red o servicio, pero en su lugar, que indican que el usuario percibe un problema. Microsoft ofrece un mecanismo de encuesta integrada, conocido como tasa Mis llamadas (RMC): para ayudar a medir la experiencia global del usuario. RMC le ayudarán a responder a las preguntas siguientes desde la perspectiva de los usuarios:

-   ¿Sabe cómo usar la solución?

-   ¿Es la solución intuitiva y fácil de usar, y es compatible con las necesidades de comunicación diarias?

-   ¿La solución me ayuda a realizar mi trabajo?

-   ¿Qué es mi percepción general de la solución?

-   ¿Puedo usar la solución en cualquier momento en el tiempo, independientemente de donde estoy?

-   ¿Puedo configurar y mantener una llamada?

#### <a name="rmc"></a>RMC

RMC se basa en equipos y Skype para la empresa y se configura automáticamente para que se muestre después de que uno en todas las llamadas de 10, o un 10% de todas las llamadas. En este breve encuesta pregunta al usuario para valorar la llamada y proporcionar un contexto poco de por qué la calidad de la llamada es posible que han sido deficiente. Una clasificación de uno o dos se considera mala, es buena tres o cuatro y cinco es excelente. Aunque es un poco de un indicador al retraso, esto es una métrica útil para descubrir problemas que pueden pasar por alto las métricas de servicio.

> [!NOTE]
> Hasta que se indique a los usuarios para responder a encuestas RMC por darnos su opinión buena además de las respuestas incorrectos, normalmente volveremos como muy negativos. La mayoría de los usuarios sólo responden cuando es mala calidad de la llamada. Por este motivo, los informes RMC podrían ser asimétrica hasta el lado deficiente incluso mientras las métricas de servicio son una buena opción. 


Puede usar CQD para informar sobre las respuestas del usuario RMC, y se incluyen informes de muestra en la plantilla de CQD. Sin embargo, no se analizan detalladamente en esta guía. Para obtener más información sobre RMC en Skype para profesionales en línea e instrucciones para informar a los usuarios para dar respuestas RMC útiles, vea esta [entrada de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Categorías de calidad

El éxito de una implementación de alta calidad y confiable en marcha depende de la exactitud operativas de creación. En concreto, preste especial atención a las tres categorías que se muestra en la figura siguiente; Estos son el enfoque de esta guía:

-   **Red:** Calidad de audio centrado en la métrica PCR, uso TCP, subredes con cable e inalámbricas e identificar el uso de servidores proxy HTTP y VPN.

-   **Extremos:** Dispositivos de audio y la versión de cliente (Skype para la empresa sólo).

-   **Administración de servicios:** Esta categoría compone de dos secciones:

    -   En primer lugar, es responsabilidad de Microsoft para administrar y mantener los equipos y Skype para servicios en línea de negocio.

    -   En segundo lugar las tareas que debe administrar su organización para garantizar un acceso confiable a del servicio, como actualizar la información de creación y mantenimiento de firewalls para nuevas direcciones IP de Office 365 como infraestructura se agrega al servicio.

![Las categorías de calidad de una organización: servicio de administración, extremos y la red.](media/quality-of-experience-review-guide-image3.png)

_La figura 3 - categorías críticas para los equipos y Skype para la implementación empresarial en línea_

El gráfico siguiente describe las tareas que debe ejecutar para cada categoría. Le recomendamos que ejecute estas tareas una vez por semana, como mínimo.

La primera vez que realice estas tareas le llevará más esfuerzo que las iteraciones posteriores, debido a que muchas de estas categorías requieren que validar las configuraciones de implementación. Una vez que haya alcanzado el estado que desea con las reuniones de los destinos que ha definido, llevar a cabo estas tareas le ayudará a mantener ese estado.

#### <a name="service-management-tasks"></a>Tareas de administración de servicio

En un mundo de la nube en primer lugar, debe realizar ciertas tareas de administración de servicio para mantener experiencias de usuario de alta calidad. Estas tareas oscilar entre asegurarse de que hay suficiente ancho de banda ponerse en contacto con el servicio sin saturar vínculos de internet, validar que la calidad de servicio (QoS) en lugar de todas las áreas de la red administrada, y, por último: permanecer en la parte superior [rangos IP de Office 365 en los servidores de seguridad](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Tareas de red

Existen dos categorías de tareas de red: confiabilidad y calidad. Confiabilidad se centra en la medición de la capacidad del usuario para realizar llamadas correctamente y permanecer conectado. Calidad se centra en la telemetría agregada que se envía a los equipos y Skype para profesionales en línea por el cliente del usuario durante y después de la llamada ha finalizado.

Dado el impacto crítico que disponga de confiabilidad en la experiencia del usuario, empezar a evaluar e investigar estas métricas antes de comenzar con la calidad.

#### <a name="endpoints-tasks"></a>Tareas de extremos

La tarea principal en esta categoría está validando qué versiones de cliente ejecutan Skype para la empresa en generaciones de escritorio de los últimos seis meses para asegurarse de que los usuarios reciben la ventaja de las optimizaciones continuas realizadas a la Skype para el cliente de escritorio empresarial. Además, esto simplifica las tareas de administración de cliente general y proporciona una experiencia de usuario coherente.

La otra área importante es qué dispositivos son frecuentes en su implementación de supervisión y que dirigen el uso de dispositivos certificados para proporcionar la mejor experiencia de usuario.

> [!IMPORTANT]
> Actualmente, los clientes de los equipos se distribuye y se actualizan automáticamente a través de la red de entrega de contenido de Azure y se mantengan actualizados por el servicio. Preparación de cliente y las actividades de investigación no son aplicables a los equipos.


## <a name="using-the-reports"></a>Uso de los informes

En esta sección se describe los aspectos básicos del trabajo con CQD. Se proporcionan directrices para los siguientes temas:

-   Buscar el identificador de inquilino

-   Creación de informes en los equipos frente a Skype para la empresa

-   En primer lugar frente a clasificaciones de segundo

-   Dimensiones, medidas y filtros

-   Secuencias frente a las llamadas

-   Llamadas de buena, deficientes y sin clasificar

-   Introducción a CQD

-   Edición de informes en CQD

-   Filtrado de informes en CQD

Para obtener información más detallada sobre recursos de aprendizaje y recursos, consulte el [Apéndice](#other-resources).

### <a name="tenant-id"></a>Identificador de inquilino

Algunos informes CQD requieren que incluir un filtro para el identificador del inquilino. Debido a la forma que CQD agrega datos, se incluye telemetría participante federado.
Aunque esto puede resultar valiosa al analizar las métricas de llamadas deficientes, informes de cliente y dispositivo requieren el filtrado de datos para un inquilino específico para excluir telemetría participante federado. Si no conoce su identificador de inquilino, puede usar uno de los métodos siguientes para encontrarlo.

Requisitos de permisos

-   Función de administrador global

-   Skype para el rol de administrador de negocio

#### <a name="azure-ad-portal"></a>Portal de Azure AD

1.  Inicie sesión el portal de Microsoft Azure:<https://portal.azure.com>

2.  Seleccione **Azure Active Directory**.

3.  En **Administrar**, seleccione **Propiedades**. El identificador de inquilino se muestra en el cuadro **Identificador de directorio** .

#### <a name="azure-powershell"></a>PowerShell de Azure

1.  [Instalar el módulo de administración de servicio de Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Abra una ventana de comandos de Windows Azure PowerShell y ejecute el siguiente script, escribir las credenciales de Office 365 cuando se le solicite:  
    **Inicio de sesión AzureRmAccount**

3.  El identificador de inquilino aparece en el resultado.

#### <a name="skype-for-business-online-admin-center"></a>Skype para el centro de administración en línea de negocio

1.  Vete a<https://portal.office.com>

2.  Inicie sesión con su cuenta profesional de administrador de inquilinos.

3.  Seleccione **Skype para la empresa** en **Centros de administrador**.

4.  El identificador de inquilino aparece como **Identificador de organización** en la página de bienvenida.

#### <a name="skype-for-business-online-using-powershell"></a>Skype para profesionales Online mediante PowerShell

1.  [Conectarse a Skype para la empresa en línea a través de PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Ejecute el siguiente comando:  
    **.Tenantid (get-cstenant)**

3.  El identificador de inquilino se muestra como un GUID.

### <a name="teams-vs-skype-for-business"></a>Los equipos frente a Skype para la empresa

CQD puede informar sobre los equipos y Skype para telemetría empresarial. Sin embargo, puede haber ocasiones cuando desea desarrollar un informe que mirar telemetría equipos independiente de Skype para la empresa.

#### <a name="summary-reports"></a>Informes de resumen

Para modificar la página de informes de resumen para ver sólo los equipos o Skype para la empresa, seleccione el menú desplegable de **Filtro del producto** desde la parte superior de la pantalla y, a continuación, seleccione el producto que desee.

![Captura de pantalla del panel de calidad de llamadas que refleja una lista desplegable menú que muestra la opción de filtrar por carga de trabajo.](media/quality-of-experience-review-guide-image4.png)

_La figura 4 - seleccionar un filtro de producto_

#### <a name="detailed-reports"></a>Informes detallados

Para filtrar un informe detallado, agregue el filtro de **Los equipos es** para el informe y establecer en True o False. Para obtener más información, vea [informes de edición](#editing-reports) más adelante en esta sección.

![Captura de pantalla del panel de calidad de llamadas que muestra el sistema de almacenamiento que se puede agregar a un informe detallado.](media/quality-of-experience-review-guide-image5.png)

_La figura 5 - agregar un filtro de Microsoft Teams a un informe_

### <a name="dimensions-measures-and-filters"></a>Dimensiones, medidas y filtros

Una consulta CQD bien formada contiene las tres de los siguientes parámetros:

-   **Dimensión:** ¿Cómo desea en los datos de tabla dinámica.

-   **Medida:** ¿Qué deseo informar sobre.

-   **Filtro:** ¿Cómo desea reducir el conjunto de datos que devuelve la consulta.

Otra forma de analizar esto es una dimensión es la función de agrupación, una medida los datos en que estoy interesado, y un filtro es cómo desea restringir los resultados a aquellos que son relevantes para la consulta.

Un ejemplo de una consulta con formato correcto es "Mostrarme deficientes secuencias [medida] por subred [dimensión] para la creación de 6 [filtro]."

Para obtener más información, vea [las dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm).

Para las dimensiones, las medidas y filtros para los informes que se utilizan en las plantillas de CQD, consulte el [Apéndice](#CQD-training).

### <a name="first-vs-second"></a>En primer lugar frente a segundo 

Muchas de las dimensiones y medidas en CQD se clasifican como primera o segunda.
CQD no usar los campos de autor de la llamada y el destinatario, éstas han sido cuyo nombre ha cambiado _en primer lugar_ y el _segundo_ porque hay pasos intermedios entre el autor de la llamada y el destinatario de la llamada. La siguiente lógica determina qué punto de conexión implicado en la transmisión o la llamada se etiqueta como primero:

-   En primer lugar siempre será un extremo de servidor (servidor de conferencia, el servidor de mediación etc.) si un servidor está involucrado en la secuencia o la llamada.

-   En segundo lugar siempre será un extremo de cliente a menos que la secuencia se encuentra entre dos extremos de un servidor.

-   Si ambos extremos son del mismo tipo, la elección de los cuales es el primera se basa en orden interno de la categoría de agente de usuario. De este modo se asegura que el orden es coherente.

Para obtener más información acerca de cómo determinar el extremo de la primero o segundo cuando están ambos el mismo, vea [las dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Secuencia frente a la llamada

Es necesario comprender la diferencia entre una llamada y una secuencia correctamente elegir qué dimensiones o medidas que se utilizan en CQD.

**Secuencia:** Existe una secuencia entre solo dos extremos. Hay sólo una secuencia para cada dirección, y dos secuencias son necesarias para la comunicación. Las secuencias son útiles para analizar los edificios o redes. En algunos casos, llamada y stream se usan en el nombre (por ejemplo, secuencia de llamada del programa de instalación o secuencia de llamada de texto).
Estos aún se clasifican como único secuencias.

**De llamadas:** Una llamada es una agrupación de todas las secuencias de todos los participantes. Consta de una llamada de, como mínimo, dos secuencias. Una sola llamada tendrá dos participantes con un mínimo de una secuencia. Las llamadas son útiles para analizar las tendencias a través del tiempo.

Para obtener instrucciones adicionales sobre si la dimensión o medida es cómo hacer referencia a una llamada o una secuencia, vea [las dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Llamadas de buena, deficientes y sin clasificar

Una llamada se categoriza ya sea como una buena, deficiente o sin clasificar. Hablemos un poco para hablar de cada uno de ellos con más detalle.

**Buena o mala:** Una llamada buena o mala consta de una llamada que contiene un conjunto completo de las métricas de servicio, para la que se generó un informe de QoE completo.
Determinar si una llamada es buena o mala es descritas [anteriormente en esta guía](#pcr).

**Sin clasificar:** Una llamada sin clasificar no contiene un conjunto completo de las métricas de servicio. A menudo son llamadas breves, normalmente menos de 60 segundos: donde no se ha podido calcular promedios y no se genera un informe de QoE.

### <a name="access-cqd-online"></a>Acceso CQD en línea

Puede tener acceso a CQD de dos maneras.

-   Vaya a <https://cqd.lync.com>.

-   Vaya a **Skype para el centro de administración de negocio** \> **Herramientas**y seleccione el vínculo a CQD, tal y como se muestra a continuación.

![Captura de pantalla que muestra "herramientas" seleccionadas en el panel de la barra de navegación izquierda y el vínculo a "Skype para profesionales Online llame al panel de calidad" seleccionado.](media/quality-of-experience-review-guide-image6.png)

_La figura 6: acceso a CQD a través de la Skype para el centro de administración de negocio_

### <a name="getting-started"></a>Introducción

Cuando en primer lugar, vaya a CQD, verá la página informes de resumen. La mayoría de los informes que se describen en esta guía están personalizados informes detallados. Para empezar a usar los informes detallados, seleccione **Informes de resumen** en la parte superior de la página y, a continuación, elija **Informes detallados**.

![Captura de pantalla de la depcting del panel de calidad de llamadas los diferentes tipos de informes que están disponibles.](media/quality-of-experience-review-guide-image7.png)

_La figura 7 - navegar a informes detallados_

La página de informes detallados en CQD es similar a la ilustración se muestra a continuación.

![Captura de pantalla de la página de informe detallado en CQD y los distintos elementos que componen un informe.](media/quality-of-experience-review-guide-image8.png)

_La figura 8 - página de informes detallados_

1.  El panel Resumen muestra contexto para el conjunto de informe que aparece a la derecha.

2.  Puede seleccionar **Editar** en el panel Resumen para establecer propiedades de nivel de informe (incluido el alto del eje y).

3.  La ruta de exploración ayuda a los usuarios a identificar su ubicación actual en la jerarquía del conjunto de informe.

4.  Informes que tienen informes secundarios se muestran con un vínculo azul. Al seleccionar el vínculo, puede desglosar los informes secundarios.

Elija a las líneas de tendencia para mostrar los valores detallados y gráficos de barras. El informe que tiene el foco mostrará el menú Acción: **Editar**, **clon**, **Eliminar**, **Descargar**y **Exportar informe de árbol**.

### <a name="editing-reports"></a>Edición de informes

Cuando seleccione **Editar** en el menú Acción de un informe, podrá abrir Editor de consultas. Cada informe se respaldados por una consulta. Un informe es una visualización de los datos devueltos por su consulta. El Editor de consultas es una interfaz de usuario para su edición estas consultas además de las opciones de presentación para el informe, como se muestra en la ilustración siguiente.

![Captura de pantalla de la página de informe detallado en CQD y los distintos elementos que componen un informe cuando el informe se está editando.](media/quality-of-experience-review-guide-image9.png)

_En la figura 9 - Editor de informes_

1.  Elija filtros, medidas y dimensiones desde el panel izquierdo. Apuntar a un valor existente, muestra un botón Cerrar (**X**), que puede optar por quitar el valor.

    1.  Mediante la selección de la dimensión o medida, puede cambiar el título mediante la edición en el campo **título** . También puede cambiar el orden seleccionando el azul hacia arriba o hacia abajo flechas en el panel superior.

    2.  Selección (**+**) junto a un título, se abre el cuadro de diálogo para agregar una nueva dimensión, una medida o un filtro.

    3.  Escriba las primeras letras de la dimensión, una medida o un filtro en la **Buscar un** campo para filtrar la lista para facilitar su búsqueda.

2.  El panel superior muestra las opciones para la personalización de gráfico.

3.  El Editor de consultas, se muestra una vista previa del informe.

4.  Use el cuadro de **Edición** en la parte inferior de la pantalla para crear o editar una descripción detallada del informe.

### <a name="filtering-reports"></a>Filtrado de informes

Las plantillas que proporciona incluye varias consultas integradas y filtros del informe. En las secciones siguientes se describen los filtros más comunes que se utilizan a lo largo de las plantillas.

#### <a name="cqd-filter"></a>Filtro CQD

Puede usar el filtro CQD o filtro para direcciones URL, para filtrar temporalmente cada consulta de informe. Es el filtro CQD más comunes que va a utilizar filtrar informes que se deben excluir telemetría participante federado. Se recomienda que este filtro se define un marcador para que se convierta en la vista predeterminada. Exclusión de datos federados de informes CQD es útil cuando está solucionar relativos a los edificios administrados o redes donde datos federados pueden influir en el informe.

Para implementar un filtro de CQD, en la barra de direcciones del explorador, anexe lo siguiente al final de la dirección URL:

/Filter/ [AllStreams]. [Segundo identificador de inquilino] \|[Su identificador de INQUILINO aquí]

**Ejemplo:**  
https://cqd.lync.com/cqd/\#/ 02-1234567/2018/filtro / [AllStreams]. [Segundo identificador de inquilino] \|[TENANTID] & inquilino = TENANTID

> [!NOTE]
> El ejemplo de dirección URL anterior es para obtener sólo la representación visual. Utilice el vínculo CQD predeterminado de <https://cqd.lync.com>.

#### <a name="query-filters"></a>Filtros de consulta

Filtros de consulta se implementan mediante el Editor de informes. Estos filtros se utilizan para reducir el número de registros devueltos por CQD, lo cual se minimiza tamaño total del informe. Esto es especialmente útil para el filtrado de redes no administradas.
Los filtros siguientes usan expresiones regulares (RegEx).

_Tabla 3 - filtros de consulta_

| Filtro               | Descripción          | Ejemplo de filtro de consulta CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Valores en blanco         | Algunos filtros no tienen la opción para filtrar los valores en blanco. Para filtrar manualmente valores en blanco, use la expresión en blanco y establezca el filtro en es igual a o no es igual a, según sus necesidades.                                                                                                                             | Nombre del segundo edificio \< \> \^ \\s\*\$                       |
| Subredes particulares populares | Sin un archivo de creación válido para separar administrada desde redes no administradas, obtener incluirá redes particulares en los informes. Estas subredes particulares están fuera del ámbito del control de TI y pueden excluirse rápidamente de un informe. Subredes particulares populares, como se define en esta guía, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Segunda subred \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Inside frente a fuera   | Se usa para filtrar un informe para (inside) administrado o no administrado (externa). La plantilla CQD administrada ya está preconfigurada con estos filtros.                                                                                                                                                                                | En segundo lugar dentro de Corp = dentro de                               |

#### <a name="report-filters"></a>Filtros del informe

Filtros del informe se implementan mediante la adición de un filtro en el informe representado, ya sea en el Editor de informes o directamente en el informe. Los siguientes filtros de informes se usan en toda la plantilla.

_Tabla 4 - filtro de informe_

| Filtro     | Descripción                            | Ejemplo de filtro de informe CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Empiece con el año inicial y, a continuación, mes. | 10 de 2017                           |
| Alfabéticos | Filtra todos los caracteres alfabéticos. | [a-z]                             |
| Numérico    | Filtra todos los caracteres numéricos.    | [0-9]                             |
| Porcentaje | Filtra por un porcentaje.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importar las plantillas CQD

Esta guía consta de [dos plantillas de CQD curated](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Estas plantillas aceleran su uso de CQD y proporcionan una oportunidad de aprovechar rápidamente las capacidades del CQD para realizar un impacto en los equipos o Skype de los usuarios para que la experiencia empresarial. La plantilla de todas las redes, aunque optimizado para trabajar con un edificio se puede usar el archivo de datos, mientras se trabaja hacia la recopilación y la carga de información de creación en CQD, tal como se describe en la siguiente sección.

**Para importar las plantillas (. CQDX) en CQD en línea**

1.  Vaya a <https://cqd.lync.com>.

2.  Realice la autenticación mediante el uso de las credenciales administrativas de Office 365.

> [!NOTE]
> Debe tener Office 365 administrador Global, Skype para Administrador empresarial o rol de lectores de informes tener acceso a CQD. 


3.  Seleccione el menú de **Informes de resumen** en la parte superior de la página y, a continuación, elija **Informes detallados**.

4.  En el panel Resumen, seleccione **Importar**. Vaya a la ubicación de guardado de CQDX, seleccione la plantilla CQDX y, a continuación, seleccione **Abrir**.

5.  Después de carga la plantilla, como una ventana emergente mostrará el mensaje "importación de informe fue correcta". Seleccione **Aceptar.**

![Captura de pantalla de una ventana emergente que informa al usuario de que la plantilla se ha importado correctamente.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Repita los pasos 4 y 5 para la segunda plantilla CQD.

> [!NOTE]
> Las plantillas CQD se importan por usuario. Si necesitan usar el informe de usuarios adicionales, debe iniciar sesión en e importar las plantillas a su instancia CQD. 


## <a name="building-mapping"></a>Asignación de creación

En un equipo o Skype para la implementación empresarial en línea, todos los clientes son externos.
Que tiene la implicación que de forma predeterminada, todos los clientes son conocida como fuera de CQD en línea, independientemente de si el cliente se ha conectado en una red corporativa interna.

Cuando se trabaja con la calidad de las llamadas, necesita conocer la ubicación de un cliente y si estaba conectado a una red puede administrar o una red no se puede administrar: la suposición de que se va a que solo puede mejorar las redes puede administrar.
Mediante la carga de red y la información de creación a CQD Online, habilitar CQD determinar si un cliente se conecta a una red interna corporativa o administrados o a una red externa y no administrado.

### <a name="building-data-file-structure"></a>Estructura de archivos de datos de creación

El formato del archivo de datos que se carga debe cumplir los siguientes requisitos para pasar la comprobación de validación antes de cargarlas.

-   El archivo debe ser un archivo TSV, lo que significa que, para cada fila, cada columna viene separada por un carácter de tabulación, o un archivo CSV en el que cada columna viene separada por una coma.

-   El archivo no se puede tener más de 50 MB.

-   El contenido de los datos de archivo *no debe incluir los encabezados de tabla*. En otras palabras, la primera línea del archivo de datos debe ser datos reales, no los encabezados de columna, como "Red".

-   Para cada columna, el tipo de datos sólo puede ser cadena, número o Bool. Si el tipo de datos es el número, el valor debe ser un valor numérico; Si es Bool, el valor debe ser 0 o 1.

-   Para cada columna, si el tipo de datos es la cadena, los datos pueden estar vacíos (pero aún deben estar separados por un delimitador adecuado, que es un carácter de tabulación o una coma). Esto sólo asigna ese campo un valor de cadena vacía.

-   Debe haber 14 columnas para cada fila. Cada columna debe tener el tipo de datos que se describen en la siguiente tabla y las columnas deben estar en el orden indicado en la tabla.

_Tabla 5: creación de la estructura de archivos_

| Nombre de columna        | Tipo de datos | Ejemplo                   | Orientación    |
|--------------------|-----------|---------------------------|-------------|
| Red            | Cadena    | 192.168.1.0               |  Obligatorio    |
| NetworkName        | Cadena    | Estados Unidos/Seattle/SEATTLE-mar-1 | Obligatorio\*  |
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

\*Si bien no es necesario por CQD, las plantillas están configuradas para mostrar la generación y red nombre.

#### <a name="supernetting"></a>Creación de superredes

Puede usar la creación de superredes, denominado habitualmente enrutamiento de interdominios sin clases (CIDR), en lugar de definir cada subred. Una *supernet* es una combinación de varias subredes que comparten un solo prefijo de enrutamiento. En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes/CIDR. Se admite la creación de superredes, pero no se recomienda usarlo.

Por ejemplo, la creación de marketing de Contoso se compone de las subredes que aparece a continuación:

-   10.1.0.0/24 – primera planta

-   10.1.1.0/24 – segundo piso

-   10.1.2.0/24 – tercer piso

-   10.1.3.0/24 – cuarto floor

En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes/CIDR: en este ejemplo, 10.1.0.0/22.

-   Red = red dividida 10.1.0.0

-   Intervalo de red = 22

A continuación presentamos algunas cosas que se deben considerar antes de implementar la creación de superredes:

-   Creación de superredes tarda menos tiempo front-, pero lo que respecta a costa de la reducción de la flexibilidad de los datos. Supongamos que hay un problema de calidad que implican subred 200.1.2.0. Si implementa la creación de superredes, no sabrá donde se encuentra la subred en el edificio o qué tipo de red es (por ejemplo, un laboratorio). Si se hubiera definido todas las subredes de un edificio y cargar información de ubicación de planta, podrá vea esa distinción.

-   Es importante para asegurarse de que la dirección de superredes/CIDR es correcta y no captura de subredes no deseadas.

-   Creación de superredes se puede usar en una asignación de creación con máscara de bits de 8 a 28 bits.

-   Es un proceso bastante común para buscar 192.168.0.0 en los datos. Para muchas organizaciones, esto indica que el usuario está en casa. Para otras personas, éste es el esquema de direcciones IP de una oficina satélite. Si su organización tiene oficinas que usan esta configuración, no la incluye en su archivo de creación como es difícil distinguir entre las redes domésticas e internas mediante el uso de subredes comunes.

> [!IMPORTANT]
> El intervalo de red puede usarse para representar un supernet. Creación de todas las nuevas cargas de archivos de datos se comprobarán para cualquier intervalos superpuestos. Si anteriormente se ha cargado un archivo de creación, debe descargar el archivo actual y cargar nuevo para identificar cualquier superposiciones y solucionar el problema. Cualquier superposición en los archivos cargados previamente puede provocar en las asignaciones de incorrectos de subredes a edificios en los informes. 


#### <a name="vpn"></a>VPN

La calidad de los datos de la experiencia (QoE) que los clientes de envían a Office 365, que es donde se proceden de datos CQD: incluye una marca VPN. Sin embargo, esta marca se basa en proveedores de VPN informar a Windows de que el adaptador de red VPN registrado es un adaptador de acceso remoto. No todos los proveedores de VPN registran correctamente los adaptadores de acceso remoto. Por este motivo, es posible que no pueda utilizar los filtros de consulta integrados de VPN. Existen dos enfoques para adaptación a subredes VPN en la creación del archivo de información.

-   Definir un **Nombre de red** mediante el texto "VPN" en este campo para subredes VPN.

![Captura de pantalla de un informe en el panel de calidad de llamadas que define cómo crear una subred VPN](media/quality-of-experience-review-guide-image10.png)

_La figura 10 - VPN mediante el nombre de red_

-   Para definir un **Nombre del edificio** , con el texto "VPN" en este campo para subredes VPN.

![Captura de pantalla de un informe en el panel de calidad de llamadas que define cómo crear una definición de creación que consta de una subred VPN.](media/quality-of-experience-review-guide-image11.png)

_La figura 11 - VPN mediante el nombre del edificio_

> [!IMPORTANT]
> Algunas implementaciones de VPN no notificar con precisión la información de subred. Si esto ocurre en la creación de informes, que se recomienda que cuando se agrega una subred VPN para el archivo de creación, en lugar de una entrada para la subred, agregar entradas independientes para cada dirección de la subred VPN como una red independiente de 32 bits. Cada fila puede tener los mismos metadatos de creación. Por ejemplo, en lugar de una fila por 172.16.18.0/24, tiene 253 filas, con una fila por cada dirección de 172.16.18.1/32 a través de 172.16.18.254/32, ambos inclusive.


> [!NOTE]
> Se sabe que las conexiones VPN identificar incorrectamente la conexión de red como por cable cuando la conexión a internet subyacente es inalámbrica. Cuando se mira calidad a través de conexiones VPN, no se puede suponer que el tipo de conexión se ha identificado con precisión.

### <a name="uploading-building-information"></a>Cargar información de creación

El panel de informes de resumen de CQD incluye una página **Inquilino la carga de datos** , puede tener acceso seleccionando la etiqueta de vínculo **Inquilino la carga de datos** en la esquina superior derecha (busque el icono del engranaje). Esta página se usa para los administradores para cargar su propia información, como la asignación de dirección IP y la información geográfica, asignación de cada punto de acceso inalámbrico y su dirección MAC y así sucesivamente.

1.  Vaya a CQD Online buscando en <https://cqd.lync.com>.

2.  Seleccione el icono del engranaje en la esquina superior derecha y elija el **Inquilino al cargar los datos** desde la página **Informes de resumen** .

![Captura de pantalla de un cuadro de diálogo en el panel de calidad de llamadas que aparece mientras se está cargando datos.](media/quality-of-experience-review-guide-image12.png)

_La figura 12 - menú cargar datos de inquilinos_

1.  Como alternativa, si se trata de la primera vez que visita CQD, se solicitará a cargar los datos de creación. Puede seleccionar **Cargar ahora** para navegar rápidamente a la página de **Carga de datos de inquilinos** .

![Captura de pantalla de una pancarta en el panel de calidad de llamada que notifica a un usuario para cargar datos de creación.](media/quality-of-experience-review-guide-image13.png)

_La figura 13: creación de pancarta de carga de datos_

1.  En la página de **Carga de datos de inquilinos** , seleccione **Examinar** para elegir un archivo de datos.

2.  Después de seleccionar un archivo de datos, especifique la **fecha de inicio** y, opcionalmente, especifique una fecha de finalización.

3.  Después de seleccionar la **fecha de inicio**, seleccione la opción **cargar** para cargar el archivo en el CQD. <br><br>Antes de que se carga el archivo, se valida. Si se produce un error de validación, se muestra un mensaje de error que solicita que se corrija el archivo. La siguiente ilustración muestra un error que se producen cuando el número de columnas en el archivo de datos es incorrecto.

![Captura de pantalla de un cuadro de diálogo en el panel de calidad de llamadas que describe un mensaje de error al importar los datos de creación.](media/quality-of-experience-review-guide-image14.png)

_La figura 14: creación de error de carga de datos_

4.  Si no se producen errores durante la validación, la carga de archivos se realizará correctamente. A continuación, puede ver el archivo de datos que se cargan en la tabla **Mis cargas** , que muestra la lista completa de todos los archivos que se cargan para el inquilino actual en la parte inferior de la página.

> [!NOTE]
> Puede tardar hasta cuatro horas para finalizar el procesamiento del archivo de creación. <br><br> Si ya se ha cargado un archivo de creación y necesita para agregar subredes que es posible que se han cumplido o excluidos, modifique el archivo original mediante la adición de las nuevas subredes, quite el archivo actual y volver a cargar el archivo recién editado. Puede haber creación activo sólo un archivo de datos en CQD. 

### <a name="missing-subnets"></a>Subredes que faltan

Después de cargar información de creación para redes administradas, cada red administrada debe tener una asociación de creación. Sin embargo, esto no siempre es el caso; Normalmente, se pierden algunas subredes. En esta sección, se explica cómo validar las redes que faltan.

Vaya a la página de **Informes detallados** en CQD en línea y navegue hasta el **Informe de subred falta** incluidas en las plantillas CQD. Esto presenta todas las subredes con secuencias de 10 o más audio que no están definidas en la creación de archivo de datos. Asegúrese de que no hay ninguna red administrada en esta lista. Si faltan subredes, actualice la creación original del archivo de datos y volver a cargarla a CQD.

> [!IMPORTANT]
> Debe agregar el identificador de inquilino como un filtro de consulta para el **Segundo identificador de inquilino** a este informe para filtrar el informe para ver sólo los datos de inquilino de su organización. De lo contrario, el informe mostrará subredes federadas.

> [!NOTE] 
> Asegúrese de ajustar el filtro de informe de año mes al mes actual. Seleccione **Editar**y ajustar el filtro de informe de **Mes año** para guardar el nuevo mes predeterminado.                                                  |

![Informe que muestra las subredes no se incluye en el archivo de datos de creación de CQD que muestran el uso.](media/quality-of-experience-review-guide-image15.png)

_La figura 15: informe de creación que falta_

## <a name="reliability-investigations"></a>Investigaciones de confiabilidad

El primer paso para mejorar la calidad es para evaluar el estado de confiabilidad de audio en toda la organización. Debido a que la confiabilidad de audio es vital para una experiencia de usuario positivo, empezamos con los dos componentes que miden la confiabilidad:

1.  **Errores en la instalación de llamadas:** No se puede establecer la sesión.

2.  **Colocar errores de llamadas:** Sesión se haya establecido y finalizado de forma inesperada

En esta sección, trataremos métodos para investigar ambas áreas.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía. La descripción del informe individuales para obtener más información, consulte.


### <a name="call-setup"></a>Programa de instalación de la llamada

Establecer prioridades de solucionar errores del programa de instalación de llamadas en esta área en primer lugar, ya que estos errores tienen un impacto negativo significativo en la experiencia del usuario.

Comenzar su investigación evaluando el porcentaje de errores en la instalación llamada general para la organización y, a continuación, asignar prioridades a las áreas de investigación según el porcentaje más alto mediante la creación o la red.

#### <a name="call-setup-failures-overall"></a>Errores de configuración generales de llamadas

Este informe de gráfico muestra la cantidad total de llamada correcta, configurar y errores del programa de instalación de llamadas a través del tiempo. Seleccione cualquiera de las columnas para mostrar sus valores individuales, como se muestra en la figura siguiente.

![Captura de pantalla de un gráfico que muestra el porcentaje de secuencia del programa de instalación error de llamada de Audio](media/quality-of-experience-review-guide-image16.png)

_Errores de la figura 16 - confiabilidad de Audio - llamadas secuencia del programa de instalación_

##### <a name="analysis"></a>Análisis

Este informe muestra el uso del programa de instalación de llamada de audio y los errores de su organización a través del tiempo. Mediante el uso de este informe, puede responder a las siguientes preguntas y determinar el curso de acción siguiente:

1.  ¿Qué es el porcentaje de error del programa de instalación de llamada total para el mes actual?

2.  ¿Es el porcentaje de errores de llamada total del programa de instalación por debajo o por encima de la métrica de destino definido?

3.  ¿Es la tendencia de error peor o mejor que el mes pasado?

4.  ¿La tendencia de errores aumenta, steady, o disminuye?

La información presentada en este informe indicará a la historia de ¿con qué frecuencia se producen errores en sus configuraciones de llamada general en toda la organización.

Independientemente de las respuestas anteriores, tómese tiempo para investigar más mediante el uso de los informes de subcaracterística incluye para buscar cualquier edificios individuales o las redes que necesiten corrección. Aunque es posible que el porcentaje de errores generales por debajo de la métrica de destino, a menudo las tasas de error para uno o varios de los edificios o redes están por encima de la métrica y necesitan corrección.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Llamar a errores en la instalación mediante la creación y la subred 

Este informe de tabla se usa para detectar y aislar los edificios o las redes que necesiten corrección.

> [!NOTE]
> Asegúrese de ajustar el filtro de informe de año mes al mes actual. Seleccione **Editar**y ajustar el filtro de informe de **Mes año** para guardar el nuevo mes predeterminado.


![Informe de que las listas de llamada del programa de instalación error motivos, organizados por creación, red y subred al mes.](media/quality-of-experience-review-guide-image17.png)

_Figura 17 - errores de Audio del programa de instalación mediante la creación o subred_

##### <a name="remediation"></a>Corrección 

Centrar los esfuerzos de corrección en los edificios o subredes que tienen el mayor volumen de errores en primer lugar, ya que esto maximizar el impacto en la experiencia del usuario y ayudan a reducir rápidamente los errores del programa de instalación de llamada organizativa.
En la siguiente tabla se enumera las dos razones para errores de llamadas del programa de instalación beneficiarán de acuerdo con CQD.

_Tabla 6: razones para errores de llamadas del programa de instalación_

| Llamar a causa de errores en la instalación                       | Causa típica                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Falta una regla de exención de inspección RV profunda del paquete | Indica que el equipo de red a lo largo de la ruta de acceso impide que la ruta de acceso de medios está estableciendo debido a las reglas de inspección profunda del paquete. Esto es probable que debido a las reglas de firewall no está configuradas correctamente. En este caso se ha realizado correctamente en el protocolo de enlace TCP pero no se ejecutó el protocolo de enlace SSL.               |
| Falta una regla de excepción del bloque RV IP               | Indica que el equipo de red a lo largo de la ruta de acceso impide que la ruta de acceso de medios está estableciendo a la red de Office 365. Esto puede resultar debido a las reglas de proxy o firewall no está configuradas correctamente para permitir el acceso a direcciones IP y los puertos usados para los equipos y Skype para el tráfico de negocio. |

Ahora cuando comience la corrección, puede Centrar los esfuerzos de un determinado edificio o subred. Como se muestra en la tabla anterior, estos problemas son debido a las configuraciones de firewall o proxy. Revise las opciones en la tabla siguiente para las acciones de corrección.

_Tabla 7: pasos siguientes para llamada de corrección de error del programa de instalación_

| Corrección           | Orientación     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar servidores | Trabajar con el equipo de red y comprobar la configuración de servidores frente a [la lista de direcciones IP de Office 365](https://aka.ms/o365ips). Compruebe que las [subredes de medios](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) y puertos se encuentran en las reglas de firewall. Compruebe que se abren los puertos TCP y UDP necesarios en el servidor de seguridad. Medios prefiere UDP a través de TCP. TCP se considera un protocolo de la conmutación por recuperación.<br><ul><li>**TCP:** el puerto 443</li><li>**UDP:** puertos 3478 – 3481</li><ul> |
| Comprobar                | Sacar provecho de la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar la conectividad de la creación afectado o subred mediante el uso de la función de comprobación de conectividad.    |


### <a name="call-drop"></a>Colocación de llamada

A diferencia de errores de llamadas del programa de instalación, no hay ningún código de motivo para indicar por qué llamada colocada errores se produjo, lo que dificulta aislar una causa concreta. Para detectar mejor llamadas interrumpidas, usa un enfoque inferido. Al solucionar relativos a las áreas de interés para el audio, aplicación de revisiones de los clientes y que dirigen el uso de dispositivos certificados para equipos y Skype para la empresa, cabría esperar errores de llamadas colocada a rechazar.

#### <a name="call-drop-failures-overall"></a>Errores de entrega general de llamadas

Este informe de gráfico muestra la cantidad total de secuencias de audio, las secuencias de audio totales colocadas, y secuencia total colocada porcentaje. Seleccione cualquiera de las columnas para mostrar sus valores, como se muestra en la ilustración siguiente.

![Captura de pantalla de un gráfico que muestra el porcentaje de colocada secuencias de llamada de Audio](media/quality-of-experience-review-guide-image18.png)

_Porcentaje de errores de la figura 18 - llamada Total colocada_

##### <a name="analysis"></a>Análisis

Este informe de gráfico muestra los errores y el uso de su organización a través del tiempo relacionadas con gotas de llamadas. Mediante el uso de este informe, puede responder a las siguientes preguntas:

1.  ¿Qué es la llamada actual total colocada porcentaje?

2.  ¿Es el porcentaje del total del buzón por debajo de la métrica de destino definido?

3.  ¿Es la tendencia de error peor o mejor que el mes pasado?

4.  ¿La tendencia de errores aumenta, steady, o disminuye?

La información presentada en este informe puede contar la historia de ¿con qué frecuencia se están produciendo sus gotas de llamada general en toda la organización.

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo para investigar utilizando los subinformes para buscar cualquier edificios o redes que podrían necesitar corrección. Aunque es posible que la velocidad de buzón global por debajo de la métrica de destino, a menudo la tasa de entrega de uno o varios de los edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Errores de unión de llamadas por edificio o subred

Errores en este informe de tabla indican que la llamada se ha colocado de forma inesperada y resulta en una experiencia de usuario negativo. Existen dos informes de tabla incluidos en la plantilla, uno para investigar la conferencia y el otro para entre dos participantes.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.


![Que el número de listas y el porcentaje de llamadas interrumpidas, organizados por subred al mes, red y creación de informes.](media/quality-of-experience-review-guide-image19.png)

_La figura 19: llamada de Audio colocada errores por edificio o subred_

##### <a name="remediation"></a>Corrección

Con el informe de tabla anterior, ahora puede aislar "problemáticos" en la red administrada donde se produzcan gotas de llamada por encima de la métrica de destino definido. Centrar los esfuerzos de corrección en los edificios o las redes que tienen el número de secuencia total más alto en primer lugar, para obtener el mayor impacto.

Causas habituales de gotas de llamada:

-   Salida de red o de internet en aprovisionado

-   Sin QoS configurado en redes limitadas

-   Versiones anteriores de cliente

-   Comportamiento de usuario

Después de descubrir problemáticos, puede aprovechar [Análisis llamar](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) para revisar aún más los usuarios de dicho edificio problemas específicos. Análisis de llamada contiene datos PII y pueden ser útil para aislar aún más los posibles motivos de gotas de la llamada.

Independientemente del siguiente paso, es una práctica recomendada para notificar el departamento de soporte técnico que se ha detectado un problema con los edificios específicos o subredes. De este modo, rápidamente pueden responder a las llamadas entrantes y clasificar los usuarios de forma más eficaz. Los usuarios marcados se pueden, a continuación, notificar al equipo de ingeniería para una mayor investigación.

En la siguiente tabla se enumera algunos métodos comunes para administrar y corregir gotas de llamada.

_Tabla 9 - pasos siguientes para llamada drop corrección_

| Corrección                              | Orientación     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Red o a internet                         | Ahora que ya sabe qué edificio se ve afectada, trabaje con su equipo de red para supervisar el ancho de banda en dicho edificio para determinar si hay problemas con sobreutilización. Si se detecta el problema a estar relacionados con la congestión de la red, considere la posibilidad de ancho de banda creciente a dicho edificio. <br><br>**QoS:** Si cada vez mayor ancho de banda es imposible o costo sumamente elevado, considere la implementación de QoS. Esto garantizará que se asignan prioridades a los paquetes de multimedia en la red administrada por encima el tráfico de medios que no sean. Como alternativa, si no hay ninguna evidencia borrar que dicho ancho de banda es el punto de entrada, tenga en cuenta estas soluciones:<br><ul><li>[Instrucciones de QoS de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obtener instrucciones de QoS de negocio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Realizar una evaluación de disponibilidad de red:** Una evaluación de la red proporciona información detallada sobre el uso del ancho de banda esperado, cómo lidiar con ancho de banda y de la red cambia y redes procedimientos recomendados para los equipos y Skype para la empresa. Uso de la tabla anterior como su origen, tener una lista de los edificios o subredes que son candidatos excelentes para una evaluación. <br><ul><li>[Evaluación de preparación de redes de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para evaluación de preparación para la red empresarial](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Herramienta de evaluación de la red de Microsoft:** Use esta herramienta para una prueba simple de rendimiento de la red para determinar el grado en que debería realizar la red para los equipos de un o Skype para llamadas en línea de negocio. La herramienta le ayuda a evaluar el rendimiento de una subred y validar la preparación de la red frente a [requisitos](https://aka.ms/performancerequirements)de rendimiento de Microsoft.<ul><li>[Descargar la herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Los clientes (Skype para la empresa sólo en línea) | Algunos clientes más antiguos tienen conocidos, documentan problemas con la confiabilidad de los medios. Revisar los informes de análisis de llamadas desde varios usuarios afectados o crear un informe de tabla de versión de cliente personalizado en CQD filtrado a edificios específicos o subredes con medida % de error Total de llamadas colocada. Esta información le ayudará a comprender si existe una relación entre gotas de llamada en dicho edificio específico y una versión específica del cliente.                                                                                                                                                              |
| Dispositivos                                  | La mayoría de los errores de dispositivo son debido al uso de dispositivos que no están certificados para los equipos o Skype para la empresa. Errores normalmente adoptan la forma del integrada altavoces o micrófonos que se usan o combinaciones de earbud/micrófono que están conectadas a la toma de audio de 3,5 mm en un dispositivo. Recomendación actual de Microsoft es que los usuarios que están experimentando llamar a gotas: o deficientes llama en general y son el uso de dispositivos integrados o controladores debe ser aprovisionar un [certificado auriculares con micrófono o altavoz](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). |
| Comportamiento de usuario                            | Si determina que ni de red, dispositivos o clientes son el problema, considere la posibilidad de contratar [Asesor de mi](https://aka.ms/myadvisor) para obtener orientación en el desarrollo de una estrategia de adopción de usuario para enseñar a los usuarios cómo procedimientos unirse y salir de las reuniones. Los equipos de una manera más eficaz y usuario de Skype generarán una mejor experiencia de usuario para todos los participantes de la reunión. Un usuario que pone a su equipo portátil en modo de suspensión (cerrando la tapa) sin salir de la reunión se clasifica como un buzón de llamada inesperada.     |

## <a name="quality-investigations"></a>Investigaciones de calidad

El siguiente paso para evaluar el estado de calidad de audio a través de la implementación es investigar Audio deficiente llamar proporción (PCR), TCP y uso de proxy. Es importante recordar que datos CQD no proporcionan una causa concreta, sino que proporcionan con áreas de problema es probable que para iniciar una conversación de colaboración con los equipos adecuados para las actividades de corrección.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía. La descripción del informe individuales para obtener más información, consulte. 


### <a name="investigate-call-quality"></a>Investigue la calidad de la llamada

El porcentaje PCR global se usa principalmente para indicar si la organización cumple los objetivos de métrica audioconferencias definidos. Es importante tener en cuenta que incluso si el porcentaje general es dentro de destino, algunas subredes o edificios podrían no cumplir los objetivos definidos y, por tanto, se necesitan más investigación. Por ejemplo, si el porcentaje PCR audio organizativo es 3 por ciento en diciembre, que cumple con el destino de ejemplo, los edificios específicos es posible que se teniendo una mala experiencia, dependiendo de la distribución de ese 3 por ciento.

#### <a name="overall-organizational-poor-call-percentage"></a>Porcentaje de llamadas deficientes organizativa general

Para evaluar el porcentaje general de las llamadas para el uso de la organización del informe de gráfico general de calidad deficientes.

![Captura de pantalla de un gráfico que muestra el porcentaje de llamadas de calidad deficiente](media/quality-of-experience-review-guide-image20.png)

_Figura 20 – una calidad de Audio - general_

##### <a name="investigation"></a>Investigación

Este informe de gráfico muestra PCR y el uso de su organización a través del tiempo. Mediante el uso de este informe, puede responder a las siguientes preguntas:

1.  ¿Qué es la PCR total para el mes actual?

2.  ¿Es la PCR debajo de la métrica de destino definido?

3.  ¿Es la tendencia de error peor o mejor que el mes pasado?

4.  ¿La tendencia de errores aumenta, steady, o disminuye?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo para investigar mediante el uso de los subinformes para buscar cualquier edificios o redes que podrían necesitar una investigación. Aunque es posible que la PCR general por debajo de la métrica de destino, a menudo la PCR para uno o varios de los edificios o redes está por encima de la métrica y necesita más investigación.

#### <a name="audio-quality-overall"></a>Calidad de audio general

Hay dos árboles de informe incluidos en las plantillas de calidad de audio, uno para investigar la conferencia y el otro para llamadas de dos participantes. Para los fines de corrección de calidad, el proceso de investigación es el mismo, por lo que nos centraremos aquí en la conferencia. Mejoras en la calidad de la conferencia positiva también afectará a la calidad de las llamadas entre dos participantes. Los informes también se incluyen a una calidad de audio para las conferencias y entre dos participantes con cable por la vista y Wi-Fi.

> [!NOTE]
> Investigación de llamadas deficientes de dos participantes es similar a investigar las llamadas de conferencia. La tarea consiste en identificar los edificios o subredes que tienen la menor calidad para validar si hay un patrón de llamadas deficientes con otro edificio o subred. 

![Captura de pantalla de la calidad de Audio - informe de conferencia en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image21.png)

_La figura 21: calidad de Audio - conferencia_

##### <a name="investigation"></a>Investigación

Este informe de gráfico muestra la conferencia o el uso de dos participantes y PCR de su organización a través del tiempo. Mediante el uso de este informe, puede responder a las siguientes preguntas:

1.  ¿Qué es la PCR total para el mes actual?

2.  ¿Es la PCR debajo de la métrica de destino definido?

3.  ¿Es PCR peor o mejor que el mes pasado?

4.  ¿La tendencia PCR aumenta, steady, o disminuye?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo para investigar mediante el uso de los subinformes para buscar cualquier edificios o redes que es posible que deben investigarse. Aunque es posible que la PCR general por debajo de la métrica de destino, a menudo la PCR para uno o varios de los edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Secuencia de audio deficiente mediante la creación y la subred

Este informe de tabla proporciona información adicional sobre qué contribuido a las llamadas que se clasificó como deficiente y ayuda a aislar los puntos activos en la red administrada.

El detalle de conexión distingue entre con cable y Wi-Fi e incluye las medidas de tiempo de ida y vuelta (RTT), la pérdida de paquetes y vibración. Un informe similar también existe en los informes de entre dos participantes y se usa para aislar las llamadas entre dos participantes en su red administrada.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado. 

> [!TIP]
> Redes particulares comunes son difíciles de evaluación de errores debido a su uso extendido. Un informe independiente que usa la dirección IP de servidor de seguridad se ha agregado a la plantilla de todas las redes para ayudar a solucionar las oficinas que utilizan redes comunes.

![Informe que se enumera los tipos de conexión, tipos de transporte y PCR mayor que % 3 junto con las diversas razones mala calidad organizados por la creación, la red y la subred al mes.](media/quality-of-experience-review-guide-image22.png)

_La figura 22 - resumen de secuencia de Audio deficiente mediante la generación de - y subred conferencia_

##### <a name="remediation"></a>Corrección

Centrar los esfuerzos de corrección en los edificios o las redes que tienen el mayor volumen de secuencias de audio, ya que esto maximizar el impacto y ayudar a mejorar el usuario experimentan rápidamente. Use la vibración, la pérdida de paquetes y las medidas de RTT para comprender lo que contribuye a la calidad de llamadas deficientes. Es posible que haya más de un problema:

-   **Vibración:** Los paquetes multimedia llegan a diferentes velocidades, que hace que un altavoz se oye robótica.

-   **La pérdida de paquetes:** Se está eliminando los paquetes multimedia, que crea el efecto de ausencia de palabras o sílabas.

-   **RTT:** Los paquetes multimedia tardan mucho tiempo para llegar a su destino, que crea un efecto transmisor-receptor portátil.

Aunque ningún origen único de verdad cuentas para lo que puede provocar una llamada deficiente, varios métodos comunes pueden ayudarle a abordar los problemas con anomalías de la red.

Para ayudar a la investigación de problemas de calidad, puede aprovechar [Análisis de llamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).
Con el análisis de llamadas, puede buscar en una conferencia concreta o informe detallado de llamadas de los usuarios. Este informe contendrá datos PII y es útil cuando se intenta discernir un motivo para errores. Una vez que sepa qué edificio se ve afectada, hacer un seguimiento a los usuarios en que creación debe ser un proceso sencillo.

No olvide que el departamento de soporte técnico sepan que estas redes están experimentando problemas de calidad, para que puedan detectar y responder a las llamadas entrantes rápidamente.

_Tabla 9 - comunes colaboradores PCR alta_

| Corrección                              | Orientación       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Redes                                 | Una red sobreutilizada o aprovisionado en puede provocar problemas con la calidad de medios. Trabajo con el equipo de red para determinar si las conexiones de red desde el usuario a la salida de internet señalan tiene suficiente ancho de banda para admitir los medios. **Realizar una evaluación de disponibilidad de red:** Una evaluación de la red proporciona información detallada sobre el uso del ancho de banda esperado, cómo lidiar con ancho de banda y de la red cambia y redes procedimientos recomendados para los equipos y Skype para la empresa. Uso de la tabla anterior como su origen, tener una lista de los edificios o subredes que son candidatos excelentes para una evaluación.<br><ul><li>[Evaluación de preparación de redes de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para evaluación de preparación para la red empresarial](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Herramienta de evaluación de la red de Microsoft:** Use esta herramienta para una prueba simple de rendimiento de la red para determinar el grado en que debería realizar la red para los equipos de un o Skype para llamadas en línea de negocio. Esta herramienta le ayuda a evaluar el rendimiento de una subred y validar la preparación de la red frente a los de rendimiento de Microsoft [requisitos](https://aka.ms/performancerequirements).<br><ul><li>[Descargar la herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Calidad de servicio (QoS)                 | QoS es un método probado para dar prioridad a los paquetes en una red para asegurarse de que llegan a su destino intacta y en el tiempo. Considere la implementación de QoS en toda la organización para maximizar la calidad de la experiencia del usuario donde está limitada o restringida ancho de banda. QoS le ayudará a solucionar problemas asociados normalmente con niveles altos de pérdida de paquetes, y, en menor grado, tiempos de ida y vuelta y vibración. <br><ul><li>[Instrucciones de QoS de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obtener instrucciones de QoS de negocio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi puede tener un impacto significativo en la calidad de la llamada. Diseño de Wi-Fi normalmente no tiene en cuenta los requisitos de red para servicios de VoIP y a menudo es una fuente de mala calidad. **QoS:** Redes inalámbricas modernas deben admitir muchos dispositivos. Estos dispositivos compiten por el ancho de banda y pueden dar lugar a problemas de calidad para servicios de VoIP donde son vitales velocidad y la latencia. Consulte a su proveedor inalámbrico para obtener detalles específicos y considere la implementación de QoS en su red inalámbrica para dar prioridad a Skype para los medios de negocios y los equipos. **Densidad AP:** Puntos de acceso (AP) pueden ser demasiado alejados o no en una ubicación ideal. Para minimizar las posibles interferencias, coloque los puntos de acceso adicionales en salas de conferencias y en ubicaciones que no están obstruidas por paredes u otros objetos. **2,4 GHz frente a 5 GHz:** 5 GHz proporciona menos interferencias de fondo y velocidades superiores y se debe asignar prioridad al implementar VoIP a través de Wi-Fi. Sin embargo, 5 GHz no es tan fuerte como a 2,4 GHz y no entrar en las paredes como fácilmente. Revise el diseño de creación para determinar qué frecuencia puede depender de la conexión de procedimientos. **Intensidad de la señal:** Tradicionalmente, medido en dBm (proporción de energía en decibelios), mide la fuerza de la señal inalámbrica. Después de que un dispositivo está conectado a un punto de acceso, no desea permitir que ir fácilmente. Medida que el dispositivo se aleja el punto de acceso, la intensidad de señal disminuye hasta un punto que provoca una mala conexión incluso aunque otra, cuanto más cerca esté el punto de acceso está disponible. Si es posible, trabajar con su proveedor de AP para asegurarse de que los puntos de acceso estén configurados para eliminar un dispositivo cuando intensidad de la señal cae por debajo de un nivel aceptable. Esto le permitirá garantizar que el dispositivo no se bloquee un punto de acceso débil. Esto es una buena solución cuando no se puede agregar fácilmente más puntos de acceso. **Controlador inalámbricos:** Cuando se produce un error en todo lo demás, asegúrese de que los controladores inalámbricos estén actualizados. Esto le ayudará a mitigar cualquier experiencia de usuario deficiente relacionado con un controlador anticuado. |
| Dispositivo de red                           | Las organizaciones más grandes deberían cientos de dispositivos repartidos por la red. Trabajo con su equipo de red para asegurarse de los dispositivos de red desde el usuario a internet se conservan y actualizados.     |
| VPN                                      | Ha sido bien documentado que los dispositivos VPN tradicionalmente no están diseñados para administrar cargas de trabajo de medios en tiempo real. Algunas configuraciones de VPN prohibirán el uso de UDP (que es el protocolo preferido para el audio) y sólo se basan en TCP. Considere la posibilidad de implementar una [solución de división túnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) para ayudar a reducir la VPN como el origen de mala calidad.        |
| Los clientes (Skype para la empresa sólo en línea) | Se sabe que los clientes más antiguos provocar problemas con los medios. Asegúrese de que los clientes se se revisen dentro de seis meses a partir de la versión. Sacar provecho de [MyAdvisor](https://aka.ms/myadvisor) para obtener instrucciones sobre el desarrollo de una estrategia de preparación de cliente e implementación de [Click-to-Run](https://technet.microsoft.com/library/jj219427.aspx).      |
| Dispositivos                                  | El uso de [optimizado dispositivos](https://partnersolutions.skypeforbusiness.com/solutionscatalog) puede ayudar a mejorar considerablemente la experiencia del usuario. Con todos los componentes iguales, los dispositivos optimizados están diseñados para maximizar la experiencia del usuario con los equipos y Skype para la empresa y producir una calidad superior. Sacar provecho de [MyAdvisor](https://aka.ms/myadvisor) para obtener instrucciones sobre el desarrollo de una estrategia de preparación del dispositivo.   |


### <a name="investigate-tcp-audio-sessions"></a>Investigar las sesiones de audio TCP

TCP se considera un transporte de la conmutación por recuperación y no el transporte principal que desee para multimedia en tiempo real. La razón es un transporte de la conmutación por recuperación es debido a la naturaleza con estado de TCP. Por ejemplo, si se realiza una llamada en una red latente y tienen un retraso de los paquetes multimedia, a continuación, los paquetes desde hace unos segundos, que ya no son útiles: compiten por el ancho de banda llegar al receptor, que puede hacer que un peor situación incorrecta. Esto hace que el punto de muestra de audio y el audio estiramiento, resultante en audibles artefactos a menudo en forma de vibración.

Los informes de esta sección no realiza una distinción entre llamadas buenas y mala. Dado que UDP es preferido, busque los informes para el uso de TCP para el audio. Esto se debe principalmente por las reglas de firewall incompleta. Para obtener más información acerca de las reglas de firewall para los equipos y Skype para profesionales en línea, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips).

> [!IMPORTANT]
> Tener un válido de [crear el archivo](#building-mapping) cargado se recomienda para poder distinguir rápidamente dentro de secuencias de audio externas cuando se examina el uso TCP. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Secuencias de audio con un uso TCP general

Este informe indica el uso general de TCP para el audio a través de los últimos siete meses, tal y como se muestra a continuación.

Todos los otros informes en esta sección se centrarán en restringir hacia abajo los edificios específicos y subredes donde TCP se usa con más frecuencia. Más subinformes desglosar el uso TCP en las conferencias y llamadas de dos participantes.

![Captura de pantalla de un gráfico que muestra el número de secuencias de audio de TCP por mes](media/quality-of-experience-review-guide-image23.png)

_La figura 23 – secuencias de Audio con un uso de TCP_

##### <a name="investigation"></a>Investigación

Este informe de gráfico muestra el uso TCP general de la organización. Mediante el uso de este informe, puede responder a las siguientes preguntas:

1.  ¿Qué es el volumen total de llamadas TCP para el mes actual?

2.  ¿Es mejor que el mes anterior o peor?

3.  ¿La tendencia de uso TCP aumenta, steady, o disminuye?

Si observa que está aumentando la tendencia de uso TCP, o por encima de uso mensual normal, tómese el tiempo para investigar mediante el uso de los subinformes para buscar cualquier edificios o redes que podrían necesitar corrección. Idealmente, desea que tan solo sesiones de audio basados en TCP como sea posible en la red administrada.

#### <a name="tcp-vs-udp"></a>TCP y UDP

Este informe de tabla identifica el volumen de TCP en lugar de en el mes más reciente para las conferencias de audio, vídeo y vídeo-based pantalla (VBSS) de uso compartido de informes de uso UDP.

![Informe que muestra el volumen de TCP frente a las secuencias de conferencia UDP, con la que se muestra para la comparación PCR](media/quality-of-experience-review-guide-image24.png)

_En la figura 24 – TCP y UDP - conferencia_

##### <a name="analysis"></a>Análisis

Aunque desea que el uso TCP para ser lo más baja como sea posible, es posible que vea un bit de uso TCP en una implementación correcto en caso contrario. Para comparar UDP para el uso TCP, dividir secuencias de audio de TCP por secuencias de audio de UDP para determinar un porcentaje. Un valor más del 1 por ciento debe investigar con más detalle.

En el ejemplo anterior, que se tomen divididas por secuencias UDP 10,481 para llegar a un valor de porcentaje 17.2 1,806 secuencias TCP. Este valor está muy por encima de 1 por ciento y nos dice que necesitamos continuar la investigación para determinar dónde se está produciendo el uso TCP.

También se incluyen en el informe es el porcentaje de Audio deficiente. Esto le ofrece una vista en la comparación de calidad de las llamadas entre UDP y TCP para ayudar a ver cómo TCP está afectando a la calidad de llamada overcall.

Por lo que ahora que ha determinado que hay un uso elevado de audio basados en TCP en la organización, ¿qué hacer a continuación? Vaya a los informes de **secuencias TCP mediante la creación y la subred** para desglosar el uso TCP mediante la creación y subredes.

#### <a name="tcp-streams-by-building-and-subnet"></a>Secuencias TCP mediante la creación y la subred

En las plantillas proporcionadas CQD, vaya a las secuencias TCP por subred y creación de informes de tabla mediante el uso de los recursos administrados o plantilla de todas las redes. Existen tres informes que se incluye en la plantilla, uno para investigar la conferencia, con y sin información de retransmisión de Microsoft y uno para investigar las llamadas entre dos participantes. Con el fin de investigar el uso TCP, el proceso es el mismo, por lo que nos centraremos la discusión aquí en sólo la conferencia.

> [!IMPORTANT]
> Tener un válido de [crear el archivo](#building-mapping) cargado se recomienda para poder distinguir rápidamente dentro de secuencias de audio externas cuando se examina el uso TCP. 

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.                                  |

![Informe que se enumera las secuencias de TCP, organizadas por la creación, la red y la subred al mes.](media/quality-of-experience-review-guide-image25.png)

_La figura 25 – secuencias TCP mediante la generación de - y subred conferencia_

##### <a name="remediation"></a>Corrección

Este informe identifica los edificios específicos y subredes que contribuyen al volumen de uso TCP. También se incluye un informe de adicional para identificar la dirección IP de retransmisión de Microsoft que se usó en la llamada para ayudar a aislar las reglas de firewall que faltan. Centrar los esfuerzos de corrección en los edificios que tienen el mayor volumen de secuencias de audio para maximizar el impacto.

La causa más común de uso TCP falta reglas de excepción en los servidores de seguridad o servidores proxy. Vamos a ser hablando acerca de los servidores proxy en la siguiente sección, por lo que por ahora centrar los esfuerzos en los servidores de seguridad. Mediante la creación o subred proporcionado, puede determinar qué servidor de seguridad debe actualizarse.

_Tabla 10 - corrección * instrucciones para las secuencias de TCP mediante la creación y la subred_

| Corrección        | Orientación     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuración del firewall | Compruebe [las direcciones y puertos IP de Office 365](https://aka.ms/o365ips) se excluyen desde el servidor de seguridad. Aunque hay muchas direcciones IP y los puertos que deben estar abiertos, para problemas relacionados con los medios TCP, centrar los esfuerzos de iniciales en lo siguiente: Compruebe las siguientes [subredes de medios](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) se encuentran en las reglas de firewall. Hacer referencia a la fila 4 en la tabla que se muestra para obtener información de subred de medios específico. [Puertos UDP 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): estos puertos son los puertos de medios preferido y deben estar abiertos, de lo contrario se producirá un error del cliente al puerto TCP 443. |
| Comprobar             | Use la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para buscar problemas de conectividad a puertos y direcciones IP de Office 365 específico de la creación afectado o subred.    |

### <a name="investigate-http-proxy-usage"></a>Investigar el uso de proxy HTTP

Servidores proxy HTTP no son la ruta de acceso preferida para establecer sesiones de medios, para un gran número de razones. Muchos contienen características de inspección profunda del paquete que pueden impedir conexiones con el servicio se completen y se presentan las interrupciones. Además, los servidores proxy podrían forzar TCP en lugar de Permitir UDP, que se recomienda para la calidad de audio óptima.

Siempre es recomendación de Microsoft para configurar el cliente para conectarse directamente a los equipos y Skype para servicios de negocios. Esto es especialmente importante para el tráfico de medios.

> [!IMPORTANT]
> Tener un válido de [creación de archivo](#building-mapping) cargado facilita distinguir correctamente dentro de secuencias de audio externas al analizar el uso de proxy. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Secuencias de audio con un uso de proxy HTTP general

Este informe resume el uso de proxy a través del tiempo en una escala mensual. El informe de secuencia de proxy HTTP de esta sección de la plantilla es muy similar a los informes TCP. No tiene el aspecto en si las llamadas son una buena o mala, pero si la llamada se conecta a través de HTTP.

![Captura de pantalla de las secuencias de Audio con el informe de uso de Proxy HTTP en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image26.png)

_La figura 26 – secuencias de Audio con un uso de Proxy HTTP_

##### <a name="analysis"></a>Análisis

Si ve un gran volumen de uso HTTP, consulte a su equipo de red para asegurarse de que las exclusiones adecuadas se encuentran disponibles para que los clientes se enrutamiento directamente a los equipos o Skype para subredes de medios en línea de negocio. Idealmente, no debería haber ningún uso de HTTP que se muestra aquí.

Si tiene un solo proxy de internet de la organización, compruebe la correcta [las direcciones URL de Office 365 y las exclusiones de intervalo de direcciones IP](https://aka.ms/o365ips). Si más de un proxy de internet está configurado en su organización, aprovechar el HTTP subcaracterísticas informar a aislar qué edificio o subred se ve afectada.

Para las organizaciones que no se pueden omitir al servidor proxy, asegúrese de que la Skype para clientes empresariales está configurado para iniciar sesión correctamente cuando se encuentra detrás de un proxy tal como se describe en el artículo [Skype para la empresa debe usar servidor proxy para iniciar sesión en lugar de intentar directa conexión](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>Secuencias de proxy HTTP mediante la creación y la subred

Este informe identifica los edificios específicos y subredes que contribuyen al uso HTTP.

> [!IMPORTANT]
> Tener un válido de [creación de archivo](#building-mapping) cargado facilita distinguir correctamente dentro de secuencias de audio externas al analizar el uso de proxy.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.                        |

![Captura de pantalla del uso de Proxy HTTP por subred y creación de informes en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image27.png)

_Figura 27 – uso de Proxy HTTP mediante la generación y subred_

##### <a name="remediation"></a>Corrección

Centrar los esfuerzos de corrección en los edificios o subredes que tienen el uso de proxy HTTP. La causa más común de uso HTTP falta reglas de excepción en los servidores proxy. Mediante la creación o subred proporcionado, puede determinar qué servidor proxy debe actualizarse.

Compruebe que los necesarios [Y los FQDN de Office 365](https://aka.ms/o365ips) se excluyen de su proxy.

## <a name="endpoint-investigations"></a>Investigaciones de extremo

En esta sección se centra en las tareas de informes de Skype para versiones de cliente – específicos de su negocio y el uso de dispositivos certificados.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía. La descripción del informe individuales para obtener más información, consulte. 


### <a name="determine-client-versions"></a>Determinar las versiones de cliente

El informe en este espacio se centra en la identificación de Skype para las versiones de cliente de negocio en uso y su volumen relativa en el entorno.

> [!IMPORTANT]
> Actualmente, los clientes de los equipos están distribuidos y se actualizan automáticamente a través de la red de entrega de contenido (CDN) de Azure y se mantengan actualizados por el servicio. Preparación de cliente y las actividades de investigación no son aplicables a los equipos.

Números de versión de Skype para profesionales de 2015 y 2016 pueden encontrarse a través de los siguientes vínculos:

-   [Versiones de canal de actualización de cliente de Office 365](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Números de versión y de compilación de Office 365 ejecutar, haga clic en](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype para la empresa, descargas y actualizaciones](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.  

> [!IMPORTANT]
> Informes de cliente requieren que se va a excluir datos participantes federados. Para excluir datos participantes federados, debe agregar un filtro de consulta para el **Segundo identificador de inquilino** establecida en el [identificador de inquilino](#tenant-id)de su organización. |

![Captura de pantalla del informe de cliente y dispositivos en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image28.png)

_En la figura 28 - informe de versiones de cliente_

#### <a name="remediation"></a>Corrección

Una parte fundamental de tiende a experiencias de usuario de alta calidad es asegurarse de que los clientes administrados están ejecutando versiones actualizadas de Skype para la empresa. Esto proporciona varios beneficios, entre ellos:

-   Es más fácil administrar versiones unas frente a número de versiones.

-   Proporciona un nivel de coherencia de la experiencia.

-   Resulta más fácil solucionar los problemas con la calidad de las llamadas y facilidad de uso.

-   Microsoft no otorga continuamente las optimizaciones y mejoras generales en todo el producto. Para que los usuarios reciban estas actualizaciones, reduce sus riesgos de ejecutar un problema que ya se ha resuelto.

Limitación de la implementación para las versiones de cliente que están menos de seis meses se mejorar la experiencia global del usuario y mejorar la manejabilidad en comparación con la necesidad de un gran número de las diferentes versiones del cliente en el mismo entorno.

Si utiliza sólo Office Click-to-Run, podrá automáticamente dentro de la ventana de seis meses. Se requiere ninguna acción adicional.

If, al igual que la mayoría de las organizaciones, tiene una mezcla de paquetes de Click-to-Run y installer (MSI), puede utilizar el informe para comprobar que se actualizan con regularidad los clientes MSI. Centrar los esfuerzos en esos clientes donde es el volumen por encima del promedio. Si observa que los clientes se están quedando anticuados, trabaje con el equipo responsable de administrar las actualizaciones de Office y asegurarse de que está aprobando y la implementación de revisiones de cliente con regularidad.

### <a name="devices-investigations"></a>Investigaciones de dispositivos

Para hacer uso de los siguientes informes de dispositivo, es mejor para comprender el concepto de la opinión Media puntuación (MOS). MOS es la medida estándar de oro para evaluar la calidad de audio detectada. Se representa como una clasificación de número entero de 0 a 5.

La base de todas las medidas de calidad de voz es cómo una persona percibe la calidad de voz. Debido a que se ve afectada por la percepción humana, es esencialmente subjetiva. Hay varias metodologías diferentes para probar subjetiva.
La mayoría de las medidas de calidad de voz se basan en una escala de clasificación (ACR) de la categorización absoluta.

En una prueba ACR subjetiva, un número estadísticamente significativo de personas valora la calidad de la experiencia en una escala del 1 (incorrecta) a 5 (excelente). El promedio de las puntuaciones es el MOS. El MOS resultante depende del intervalo de experiencias que se exponen para el grupo y el tipo de la experiencia que se clasificaron.

Debido a que no resulta práctico para realizar pruebas subjetivas de calidad de voz para un sistema de comunicación live, equipos y Skype para la empresa generan valores MOS mediante el uso de algoritmos avanzados para predecir objetiva de los resultados de una prueba subjetiva.

El conjunto disponible de MOS y métricas asociadas proporcionan una vista a la calidad de la experiencia de entregarse a los usuarios.

Al proporcionar a los usuarios con los dispositivos certificados para los equipos y Skype para la empresa, se reduce la probabilidad de que se produzcan experiencias negativas debido al propio dispositivo (que es más probable, por ejemplo, con micrófonos y altavoces portátil integrada). Para obtener más información, vea [teléfonos y dispositivos para Skype para la empresa](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Uso de dispositivos de captura (micrófonos) por volumen para la organización

Este informe se usa para evaluar el uso de micrófono por volumen y puntuación MOS y puede encontrarse en las plantillas que lo acompaña en los clientes y dispositivos *.*

> [!IMPORTANT]
> Dispositivo informes requieren que se va a excluir datos participantes federados. Para excluir datos participantes federados, debe agregar un filtro de consulta para el **Segundo identificador de inquilino** establecida en el [identificador de inquilino](#tenant-id)de su organización. 

> [!NOTE] 
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.<br><br> Es posible que tenga en cuenta cuando la visualización de este informe que ve el mismo dispositivo registrada varias veces. Esto es debido a la forma en que el dispositivo se indica que se notifiquen al CQD. Las diferencias de hardware y configuración regional del SO notificar los datos del dispositivo de forma diferente.

![Captura de pantalla del informe de dispositivos (micrófono) en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image29.png)

_Figura 29 - – informe de dispositivos (micrófono)_

##### <a name="remediation"></a>Corrección

La primera tarea es determinar el destino MOS que le gustaría alcanzar. MOS puntuaciones comprendido entre 1 y 5, con 5 es la mejor. Elija un destino razonable en función de su entorno y los resultados de la consulta. En el siguiente ejemplo, el destino es una puntuación MOS de 3.6 o superior para todos los dispositivos que tienen más de 100 secuencias. Obtendrá la calidad de los dispositivos de destino cuando:

-   Los resultados de consulta de dispositivo devuelven MOS \> 3.6 para NumStreams \> 100

Normalmente, necesitará reemplazar dispositivos bajo rendimiento con los dispositivos de certificado. Se incluyen algunas consideraciones para la revisión del informe de dispositivo:

-   ¿Son las dispositivos certificados o conocidos para ser buena en su entorno? Si un dispositivo certificado o buena se devuelve en la consulta con una puntuación MOS inferior a la línea de base, puede haber otros factores desconocidos (por ejemplo, una red deficiente o baja potencia pc) que contribuye a la puntuación de baja.
    Se requerirá una investigación adicional.

-   Puede identificar a los usuarios de un dispositivo a través de [Análisis de llamadas](#call-analytics-training). Compruebe para asegurarse de que disponen de los controladores de dispositivo más recientes y que su dispositivo no está conectado a través de un concentrador USB.

-   Compruebe si hay una correlación entre los dispositivos defectuosos y creación de un sistema concreto y modelo. Si es así, el dispositivo podría ser incompatible o se necesitan actualizaciones de controlador.

La segunda tarea es determinar el uso general de dispositivos que no sean certificados. Se recomienda que al menos el 80% de todas las secuencias de audioconferencias usar un dispositivo certificado.
Esto se logra mejor por el informe de dispositivos a exportar a Excel y calcular manualmente el uso de dispositivos aprobados o certificados. Las organizaciones normalmente mantenga una lista de todos los dispositivos aprobados, para poder filtrar y ordenar los datos deben ser un proceso sencillo.

## <a name="appendix-a-lync-networking-guide"></a>Guía de redes del apéndice Lync r.

Para obtener más información sobre los equipos y Skype para conceptos de redes empresariales y la lógica tras su importancia a la calidad, la [Guía de redes de Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) sigue siendo aplicable.

## <a name="appendix-b-network-performance-requirements"></a>Requisitos de rendimiento de red B. apéndice

La calidad de medios en tiempo real (audio, vídeo y uso compartido de aplicaciones) a través de IP depende en gran medida la calidad de la conectividad de red de extremo a otro. Óptima equipos o Skype para calidad de los medios empresariales, de la red debe cumplir las siguientes métricas de rendimiento de red.

_Tabla 11 - requisitos de rendimiento de red_

| Métrica                           | Cliente a Microsoft Edge           | Perímetro de cliente a Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Latencia (unidireccional)                | \<50 ms                            | \<30 ms                            |
| Latencia (RTT o tiempo de ida y vuelta) | \<100 ms                           | \<60 ms                            |
| Ráfagas de pérdida de paquetes                | \<10% durante un intervalo de 200 ms   | \<% 1 durante cualquier intervalo de 200 ms    |
| Pérdida de paquetes                      | \<% 1 durante cualquier intervalo de 15 segundos    | \<0,1% durante un intervalo de 15 segundos  |
| Vibración de llegada entre granjas de paquetes      | \<30 ms durante un intervalo de 15 segundos | \<15 ms durante un intervalo de 15 segundos |
| Reaprovisionamiento de paquetes                   | \<paquetes de salida de orden 0,05%       | \<paquetes de salida de orden 0,01%      |

Para obtener más información, vea el artículo siguiente acerca del [rendimiento de red y de calidad de medios](https://aka.ms/performancerequirements) para los equipos y Skype para profesionales en línea.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Apéndice C. Otros recursos

### <a name="building-data-file"></a>Archivo de datos de creación

-   [Activar y usar CQD en Skype para profesionales en línea](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>Formación de CQD

-   <https://aka.ms/sof-cqd>

-   Guía de [Introducción a CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) y taller.

-   [Guía en línea CQD dimensiones y medidas](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Aprendizaje de análisis de llamada

-   [Introducción a la llamada de análisis](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar el análisis de llamadas de Skype Empresarial](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [Diferencia entre el análisis de llamadas y el Panel de calidad de llamadas](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Usar el análisis de llamadas para solucionar problemas de mala calidad de llamada en Skype Empresarial](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Soporte de análisis de llamada

-   [Skype para el programa de vista previa de negocio](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram) de la Comunidad:

-   Para obtener soporte técnico, inicie sesión en nuestro [www.skypepreview.com](http://www.skypepreview.com)de vista previa del portal, seleccione **informe de un problema**y usar la opción **Crear nuevo error** para notificar un problema. Tenga en cuenta que los ingenieros de soporte técnico están disponibles para proporcionar compatibilidad con del lunes al viernes, entre las horas de 6 AM a 9 P.M. EST. Las solicitudes fuera de las horas se va a evaluar el día siguiente.

### <a name="devices"></a>Dispositivos

-   [Skype para soluciones empresariales de catálogo periféricos personales y PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Creación de informes de inquilinos

-   [Paquete de contenido de adopción de Office 365](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Creación de informes en Skype Empresarial Online](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Teams Microsoft reporting](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
    =======
---
title: Calidad de experiencia consulte la guía para los equipos de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guía para analizar el rendimiento de medios en tiempo real para Microsoft Teams utilizando el panel de calidad de llamadas (CQD).
MS.collection: Strat_MT_TeamsAdmin
appliesto:
  - Microsoft Teams
---

# <a name="quality-of-experience-review-guide"></a>Calidad de experiencia consulte la Guía

Esta guía es acerca de la fase de valor de unidad para Microsoft Teams y Skype para profesionales en línea. Puede [descargar una versión de Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) de esta guía.

## <a name="introduction"></a>Introducción

Para que el mayor impacto sobre cómo mejorar la experiencia del usuario, las organizaciones necesitan que controle las áreas clave que se muestran en la ilustración siguiente.
Áreas adicionales incluyen la identificación de las tareas operativas, establecimiento de los objetivos de métricas de calidad, determinar las métricas para utilizar para medir el éxito organizativo y áreas de investigación de restricción según sea necesario.

![Áreas clave para la calidad de la experiencia de usuario incluyen audio, confiabilidad, encuestas al usuario, dispositivos y clientes.](media/quality-of-experience-review-guide-image1.png)

_En la figura 1 - áreas operativas clave tratadas a lo largo de este documento_

Al continuamente evaluar y solucionar relativos a las áreas que se describen en este documento, puede reducir su potencial de afectar negativamente a la calidad de la experiencia de los usuarios. Mayoría de experiencia de usuario los problemas encontrada en una implementación puede agruparse en las siguientes categorías:

-   Configuración de firewall o proxy incompleto

-   Cobertura Wi-Fi deficiente

-   Ancho de banda insuficiente

-   VPN

-   Versiones de cliente incoherentes o no actualizada

-   Dispositivos de audio integrados o no optimizados

-   Subredes problemáticas o dispositivos de red

A través de planear y diseñar correctamente antes de implementar los equipos o Skype para profesionales en línea, puede reducir la cantidad de esfuerzo que será necesarios para mantener experiencias de alta calidad.

Esta guía se centra en usar el panel de calidad de llamadas (CQD) Online como la principal herramienta para notificar e investigar cada área, con especial hincapié en audio para maximizar la adopción y el impacto. Todas las mejoras realizadas a la red para mejorar la experiencia de audio traducirá también directamente a las mejoras en uso compartido de escritorio y de vídeo.

Para acelerar la evaluación, se proporcionan dos plantillas CQD curated: uno para administrar todas las redes y la otra se filtra como administrado sólo redes (internas). Aunque los informes de la plantilla de todas las redes están configurados para mostrar la creación y la información de red, aún puede usarse mientras trabaja hacia la recopilación y la carga de información de creación. Cargar información en CQD de compilación, habilita el servicio mejorar la creación de informes mediante la adición de información de creación, la red y la ubicación personalizada mientras diferenciar interno de subredes externas. Para obtener más información, vea [asignación de creación](#building-mapping) más adelante en este documento.

### <a name="what-is-the-cqd"></a>¿Qué es la CQD?

Use el panel de calidad de llamadas (CQD) para obtener información sobre la calidad de las llamadas realizadas mediante el uso de los equipos y Skype para servicios de negocios. CQD está diseñado para ayudar a Skype para profesionales y los equipos de los administradores y los ingenieros de red optimizan la red. CQD busca agregada información para una organización completa donde patrones generales pueden convertirse en evidentes, lo que permite personal realizar las evaluaciones informadas de calidad de la llamada. CQD proporciona informes de métricas de llamada que brindar información sobre la calidad general de las llamadas, llamada de confiabilidad y experiencia del usuario.

> [!NOTE]
> CQD no contiene información de identificación personal (PII). PII es información que puede usar en su propio o con otra información para identificar, póngase en contacto con o busque a una sola persona, o para identificar a un individuo en contexto. 

### <a name="intended-audience"></a>Público objetivo

Este documento está destinado a ser utilizado por las partes interesadas de clientes y socios con funciones como arquitecto o jefe de colaboración, consultor, especialista en administración y adopción de cambio, jefe de soporte técnico y ayuda de asistencia al cliente, potenciales de red, potenciales de escritorio y Admin de TI.

Este documento también está pensada para usarse por la champion(s) calidad designada.
Para obtener más información, vea [la función de los pesos pesados calidad](https://docs.microsoft.com/MicrosoftTeams/4-envision-plan-my-service-management#the-quality-champion-role).

## <a name="prerequisites"></a>Requisitos previos

Antes de usar a esta guía, asegúrese de que tiene el inquilino adecuados [roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) asignados por lo que puede tener acceso a CQD.

-   **Función de administrador Global de office 365:** Tiene acceso a todas las características administrativas en el conjunto de aplicaciones de Office 365 de servicios en el plan, incluyendo Skype para la empresa.

-   **Skype para el rol de administrador empresarial:** Configura Skype para la empresa para su organización y puede ver todos los [informes de actividad](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración de Office 365. Esta función es necesaria, incluso si se implementación sólo los equipos.

Como alternativa, puede asignar la siguiente función a una cuenta de usuario de Office 365 para permitir el acceso a sólo las características de informes.

-   **Lector de informes:** Puede ver todos los [informes de actividad](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) en el centro de administración de Office 365, los informes desde el [paquete de contenido de Office 365 adopción](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)e informes CQD.

Descripción de los conceptos clave de CQD ayuda a maximizar el impacto que puede realizar en la mejora de la experiencia de los usuarios con los equipos o Skype para profesionales en línea.
Recursos adicionales pueden encontrarse en el [Apéndice](#other-resources).

## <a name="what-is-quality"></a>¿Qué es la calidad?

Al hablar de calidad en los equipos y Skype para la empresa, es importante definir el término para lograr una comprensión común. Calidad, tal como se define aquí, es una combinación de la experiencia de usuario y las métricas de servicio.

![Métricas de servicio se componen de las versiones de relación, confiabilidad, extremos y a los dispositivos y cliente de llamadas deficientes. Experiencia del usuario final se compone de la percepción del usuario de la calidad de servicio.](media/quality-of-experience-review-guide-image2.png)

_La figura 2: ¿qué es la calidad?_

### <a name="define-your-target-metrics"></a>Definir las métricas de destino

En esta sección se describe las métricas de servicio principal que usamos para evaluar cómo servicios experimentan mantenimiento. Al continuamente evaluar y que dirigen los esfuerzos para mantener estas métricas debajo de destino, ayudaremos a garantizar la que calidad de la llamada coherente y confiable de experiencia de los usuarios. Para comenzar, se proporcionan los siguientes objetivos.
Vamos a explicar brevemente la diferencia entre una red administrada y no administrada:

-   Una red *administrada* puede ser influenciada y controlada por la organización.
    Esto incluye la LAN interna, WAN remoto y VPN.

-   Una red *no administrada* no se puede ser influenciada o controlada por la organización. Un ejemplo de una red no administrada es una red de hotel o un aeropuerto.

_Tabla 1 - medidas de evaluación de estado de destino principales_

|               | Calidad para redes administradas | Confiabilidad para redes administradas |                      |
|---------------|------------------------------|----------------------------------|----------------------|
| Nombre de la métrica   | Relación entre % de llamadas de audioconferencias deficientes      | Configuración de la llamada % de errores            | Llamar a colocar % de errores |
| Destino de ejemplo | \<% 3                         | \<% 1                             | \<% 4                 |

Es importante discutir y definir los objetivos de la organización para cumplir los objetivos del negocio. Idealmente, debe identificar estos destinos antes de la implementación.

#### <a name="audio-pcr-"></a>% De audio PCR 

Audio deficiente llamar proporción (PCR) representa el porcentaje general de la organización de las llamadas que tengan la mala calidad de audio. Esta métrica está diseñada para resaltar las áreas donde la organización puede centrarse en tener el impacto más sólido hacia reducir este valor y mejora de la experiencia del usuario, lo que las redes administradas son el foco principal cuando se mira PCR. Los usuarios externos son importantes demasiado, pero difiere de investigaciones de forma organizativa y usuario.
Considere la posibilidad de proporcionar procedimientos recomendados para los usuarios externos y fíjese en las llamadas externas independientemente de la organización global.

#### <a name="call-setup-failures-"></a>Configuración de la llamada % de errores 

Esto representa cualquier sesión de medios que no se ha podido establecerse. Dada la gravedad del impacto en la experiencia del usuario que se mide aquí, el objetivo es reducir este valor para como cercanos a cero como sea posible. Un valor alto para que esta métrica es más frecuente en las nuevas implementaciones con reglas de firewall incompletos que una implementación consolidada, pero sigue siendo importante inspeccionar de forma regular. A medida que crezca su exactitud operativa, puede expandir esta métrica para incluir las cargas de trabajo de vídeo y uso compartido de escritorio.

#### <a name="call-drop-failures-"></a>Llamar a colocar % de errores 

Esto se aplica a una carga de trabajo de audio donde finalizó la sesión de forma inesperada. A medida que crezca su exactitud operativa, puede expandir esta métrica para incluir las cargas de trabajo de vídeo y uso compartido de escritorio.

### <a name="service-metrics"></a>Métricas de servicio

Los objetivos de métricas de servicio constan de las medidas específicas basadas en cliente.

#### <a name="pcr"></a>PCR

La base para determinar si una llamada se clasificó como deficiente es mediante el uso de la relación de llamada deficiente (PCR). PCR se compone de las cinco métricas de red que se describen en la siguiente tabla. Para que una llamada se clasifican como deficiente, sólo una métrica necesita supere el umbral definido. Para obtener más información acerca del proceso de clasificación de llamadas, vea [esta entrada de blog](https://blogs.technet.microsoft.com/jenstr/2013/09/20/what-is-the-basis-for-classifying-a-call-as-poor-in-lync-2013-qoe/).

_Tabla 2 - métricas de servicio de llamadas deficientes_

| Métrica                                           | Descripción                                                                                                                                                                                                                                                                                                                                                                  | Experiencia de usuario                                                                                                                                                          |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Vibración \>30 ms                                   | Éste es el cambio promedio de retraso entre envíos sucesivos de paquetes. Los equipos y Skype para la empresa pueden adaptarse a algunos niveles de vibración a través de almacenamiento en búfer. Es sólo cuando la vibración supera el almacenamiento en búfer que un participante avisos de los efectos de vibración.                                                                                                                         | Los paquetes que llegan a diferentes velocidades provocarán voz de un altavoz se oye robótica.                                                                                       |
| Tasa de pérdida de paquetes \>0,1 o 10%                    | A menudo se define como un porcentaje de paquetes que se pierden. Pérdida de paquetes afecta directamente a la calidad de audio: desde pequeñas, individual los paquetes perdidos que no tienen casi afectar a las pérdidas de ráfagas opuesta que causa el audio para recortar completamente.                                                                                                                               | Los paquetes se perdidos y que no llegan a su destino previsto provocarán diferencias en los medios, resultantes en palabras y sílabas perdidas y entrecortados vídeo y uso compartidos. |
| Tiempo de ida y vuelta \>500 ms                         | Esto es el tiempo necesario para obtener un paquete IP de punto A punto b y volver al punto A. Este retraso de propagación de red está asociado a la distancia física entre los dos puntos y la velocidad de la luz e incluye una sobrecarga adicional realizada por los diversos dispositivos en la ruta de acceso de red.                                                                                  | Los paquetes tarda mucho tiempo para llegar a su destino causar un efecto transmisor-receptor portátil.                                                                                 |
| Promedio de degradación de NMOS \> 1.0                  | Una o varias de estas métricas de red, aunque individualmente no estaban deficiente, juntos deberse a que la [Media de puntuación de opinión](https://technet.microsoft.com/library/bb894481(v=office.12).aspx) de red (NMOS) para colocar más de un punto. Esto no significa necesariamente la conexión de red es deficiente, pero se han producido suficiente problemas durante la llamada que se ha reducido la calidad. | Esto es una combinación de vibración, la pérdida de paquetes, y, en menor grado, aumenta el tiempo de ida y vuelta. El usuario puede haber una combinación de estos síntomas.          |
| Relación media de muestras ocultas \> 7% o 0,07 | Una o varias de estas métricas de red, aunque individualmente no estaban deficiente, causó el cliente para resolver problemas de los medios. Un ejemplo de audio oculto es una técnica que se utiliza para emparejar la abrupta transición que normalmente podría deberse a paquetes de red perdidos.                                                                                                                | Valores altos indican que se han aplicado niveles significativos de ocultación de pérdida y esperó audio distorsionado o pierden.                                                  |

#### <a name="client-and-device-readiness"></a>Preparación de clientes y dispositivos

Se necesita una estrategia de cliente y dispositivo sólida para asegurarse de que los usuarios tengan una experiencia de usuario coherente y positiva. Unos principios claves de cada estrategia de preparación para la unidad.

##### <a name="client-readiness"></a>Preparación del cliente

Una estrategia de preparación de cliente seguro garantiza que los usuarios están ejecutando la versión más reciente del cliente disfrutando de la mejor experiencia posible.
Microsoft revisiones rutinariamente el Skype para clientes empresariales; asegurarse de que la mantenga actualizados en su entorno es vital para el éxito general.

Se recomienda que no permita que sus versiones de cliente se dividen por más de seis meses. Si está utilizando Office Click-to-Run, está ya que se mantiene actualizados por el servicio. Use el incluye [Un informe de cliente](#determine-client-versions), tal como se describe más adelante en esta guía, para ayudarle con este proceso. También puede aprovechar los informes de ejemplo tasa Mis llamadas para mejorar aún más la estrategia de preparación del cliente.

> [!IMPORTANT]
> Actualmente, los clientes de los equipos se distribuye y se actualizan automáticamente a través de la red de entrega de contenido de Azure y se mantengan actualizados por el servicio. Preparación de cliente y las actividades de investigación no son aplicables a los equipos.


##### <a name="device-readiness"></a>Preparación de dispositivo

No hay una estrategia de único puede afectar a la experiencia del usuario más que la estrategia de preparación del dispositivo. Mayoría de las organizaciones es feliz quitar los dispositivos innecesarios de los usuarios (por ejemplo, teléfonos de escritorio u otros dispositivos de audioconferencias dedicados) y, a menudo, esto es una justificación del negocio principales para cambiar a los equipos o Skype para la empresa. Sin embargo, esas organizaciones mismas dudan a veces para proporcionar dispositivos de sustitución, incluso si esos dispositivos son menos costosas. Equipos portátiles moderna y PCs, aunque dispongan de micrófono y altavoz, no están optimizados para voz de clase empresarial sobre IP (VoIP). A menudo esto crea una mala experiencia para todos los participantes, especialmente si el altavoz está en un entorno con mucho ruido. Programa de certificación de dispositivo de Microsoft se asegura de que, cuando un usuario participa en una llamada telefónica mediante el uso de cualquier dispositivo certificado para los equipos o Skype para la empresa, genera una experiencia que es superior de un dispositivo no certificados.

Siempre se recomienda que los equipos y Skype para usuarios profesionales usar un certificado de auriculares con micrófono o altavoz cuando participa en una llamada de voz mediante el uso de un cliente de escritorio.
Para obtener más información acerca de los dispositivos de certificación de Microsoft, revise este [artículo sobre teléfonos y dispositivos compatibles](https://technet.microsoft.com/office/dn788944.aspx). Use el [Informe de dispositivos](#devices-investigations), más adelante en esta guía, para obtener ayuda con la administración de los dispositivos. También puede usar los informes de ejemplo tasa Mis llamadas para mejorar aún más la estrategia de preparación del dispositivo.

### <a name="user-experience"></a>Experiencia de usuario

Análisis de la experiencia del usuario es más que science, debido a que las métricas se recopilan aquí no siempre significa que hay un problema con la red o servicio, pero en su lugar, que indican que el usuario percibe un problema. Microsoft ofrece un mecanismo de encuesta integrada, conocido como tasa Mis llamadas (RMC): para ayudar a medir la experiencia global del usuario. RMC le ayudarán a responder a las preguntas siguientes desde la perspectiva de los usuarios:

-   ¿Sabe cómo usar la solución?

-   ¿Es la solución intuitiva y fácil de usar, y es compatible con las necesidades de comunicación diarias?

-   ¿La solución me ayuda a realizar mi trabajo?

-   ¿Qué es mi percepción general de la solución?

-   ¿Puedo usar la solución en cualquier momento en el tiempo, independientemente de donde estoy?

-   ¿Puedo configurar y mantener una llamada?

#### <a name="rmc"></a>RMC

RMC se basa en equipos y Skype para la empresa y se configura automáticamente para que se muestre después de que uno en todas las llamadas de 10, o un 10% de todas las llamadas. En este breve encuesta pregunta al usuario para valorar la llamada y proporcionar un contexto poco de por qué la calidad de la llamada es posible que han sido deficiente. Una clasificación de uno o dos se considera mala, es buena tres o cuatro y cinco es excelente. Aunque es un poco de un indicador al retraso, esto es una métrica útil para descubrir problemas que pueden pasar por alto las métricas de servicio.

> [!NOTE]
> Hasta que se indique a los usuarios para responder a encuestas RMC por darnos su opinión buena además de las respuestas incorrectos, normalmente volveremos como muy negativos. La mayoría de los usuarios sólo responden cuando es mala calidad de la llamada. Por este motivo, los informes RMC podrían ser asimétrica hasta el lado deficiente incluso mientras las métricas de servicio son una buena opción. 


Puede usar CQD para informar sobre las respuestas del usuario RMC, y se incluyen informes de muestra en la plantilla de CQD. Sin embargo, no se analizan detalladamente en esta guía. Para obtener más información sobre RMC en Skype para profesionales en línea e instrucciones para informar a los usuarios para dar respuestas RMC útiles, vea esta [entrada de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

### <a name="categories-of-quality"></a>Categorías de calidad

El éxito de una implementación de alta calidad y confiable en marcha depende de la exactitud operativas de creación. En concreto, preste especial atención a las tres categorías que se muestra en la figura siguiente; Estos son el enfoque de esta guía:

-   **Red:** Calidad de audio centrado en la métrica PCR, uso TCP, subredes con cable e inalámbricas e identificar el uso de servidores proxy HTTP y VPN.

-   **Extremos:** Dispositivos de audio y la versión de cliente (Skype para la empresa sólo).

-   **Administración de servicios:** Esta categoría compone de dos secciones:

    -   En primer lugar, es responsabilidad de Microsoft para administrar y mantener los equipos y Skype para servicios en línea de negocio.

    -   En segundo lugar las tareas que debe administrar su organización para garantizar un acceso confiable a del servicio, como actualizar la información de creación y mantenimiento de firewalls para nuevas direcciones IP de Office 365 como infraestructura se agrega al servicio.

![Las categorías de calidad de una organización: servicio de administración, extremos y la red.](media/quality-of-experience-review-guide-image3.png)

_La figura 3 - categorías críticas para los equipos y Skype para la implementación empresarial en línea_

El gráfico siguiente describe las tareas que debe ejecutar para cada categoría. Le recomendamos que ejecute estas tareas una vez por semana, como mínimo.

La primera vez que realice estas tareas le llevará más esfuerzo que las iteraciones posteriores, debido a que muchas de estas categorías requieren que validar las configuraciones de implementación. Una vez que haya alcanzado el estado que desea con las reuniones de los destinos que ha definido, llevar a cabo estas tareas le ayudará a mantener ese estado.

#### <a name="service-management-tasks"></a>Tareas de administración de servicio

En un mundo de la nube en primer lugar, debe realizar ciertas tareas de administración de servicio para mantener experiencias de usuario de alta calidad. Estas tareas oscilar entre asegurarse de que hay suficiente ancho de banda ponerse en contacto con el servicio sin saturar vínculos de internet, validar que la calidad de servicio (QoS) en lugar de todas las áreas de la red administrada, y, por último: permanecer en la parte superior [rangos IP de Office 365 en los servidores de seguridad](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

#### <a name="network-tasks"></a>Tareas de red

Existen dos categorías de tareas de red: confiabilidad y calidad. Confiabilidad se centra en la medición de la capacidad del usuario para realizar llamadas correctamente y permanecer conectado. Calidad se centra en la telemetría agregada que se envía a los equipos y Skype para profesionales en línea por el cliente del usuario durante y después de la llamada ha finalizado.

Dado el impacto crítico que disponga de confiabilidad en la experiencia del usuario, empezar a evaluar e investigar estas métricas antes de comenzar con la calidad.

#### <a name="endpoints-tasks"></a>Tareas de extremos

La tarea principal en esta categoría está validando qué versiones de cliente ejecutan Skype para la empresa en generaciones de escritorio de los últimos seis meses para asegurarse de que los usuarios reciben la ventaja de las optimizaciones continuas realizadas a la Skype para el cliente de escritorio empresarial. Además, esto simplifica las tareas de administración de cliente general y proporciona una experiencia de usuario coherente.

La otra área importante es qué dispositivos son frecuentes en su implementación de supervisión y que dirigen el uso de dispositivos certificados para proporcionar la mejor experiencia de usuario.

> [!IMPORTANT]
> Actualmente, los clientes de los equipos se distribuye y se actualizan automáticamente a través de la red de entrega de contenido de Azure y se mantengan actualizados por el servicio. Preparación de cliente y las actividades de investigación no son aplicables a los equipos.


## <a name="using-the-reports"></a>Uso de los informes

En esta sección se describe los aspectos básicos del trabajo con CQD. Se proporcionan directrices para los siguientes temas:

-   Buscar el identificador de inquilino

-   Creación de informes en los equipos frente a Skype para la empresa

-   En primer lugar frente a clasificaciones de segundo

-   Dimensiones, medidas y filtros

-   Secuencias frente a las llamadas

-   Llamadas de buena, deficientes y sin clasificar

-   Introducción a CQD

-   Edición de informes en CQD

-   Filtrado de informes en CQD

Para obtener información más detallada sobre recursos de aprendizaje y recursos, consulte el [Apéndice](#other-resources).

### <a name="tenant-id"></a>Identificador de inquilino

Algunos informes CQD requieren que incluir un filtro para el identificador del inquilino. Debido a la forma que CQD agrega datos, se incluye telemetría participante federado.
Aunque esto puede resultar valiosa al analizar las métricas de llamadas deficientes, informes de cliente y dispositivo requieren el filtrado de datos para un inquilino específico para excluir telemetría participante federado. Si no conoce su identificador de inquilino, puede usar uno de los métodos siguientes para encontrarlo.

Requisitos de permisos

-   Función de administrador global

-   Skype para el rol de administrador de negocio

#### <a name="azure-ad-portal"></a>Portal de Azure AD

1.  Inicie sesión el portal de Microsoft Azure:<https://portal.azure.com>

2.  Seleccione **Azure Active Directory**.

3.  En **Administrar**, seleccione **Propiedades**. El identificador de inquilino se muestra en el cuadro **Identificador de directorio** .

#### <a name="azure-powershell"></a>PowerShell de Azure

1.  [Instalar el módulo de administración de servicio de Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Abra una ventana de comandos de Windows Azure PowerShell y ejecute el siguiente script, escribir las credenciales de Office 365 cuando se le solicite:  
    **Inicio de sesión AzureRmAccount**

3.  El identificador de inquilino aparece en el resultado.

#### <a name="skype-for-business-online-admin-center"></a>Skype para el centro de administración en línea de negocio

1.  Vete a<https://portal.office.com>

2.  Inicie sesión con su cuenta profesional de administrador de inquilinos.

3.  Seleccione **Skype para la empresa** en **Centros de administrador**.

4.  El identificador de inquilino aparece como **Identificador de organización** en la página de bienvenida.

#### <a name="skype-for-business-online-using-powershell"></a>Skype para profesionales Online mediante PowerShell

1.  [Conectarse a Skype para la empresa en línea a través de PowerShell](https://technet.microsoft.com/library/dn362839(v=ocs.15).aspx).

2.  Ejecute el siguiente comando:  
    **.Tenantid (get-cstenant)**

3.  El identificador de inquilino se muestra como un GUID.

### <a name="teams-vs-skype-for-business"></a>Los equipos frente a Skype para la empresa

CQD puede informar sobre los equipos y Skype para telemetría empresarial. Sin embargo, puede haber ocasiones cuando desea desarrollar un informe que mirar telemetría equipos independiente de Skype para la empresa.

#### <a name="summary-reports"></a>Informes de resumen

Para modificar la página de informes de resumen para ver sólo los equipos o Skype para la empresa, seleccione el menú desplegable de **Filtro del producto** desde la parte superior de la pantalla y, a continuación, seleccione el producto que desee.

![Captura de pantalla del panel de calidad de llamadas que refleja una lista desplegable menú que muestra la opción de filtrar por carga de trabajo.](media/quality-of-experience-review-guide-image4.png)

_La figura 4 - seleccionar un filtro de producto_

#### <a name="detailed-reports"></a>Informes detallados

Para filtrar un informe detallado, agregue el filtro de **Los equipos es** para el informe y establecer en True o False. Para obtener más información, vea [informes de edición](#editing-reports) más adelante en esta sección.

![Captura de pantalla del panel de calidad de llamadas que muestra el sistema de almacenamiento que se puede agregar a un informe detallado.](media/quality-of-experience-review-guide-image5.png)

_La figura 5 - agregar un filtro de Microsoft Teams a un informe_

### <a name="dimensions-measures-and-filters"></a>Dimensiones, medidas y filtros

Una consulta CQD bien formada contiene las tres de los siguientes parámetros:

-   **Dimensión:** ¿Cómo desea en los datos de tabla dinámica.

-   **Medida:** ¿Qué deseo informar sobre.

-   **Filtro:** ¿Cómo desea reducir el conjunto de datos que devuelve la consulta.

Otra forma de analizar esto es una dimensión es la función de agrupación, una medida los datos en que estoy interesado, y un filtro es cómo desea restringir los resultados a aquellos que son relevantes para la consulta.

Un ejemplo de una consulta con formato correcto es "Mostrarme deficientes secuencias [medida] por subred [dimensión] para la creación de 6 [filtro]."

Para obtener más información, vea [las dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm).

Para las dimensiones, las medidas y filtros para los informes que se utilizan en las plantillas de CQD, consulte el [Apéndice](#CQD-training).

### <a name="first-vs-second"></a>En primer lugar frente a segundo 

Muchas de las dimensiones y medidas en CQD se clasifican como primera o segunda.
CQD no usar los campos de autor de la llamada y el destinatario, éstas han sido cuyo nombre ha cambiado _en primer lugar_ y el _segundo_ porque hay pasos intermedios entre el autor de la llamada y el destinatario de la llamada. La siguiente lógica determina qué punto de conexión implicado en la transmisión o la llamada se etiqueta como primero:

-   En primer lugar siempre será un extremo de servidor (servidor de conferencia, el servidor de mediación etc.) si un servidor está involucrado en la secuencia o la llamada.

-   En segundo lugar siempre será un extremo de cliente a menos que la secuencia se encuentra entre dos extremos de un servidor.

-   Si ambos extremos son del mismo tipo, la elección de los cuales es el primera se basa en orden interno de la categoría de agente de usuario. De este modo se asegura que el orden es coherente.

Para obtener más información acerca de cómo determinar el extremo de la primero o segundo cuando están ambos el mismo, vea [las dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Secuencia frente a la llamada

Es necesario comprender la diferencia entre una llamada y una secuencia correctamente elegir qué dimensiones o medidas que se utilizan en CQD.

**Secuencia:** Existe una secuencia entre solo dos extremos. Hay sólo una secuencia para cada dirección, y dos secuencias son necesarias para la comunicación. Las secuencias son útiles para analizar los edificios o redes. En algunos casos, llamada y stream se usan en el nombre (por ejemplo, secuencia de llamada del programa de instalación o secuencia de llamada de texto).
Estos aún se clasifican como único secuencias.

**De llamadas:** Una llamada es una agrupación de todas las secuencias de todos los participantes. Consta de una llamada de, como mínimo, dos secuencias. Una sola llamada tendrá dos participantes con un mínimo de una secuencia. Las llamadas son útiles para analizar las tendencias a través del tiempo.

Para obtener instrucciones adicionales sobre si la dimensión o medida es cómo hacer referencia a una llamada o una secuencia, vea [las dimensiones y medidas disponibles en CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Llamadas de buena, deficientes y sin clasificar

Una llamada se categoriza ya sea como una buena, deficiente o sin clasificar. Hablemos un poco para hablar de cada uno de ellos con más detalle.

**Buena o mala:** Una llamada buena o mala consta de una llamada que contiene un conjunto completo de las métricas de servicio, para la que se generó un informe de QoE completo.
Determinar si una llamada es buena o mala es descritas [anteriormente en esta guía](#pcr).

**Sin clasificar:** Una llamada sin clasificar no contiene un conjunto completo de las métricas de servicio. A menudo son llamadas breves, normalmente menos de 60 segundos: donde no se ha podido calcular promedios y no se genera un informe de QoE.

### <a name="access-cqd-online"></a>Acceso CQD en línea

Puede tener acceso a CQD de dos maneras.

-   Vaya a <https://cqd.lync.com>.

-   Vaya a **Skype para el centro de administración de negocio** \> **Herramientas**y seleccione el vínculo a CQD, tal y como se muestra a continuación.

![Captura de pantalla que muestra "herramientas" seleccionadas en el panel de la barra de navegación izquierda y el vínculo a "Skype para profesionales Online llame al panel de calidad" seleccionado.](media/quality-of-experience-review-guide-image6.png)

_La figura 6: acceso a CQD a través de la Skype para el centro de administración de negocio_

### <a name="getting-started"></a>Introducción

Cuando en primer lugar, vaya a CQD, verá la página informes de resumen. La mayoría de los informes que se describen en esta guía están personalizados informes detallados. Para empezar a usar los informes detallados, seleccione **Informes de resumen** en la parte superior de la página y, a continuación, elija **Informes detallados**.

![Captura de pantalla de la depcting del panel de calidad de llamadas los diferentes tipos de informes que están disponibles.](media/quality-of-experience-review-guide-image7.png)

_La figura 7 - navegar a informes detallados_

La página de informes detallados en CQD es similar a la ilustración se muestra a continuación.

![Captura de pantalla de la página de informe detallado en CQD y los distintos elementos que componen un informe.](media/quality-of-experience-review-guide-image8.png)

_La figura 8 - página de informes detallados_

1.  El panel Resumen muestra contexto para el conjunto de informe que aparece a la derecha.

2.  Puede seleccionar **Editar** en el panel Resumen para establecer propiedades de nivel de informe (incluido el alto del eje y).

3.  La ruta de exploración ayuda a los usuarios a identificar su ubicación actual en la jerarquía del conjunto de informe.

4.  Informes que tienen informes secundarios se muestran con un vínculo azul. Al seleccionar el vínculo, puede desglosar los informes secundarios.

Elija a las líneas de tendencia para mostrar los valores detallados y gráficos de barras. El informe que tiene el foco mostrará el menú Acción: **Editar**, **clon**, **Eliminar**, **Descargar**y **Exportar informe de árbol**.

### <a name="editing-reports"></a>Edición de informes

Cuando seleccione **Editar** en el menú Acción de un informe, podrá abrir Editor de consultas. Cada informe se respaldados por una consulta. Un informe es una visualización de los datos devueltos por su consulta. El Editor de consultas es una interfaz de usuario para su edición estas consultas además de las opciones de presentación para el informe, como se muestra en la ilustración siguiente.

![Captura de pantalla de la página de informe detallado en CQD y los distintos elementos que componen un informe cuando el informe se está editando.](media/quality-of-experience-review-guide-image9.png)

_En la figura 9 - Editor de informes_

1.  Elija filtros, medidas y dimensiones desde el panel izquierdo. Apuntar a un valor existente, muestra un botón Cerrar (**X**), que puede optar por quitar el valor.

    1.  Mediante la selección de la dimensión o medida, puede cambiar el título mediante la edición en el campo **título** . También puede cambiar el orden seleccionando el azul hacia arriba o hacia abajo flechas en el panel superior.

    2.  Selección (**+**) junto a un título, se abre el cuadro de diálogo para agregar una nueva dimensión, una medida o un filtro.

    3.  Escriba las primeras letras de la dimensión, una medida o un filtro en la **Buscar un** campo para filtrar la lista para facilitar su búsqueda.

2.  El panel superior muestra las opciones para la personalización de gráfico.

3.  El Editor de consultas, se muestra una vista previa del informe.

4.  Use el cuadro de **Edición** en la parte inferior de la pantalla para crear o editar una descripción detallada del informe.

### <a name="filtering-reports"></a>Filtrado de informes

Las plantillas que proporciona incluye varias consultas integradas y filtros del informe. En las secciones siguientes se describen los filtros más comunes que se utilizan a lo largo de las plantillas.

#### <a name="cqd-filter"></a>Filtro CQD

Puede usar el filtro CQD o filtro para direcciones URL, para filtrar temporalmente cada consulta de informe. Es el filtro CQD más comunes que va a utilizar filtrar informes que se deben excluir telemetría participante federado. Se recomienda que este filtro se define un marcador para que se convierta en la vista predeterminada. Exclusión de datos federados de informes CQD es útil cuando está solucionar relativos a los edificios administrados o redes donde datos federados pueden influir en el informe.

Para implementar un filtro de CQD, en la barra de direcciones del explorador, anexe lo siguiente al final de la dirección URL:

/Filter/ [AllStreams]. [Segundo identificador de inquilino] \|[Su identificador de INQUILINO aquí]

**Ejemplo:**  
https://cqd.lync.com/cqd/\#/ 02-1234567/2018/filtro / [AllStreams]. [Segundo identificador de inquilino] \|[TENANTID] & inquilino = TENANTID

> [!NOTE]
> El ejemplo de dirección URL anterior es para obtener sólo la representación visual. Utilice el vínculo CQD predeterminado de <https://cqd.lync.com>.

#### <a name="query-filters"></a>Filtros de consulta

Filtros de consulta se implementan mediante el Editor de informes. Estos filtros se utilizan para reducir el número de registros devueltos por CQD, lo cual se minimiza tamaño total del informe. Esto es especialmente útil para el filtrado de redes no administradas.
Los filtros siguientes usan expresiones regulares (RegEx).

_Tabla 3 - filtros de consulta_

| Filtro               | Descripción          | Ejemplo de filtro de consulta CQD                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Valores en blanco         | Algunos filtros no tienen la opción para filtrar los valores en blanco. Para filtrar manualmente valores en blanco, use la expresión en blanco y establezca el filtro en es igual a o no es igual a, según sus necesidades.                                                                                                                             | Nombre del segundo edificio \< \> \^ \\s\*\$                       |
| Subredes particulares populares | Sin un archivo de creación válido para separar administrada desde redes no administradas, obtener incluirá redes particulares en los informes. Estas subredes particulares están fuera del ámbito del control de TI y pueden excluirse rápidamente de un informe. Subredes particulares populares, como se define en esta guía, son 10.0.0.0, 192.168.1.0 y 192.168.0.0. | Segunda subred \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Inside frente a fuera   | Se usa para filtrar un informe para (inside) administrado o no administrado (externa). La plantilla CQD administrada ya está preconfigurada con estos filtros.                                                                                                                                                                                | En segundo lugar dentro de Corp = dentro de                               |

#### <a name="report-filters"></a>Filtros del informe

Filtros del informe se implementan mediante la adición de un filtro en el informe representado, ya sea en el Editor de informes o directamente en el informe. Los siguientes filtros de informes se usan en toda la plantilla.

_Tabla 4 - filtro de informe_

| Filtro     | Descripción                            | Ejemplo de filtro de informe CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Empiece con el año inicial y, a continuación, mes. | 10 de 2017                           |
| Alfabéticos | Filtra todos los caracteres alfabéticos. | [a-z]                             |
| Numérico    | Filtra todos los caracteres numéricos.    | [0-9]                             |
| Porcentaje | Filtra por un porcentaje.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importar las plantillas CQD

Esta guía consta de [dos plantillas de CQD curated](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true). Estas plantillas aceleran su uso de CQD y proporcionan una oportunidad de aprovechar rápidamente las capacidades del CQD para realizar un impacto en los equipos o Skype de los usuarios para que la experiencia empresarial. La plantilla de todas las redes, aunque optimizado para trabajar con un edificio se puede usar el archivo de datos, mientras se trabaja hacia la recopilación y la carga de información de creación en CQD, tal como se describe en la siguiente sección.

**Para importar las plantillas (. CQDX) en CQD en línea**

1.  Vaya a <https://cqd.lync.com>.

2.  Realice la autenticación mediante el uso de las credenciales administrativas de Office 365.

> [!NOTE]
> Debe tener Office 365 administrador Global, Skype para Administrador empresarial o rol de lectores de informes tener acceso a CQD. 


3.  Seleccione el menú de **Informes de resumen** en la parte superior de la página y, a continuación, elija **Informes detallados**.

4.  En el panel Resumen, seleccione **Importar**. Vaya a la ubicación de guardado de CQDX, seleccione la plantilla CQDX y, a continuación, seleccione **Abrir**.

5.  Después de carga la plantilla, como una ventana emergente mostrará el mensaje "importación de informe fue correcta". Seleccione **Aceptar.**

![Captura de pantalla de una ventana emergente que informa al usuario de que la plantilla se ha importado correctamente.](media/quality-of-experience-review-guide-imagestep5.png)

6.  Repita los pasos 4 y 5 para la segunda plantilla CQD.

> [!NOTE]
> Las plantillas CQD se importan por usuario. Si necesitan usar el informe de usuarios adicionales, debe iniciar sesión en e importar las plantillas a su instancia CQD. 


## <a name="building-mapping"></a>Asignación de creación

En un equipo o Skype para la implementación empresarial en línea, todos los clientes son externos.
Que tiene la implicación que de forma predeterminada, todos los clientes son conocida como fuera de CQD en línea, independientemente de si el cliente se ha conectado en una red corporativa interna.

Cuando se trabaja con la calidad de las llamadas, necesita conocer la ubicación de un cliente y si estaba conectado a una red puede administrar o una red no se puede administrar: la suposición de que se va a que solo puede mejorar las redes puede administrar.
Mediante la carga de red y la información de creación a CQD Online, habilitar CQD determinar si un cliente se conecta a una red interna corporativa o administrados o a una red externa y no administrado.

### <a name="building-data-file-structure"></a>Estructura de archivos de datos de creación

El formato del archivo de datos que se carga debe cumplir los siguientes requisitos para pasar la comprobación de validación antes de cargarlas.

-   El archivo debe ser un archivo TSV, lo que significa que, para cada fila, cada columna viene separada por un carácter de tabulación, o un archivo CSV en el que cada columna viene separada por una coma.

-   El archivo no se puede tener más de 50 MB.

-   El contenido de los datos de archivo *no debe incluir los encabezados de tabla*. En otras palabras, la primera línea del archivo de datos debe ser datos reales, no los encabezados de columna, como "Red".

-   Para cada columna, el tipo de datos sólo puede ser cadena, número o Bool. Si el tipo de datos es el número, el valor debe ser un valor numérico; Si es Bool, el valor debe ser 0 o 1.

-   Para cada columna, si el tipo de datos es la cadena, los datos pueden estar vacíos (pero aún deben estar separados por un delimitador adecuado, que es un carácter de tabulación o una coma). Esto sólo asigna ese campo un valor de cadena vacía.

-   Debe haber 14 columnas para cada fila. Cada columna debe tener el tipo de datos que se describen en la siguiente tabla y las columnas deben estar en el orden indicado en la tabla.

_Tabla 5: creación de la estructura de archivos_

| Nombre de columna        | Tipo de datos | Ejemplo                   | Orientación    |
|--------------------|-----------|---------------------------|-------------|
| Red            | Cadena    | 192.168.1.0               |  Obligatorio    |
| NetworkName        | Cadena    | Estados Unidos/Seattle/SEATTLE-mar-1 | Obligatorio\*  |
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

\*Si bien no es necesario por CQD, las plantillas están configuradas para mostrar la generación y red nombre.

#### <a name="supernetting"></a>Creación de superredes

Puede usar la creación de superredes, denominado habitualmente enrutamiento de interdominios sin clases (CIDR), en lugar de definir cada subred. Una *supernet* es una combinación de varias subredes que comparten un solo prefijo de enrutamiento. En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes/CIDR. Se admite la creación de superredes, pero no se recomienda usarlo.

Por ejemplo, la creación de marketing de Contoso se compone de las subredes que aparece a continuación:

-   10.1.0.0/24 – primera planta

-   10.1.1.0/24 – segundo piso

-   10.1.2.0/24 – tercer piso

-   10.1.3.0/24 – cuarto floor

En lugar de agregar una entrada para cada subred, puede usar la dirección de superredes/CIDR: en este ejemplo, 10.1.0.0/22.

-   Red = red dividida 10.1.0.0

-   Intervalo de red = 22

A continuación presentamos algunas cosas que se deben considerar antes de implementar la creación de superredes:

-   Creación de superredes tarda menos tiempo front-, pero lo que respecta a costa de la reducción de la flexibilidad de los datos. Supongamos que hay un problema de calidad que implican subred 200.1.2.0. Si implementa la creación de superredes, no sabrá donde se encuentra la subred en el edificio o qué tipo de red es (por ejemplo, un laboratorio). Si se hubiera definido todas las subredes de un edificio y cargar información de ubicación de planta, podrá vea esa distinción.

-   Es importante para asegurarse de que la dirección de superredes/CIDR es correcta y no captura de subredes no deseadas.

-   Creación de superredes se puede usar en una asignación de creación con máscara de bits de 8 a 28 bits.

-   Es un proceso bastante común para buscar 192.168.0.0 en los datos. Para muchas organizaciones, esto indica que el usuario está en casa. Para otras personas, éste es el esquema de direcciones IP de una oficina satélite. Si su organización tiene oficinas que usan esta configuración, no la incluye en su archivo de creación como es difícil distinguir entre las redes domésticas e internas mediante el uso de subredes comunes.

> [!IMPORTANT]
> El intervalo de red puede usarse para representar un supernet. Creación de todas las nuevas cargas de archivos de datos se comprobarán para cualquier intervalos superpuestos. Si anteriormente se ha cargado un archivo de creación, debe descargar el archivo actual y cargar nuevo para identificar cualquier superposiciones y solucionar el problema. Cualquier superposición en los archivos cargados previamente puede provocar en las asignaciones de incorrectos de subredes a edificios en los informes. 


#### <a name="vpn"></a>VPN

La calidad de los datos de la experiencia (QoE) que los clientes de envían a Office 365, que es donde se proceden de datos CQD: incluye una marca VPN. Sin embargo, esta marca se basa en proveedores de VPN informar a Windows de que el adaptador de red VPN registrado es un adaptador de acceso remoto. No todos los proveedores de VPN registran correctamente los adaptadores de acceso remoto. Por este motivo, es posible que no pueda utilizar los filtros de consulta integrados de VPN. Existen dos enfoques para adaptación a subredes VPN en la creación del archivo de información.

-   Definir un **Nombre de red** mediante el texto "VPN" en este campo para subredes VPN.

![Captura de pantalla de un informe en el panel de calidad de llamadas que define cómo crear una subred VPN](media/quality-of-experience-review-guide-image10.png)

_La figura 10 - VPN mediante el nombre de red_

-   Para definir un **Nombre del edificio** , con el texto "VPN" en este campo para subredes VPN.

![Captura de pantalla de un informe en el panel de calidad de llamadas que define cómo crear una definición de creación que consta de una subred VPN.](media/quality-of-experience-review-guide-image11.png)

_La figura 11 - VPN mediante el nombre del edificio_

> [!IMPORTANT]
> Algunas implementaciones de VPN no notificar con precisión la información de subred. Si esto ocurre en la creación de informes, que se recomienda que cuando se agrega una subred VPN para el archivo de creación, en lugar de una entrada para la subred, agregar entradas independientes para cada dirección de la subred VPN como una red independiente de 32 bits. Cada fila puede tener los mismos metadatos de creación. Por ejemplo, en lugar de una fila por 172.16.18.0/24, tiene 253 filas, con una fila por cada dirección de 172.16.18.1/32 a través de 172.16.18.254/32, ambos inclusive.


> [!NOTE]
> Se sabe que las conexiones VPN identificar incorrectamente la conexión de red como por cable cuando la conexión a internet subyacente es inalámbrica. Cuando se mira calidad a través de conexiones VPN, no se puede suponer que el tipo de conexión se ha identificado con precisión.

### <a name="uploading-building-information"></a>Cargar información de creación

El panel de informes de resumen de CQD incluye una página **Inquilino la carga de datos** , puede tener acceso seleccionando la etiqueta de vínculo **Inquilino la carga de datos** en la esquina superior derecha (busque el icono del engranaje). Esta página se usa para los administradores para cargar su propia información, como la asignación de dirección IP y la información geográfica, asignación de cada punto de acceso inalámbrico y su dirección MAC y así sucesivamente.

1.  Vaya a CQD Online buscando en <https://cqd.lync.com>.

2.  Seleccione el icono del engranaje en la esquina superior derecha y elija el **Inquilino al cargar los datos** desde la página **Informes de resumen** .

![Captura de pantalla de un cuadro de diálogo en el panel de calidad de llamadas que aparece mientras se está cargando datos.](media/quality-of-experience-review-guide-image12.png)

_La figura 12 - menú cargar datos de inquilinos_

1.  Como alternativa, si se trata de la primera vez que visita CQD, se solicitará a cargar los datos de creación. Puede seleccionar **Cargar ahora** para navegar rápidamente a la página de **Carga de datos de inquilinos** .

![Captura de pantalla de una pancarta en el panel de calidad de llamada que notifica a un usuario para cargar datos de creación.](media/quality-of-experience-review-guide-image13.png)

_La figura 13: creación de pancarta de carga de datos_

1.  En la página de **Carga de datos de inquilinos** , seleccione **Examinar** para elegir un archivo de datos.

2.  Después de seleccionar un archivo de datos, especifique la **fecha de inicio** y, opcionalmente, especifique una fecha de finalización.

3.  Después de seleccionar la **fecha de inicio**, seleccione la opción **cargar** para cargar el archivo en el CQD. <br><br>Antes de que se carga el archivo, se valida. Si se produce un error de validación, se muestra un mensaje de error que solicita que se corrija el archivo. La siguiente ilustración muestra un error que se producen cuando el número de columnas en el archivo de datos es incorrecto.

![Captura de pantalla de un cuadro de diálogo en el panel de calidad de llamadas que describe un mensaje de error al importar los datos de creación.](media/quality-of-experience-review-guide-image14.png)

_La figura 14: creación de error de carga de datos_

4.  Si no se producen errores durante la validación, la carga de archivos se realizará correctamente. A continuación, puede ver el archivo de datos que se cargan en la tabla **Mis cargas** , que muestra la lista completa de todos los archivos que se cargan para el inquilino actual en la parte inferior de la página.

> [!NOTE]
> Puede tardar hasta cuatro horas para finalizar el procesamiento del archivo de creación. <br><br> Si ya se ha cargado un archivo de creación y necesita para agregar subredes que es posible que se han cumplido o excluidos, modifique el archivo original mediante la adición de las nuevas subredes, quite el archivo actual y volver a cargar el archivo recién editado. Puede haber creación activo sólo un archivo de datos en CQD. 

### <a name="missing-subnets"></a>Subredes que faltan

Después de cargar información de creación para redes administradas, cada red administrada debe tener una asociación de creación. Sin embargo, esto no siempre es el caso; Normalmente, se pierden algunas subredes. En esta sección, se explica cómo validar las redes que faltan.

Vaya a la página de **Informes detallados** en CQD en línea y navegue hasta el **Informe de subred falta** incluidas en las plantillas CQD. Esto presenta todas las subredes con secuencias de 10 o más audio que no están definidas en la creación de archivo de datos. Asegúrese de que no hay ninguna red administrada en esta lista. Si faltan subredes, actualice la creación original del archivo de datos y volver a cargarla a CQD.

> [!IMPORTANT]
> Debe agregar el identificador de inquilino como un filtro de consulta para el **Segundo identificador de inquilino** a este informe para filtrar el informe para ver sólo los datos de inquilino de su organización. De lo contrario, el informe mostrará subredes federadas.

> [!NOTE] 
> Asegúrese de ajustar el filtro de informe de año mes al mes actual. Seleccione **Editar**y ajustar el filtro de informe de **Mes año** para guardar el nuevo mes predeterminado.                                                  |

![Informe que muestra las subredes no se incluye en el archivo de datos de creación de CQD que muestran el uso.](media/quality-of-experience-review-guide-image15.png)

_La figura 15: informe de creación que falta_

## <a name="reliability-investigations"></a>Investigaciones de confiabilidad

El primer paso para mejorar la calidad es para evaluar el estado de confiabilidad de audio en toda la organización. Debido a que la confiabilidad de audio es vital para una experiencia de usuario positivo, empezamos con los dos componentes que miden la confiabilidad:

1.  **Errores en la instalación de llamadas:** No se puede establecer la sesión.

2.  **Colocar errores de llamadas:** Sesión se haya establecido y finalizado de forma inesperada

En esta sección, trataremos métodos para investigar ambas áreas.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía. La descripción del informe individuales para obtener más información, consulte.


### <a name="call-setup"></a>Programa de instalación de la llamada

Establecer prioridades de solucionar errores del programa de instalación de llamadas en esta área en primer lugar, ya que estos errores tienen un impacto negativo significativo en la experiencia del usuario.

Comenzar su investigación evaluando el porcentaje de errores en la instalación llamada general para la organización y, a continuación, asignar prioridades a las áreas de investigación según el porcentaje más alto mediante la creación o la red.

#### <a name="call-setup-failures-overall"></a>Errores de configuración generales de llamadas

Este informe de gráfico muestra la cantidad total de llamada correcta, configurar y errores del programa de instalación de llamadas a través del tiempo. Seleccione cualquiera de las columnas para mostrar sus valores individuales, como se muestra en la figura siguiente.

![Captura de pantalla de un gráfico que muestra el porcentaje de secuencia del programa de instalación error de llamada de Audio](media/quality-of-experience-review-guide-image16.png)

_Errores de la figura 16 - confiabilidad de Audio - llamadas secuencia del programa de instalación_

##### <a name="analysis"></a>Análisis

Este informe muestra el uso del programa de instalación de llamada de audio y los errores de su organización a través del tiempo. Mediante el uso de este informe, puede responder a las siguientes preguntas y determinar el curso de acción siguiente:

1.  ¿Qué es el porcentaje de error del programa de instalación de llamada total para el mes actual?

2.  ¿Es el porcentaje de errores de llamada total del programa de instalación por debajo o por encima de la métrica de destino definido?

3.  ¿Es la tendencia de error peor o mejor que el mes pasado?

4.  ¿La tendencia de errores aumenta, steady, o disminuye?

La información presentada en este informe indicará a la historia de ¿con qué frecuencia se producen errores en sus configuraciones de llamada general en toda la organización.

Independientemente de las respuestas anteriores, tómese tiempo para investigar más mediante el uso de los informes de subcaracterística incluye para buscar cualquier edificios individuales o las redes que necesiten corrección. Aunque es posible que el porcentaje de errores generales por debajo de la métrica de destino, a menudo las tasas de error para uno o varios de los edificios o redes están por encima de la métrica y necesitan corrección.

#### <a name="call-setup-failures-by-building-and-subnet"></a>Llamar a errores en la instalación mediante la creación y la subred 

Este informe de tabla se usa para detectar y aislar los edificios o las redes que necesiten corrección.

> [!NOTE]
> Asegúrese de ajustar el filtro de informe de año mes al mes actual. Seleccione **Editar**y ajustar el filtro de informe de **Mes año** para guardar el nuevo mes predeterminado.


![Informe de que las listas de llamada del programa de instalación error motivos, organizados por creación, red y subred al mes.](media/quality-of-experience-review-guide-image17.png)

_Figura 17 - errores de Audio del programa de instalación mediante la creación o subred_

##### <a name="remediation"></a>Corrección 

Centrar los esfuerzos de corrección en los edificios o subredes que tienen el mayor volumen de errores en primer lugar, ya que esto maximizar el impacto en la experiencia del usuario y ayudan a reducir rápidamente los errores del programa de instalación de llamada organizativa.
En la siguiente tabla se enumera las dos razones para errores de llamadas del programa de instalación beneficiarán de acuerdo con CQD.

_Tabla 6: razones para errores de llamadas del programa de instalación_

| Llamar a causa de errores en la instalación                       | Causa típica                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Falta una regla de exención de inspección RV profunda del paquete | Indica que el equipo de red a lo largo de la ruta de acceso impide que la ruta de acceso de medios está estableciendo debido a las reglas de inspección profunda del paquete. Esto es probable que debido a las reglas de firewall no está configuradas correctamente. En este caso se ha realizado correctamente en el protocolo de enlace TCP pero no se ejecutó el protocolo de enlace SSL.               |
| Falta una regla de excepción del bloque RV IP               | Indica que el equipo de red a lo largo de la ruta de acceso impide que la ruta de acceso de medios está estableciendo a la red de Office 365. Esto puede resultar debido a las reglas de proxy o firewall no está configuradas correctamente para permitir el acceso a direcciones IP y los puertos usados para los equipos y Skype para el tráfico de negocio. |

Ahora cuando comience la corrección, puede Centrar los esfuerzos de un determinado edificio o subred. Como se muestra en la tabla anterior, estos problemas son debido a las configuraciones de firewall o proxy. Revise las opciones en la tabla siguiente para las acciones de corrección.

_Tabla 7: pasos siguientes para llamada de corrección de error del programa de instalación_

| Corrección           | Orientación     |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar servidores | Trabajar con el equipo de red y comprobar la configuración de servidores frente a [la lista de direcciones IP de Office 365](https://aka.ms/o365ips). Compruebe que las [subredes de medios](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) y puertos se encuentran en las reglas de firewall. Compruebe que se abren los puertos TCP y UDP necesarios en el servidor de seguridad. Medios prefiere UDP a través de TCP. TCP se considera un protocolo de la conmutación por recuperación.<br><ul><li>**TCP:** el puerto 443</li><li>**UDP:** puertos 3478 – 3481</li><ul> |
| Comprobar                | Sacar provecho de la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar la conectividad de la creación afectado o subred mediante el uso de la función de comprobación de conectividad.    |


### <a name="call-drop"></a>Colocación de llamada

A diferencia de errores de llamadas del programa de instalación, no hay ningún código de motivo para indicar por qué llamada colocada errores se produjo, lo que dificulta aislar una causa concreta. Para detectar mejor llamadas interrumpidas, usa un enfoque inferido. Al solucionar relativos a las áreas de interés para el audio, aplicación de revisiones de los clientes y que dirigen el uso de dispositivos certificados para equipos y Skype para la empresa, cabría esperar errores de llamadas colocada a rechazar.

#### <a name="call-drop-failures-overall"></a>Errores de entrega general de llamadas

Este informe de gráfico muestra la cantidad total de secuencias de audio, las secuencias de audio totales colocadas, y secuencia total colocada porcentaje. Seleccione cualquiera de las columnas para mostrar sus valores, como se muestra en la ilustración siguiente.

![Captura de pantalla de un gráfico que muestra el porcentaje de colocada secuencias de llamada de Audio](media/quality-of-experience-review-guide-image18.png)

_Porcentaje de errores de la figura 18 - llamada Total colocada_

##### <a name="analysis"></a>Análisis

Este informe de gráfico muestra los errores y el uso de su organización a través del tiempo relacionadas con gotas de llamadas. Mediante el uso de este informe, puede responder a las siguientes preguntas:

1.  ¿Qué es la llamada actual total colocada porcentaje?

2.  ¿Es el porcentaje del total del buzón por debajo de la métrica de destino definido?

3.  ¿Es la tendencia de error peor o mejor que el mes pasado?

4.  ¿La tendencia de errores aumenta, steady, o disminuye?

La información presentada en este informe puede contar la historia de ¿con qué frecuencia se están produciendo sus gotas de llamada general en toda la organización.

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo para investigar utilizando los subinformes para buscar cualquier edificios o redes que podrían necesitar corrección. Aunque es posible que la velocidad de buzón global por debajo de la métrica de destino, a menudo la tasa de entrega de uno o varios de los edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="call-drop-failures-by-building-or-subnet"></a>Errores de unión de llamadas por edificio o subred

Errores en este informe de tabla indican que la llamada se ha colocado de forma inesperada y resulta en una experiencia de usuario negativo. Existen dos informes de tabla incluidos en la plantilla, uno para investigar la conferencia y el otro para entre dos participantes.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.


![Que el número de listas y el porcentaje de llamadas interrumpidas, organizados por subred al mes, red y creación de informes.](media/quality-of-experience-review-guide-image19.png)

_La figura 19: llamada de Audio colocada errores por edificio o subred_

##### <a name="remediation"></a>Corrección

Con el informe de tabla anterior, ahora puede aislar "problemáticos" en la red administrada donde se produzcan gotas de llamada por encima de la métrica de destino definido. Centrar los esfuerzos de corrección en los edificios o las redes que tienen el número de secuencia total más alto en primer lugar, para obtener el mayor impacto.

Causas habituales de gotas de llamada:

-   Salida de red o de internet en aprovisionado

-   Sin QoS configurado en redes limitadas

-   Versiones anteriores de cliente

-   Comportamiento de usuario

Después de descubrir problemáticos, puede aprovechar [Análisis llamar](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) para revisar aún más los usuarios de dicho edificio problemas específicos. Análisis de llamada contiene datos PII y pueden ser útil para aislar aún más los posibles motivos de gotas de la llamada.

Independientemente del siguiente paso, es una práctica recomendada para notificar el departamento de soporte técnico que se ha detectado un problema con los edificios específicos o subredes. De este modo, rápidamente pueden responder a las llamadas entrantes y clasificar los usuarios de forma más eficaz. Los usuarios marcados se pueden, a continuación, notificar al equipo de ingeniería para una mayor investigación.

En la siguiente tabla se enumera algunos métodos comunes para administrar y corregir gotas de llamada.

_Tabla 9 - pasos siguientes para llamada drop corrección_

| Corrección                              | Orientación     |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Red o a internet                         | Ahora que ya sabe qué edificio se ve afectada, trabaje con su equipo de red para supervisar el ancho de banda en dicho edificio para determinar si hay problemas con sobreutilización. Si se detecta el problema a estar relacionados con la congestión de la red, considere la posibilidad de ancho de banda creciente a dicho edificio. <br><br>**QoS:** Si cada vez mayor ancho de banda es imposible o costo sumamente elevado, considere la implementación de QoS. Esto garantizará que se asignan prioridades a los paquetes de multimedia en la red administrada por encima el tráfico de medios que no sean. Como alternativa, si no hay ninguna evidencia borrar que dicho ancho de banda es el punto de entrada, tenga en cuenta estas soluciones:<br><ul><li>[Instrucciones de QoS de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obtener instrucciones de QoS de negocio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Realizar una evaluación de disponibilidad de red:** Una evaluación de la red proporciona información detallada sobre el uso del ancho de banda esperado, cómo lidiar con ancho de banda y de la red cambia y redes procedimientos recomendados para los equipos y Skype para la empresa. Uso de la tabla anterior como su origen, tener una lista de los edificios o subredes que son candidatos excelentes para una evaluación. <br><ul><li>[Evaluación de preparación de redes de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para evaluación de preparación para la red empresarial](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Herramienta de evaluación de la red de Microsoft:** Use esta herramienta para una prueba simple de rendimiento de la red para determinar el grado en que debería realizar la red para los equipos de un o Skype para llamadas en línea de negocio. La herramienta le ayuda a evaluar el rendimiento de una subred y validar la preparación de la red frente a [requisitos](https://aka.ms/performancerequirements)de rendimiento de Microsoft.<ul><li>[Descargar la herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul>         |
| Los clientes (Skype para la empresa sólo en línea) | Algunos clientes más antiguos tienen conocidos, documentan problemas con la confiabilidad de los medios. Revisar los informes de análisis de llamadas desde varios usuarios afectados o crear un informe de tabla de versión de cliente personalizado en CQD filtrado a edificios específicos o subredes con medida % de error Total de llamadas colocada. Esta información le ayudará a comprender si existe una relación entre gotas de llamada en dicho edificio específico y una versión específica del cliente.                                                                                                                                                              |
| Dispositivos                                  | La mayoría de los errores de dispositivo son debido al uso de dispositivos que no están certificados para los equipos o Skype para la empresa. Errores normalmente adoptan la forma del integrada altavoces o micrófonos que se usan o combinaciones de earbud/micrófono que están conectadas a la toma de audio de 3,5 mm en un dispositivo. Recomendación actual de Microsoft es que los usuarios que están experimentando llamar a gotas: o deficientes llama en general y son el uso de dispositivos integrados o controladores debe ser aprovisionar un [certificado auriculares con micrófono o altavoz](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). |
| Comportamiento de usuario                            | Si determina que ni de red, dispositivos o clientes son el problema, considere la posibilidad de contratar [Asesor de mi](https://aka.ms/myadvisor) para obtener orientación en el desarrollo de una estrategia de adopción de usuario para enseñar a los usuarios cómo procedimientos unirse y salir de las reuniones. Los equipos de una manera más eficaz y usuario de Skype generarán una mejor experiencia de usuario para todos los participantes de la reunión. Un usuario que pone a su equipo portátil en modo de suspensión (cerrando la tapa) sin salir de la reunión se clasifica como un buzón de llamada inesperada.     |

## <a name="quality-investigations"></a>Investigaciones de calidad

El siguiente paso para evaluar el estado de calidad de audio a través de la implementación es investigar Audio deficiente llamar proporción (PCR), TCP y uso de proxy. Es importante recordar que datos CQD no proporcionan una causa concreta, sino que proporcionan con áreas de problema es probable que para iniciar una conversación de colaboración con los equipos adecuados para las actividades de corrección.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía. La descripción del informe individuales para obtener más información, consulte. 


### <a name="investigate-call-quality"></a>Investigue la calidad de la llamada

El porcentaje PCR global se usa principalmente para indicar si la organización cumple los objetivos de métrica audioconferencias definidos. Es importante tener en cuenta que incluso si el porcentaje general es dentro de destino, algunas subredes o edificios podrían no cumplir los objetivos definidos y, por tanto, se necesitan más investigación. Por ejemplo, si el porcentaje PCR audio organizativo es 3 por ciento en diciembre, que cumple con el destino de ejemplo, los edificios específicos es posible que se teniendo una mala experiencia, dependiendo de la distribución de ese 3 por ciento.

#### <a name="overall-organizational-poor-call-percentage"></a>Porcentaje de llamadas deficientes organizativa general

Para evaluar el porcentaje general de las llamadas para el uso de la organización del informe de gráfico general de calidad deficientes.

![Captura de pantalla de un gráfico que muestra el porcentaje de llamadas de calidad deficiente](media/quality-of-experience-review-guide-image20.png)

_Figura 20 – una calidad de Audio - general_

##### <a name="investigation"></a>Investigación

Este informe de gráfico muestra PCR y el uso de su organización a través del tiempo. Mediante el uso de este informe, puede responder a las siguientes preguntas:

1.  ¿Qué es la PCR total para el mes actual?

2.  ¿Es la PCR debajo de la métrica de destino definido?

3.  ¿Es la tendencia de error peor o mejor que el mes pasado?

4.  ¿La tendencia de errores aumenta, steady, o disminuye?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo para investigar mediante el uso de los subinformes para buscar cualquier edificios o redes que podrían necesitar una investigación. Aunque es posible que la PCR general por debajo de la métrica de destino, a menudo la PCR para uno o varios de los edificios o redes está por encima de la métrica y necesita más investigación.

#### <a name="audio-quality-overall"></a>Calidad de audio general

Hay dos árboles de informe incluidos en las plantillas de calidad de audio, uno para investigar la conferencia y el otro para llamadas de dos participantes. Para los fines de corrección de calidad, el proceso de investigación es el mismo, por lo que nos centraremos aquí en la conferencia. Mejoras en la calidad de la conferencia positiva también afectará a la calidad de las llamadas entre dos participantes. Los informes también se incluyen a una calidad de audio para las conferencias y entre dos participantes con cable por la vista y Wi-Fi.

> [!NOTE]
> Investigación de llamadas deficientes de dos participantes es similar a investigar las llamadas de conferencia. La tarea consiste en identificar los edificios o subredes que tienen la menor calidad para validar si hay un patrón de llamadas deficientes con otro edificio o subred. 

![Captura de pantalla de la calidad de Audio - informe de conferencia en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image21.png)

_La figura 21: calidad de Audio - conferencia_

##### <a name="investigation"></a>Investigación

Este informe de gráfico muestra la conferencia o el uso de dos participantes y PCR de su organización a través del tiempo. Mediante el uso de este informe, puede responder a las siguientes preguntas:

1.  ¿Qué es la PCR total para el mes actual?

2.  ¿Es la PCR debajo de la métrica de destino definido?

3.  ¿Es PCR peor o mejor que el mes pasado?

4.  ¿La tendencia PCR aumenta, steady, o disminuye?

Independientemente de las respuestas a las preguntas anteriores, tómese el tiempo para investigar mediante el uso de los subinformes para buscar cualquier edificios o redes que es posible que deben investigarse. Aunque es posible que la PCR general por debajo de la métrica de destino, a menudo la PCR para uno o varios de los edificios o redes está por encima de la métrica y necesita corrección.

#### <a name="poor-audio-stream-by-building-and-subnet"></a>Secuencia de audio deficiente mediante la creación y la subred

Este informe de tabla proporciona información adicional sobre qué contribuido a las llamadas que se clasificó como deficiente y ayuda a aislar los puntos activos en la red administrada.

El detalle de conexión distingue entre con cable y Wi-Fi e incluye las medidas de tiempo de ida y vuelta (RTT), la pérdida de paquetes y vibración. Un informe similar también existe en los informes de entre dos participantes y se usa para aislar las llamadas entre dos participantes en su red administrada.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado. 

> [!TIP]
> Redes particulares comunes son difíciles de evaluación de errores debido a su uso extendido. Un informe independiente que usa la dirección IP de servidor de seguridad se ha agregado a la plantilla de todas las redes para ayudar a solucionar las oficinas que utilizan redes comunes.

![Informe que se enumera los tipos de conexión, tipos de transporte y PCR mayor que % 3 junto con las diversas razones mala calidad organizados por la creación, la red y la subred al mes.](media/quality-of-experience-review-guide-image22.png)

_La figura 22 - resumen de secuencia de Audio deficiente mediante la generación de - y subred conferencia_

##### <a name="remediation"></a>Corrección

Centrar los esfuerzos de corrección en los edificios o las redes que tienen el mayor volumen de secuencias de audio, ya que esto maximizar el impacto y ayudar a mejorar el usuario experimentan rápidamente. Use la vibración, la pérdida de paquetes y las medidas de RTT para comprender lo que contribuye a la calidad de llamadas deficientes. Es posible que haya más de un problema:

-   **Vibración:** Los paquetes multimedia llegan a diferentes velocidades, que hace que un altavoz se oye robótica.

-   **La pérdida de paquetes:** Se está eliminando los paquetes multimedia, que crea el efecto de ausencia de palabras o sílabas.

-   **RTT:** Los paquetes multimedia tardan mucho tiempo para llegar a su destino, que crea un efecto transmisor-receptor portátil.

Aunque ningún origen único de verdad cuentas para lo que puede provocar una llamada deficiente, varios métodos comunes pueden ayudarle a abordar los problemas con anomalías de la red.

Para ayudar a la investigación de problemas de calidad, puede aprovechar [Análisis de llamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309).
Con el análisis de llamadas, puede buscar en una conferencia concreta o informe detallado de llamadas de los usuarios. Este informe contendrá datos PII y es útil cuando se intenta discernir un motivo para errores. Una vez que sepa qué edificio se ve afectada, hacer un seguimiento a los usuarios en que creación debe ser un proceso sencillo.

No olvide que el departamento de soporte técnico sepan que estas redes están experimentando problemas de calidad, para que puedan detectar y responder a las llamadas entrantes rápidamente.

_Tabla 9 - comunes colaboradores PCR alta_

| Corrección                              | Orientación       |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Redes                                 | Una red sobreutilizada o aprovisionado en puede provocar problemas con la calidad de medios. Trabajo con el equipo de red para determinar si las conexiones de red desde el usuario a la salida de internet señalan tiene suficiente ancho de banda para admitir los medios. **Realizar una evaluación de disponibilidad de red:** Una evaluación de la red proporciona información detallada sobre el uso del ancho de banda esperado, cómo lidiar con ancho de banda y de la red cambia y redes procedimientos recomendados para los equipos y Skype para la empresa. Uso de la tabla anterior como su origen, tener una lista de los edificios o subredes que son candidatos excelentes para una evaluación.<br><ul><li>[Evaluación de preparación de redes de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#test-the-network)</li><li>[Skype para evaluación de preparación para la red empresarial](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Herramienta de evaluación de la red de Microsoft:** Use esta herramienta para una prueba simple de rendimiento de la red para determinar el grado en que debería realizar la red para los equipos de un o Skype para llamadas en línea de negocio. Esta herramienta le ayuda a evaluar el rendimiento de una subred y validar la preparación de la red frente a los de rendimiento de Microsoft [requisitos](https://aka.ms/performancerequirements).<br><ul><li>[Descargar la herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885) </li></ul>        |
| Calidad de servicio (QoS)                 | QoS es un método probado para dar prioridad a los paquetes en una red para asegurarse de que llegan a su destino intacta y en el tiempo. Considere la implementación de QoS en toda la organización para maximizar la calidad de la experiencia del usuario donde está limitada o restringida ancho de banda. QoS le ayudará a solucionar problemas asociados normalmente con niveles altos de pérdida de paquetes, y, en menor grado, tiempos de ida y vuelta y vibración. <br><ul><li>[Instrucciones de QoS de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)</li><li>[Skype para obtener instrucciones de QoS de negocio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul>    |
| Wi-Fi                                    | Wi-Fi puede tener un impacto significativo en la calidad de la llamada. Diseño de Wi-Fi normalmente no tiene en cuenta los requisitos de red para servicios de VoIP y a menudo es una fuente de mala calidad. **QoS:** Redes inalámbricas modernas deben admitir muchos dispositivos. Estos dispositivos compiten por el ancho de banda y pueden dar lugar a problemas de calidad para servicios de VoIP donde son vitales velocidad y la latencia. Consulte a su proveedor inalámbrico para obtener detalles específicos y considere la implementación de QoS en su red inalámbrica para dar prioridad a Skype para los medios de negocios y los equipos. **Densidad AP:** Puntos de acceso (AP) pueden ser demasiado alejados o no en una ubicación ideal. Para minimizar las posibles interferencias, coloque los puntos de acceso adicionales en salas de conferencias y en ubicaciones que no están obstruidas por paredes u otros objetos. **2,4 GHz frente a 5 GHz:** 5 GHz proporciona menos interferencias de fondo y velocidades superiores y se debe asignar prioridad al implementar VoIP a través de Wi-Fi. Sin embargo, 5 GHz no es tan fuerte como a 2,4 GHz y no entrar en las paredes como fácilmente. Revise el diseño de creación para determinar qué frecuencia puede depender de la conexión de procedimientos. **Intensidad de la señal:** Tradicionalmente, medido en dBm (proporción de energía en decibelios), mide la fuerza de la señal inalámbrica. Después de que un dispositivo está conectado a un punto de acceso, no desea permitir que ir fácilmente. Medida que el dispositivo se aleja el punto de acceso, la intensidad de señal disminuye hasta un punto que provoca una mala conexión incluso aunque otra, cuanto más cerca esté el punto de acceso está disponible. Si es posible, trabajar con su proveedor de AP para asegurarse de que los puntos de acceso estén configurados para eliminar un dispositivo cuando intensidad de la señal cae por debajo de un nivel aceptable. Esto le permitirá garantizar que el dispositivo no se bloquee un punto de acceso débil. Esto es una buena solución cuando no se puede agregar fácilmente más puntos de acceso. **Controlador inalámbricos:** Cuando se produce un error en todo lo demás, asegúrese de que los controladores inalámbricos estén actualizados. Esto le ayudará a mitigar cualquier experiencia de usuario deficiente relacionado con un controlador anticuado. |
| Dispositivo de red                           | Las organizaciones más grandes deberían cientos de dispositivos repartidos por la red. Trabajo con su equipo de red para asegurarse de los dispositivos de red desde el usuario a internet se conservan y actualizados.     |
| VPN                                      | Ha sido bien documentado que los dispositivos VPN tradicionalmente no están diseñados para administrar cargas de trabajo de medios en tiempo real. Algunas configuraciones de VPN prohibirán el uso de UDP (que es el protocolo preferido para el audio) y sólo se basan en TCP. Considere la posibilidad de implementar una [solución de división túnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) para ayudar a reducir la VPN como el origen de mala calidad.        |
| Los clientes (Skype para la empresa sólo en línea) | Se sabe que los clientes más antiguos provocar problemas con los medios. Asegúrese de que los clientes se se revisen dentro de seis meses a partir de la versión. Sacar provecho de [MyAdvisor](https://aka.ms/myadvisor) para obtener instrucciones sobre el desarrollo de una estrategia de preparación de cliente e implementación de [Click-to-Run](https://technet.microsoft.com/library/jj219427.aspx).      |
| Dispositivos                                  | El uso de [optimizado dispositivos](https://partnersolutions.skypeforbusiness.com/solutionscatalog) puede ayudar a mejorar considerablemente la experiencia del usuario. Con todos los componentes iguales, los dispositivos optimizados están diseñados para maximizar la experiencia del usuario con los equipos y Skype para la empresa y producir una calidad superior. Sacar provecho de [MyAdvisor](https://aka.ms/myadvisor) para obtener instrucciones sobre el desarrollo de una estrategia de preparación del dispositivo.   |


### <a name="investigate-tcp-audio-sessions"></a>Investigar las sesiones de audio TCP

TCP se considera un transporte de la conmutación por recuperación y no el transporte principal que desee para multimedia en tiempo real. La razón es un transporte de la conmutación por recuperación es debido a la naturaleza con estado de TCP. Por ejemplo, si se realiza una llamada en una red latente y tienen un retraso de los paquetes multimedia, a continuación, los paquetes desde hace unos segundos, que ya no son útiles: compiten por el ancho de banda llegar al receptor, que puede hacer que un peor situación incorrecta. Esto hace que el punto de muestra de audio y el audio estiramiento, resultante en audibles artefactos a menudo en forma de vibración.

Los informes de esta sección no realiza una distinción entre llamadas buenas y mala. Dado que UDP es preferido, busque los informes para el uso de TCP para el audio. Esto se debe principalmente por las reglas de firewall incompleta. Para obtener más información acerca de las reglas de firewall para los equipos y Skype para profesionales en línea, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips).

> [!IMPORTANT]
> Tener un válido de [crear el archivo](#building-mapping) cargado se recomienda para poder distinguir rápidamente dentro de secuencias de audio externas cuando se examina el uso TCP. 


#### <a name="audio-streams-with-tcp-usage-overall"></a>Secuencias de audio con un uso TCP general

Este informe indica el uso general de TCP para el audio a través de los últimos siete meses, tal y como se muestra a continuación.

Todos los otros informes en esta sección se centrarán en restringir hacia abajo los edificios específicos y subredes donde TCP se usa con más frecuencia. Más subinformes desglosar el uso TCP en las conferencias y llamadas de dos participantes.

![Captura de pantalla de un gráfico que muestra el número de secuencias de audio de TCP por mes](media/quality-of-experience-review-guide-image23.png)

_La figura 23 – secuencias de Audio con un uso de TCP_

##### <a name="investigation"></a>Investigación

Este informe de gráfico muestra el uso TCP general de la organización. Mediante el uso de este informe, puede responder a las siguientes preguntas:

1.  ¿Qué es el volumen total de llamadas TCP para el mes actual?

2.  ¿Es mejor que el mes anterior o peor?

3.  ¿La tendencia de uso TCP aumenta, steady, o disminuye?

Si observa que está aumentando la tendencia de uso TCP, o por encima de uso mensual normal, tómese el tiempo para investigar mediante el uso de los subinformes para buscar cualquier edificios o redes que podrían necesitar corrección. Idealmente, desea que tan solo sesiones de audio basados en TCP como sea posible en la red administrada.

#### <a name="tcp-vs-udp"></a>TCP y UDP

Este informe de tabla identifica el volumen de TCP en lugar de en el mes más reciente para las conferencias de audio, vídeo y vídeo-based pantalla (VBSS) de uso compartido de informes de uso UDP.

![Informe que muestra el volumen de TCP frente a las secuencias de conferencia UDP, con la que se muestra para la comparación PCR](media/quality-of-experience-review-guide-image24.png)

_En la figura 24 – TCP y UDP - conferencia_

##### <a name="analysis"></a>Análisis

Aunque desea que el uso TCP para ser lo más baja como sea posible, es posible que vea un bit de uso TCP en una implementación correcto en caso contrario. Para comparar UDP para el uso TCP, dividir secuencias de audio de TCP por secuencias de audio de UDP para determinar un porcentaje. Un valor más del 1 por ciento debe investigar con más detalle.

En el ejemplo anterior, que se tomen divididas por secuencias UDP 10,481 para llegar a un valor de porcentaje 17.2 1,806 secuencias TCP. Este valor está muy por encima de 1 por ciento y nos dice que necesitamos continuar la investigación para determinar dónde se está produciendo el uso TCP.

También se incluyen en el informe es el porcentaje de Audio deficiente. Esto le ofrece una vista en la comparación de calidad de las llamadas entre UDP y TCP para ayudar a ver cómo TCP está afectando a la calidad de llamada overcall.

Por lo que ahora que ha determinado que hay un uso elevado de audio basados en TCP en la organización, ¿qué hacer a continuación? Vaya a los informes de **secuencias TCP mediante la creación y la subred** para desglosar el uso TCP mediante la creación y subredes.

#### <a name="tcp-streams-by-building-and-subnet"></a>Secuencias TCP mediante la creación y la subred

En las plantillas proporcionadas CQD, vaya a las secuencias TCP por subred y creación de informes de tabla mediante el uso de los recursos administrados o plantilla de todas las redes. Existen tres informes que se incluye en la plantilla, uno para investigar la conferencia, con y sin información de retransmisión de Microsoft y uno para investigar las llamadas entre dos participantes. Con el fin de investigar el uso TCP, el proceso es el mismo, por lo que nos centraremos la discusión aquí en sólo la conferencia.

> [!IMPORTANT]
> Tener un válido de [crear el archivo](#building-mapping) cargado se recomienda para poder distinguir rápidamente dentro de secuencias de audio externas cuando se examina el uso TCP. 

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.                                  |

![Informe que se enumera las secuencias de TCP, organizadas por la creación, la red y la subred al mes.](media/quality-of-experience-review-guide-image25.png)

_La figura 25 – secuencias TCP mediante la generación de - y subred conferencia_

##### <a name="remediation"></a>Corrección

Este informe identifica los edificios específicos y subredes que contribuyen al volumen de uso TCP. También se incluye un informe de adicional para identificar la dirección IP de retransmisión de Microsoft que se usó en la llamada para ayudar a aislar las reglas de firewall que faltan. Centrar los esfuerzos de corrección en los edificios que tienen el mayor volumen de secuencias de audio para maximizar el impacto.

La causa más común de uso TCP falta reglas de excepción en los servidores de seguridad o servidores proxy. Vamos a ser hablando acerca de los servidores proxy en la siguiente sección, por lo que por ahora centrar los esfuerzos en los servidores de seguridad. Mediante la creación o subred proporcionado, puede determinar qué servidor de seguridad debe actualizarse.

_Tabla 10 - corrección * instrucciones para las secuencias de TCP mediante la creación y la subred_

| Corrección        | Orientación     |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuración del firewall | Compruebe [las direcciones y puertos IP de Office 365](https://aka.ms/o365ips) se excluyen desde el servidor de seguridad. Aunque hay muchas direcciones IP y los puertos que deben estar abiertos, para problemas relacionados con los medios TCP, centrar los esfuerzos de iniciales en lo siguiente: Compruebe las siguientes [subredes de medios](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) se encuentran en las reglas de firewall. Hacer referencia a la fila 4 en la tabla que se muestra para obtener información de subred de medios específico. [Puertos UDP 3478 – 3481](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Updated-IP-ranges-and-ports-for-Skype-for-Business-Online/ba-p/47470): estos puertos son los puertos de medios preferido y deben estar abiertos, de lo contrario se producirá un error del cliente al puerto TCP 443. |
| Comprobar             | Use la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para buscar problemas de conectividad a puertos y direcciones IP de Office 365 específico de la creación afectado o subred.    |

### <a name="investigate-http-proxy-usage"></a>Investigar el uso de proxy HTTP

Servidores proxy HTTP no son la ruta de acceso preferida para establecer sesiones de medios, para un gran número de razones. Muchos contienen características de inspección profunda del paquete que pueden impedir conexiones con el servicio se completen y se presentan las interrupciones. Además, los servidores proxy podrían forzar TCP en lugar de Permitir UDP, que se recomienda para la calidad de audio óptima.

Siempre es recomendación de Microsoft para configurar el cliente para conectarse directamente a los equipos y Skype para servicios de negocios. Esto es especialmente importante para el tráfico de medios.

> [!IMPORTANT]
> Tener un válido de [creación de archivo](#building-mapping) cargado facilita distinguir correctamente dentro de secuencias de audio externas al analizar el uso de proxy. 


#### <a name="audio-streams-with-http-proxy-usage-overall"></a>Secuencias de audio con un uso de proxy HTTP general

Este informe resume el uso de proxy a través del tiempo en una escala mensual. El informe de secuencia de proxy HTTP de esta sección de la plantilla es muy similar a los informes TCP. No tiene el aspecto en si las llamadas son una buena o mala, pero si la llamada se conecta a través de HTTP.

![Captura de pantalla de las secuencias de Audio con el informe de uso de Proxy HTTP en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image26.png)

_La figura 26 – secuencias de Audio con un uso de Proxy HTTP_

##### <a name="analysis"></a>Análisis

Si ve un gran volumen de uso HTTP, consulte a su equipo de red para asegurarse de que las exclusiones adecuadas se encuentran disponibles para que los clientes se enrutamiento directamente a los equipos o Skype para subredes de medios en línea de negocio. Idealmente, no debería haber ningún uso de HTTP que se muestra aquí.

Si tiene un solo proxy de internet de la organización, compruebe la correcta [las direcciones URL de Office 365 y las exclusiones de intervalo de direcciones IP](https://aka.ms/o365ips). Si más de un proxy de internet está configurado en su organización, aprovechar el HTTP subcaracterísticas informar a aislar qué edificio o subred se ve afectada.

Para las organizaciones que no se pueden omitir al servidor proxy, asegúrese de que la Skype para clientes empresariales está configurado para iniciar sesión correctamente cuando se encuentra detrás de un proxy tal como se describe en el artículo [Skype para la empresa debe usar servidor proxy para iniciar sesión en lugar de intentar directa conexión](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin).

#### <a name="http-proxy-streams-by-building-and-subnet"></a>Secuencias de proxy HTTP mediante la creación y la subred

Este informe identifica los edificios específicos y subredes que contribuyen al uso HTTP.

> [!IMPORTANT]
> Tener un válido de [creación de archivo](#building-mapping) cargado facilita distinguir correctamente dentro de secuencias de audio externas al analizar el uso de proxy.

> [!NOTE]
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.                        |

![Captura de pantalla del uso de Proxy HTTP por subred y creación de informes en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image27.png)

_Figura 27 – uso de Proxy HTTP mediante la generación y subred_

##### <a name="remediation"></a>Corrección

Centrar los esfuerzos de corrección en los edificios o subredes que tienen el uso de proxy HTTP. La causa más común de uso HTTP falta reglas de excepción en los servidores proxy. Mediante la creación o subred proporcionado, puede determinar qué servidor proxy debe actualizarse.

Compruebe que los necesarios [Y los FQDN de Office 365](https://aka.ms/o365ips) se excluyen de su proxy.

## <a name="endpoint-investigations"></a>Investigaciones de extremo

En esta sección se centra en las tareas de informes de Skype para versiones de cliente – específicos de su negocio y el uso de dispositivos certificados.

> [!NOTE]
> No todos los informes que se incluyen en las plantillas se tratan en esta guía. La descripción del informe individuales para obtener más información, consulte. 


### <a name="determine-client-versions"></a>Determinar las versiones de cliente

El informe en este espacio se centra en la identificación de Skype para las versiones de cliente de negocio en uso y su volumen relativa en el entorno.

> [!IMPORTANT]
> Actualmente, los clientes de los equipos están distribuidos y se actualizan automáticamente a través de la red de entrega de contenido (CDN) de Azure y se mantengan actualizados por el servicio. Preparación de cliente y las actividades de investigación no son aplicables a los equipos.

Números de versión de Skype para profesionales de 2015 y 2016 pueden encontrarse a través de los siguientes vínculos:

-   [Versiones de canal de actualización de cliente de Office 365](https://technet.microsoft.com/office/mt465751?f=255&MSPPError=-2147217396)

-   [Números de versión y de compilación de Office 365 ejecutar, haga clic en](https://support.office.com/article/Version-and-build-numbers-of-update-channel-releases-ae942449-1fca-4484-898b-a933ea23def7)

-   [Skype para la empresa, descargas y actualizaciones](https://technet.microsoft.com/office/dn788954.aspx)

> [!NOTE] 
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.  

> [!IMPORTANT]
> Informes de cliente requieren que se va a excluir datos participantes federados. Para excluir datos participantes federados, debe agregar un filtro de consulta para el **Segundo identificador de inquilino** establecida en el [identificador de inquilino](#tenant-id)de su organización. |

![Captura de pantalla del informe de cliente y dispositivos en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image28.png)

_En la figura 28 - informe de versiones de cliente_

#### <a name="remediation"></a>Corrección

Una parte fundamental de tiende a experiencias de usuario de alta calidad es asegurarse de que los clientes administrados están ejecutando versiones actualizadas de Skype para la empresa. Esto proporciona varios beneficios, entre ellos:

-   Es más fácil administrar versiones unas frente a número de versiones.

-   Proporciona un nivel de coherencia de la experiencia.

-   Resulta más fácil solucionar los problemas con la calidad de las llamadas y facilidad de uso.

-   Microsoft no otorga continuamente las optimizaciones y mejoras generales en todo el producto. Para que los usuarios reciban estas actualizaciones, reduce sus riesgos de ejecutar un problema que ya se ha resuelto.

Limitación de la implementación para las versiones de cliente que están menos de seis meses se mejorar la experiencia global del usuario y mejorar la manejabilidad en comparación con la necesidad de un gran número de las diferentes versiones del cliente en el mismo entorno.

Si utiliza sólo Office Click-to-Run, podrá automáticamente dentro de la ventana de seis meses. Se requiere ninguna acción adicional.

If, al igual que la mayoría de las organizaciones, tiene una mezcla de paquetes de Click-to-Run y installer (MSI), puede utilizar el informe para comprobar que se actualizan con regularidad los clientes MSI. Centrar los esfuerzos en esos clientes donde es el volumen por encima del promedio. Si observa que los clientes se están quedando anticuados, trabaje con el equipo responsable de administrar las actualizaciones de Office y asegurarse de que está aprobando y la implementación de revisiones de cliente con regularidad.

### <a name="devices-investigations"></a>Investigaciones de dispositivos

Para hacer uso de los siguientes informes de dispositivo, es mejor para comprender el concepto de la opinión Media puntuación (MOS). MOS es la medida estándar de oro para evaluar la calidad de audio detectada. Se representa como una clasificación de número entero de 0 a 5.

La base de todas las medidas de calidad de voz es cómo una persona percibe la calidad de voz. Debido a que se ve afectada por la percepción humana, es esencialmente subjetiva. Hay varias metodologías diferentes para probar subjetiva.
La mayoría de las medidas de calidad de voz se basan en una escala de clasificación (ACR) de la categorización absoluta.

En una prueba ACR subjetiva, un número estadísticamente significativo de personas valora la calidad de la experiencia en una escala del 1 (incorrecta) a 5 (excelente). El promedio de las puntuaciones es el MOS. El MOS resultante depende del intervalo de experiencias que se exponen para el grupo y el tipo de la experiencia que se clasificaron.

Debido a que no resulta práctico para realizar pruebas subjetivas de calidad de voz para un sistema de comunicación live, equipos y Skype para la empresa generan valores MOS mediante el uso de algoritmos avanzados para predecir objetiva de los resultados de una prueba subjetiva.

El conjunto disponible de MOS y métricas asociadas proporcionan una vista a la calidad de la experiencia de entregarse a los usuarios.

Al proporcionar a los usuarios con los dispositivos certificados para los equipos y Skype para la empresa, se reduce la probabilidad de que se produzcan experiencias negativas debido al propio dispositivo (que es más probable, por ejemplo, con micrófonos y altavoces portátil integrada). Para obtener más información, vea [teléfonos y dispositivos para Skype para la empresa](https://technet.microsoft.com/office/dn947482).

#### <a name="organizational-usage-of-capture-devices-microphones-by-volume"></a>Uso de dispositivos de captura (micrófonos) por volumen para la organización

Este informe se usa para evaluar el uso de micrófono por volumen y puntuación MOS y puede encontrarse en las plantillas que lo acompaña en los clientes y dispositivos *.*

> [!IMPORTANT]
> Dispositivo informes requieren que se va a excluir datos participantes federados. Para excluir datos participantes federados, debe agregar un filtro de consulta para el **Segundo identificador de inquilino** establecida en el [identificador de inquilino](#tenant-id)de su organización. 

> [!NOTE] 
> Asegúrese de ajustar el filtro año mes al mes actual. Seleccione **Editar**y ajustar **Mes año** para guardar el nuevo mes predeterminado.<br><br> Es posible que tenga en cuenta cuando la visualización de este informe que ve el mismo dispositivo registrada varias veces. Esto es debido a la forma en que el dispositivo se indica que se notifiquen al CQD. Las diferencias de hardware y configuración regional del SO notificar los datos del dispositivo de forma diferente.

![Captura de pantalla del informe de dispositivos (micrófono) en el panel de calidad de llamadas.](media/quality-of-experience-review-guide-image29.png)

_Figura 29 - – informe de dispositivos (micrófono)_

##### <a name="remediation"></a>Corrección

La primera tarea es determinar el destino MOS que le gustaría alcanzar. MOS puntuaciones comprendido entre 1 y 5, con 5 es la mejor. Elija un destino razonable en función de su entorno y los resultados de la consulta. En el siguiente ejemplo, el destino es una puntuación MOS de 3.6 o superior para todos los dispositivos que tienen más de 100 secuencias. Obtendrá la calidad de los dispositivos de destino cuando:

-   Los resultados de consulta de dispositivo devuelven MOS \> 3.6 para NumStreams \> 100

Normalmente, necesitará reemplazar dispositivos bajo rendimiento con los dispositivos de certificado. Se incluyen algunas consideraciones para la revisión del informe de dispositivo:

-   ¿Son las dispositivos certificados o conocidos para ser buena en su entorno? Si un dispositivo certificado o buena se devuelve en la consulta con una puntuación MOS inferior a la línea de base, puede haber otros factores desconocidos (por ejemplo, una red deficiente o baja potencia pc) que contribuye a la puntuación de baja.
    Se requerirá una investigación adicional.

-   Puede identificar a los usuarios de un dispositivo a través de [Análisis de llamadas](#call-analytics-training). Compruebe para asegurarse de que disponen de los controladores de dispositivo más recientes y que su dispositivo no está conectado a través de un concentrador USB.

-   Compruebe si hay una correlación entre los dispositivos defectuosos y creación de un sistema concreto y modelo. Si es así, el dispositivo podría ser incompatible o se necesitan actualizaciones de controlador.

La segunda tarea es determinar el uso general de dispositivos que no sean certificados. Se recomienda que al menos el 80% de todas las secuencias de audioconferencias usar un dispositivo certificado.
Esto se logra mejor por el informe de dispositivos a exportar a Excel y calcular manualmente el uso de dispositivos aprobados o certificados. Las organizaciones normalmente mantenga una lista de todos los dispositivos aprobados, para poder filtrar y ordenar los datos deben ser un proceso sencillo.

## <a name="appendix-a-lync-networking-guide"></a>Guía de redes del apéndice Lync r.

Para obtener más información sobre los equipos y Skype para conceptos de redes empresariales y la lógica tras su importancia a la calidad, la [Guía de redes de Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) sigue siendo aplicable.

## <a name="appendix-b-network-performance-requirements"></a>Requisitos de rendimiento de red B. apéndice

La calidad de medios en tiempo real (audio, vídeo y uso compartido de aplicaciones) a través de IP depende en gran medida la calidad de la conectividad de red de extremo a otro. Óptima equipos o Skype para calidad de los medios empresariales, de la red debe cumplir las siguientes métricas de rendimiento de red.

_Tabla 11 - requisitos de rendimiento de red_

| Métrica                           | Cliente a Microsoft Edge           | Perímetro de cliente a Microsoft Edge    |
|----------------------------------|------------------------------------|------------------------------------|
| Latencia (unidireccional)                | \<50 ms                            | \<30 ms                            |
| Latencia (RTT o tiempo de ida y vuelta) | \<100 ms                           | \<60 ms                            |
| Ráfagas de pérdida de paquetes                | \<10% durante un intervalo de 200 ms   | \<% 1 durante cualquier intervalo de 200 ms    |
| Pérdida de paquetes                      | \<% 1 durante cualquier intervalo de 15 segundos    | \<0,1% durante un intervalo de 15 segundos  |
| Vibración de llegada entre granjas de paquetes      | \<30 ms durante un intervalo de 15 segundos | \<15 ms durante un intervalo de 15 segundos |
| Reaprovisionamiento de paquetes                   | \<paquetes de salida de orden 0,05%       | \<paquetes de salida de orden 0,01%      |

Para obtener más información, vea el artículo siguiente acerca del [rendimiento de red y de calidad de medios](https://aka.ms/performancerequirements) para los equipos y Skype para profesionales en línea.

<a name="other-resources"></a>

## <a name="appendix-c-other-resources"></a>Apéndice C. Otros recursos

### <a name="building-data-file"></a>Archivo de datos de creación

-   [Activar y usar CQD en Skype para profesionales en línea](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)

<a name="CQD-training"></a>

### <a name="cqd-training"></a>Formación de CQD

-   <https://aka.ms/sof-cqd>

-   Guía de [Introducción a CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) y taller.

-   [Guía en línea CQD dimensiones y medidas](https://support.office.com/article/Dimensions-and-measures-available-in-Call-Quality-Dashboard-in-Skype-for-Business-Online-e97aeeee-9e43-416f-b433-9cdd63d8874b)

### <a name="call-analytics-training"></a>Aprendizaje de análisis de llamada

-   [Introducción a la llamada de análisis](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar el análisis de llamadas de Skype Empresarial](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-FBF7247A-84AE-46CC-9204-2C45B1C734CD)

-   [Diferencia entre el análisis de llamadas y el Panel de calidad de llamadas](https://support.office.com/article/What-s-the-difference-between-Call-Analytics-and-Call-Quality-Dashboard-4CD5FE35-8463-4996-A252-086CD3CA2D9A)

-   [Usar el análisis de llamadas para solucionar problemas de mala calidad de llamada en Skype Empresarial](https://support.office.com/article/Use-Call-Analytics-to-troubleshoot-poor-Skype-for-Business-call-quality-66945036-ae87-4c08-a0bb-984e50d6b009)

### <a name="call-analytics-support"></a>Soporte de análisis de llamada

-   [Skype para el programa de vista previa de negocio](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram) de la Comunidad:

-   Para obtener soporte técnico, inicie sesión en nuestro [www.skypepreview.com](http://www.skypepreview.com)de vista previa del portal, seleccione **informe de un problema**y usar la opción **Crear nuevo error** para notificar un problema. Tenga en cuenta que los ingenieros de soporte técnico están disponibles para proporcionar compatibilidad con del lunes al viernes, entre las horas de 6 AM a 9 P.M. EST. Las solicitudes fuera de las horas se va a evaluar el día siguiente.

### <a name="devices"></a>Dispositivos

-   [Skype para soluciones empresariales de catálogo periféricos personales y PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Creación de informes de inquilinos

-   [Paquete de contenido de adopción de Office 365](https://blogs.office.com/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Creación de informes en Skype Empresarial Online](https://support.office.com/article/Skype-for-Business-Online-reporting-4935cddf-fafa-442d-91a3-246af01f8373)

-   [Teams Microsoft reporting](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)

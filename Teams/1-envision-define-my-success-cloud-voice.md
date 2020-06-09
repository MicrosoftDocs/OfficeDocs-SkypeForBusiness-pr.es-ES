---
title: Audioconferencia, planes de llamadas o enrutamiento directo
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Definir el éxito de la implementación de audioconferencias, sistemas telefónicos con planes de llamadas o enrutamiento directo de sistema telefónico para su organización.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 94430052082d523861ed4a938e0e0b02b70049f9
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610989"
---
# <a name="define-my-success"></a>Definir mi éxito

Este artículo proporciona una descripción general de los requisitos para definir el éxito en la implementación de audioconferencias, sistemas telefónicos con planes de llamadas o enrutamiento directo de sistema telefónico para su organización. Si define correctamente qué es el éxito, puede medir los resultados a medida que avanza en la implementación y verificar que los resultados que obtiene son los que desea.

<!--ENDOFSECTION-->

La **audioconferencia** proporciona a las organizaciones puntos de entrada adicionales a cualquier reunión (ad hoc o programada) al permitir que los participantes de la reunión se unan a través de una red de telefonía pública conmutada (RTC) mediante llamadas a teléfonos fijos tradicionales, centrales de conmutación (PBX) o móviles. Esto es útil cuando el organizador o los participantes no están delante de un equipo. o cuando las conexiones de datos no están disponibles o son demasiado inconfiables para admitir las comunicaciones de voz, como en un área remota con cobertura de datos de Spotty Mobile, o conectados a un servicio de Wi-Fi público gratuito con un ancho de banda limitado o cuando los participantes de la reunión prefieren llamar a la reunión con un punto de conexión de telefonía que sea fácil de usar.

El **sistema telefónico con los planes de llamadas ("planes de llamadas")** ofrece a las organizaciones una forma de modernizar su lugar de trabajo al permitir que los usuarios hagan llamadas telefónicas relacionadas con el negocio desde sus equipos y dispositivos móviles. El proceso de actualización de un lugar de trabajo puede formar parte de varios escenarios: una implementación de trabajo basada en actividades, una importante mudanza de Office, una actualización de la oficina, la retirada de una solución PBX heredada, la conclusión de un contrato de proveedor de servicios RTC, etc. Con los planes de llamadas, Microsoft facilita la conectividad a la RTC.

El **enrutamiento directo de sistema telefónico ("enrutamiento directo")** ofrece a las organizaciones los mismos beneficios mencionados anteriormente para los planes de llamadas, excepto que un proveedor de terceros, en lugar de Microsoft, les facilite la conectividad con RTC. Esto permite la implementación en países en los que los planes de llamadas no están disponibles, o en implementaciones en las que es necesario mantener un contrato de proveedor de servicios RTC existente o la interoperabilidad con ciertos sistemas locales. Un escenario adicional para considerar el enrutamiento directo es la interoperabilidad del sistema de telefonía. Mientras se están pasando los usuarios a las llamadas en Teams, es posible que algunos usuarios permanezcan en sistemas PBX heredados. El enrutamiento directo permite que los dos casos de uso coexistan. El tráfico de llamadas entre los usuarios de sistemas heredados y de equipos se mantiene dentro de la organización.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definir casos de uso empresarial para conferencias de audio, planes de llamadas o enrutamiento directo

Para empezar, los participantes principales del proyecto necesitan definir casos de uso empresarial que admitan la implementación de audioconferencias, planes de llamadas o enrutamiento directo.

Los casos de uso empresarial están diseñados para definir y documentar resultados de negocios previstos y medibles, e incluyen lo siguiente:

-   Descripción del proceso de negocio actual

-   Desafíos con el proceso empresarial existente

-   De qué manera la tecnología puede ayudar a alcanzar estos retos.

-   Los resultados empresariales que se esperan y que se pueden medir si se superan los retos.

> [!TIP]
> Este es un ejemplo de un caso de uso empresarial completo para audioconferencia:
> 
> |         |
> |---------|
> |**Descripción del proceso de negocio actual**<br>Contoso utiliza en estos momentos los servicios de Conferencia RTC que ofrece el proveedor de telefonía local que le corresponde y que se cobran por minutos de reunión en reuniones internas y reuniones en las que participan usuarios externos.|
> |**Retos que se deben conseguir con el proceso de negocio actual definido**<br>Contoso gasta aproximadamente USD1 millones por año para el servicio actual de conferencias RTC, con un 75% del costo de las reuniones internas. El uso de puntos de conexión de telefonía tradicionales para unirse a las reuniones hospedadas por el servicio de conferencias RTC no se alinea con el plan para que la organización adopte equipos como plataforma de comunicaciones y colaboración moderna.|
> |**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>Con la adopción de Microsoft Teams como plataforma moderna de comunicaciones y colaboración, se espera que los usuarios internos se unan principalmente a las reuniones mediante equipos equipados con auriculares con micrófono y dispositivos de sala de reuniones optimizados. El servicio de audioconferencia estará disponible para admitir participantes externos o para admitir situaciones en las que el uso de audio de PC no sea favorable para los participantes internos.|
> |**Propósitos y medición de los resultados de negocio**<br>El cambio a los equipos como plataforma moderna de comunicaciones y colaboración, combinado con el servicio de audioconferencia, reducirá enormemente el coste de entrega del servicio de conferencias RTC.|

<br>

> [!TIP]
> Este es un ejemplo de un caso de uso empresarial completo para planes de llamadas:
> 
> |         |
> |---------|
> |**Descripción del proceso de negocio actual**<br>La configuración estándar de las áreas de trabajo de Office de Contoso incluye un teléfono de escritorio para cada escritorio. A cada empleado se le ha otorgado un número de teléfono de marcación directa. Los teléfonos de escritorio se conectan a un sistema PBX y se conectan a la RTC a través de un tronco de protocolo de inicio de sesión (SIP). Los empleados solo pueden hacer y recibir llamadas telefónicas a sus teléfonos de escritorio asignados.|
> |**Retos que se deben conseguir con el proceso de negocio actual definido**<br>El análisis de uso de los teléfonos de escritorio muestra que solo el 10% de los teléfonos de escritorio se usan activamente, con el resto configurado para desviar llamadas a teléfonos móviles o para llamar simultáneamente a teléfonos móviles. Mantener el sistema PBX existente y los teléfonos de escritorio asociados contribuye al 20% del costo mensual de los servicios de telefonía de contoso.|
> |**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>Los planes de llamadas permitirán que el equipo de un usuario reciba y realice llamadas telefónicas a través de la red de datos mediante la aplicación nativa Microsoft Teams. Esto elimina la necesidad de implementar y mantener los teléfonos de escritorio, y abre la oportunidad de dar de baja el sistema PBX existente, porque el servicio telefónico se puede enviar a través de la red sin dependencia en un sistema telefónico tradicional.|
> |**Propósitos y medición de los resultados de negocio**<br>La eliminación de los requisitos de mantenimiento y la retirada de los teléfonos PBX y de escritorio heredados ofrecerán una reducción del 20% en los gastos mensuales de servicio de telefonía. Los planes de llamadas simplificarán las áreas de trabajo de Office, lo que permite a contoso expandir sus operaciones mediante el establecimiento de nuevas oficinas con gastos de telefonía iniciales mínimos.|

<br>

> [!TIP]
> Este es un ejemplo de un caso de uso empresarial completado para el enrutamiento directo:
> 
> |         |
> |---------|
> |**Descripción del proceso de negocio actual**<br>La configuración estándar de las áreas de trabajo de Office de Contoso incluye un teléfono de escritorio para cada escritorio. A cada empleado se le ha otorgado un número de teléfono de marcación directa. Los teléfonos de escritorio se conectan a un sistema PBX y se conectan a la RTC a través de un tronco de protocolo de inicio de sesión (SIP). Los empleados solo pueden hacer y recibir llamadas telefónicas a sus teléfonos de escritorio asignados.|
> |**Retos que se deben conseguir con el proceso de negocio actual definido**<br>El análisis de uso de los teléfonos de escritorio muestra que solo el 10% de los teléfonos de escritorio se usan activamente, con el resto configurado para desviar llamadas a teléfonos móviles o para llamar simultáneamente a teléfonos móviles. Mantener el sistema PBX existente y los teléfonos de escritorio asociados contribuye al 20% del costo mensual de los servicios de telefonía de contoso.|
> |**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>El contrato de proveedor de troncales SIP ha sido firmado recientemente y estará vigente durante tres años. El enrutamiento directo permite que el proveedor de troncal de SIP proporcione la conectividad RTC y también permite que el equipo personal de un usuario reciba y realice llamadas telefónicas a través de la red de datos mediante la aplicación nativa Microsoft Teams. Esto elimina la necesidad de implementar y mantener los teléfonos de escritorio, y abre la oportunidad de retirar el sistema PBX existente, manteniendo al mismo tiempo una superficie de controlador de borde de sesión (SBC) local limitada.|
> |**Propósitos y medición de los resultados de negocio**<br>La eliminación de los requisitos de mantenimiento y la retirada de los teléfonos PBX y de escritorio heredados ofrecerán una reducción del 20% en los gastos mensuales de servicio de telefonía. El enrutamiento directo simplifica las áreas de trabajo de Office, lo que permite a contoso expandir sus operaciones mediante el establecimiento de nuevas oficinas con gastos de telefonía iniciales mínimos.|

Además de definir los casos de uso de la empresa, para establecer los límites del proyecto, debe tener en cuentan la claridad:

-   **Ámbito organizativo:** La implementación de audioconferencias, planes de llamadas o enrutamiento directo puede abarcar a toda la organización o solo a unidades de negocio específicas.

-   **Escala de tiempo del proyecto:** La escala de tiempo específica que se ejecutará en el proyecto.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Puntos de decisión|<ul><li>¿Cuáles son todos los casos de uso empresarial de las conferencias de audio que puede identificar en su organización?</li><li>¿Cuáles son todos los casos de uso empresarial para planes de llamadas que puede identificar en su organización?</li><li>¿Cuáles son todos los casos de uso empresarial para el enrutamiento directo que puede identificar en su organización?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente todos los casos de uso empresarial de las conferencias de audio de su organización.</li><li>Documente todos los casos de uso empresarial de los planes de llamadas de su organización.</li><li>Documente todos los casos de uso empresarial para el enrutamiento directo de su organización.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificar las partes interesadas clave

Los casos de uso empresarial definidos en el paso anterior incluyen un ámbito organizativo para la Conferencia de audio, los planes de llamadas o la implementación de enrutamiento directo. En función de eso, puede completar la matriz completa de los participantes para incluir a las personas adecuadas para que participen en el proyecto.

> [!TIP]
> A continuación se muestra un ejemplo de plantilla de matriz de participantes que puede usar para documentar los participantes del proyecto:
> 
> |Rol  |Descripción  |Nombre, información de contacto, ubicación  |
> |---------|---------|---------|
> |Patrocinador ejecutivo de proyecto|<ul><li>Tome las máximas autoridades y responsabilidad para el proyecto y la entrega en los objetivos del proyecto.</li><li>Ayudar a resolver los problemas que ha remitido el jefe de proyecto.</li><li>Patrocinar la comunicación dentro de la empresa sobre los objetivos del proyecto.</li><li>Tomar decisiones clave.</li><li>Garantizar la disponibilidad de los recursos requeridos y el presupuesto.</li><li>Opiniones trimestrales de negocios de Lead (QBRs).</li><li>Impulsar la compra y el soporte técnico de los esfuerzos de la campaña de sensibilización.</li><li>Servir como el patrocinador del proyecto para el lanzamiento del programa.</li></ul>|Por añadir|
> |Responsable de proyecto|<ul><li>Administrar y dirigir al equipo del proyecto.</li><li>Coordine socios y los equipos de trabajo que participan en el proyecto.</li><li>Sea responsable de crear y administrar planes de proyecto para cumplir con los resultados de los meses.</li><li>Resolver problemas de funciones cruzadas.</li><li>Proporcionar actualizaciones periódicas a los patrocinadores del proyecto.</li><li>Incorporar los aspectos de la adopción en el plan del proyecto completo.</li><li>Lidera las revisiones empresariales y operativas mensuales (MBRs), contribuya a QBRs.</li></ul>|Por añadir|
> |Arquitecto/responsable de colaboración|<ul><li>Ejecutarse en la estrategia de colaboración definida por los ejecutivos de la empresa.</li><li>Analizar y elegir los productos de colaboración que cumplen los objetivos empresariales de la empresa.</li><li>Operaciones de diseño para productos de colaboración.</li><li>Definir modelos de funcionamiento y soporte técnico.</li><li>Contribuye a las revisiones mensuales y trimestrales de la empresa.</li></ul>|Por añadir|
> |Consultor|<ul><li>Ser responsable de los servicios de configuración</li><li>Contribuir a la arquitectura general de la solución.</li></ul>|Por añadir|
> |Jefe de proyecto|<ul><li>Desarrollar y mantener el plan del proyecto.</li><li>Administrar las entregas del proyecto en línea con el plan y el presupuesto del proyecto.</li><li>Grabe y administre problemas del proyecto, incluidas las escalaciones.</li><li>Realiza llamadas standup semanales.</li><li>Establecer un dedo y proporcionar actualizaciones a los patrocinadores ejecutivos de Project.</li><li>Trabaje con el arquitecto para definir el enfoque de la administración de cambios y los planes de comunicación.</li></ul>|Por añadir|
> |Especialista en adopción/administración de cambios|<ul><li>Proporcionar información durante la fase de descubrimiento en los procesos de adopción y formación.</li><li>Participar en el taller de estrategia de adopción.</li><li>Desarrollar y asumir la responsabilidad de la estrategia de adopción.</li><li>Desarrollar y ejecutar el plan de comunicación.</li><li>Proporcionar formación a los usuarios.</li><li>Recopilar comentarios y realizar encuestas.</li></ul>|Por añadir|
> |Responsable de redes|<ul><li>Proporcionar información durante la fase de descubrimiento en el diseño de red.</li><li>Participar en la planificación durante el taller de fase de previsión.</li><li>Coordine el trabajo del equipo de redes durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable de seguridad|<ul><li>Proporcionar información durante la fase de descubrimiento en el diseño y los procesos de seguridad.</li><li>Participar en la planificación durante el taller de fase de previsión.</li><li>Coordine el trabajo del equipo de seguridad durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable de telefonía|<ul><li>Proporcionar información durante la fase de descubrimiento en el diseño de telefonía.</li><li>Participar en la planificación durante el taller de fase de previsión.</li><li>Coordine el trabajo del equipo de telefonía durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable de escritorio|<ul><li>Proporcionar información durante la fase de descubrimiento en los clientes y en el proceso de actualización.</li><li>Participar en la planificación durante el taller de enVision.</li><li>Coordine el trabajo del equipo de escritorio durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable del servicio de asistencia y soporte técnico|<ul><li>Proporcionar información durante la fase de descubrimiento en modelos operativos y de soporte técnico.</li><li>Participar en la planificación durante el taller de fase de previsión.</li><li>Participar en la planeación de modelos de soporte.</li><li>Coordine el trabajo de los equipos de soporte técnico y los recursos durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Representantes de la unidad de negocio|<ul><li>Participe en materiales y guías de adopción de usuarios.</li><li>Contribuya y revise los casos de uso de la empresa.</li></ul>|Por añadir|
> |Responsable de implementación|<ul><li>Asegúrese de que se cumplan los requisitos previos de implementación.</li><li>Contrata recursos para que participen en las actividades de la fase integrada.</li><li>Participe en reuniones para revisar y preparar informes sobre el estado de implementación.</li></ul>|Por añadir|
> |Administradores de TI|<ul><li>Ayuda para la planificación y ejecución de pruebas. Esta función es para los profesionales de ti.</li></ul>|Por añadir|
> |Propietario del servicio|<ul><li>Responsabilizarse del funcionamiento de las conferencias de audio, planes de llamadas o servicio de enrutamiento directo.</li><li>Es el propietario de las audioconferencias, los planes de llamadas o el servicio de enrutamiento directo.</li></ul>|Por añadir|
> |Expertos en calidad|<ul><li>Calidad de la unidad, confiabilidad y comentarios del usuario.</li><li>Identifique tendencias de calidad y corrija la corrección de los equipos respectivos.</li><li>Denunciar a través del Comité Directivo al liderazgo.</li><li>Informe sobre la calidad, la fiabilidad y la opinión del usuario mediante la tasa de mi llamada y la puntuación de la Promoter de red.</li></ul>|Por añadir|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Puntos de decisión|<ul><li>¿Quién rellenará cada rol de participante clave para su organización?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente todas las partes clave y comunique las responsabilidades y las expectativas de la función a cada persona asignada.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definir OKRs, KSIs y riesgos

Con los participantes ensamblados por el proyecto, puede traducir los casos de uso de la empresa, el ámbito de la organización y las escalas de tiempo del proyecto en objetivos y resultados clave (OKRs), y las medidas de éxito del proyecto se pueden definir como una lista de indicadores de éxito clave (KSIs).

La participación completa de las partes interesadas del proyecto en la definición de OKRs y KSIs es esencial para garantizar que sienten un sentido de propiedad y alinear estas medidas de éxito con los requisitos empresariales de la organización.

OKRs contienen los objetivos que estableció al principio del proyecto y define los resultados de las teclas medibles cada trimestre. Los resultados clave se revisan cada mes para realizar un seguimiento del estado del proyecto en general y, en función del progreso, ajustar los planes trimestrales según sea necesario.

> [!TIP]
> A continuación, se puede hacer referencia a los ejemplos de OKRs relevantes para una implementación de audioconferencia:
> <br>
> 
> **Visión: aumentar la productividad al maximizar las inversiones en Microsoft 365 u Office 365**
> 
> |Objetivos  |Resultados clave  |Tareas pendientes  |
> |---------|---------|---------|
> |Implementar Audioconferencia en Microsoft Teams al final del año fiscal 2018|T1 2018: implementar Audioconferencia en Microsoft Teams globalmente|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
> |Retirar globalmente el servicio de Conferencia RTC antiguo a mediados del año fiscal 2018|T2 2018: retirar globalmente el servicio de Conferencia RTC antiguo|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|

<br>

> [!TIP]
> A continuación, se puede hacer referencia a ejemplos de OKRs relacionados con la implementación de planes de llamada:
> <br>
> 
> **Visión: aumentar la productividad al maximizar las inversiones en Microsoft 365 u Office 365**
> 
> |Objetivos  |Resultados clave  |Tareas pendientes  |
> |---------|---------|---------|
> |Implementar planes de llamadas en sucursales europeas al final del año fiscal 2018|FY18Q3: implementar planes de llamadas en Office de Londres|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
> |Retirar la PBX heredada en la oficina de Londres al final del año fiscal 2018|FY18Q4: retirar PBX heredado en la oficina de Londres|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|
> 
> [!TIP]
> A continuación se puede consultar ejemplos de OKRs relevantes para una implementación de enrutamiento directo:
> <br>
> 
> **Visión: aumentar la productividad al maximizar las inversiones en Microsoft 365 u Office 365**
> 
> |Objetivos  |Resultados clave  |Tareas pendientes  |
> |---------|---------|---------|
> |Implementar el enrutamiento directo en sucursales de Canadá al final del año fiscal 2018|FY18Q3: implementar enrutamiento directo en Office de Toronto|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
> |Retirar la PBX heredada en la oficina de Toronto por el final del año fiscal 2018|FY18Q4: retirar PBX heredado en Office de Toronto|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|

<br>

KSIs Mida la calidad y el éxito de los resultados clave y complemente la naturaleza binaria de OKRs (alcanzado o no) detallando los resultados positivos y/o incorrectos.

Al definir KSIs, le recomendamos que use criterios "específicos, medibles, asignables, realistas, realistas y relacionados con el tiempo" (inteligente):

-   Específico: destinar un área específica para mejorar

-   Medible: cuantificar o, al menos, sugerir un indicador de progreso

-   Asignable: especificar quién lo hará

-   Realista: indicar qué resultados pueden lograrse de manera realista, dados los recursos disponibles

-   Relacionados con el tiempo: especificar Cuándo se pueden lograr los resultados

> [!TIP]
> A continuación se muestra un ejemplo de KSI relevantes para este proyecto:
> 
> |Tipo  |Cuestiones y criterios sobre el KSI  |Cómo se miden  |Criterios de éxito  |Medidos  |Responsable  |
> |---------|---------|---------|---------|---------|---------|
> |Uso/adopción|La calidad de las llamadas es igual o mejor que en la solución anterior|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de tecnología de la información|
> |Uso/adopción|El proceso de comunicación fue más sencillo gracias a Microsoft Teams|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de administración de cambios|
> |Uso/adopción|Los usuarios utilizan la solución activamente|Informes de Microsoft 365, panel de calidad de llamadas|El 80 % de los usuarios son usuarios activos diarios|Cada día|Equipo de administración de cambios|
> |Uso/calidad|El porcentaje de llamadas/conferencias de mala calidad debe ser mínimo|Panel de calidad de llamadas|Menos del 5 % de llamadas de mala calidad al mes|A diario|Equipo de tecnología de la información|
> |Uso/soporte|Sé cómo conseguir soporte técnico|Encuesta|El 90% de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de administración de cambios|
> |Uso/soporte|Estoy satisfecho con la calidad del soporte técnico|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras cada incidente|Equipo de tecnología de la información|
> |Financiero|Reducción de los minutos de conferencias antiguas|Sistema financiero|Cumplir el ROI definido|Basado en ROI|Equipo de administración de cambios|

Debe identificar los riesgos empresariales como parte de este ejercicio y definir un plan de mitigación para cada riesgo identificado. Esta información puede ser capturada en un registro de riesgos.

> [!TIP]
> El registro de riesgos se puede documentar como el ejemplo siguiente:
> 
> |Riesgo  |Probabilidad  |Impacto  |General  |Plan de mitigación  |
> |---------|---------|---------|---------|---------|
> |Con la próxima fusión se sumarán hasta 1000 personas|Alto|Alto|Alto|<ul><li>Para empresas combinadas, cree un OKR independiente que se aplique a sus propias fases del proyecto (enVision, onboard, valor de unidad).</li><li>No incluyas estas OKRs en OKRs existentes</li></ul>|
> |La portabilidad de los números de teléfono retrasará la finalización del proyecto.|Alto|Alto|Alto|<ul><li>Preparar toda la información necesaria para el número de teléfono que se traslada con antelación (registro de servicio al cliente, detalles de facturación, carta de autorización)</li><li>Ajustar la escala de tiempo del proyecto para dar cabida al tiempo de procesamiento de la ejecución de migración de números de teléfono</li><li>Se debe comunicar el uso de los nuevos números de conferencia de acceso telefónico local a los participantes externos.</li><li>Usar números de teléfono temporales con manipulación de identificación de llamadas</li></ul>|
> |Se ha planificado rediseñar las redes|Alta|Medio|Medio|<ul><li>Antes de implementar Teams como plataforma de comunicaciones y colaboración moderna, realice una evaluación de disponibilidad de red para los sitios en el ámbito del proyecto.</li></ul>|
> |Configuración de SBC|Alto|Alto|Alto|<ul><li>Antes de implementar Teams como reemplazo para el sistema PBX existente, confirme que puede cumplir todos los requisitos de configuración de SBC</li><li>Confirmar que los recursos de soporte de SBC tienen el conjunto de aptitudes adecuado para configurar SBC para el enrutamiento directo</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Puntos de decisión|<ul><li>¿Qué es su organización&#39;OKRs y KSIs?</li><li>¿Cuáles son los riesgos que identificó relevantes para la implementación de audioconferencia en su organización? ¿Cuáles son los planes de mitigación de los riesgos identificados?</li><li>¿Cuáles son los riesgos que identificó relevantes para la implementación de planes de llamadas en su organización? ¿Cuáles son los planes de mitigación de los riesgos identificados?</li><li>¿Qué riesgos identificó relevantes para la implementación de enrutamiento directo en su organización? ¿Cuáles son los planes de mitigación de los riesgos identificados?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente la OKRs y KSIs y establezca el registro de riesgos.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Establecer un Comité Directivo

Un Comité de dirección es un grupo de miembros clave y líderes de proyectos que se han recopilado para guiar un proyecto o programa hacia sus resultados empresariales definidos. El Comité Directivo no se responsabiliza directamente del *modo* en que se entrega el proyecto, sino más *lo que* el proyecto ofrece a la empresa.

Cada proyecto requiere un contrato y una visión acordados. Para ofrecer los resultados que desea del proyecto, la visión debe estar claramente definida y debe ser supervisada y mantenida. Esto se convierte en la responsabilidad del Comité de dirección: para impulsar las decisiones, aconsejar, proporcionar supervisión estratégica, para servir como defensores de la organización para las iniciativas del proyecto y, cuando sea necesario, quitar bloqueos.

Su organización debe considerar significativamente la formación del Comité de dirección. El Comité debe garantizar que el proyecto cumpla con los objetivos empresariales que ha definido para impulsar el cambio en toda la organización, reunirse periódicamente para discutir la pulso actual del proyecto y ayudar a desbloquear los obstáculos que se encuentren en el camino.

El Comité debe definir su charter para incluir algunos objetivos clave:

-   Mantenga una sólida alineación entre el equipo del proyecto y el Patrocinador Ejecutivo o el liderazgo ejecutivo.

-   Proporciona información sobre el estado del proyecto al Patrocinador Ejecutivo o al liderazgo ejecutivo.

-   Permita al Patrocinador Ejecutivo o al equipo de liderazgo ejecutivo proporcionar dirección e información en el proyecto y asegurarse de que se alinee con objetivos empresariales importantes, ajustando los planes de proyecto, los resultados clave de objetivos (OKRs) y otras actividades del proyecto.

El Comité Directivo reúne un intervalo de repetición durante todo el período de duración de un proyecto para garantizar la alineación entre el liderazgo organizacional y el equipo del proyecto. Esta reunión crítica garantiza que la dirección del proyecto tenga soporte técnico total y incorpora comentarios proporcionados por el liderazgo en el proyecto para impulsar el éxito. El Comité usa estas reuniones para obtener información sobre el estado del proyecto y para:

-   Acuerden resultados empresariales que se alineen con el caso empresarial y asegúrese de que el proyecto está conduciendo hacia el envío de estos resultados.

-   Comprobar y aprobar el proyecto para su precisión y cumplimiento con el caso empresarial.

-   Revise y verifique los cambios realizados en el caso empresarial que podrían afectar a cualquier resultado definido.

-   Tomar decisiones estratégicas en relación con la priorización de las entregas del proyecto y aprobar entregas provisionales.

-   Identifique, administre y reduzca las lagunas, riesgos y problemas en los que el Comité requiere más influencia.

-   Recopilar el apoyo del Patrocinador Ejecutivo o de un equipo ejecutivo de liderazgo para los problemas que requieren escalamiento, priorizar y resolver cualquier conflicto entre unidades empresariales de partes interesadas. 

-   Proporciona comentarios formales y recomendaciones para el liderazgo ejecutivo, el Comité Asesor del cambio u otras partes interesadas y empresariales, según sea el caso.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Puntos de decisión|<ul><li>Decidir si es necesario un Comité de dirección para su organización.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Identifique a los miembros del Comité de dirección.</li><li>Programar reuniones en el Comité.</li><li>Prepararse para las reuniones del Comité Director.</li><li>Celebrar reuniones del Comité de dirección.</li><li>Tomar medidas según la entrada de la reunión del Comité Directivo.</li></ul>|

Encontrará instrucciones detalladas adicionales sobre cómo manejar un Comité Directivo adecuado en la guía del [Comité Director](envision-steering-committee-complete-guide.md).

<!--ENDOFSECTION-->

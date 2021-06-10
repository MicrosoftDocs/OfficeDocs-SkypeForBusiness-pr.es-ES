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
description: Definir el éxito de la implementación de audioconferencias, Sistema telefónico con planes de llamadas o Sistema telefónico enrutamiento directo para su organización.
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

En este artículo se proporciona información general sobre los requisitos para definir el éxito de la implementación de audioconferencias, Sistema telefónico con planes de llamadas o Sistema telefónico enrutamiento directo para su organización. Al definir correctamente el aspecto del éxito, puede medir los resultados a medida que avanza en la implementación y comprobar que los resultados que obtiene son los que desea.

<!--ENDOFSECTION-->

 Las audioconferencias proporcionan a las organizaciones puntos de entrada adicionales a cualquier reunión (ad hoc o programada) al permitir que los participantes de la reunión se unan a través de la red telefónica conmutada (RTC) mediante llamadas telefónicas con teléfono fijo tradicional, centrales privadas (PBX) o teléfonos móviles. Esto es útil cuando el organizador o los participantes no están delante de un equipo, o cuando las conexiones de datos no están disponibles o son demasiado poco confiables para admitir las comunicaciones de voz, como en un área remota con cobertura de datos móviles impecable, o conectada a un servicio Wi-Fi público gratuito con ancho de banda limitado, o cuando los participantes de la reunión prefieren llamar a la reunión mediante un punto de conexión de telefonía fácilmente accesible para ellos.

Sistema telefónico planes de llamadas ("Planes de **llamadas")** ofrece a las organizaciones una forma de modernizar su lugar de trabajo al permitir a los usuarios realizar llamadas telefónicas relacionadas con la empresa desde sus equipos y dispositivos móviles. La modernización del lugar de trabajo puede formar parte de cualquier número de escenarios: una implementación de trabajo basada en actividades, un movimiento de oficina importante, una actualización de adaptación de la oficina, la retirada de una solución PBX heredada, la conclusión de un contrato de proveedor de servicios RTC, y así sucesivamente. Con planes de llamadas, Microsoft facilita la conectividad a la RTC.

Sistema telefónico enrutamiento directo **("Enrutamiento directo")** proporciona a las organizaciones las mismas ventajas enumeradas anteriormente para planes de llamadas, excepto que la conectividad RTC se facilita por un proveedor de terceros en lugar de Microsoft. Esto permite la implementación en países donde los planes de llamadas no están disponibles o en implementaciones en las que es necesario mantener un contrato de proveedor de servicios RTC existente o interoperabilidad con determinados sistemas locales. Un escenario adicional para considerar enrutamiento directo es la interoperabilidad del sistema de telefonía. Mientras los usuarios se están transición a Llamadas en Teams, es posible que algunos usuarios permanezcan en PBX heredados. Enrutamiento directo permite que ambos casos de uso coexistan. El tráfico de llamadas entre los usuarios de sistemas heredados Teams los usuarios permanecen dentro de la organización.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definir casos de uso empresarial para audioconferencias, planes de llamadas o enrutamiento directo

Para empezar, las partes interesadas principales del proyecto deben definir casos de uso empresarial que admitan la implementación de audioconferencias, planes de llamadas o enrutamiento directo.

Los casos de uso empresarial están diseñados para definir y documentar los resultados empresariales esperados y mensurables, e incluyen lo siguiente:

-   Descripción del proceso empresarial actual

-   Retos con el proceso empresarial existente

-   De qué manera la tecnología puede ayudar a alcanzar estos retos.

-   Los resultados empresariales que se esperan y que se pueden medir si se superan los retos.

> [!TIP]
> A continuación se muestra un ejemplo de un caso de uso empresarial completado para las audioconferencias:
> 
> |         |
> |---------|
> |**Descripción del proceso de negocio actual**<br>Contoso utiliza en estos momentos los servicios de Conferencia RTC que ofrece el proveedor de telefonía local que le corresponde y que se cobran por minutos de reunión en reuniones internas y reuniones en las que participan usuarios externos.|
> |**Retos que se deben conseguir con el proceso de negocio actual definido**<br>Contoso gasta aproximadamente un millón de usd al año para el servicio de conferencias RTC actual, con el 75 % del costo en que se incurre para las reuniones internas. El uso de puntos de conexión de telefonía tradicionales para unirse a las reuniones hospedadas por el servicio de conferencias RTC no está alineado con el plan para que la organización adopte Teams como una plataforma moderna de comunicaciones y colaboración.|
> |**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>Con la adopción de Microsoft Teams como una plataforma moderna de comunicaciones y colaboración, se espera que los usuarios internos se unan principalmente a las reuniones con sus equipos equipados con auriculares optimizados y dispositivos de salas de reuniones. El servicio de audioconferencia estará disponible para admitir participantes externos o para admitir situaciones en las que el uso del audio del equipo no sea favorable para los participantes internos.|
> |**Propósitos y medición de los resultados de negocio**<br>El paso a Teams como una plataforma moderna de comunicaciones y colaboración, combinada con el servicio de audioconferencia, reducirá en gran medida el costo de la entrega del servicio de conferencias RTC.|

<br>

> [!TIP]
> A continuación se muestra un ejemplo de un caso de uso empresarial completado para planes de llamadas:
> 
> |         |
> |---------|
> |**Descripción del proceso de negocio actual**<br>La configuración estándar de las áreas de trabajo de office de Contoso incluye un teléfono de escritorio para cada escritorio. A cada empleado se le ha concedido un número de teléfono de marcación directa (DID). Los teléfonos de escritorio están conectados a un sistema PBX y conectados a RTC a través de un tronco de protocolo de inicio de sesión (SIP). Los empleados solo pueden realizar y recibir llamadas telefónicas en sus teléfonos de escritorio asignados.|
> |**Retos que se deben conseguir con el proceso de negocio actual definido**<br>El análisis de uso de los teléfonos de escritorio muestra que solo el 10 % de los teléfonos de escritorio se usan activamente, mientras que el resto está configurado para reenviar llamadas a teléfonos móviles o para llamar simultáneamente a teléfonos móviles. Mantener el sistema PBX existente y los teléfonos de escritorio asociados contribuye al 20 % del costo mensual del servicio de telefonía de Contoso.|
> |**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>Los planes de llamadas permitirán al equipo personal de un usuario recibir y realizar llamadas telefónicas a través de la red de datos aprovechando la aplicación nativa Microsoft Teams usuario. Esto quita la necesidad de implementar y mantener teléfonos de escritorio y abre la oportunidad de retirar el sistema PBX existente, ya que el servicio telefónico se puede entregar a través de la nube a través de la red sin dependencia de un sistema telefónico tradicional.|
> |**Propósitos y medición de los resultados de negocio**<br>La eliminación de los requisitos de mantenimiento y la retirada de PBX y teléfonos de escritorio heredados permitirá una reducción del 20 % en los gastos mensuales del servicio de telefonía. Los planes de llamadas simplificarán los espacios de trabajo de office, lo que permite a Contoso expandir sus operaciones estableciendo nuevas oficinas con costos de telefonía inicial mínimos.|

<br>

> [!TIP]
> A continuación se muestra un ejemplo de un caso de uso empresarial completado para enrutamiento directo:
> 
> |         |
> |---------|
> |**Descripción del proceso de negocio actual**<br>La configuración estándar de las áreas de trabajo de office de Contoso incluye un teléfono de escritorio para cada escritorio. A cada empleado se le ha concedido un número de teléfono de marcación directa (DID). Los teléfonos de escritorio están conectados a un sistema PBX y conectados a RTC a través de un tronco de protocolo de inicio de sesión (SIP). Los empleados solo pueden realizar y recibir llamadas telefónicas en sus teléfonos de escritorio asignados.|
> |**Retos que se deben conseguir con el proceso de negocio actual definido**<br>El análisis de uso de los teléfonos de escritorio muestra que solo el 10 % de los teléfonos de escritorio se usan activamente, mientras que el resto está configurado para reenviar llamadas a teléfonos móviles o para llamar simultáneamente a teléfonos móviles. Mantener el sistema PBX existente y los teléfonos de escritorio asociados contribuye al 20 % del costo mensual del servicio de telefonía de Contoso.|
> |**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>El contrato de proveedor de troncos SIP se firmó recientemente y estará en su lugar durante tres años. Enrutamiento directo permite que el proveedor de troncos SIP pueda proporcionar conectividad RTC y también permitirá que el equipo personal de un usuario reciba y haga llamadas telefónicas a través de la red de datos aprovechando la aplicación nativa Microsoft Teams datos. Esto quita la necesidad de implementar y mantener los teléfonos de escritorio y abre la oportunidad de retirar el sistema PBX existente, al tiempo que se mantiene una huella limitada del controlador de borde de sesión local (SBC).|
> |**Propósitos y medición de los resultados de negocio**<br>La eliminación de los requisitos de mantenimiento y la retirada de PBX y teléfonos de escritorio heredados permitirá una reducción del 20 % en los gastos mensuales del servicio de telefonía. Enrutamiento directo simplificará los espacios de trabajo de office, lo que permite a Contoso expandir sus operaciones estableciendo nuevas oficinas con costos de telefonía inicial mínimos.|

Además de definir los casos de uso de su empresa, para establecer los límites del proyecto, debe apuntar a mejorar la claridad:

-   **Ámbito de la organización:** La implementación de audioconferencias, planes de llamadas o enrutamiento directo puede abarcar toda la organización o solo unidades de negocio específicas.

-   **Project escala de tiempo:** La escala de tiempo específica que se ejecutará el proyecto.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Puntos de decisión|<ul><li>¿Cuáles son todos los casos de uso empresarial para las audioconferencias que puede identificar en su organización?</li><li>¿Cuáles son todos los casos de uso empresarial para planes de llamadas que puede identificar en su organización?</li><li>¿Cuáles son todos los casos de uso empresarial para enrutamiento directo que puede identificar en su organización?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente todos los casos de uso empresarial para conferencias de audio para su organización.</li><li>Documente todos los casos de uso empresarial para planes de llamadas de su organización.</li><li>Documente todos los casos de uso empresarial para enrutamiento directo para su organización.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificar las partes interesadas clave

Los casos de uso empresarial definidos en el paso anterior incluyen un ámbito organizativo para la implementación de audioconferencias, planes de llamadas o enrutamiento directo. En función de eso, puede completar la matriz completa de partes interesadas para incluir a las personas correctas para participar en el proyecto.

> [!TIP]
> A continuación se muestra un ejemplo de plantilla de matriz de participantes que puede usar para documentar los participantes del proyecto:
> 
> |Rol  |Descripción  |Nombre, información de contacto, ubicación  |
> |---------|---------|---------|
> |Patrocinador ejecutivo de proyecto|<ul><li>Tome la máxima autoridad y responsabilidad para el proyecto y la entrega de los objetivos del proyecto.</li><li>Ayude a resolver los problemas que ha escalado el Project cliente potencial.</li><li>Comunicación de patrocinador dentro de la empresa sobre los objetivos del proyecto.</li><li>Tome decisiones estratégicas clave.</li><li>Asegúrese de la disponibilidad de los recursos y el presupuesto necesarios.</li><li>Liderar revisiones empresariales trimestrales (QBR).</li><li>Impulsar la compra y el soporte de los esfuerzos de campaña de concienciación.</li><li>Sirva como el Project patrocinador del lanzamiento del programa.</li></ul>|Por añadir|
> |Responsable de proyecto|<ul><li>Administrar y dirigir el equipo del proyecto.</li><li>Coordinar partners y equipos de trabajo implicados en el proyecto.</li><li>Sea responsable de la creación y administración de planes de proyecto para cumplir los resultados clave trimestrales.</li><li>Resolver problemas entre funciones.</li><li>Proporcione actualizaciones periódicas a los patrocinadores del proyecto.</li><li>Incorporar aspectos de adopción en el plan de proyecto integral.</li><li>Dirigir revisiones operativas y empresariales mensuales (MBR), contribuir a los QBR.</li></ul>|Por añadir|
> |Arquitecto/responsable de colaboración|<ul><li>Ejecutar en la estrategia de colaboración definida por los ejecutivos de la compañía.</li><li>Analice y elija productos de colaboración que cumplan los objetivos empresariales de la empresa.</li><li>Diseñar operaciones para productos de colaboración.</li><li>Definir modelos de operación y soporte técnico.</li><li>Contribuya a las revisiones empresariales mensuales y trimestrales.</li></ul>|Por añadir|
> |Consultor|<ul><li>Ser responsable de los servicios de configuración</li><li>Contribuya a la arquitectura general de la solución.</li></ul>|Por añadir|
> |Jefe de proyecto|<ul><li>Desarrollar y mantener el plan de proyecto.</li><li>Administre las entregas de proyectos en línea con el plan y el presupuesto del proyecto.</li><li>Registre y administre problemas del proyecto, incluidas las escalas.</li><li>Realizar llamadas de standup semanales.</li><li>Liaise with, and provide updates to, project executive sponsors.</li><li>Trabaje con el arquitecto para definir el enfoque de administración de cambios y los planes de comunicación.</li></ul>|Por añadir|
> |Especialista en adopción/administración de cambios|<ul><li>Proporcione información durante la fase de detección en procesos de adopción y aprendizaje.</li><li>Participar en el taller de estrategia de adopción.</li><li>Desarrollar y asumir la responsabilidad de la estrategia de adopción.</li><li>Desarrollar y ejecutar el plan de comunicación.</li><li>Ofrezca aprendizajes a los usuarios.</li><li>Recopilar comentarios y realizar encuestas.</li></ul>|Por añadir|
> |Responsable de redes|<ul><li>Proporcione información durante la fase de detección en el diseño de red.</li><li>Participe en la planificación durante el taller de fase de Envision.</li><li>Coordinar el trabajo del equipo de red durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable de seguridad|<ul><li>Proporcione información durante la fase de detección en el diseño y los procesos de seguridad.</li><li>Participe en la planificación durante el taller de fase de Envision.</li><li>Coordinar el trabajo del equipo de seguridad durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable de telefonía|<ul><li>Proporcione información durante la fase de detección en el diseño de telefonía.</li><li>Participe en la planificación durante el taller de fase de Envision.</li><li>Coordinar el trabajo del equipo de telefonía durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable de escritorio|<ul><li>Proporcione información durante la fase de detección en los clientes y el proceso de actualización.</li><li>Participe en la planificación durante el taller de Envision.</li><li>Coordinar el trabajo del equipo de escritorio durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable del servicio de asistencia y soporte técnico|<ul><li>Proporcione información durante la fase de detección en modelos operativos y de soporte técnico.</li><li>Participe en la planificación durante el taller de fase de Envision.</li><li>Participar en la planificación de modelos de soporte técnico.</li><li>Coordinar el trabajo de los equipos de soporte técnico y los recursos durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Representantes de la unidad de negocio|<ul><li>Contribuir a las guías y materiales de adopción basados en el usuario.</li><li>Contribuir y revisar casos de uso empresarial.</li></ul>|Por añadir|
> |Responsable de implementación|<ul><li>Asegúrese de que se cumplen los requisitos previos de implementación.</li><li>Involucrar recursos para participar en las actividades de la fase incorporación.</li><li>Participe en reuniones para revisar y preparar informes sobre el estado de la implementación.</li></ul>|Por añadir|
> |Administradores de TI|<ul><li>Ayude con la planificación y ejecución de pruebas. Este rol es para los profesionales de TI.</li></ul>|Por añadir|
> |Propietario del servicio|<ul><li>Sé responsable del funcionamiento del servicio de audioconferencia, planes de llamadas o enrutamiento directo, todo hacia arriba.</li><li>Es el propietario del servicio de audioconferencia, planes de llamadas o enrutamiento directo.</li></ul>|Por añadir|
> |Expertos en calidad|<ul><li>Unidades de calidad, confiabilidad y comentarios de los usuarios.</li><li>Identifique tendencias de calidad e impulse la corrección con los equipos correspondientes.</li><li>Informe a través del comité de dirección a los líderes.</li><li>Informe sobre la calidad, la confiabilidad y el sentimiento de los usuarios a través de Calificar mi llamada y Puntuación neta del patrocinador.</li></ul>|Por añadir|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Puntos de decisión|<ul><li>Quién ocupará cada rol clave de las partes interesadas de su organización?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente a todas las partes interesadas clave y comunique las responsabilidades y expectativas del rol a cada persona asignada.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definir okrs, KSIs y riesgos

Con las partes interesadas del proyecto reunidas, puede traducir los casos de uso empresarial, el ámbito organizativo y las escalas de tiempo del proyecto en objetivos y resultados clave (OKR), y las medidas de éxito del proyecto se pueden definir como una lista de indicadores clave de éxito (KSIs).

La participación total de las partes interesadas del proyecto en la definición de OKR y KSIs es esencial para garantizar que sientan una sensación de propiedad y alinear estas medidas de éxito a los requisitos empresariales de la organización.

Los OKR contienen los objetivos que estableció al principio del proyecto y define los resultados clave mensurables de forma trimestral. Revisa mensualmente los resultados clave para realizar un seguimiento del estado del proyecto general y, según el progreso, ajusta los planes trimestrales según sea necesario.

> [!TIP]
> A continuación se puede hacer referencia a ejemplos de OKR relevantes para una implementación de audioconferencia:
> <br>
> 
> **Visión: Aumentar la productividad maximizando Microsoft 365 o Office 365 inversiones**
> 
> |Objetivos  |Resultados clave  |Para hacer  |
> |---------|---------|---------|
> |Implementar Audioconferencia en Microsoft Teams al final del año fiscal 2018|T1 2018: implementar Audioconferencia en Microsoft Teams globalmente|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
> |Retirar globalmente el servicio de Conferencia RTC antiguo a mediados del año fiscal 2018|T2 2018: retirar globalmente el servicio de Conferencia RTC antiguo|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|

<br>

> [!TIP]
> A continuación se puede hacer referencia a ejemplos de OKR relevantes para una implementación de planes de llamadas:
> <br>
> 
> **Visión: Aumentar la productividad maximizando Microsoft 365 o Office 365 inversiones**
> 
> |Objetivos  |Resultados clave  |Para hacer  |
> |---------|---------|---------|
> |Implementar planes de llamadas en sucursales europeas al final del año fiscal 2018|FY18Q3: Implementar planes de llamadas en la oficina de Londres|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
> |Retirar PBX heredado en la oficina de Londres al final del año fiscal 2018|FY18Q4: Retirar PBX heredado en la oficina de Londres|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|
> 
> [!TIP]
> A continuación se puede hacer referencia a ejemplos de OKR relevantes para una implementación de enrutamiento directo:
> <br>
> 
> **Visión: Aumentar la productividad maximizando Microsoft 365 o Office 365 inversiones**
> 
> |Objetivos  |Resultados clave  |Para hacer  |
> |---------|---------|---------|
> |Implementar enrutamiento directo en sucursales canadienses al final del año fiscal 2018|FY18Q3: Implementar enrutamiento directo en la oficina de Toronto|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
> |Retirar PBX heredado en la oficina de Toronto al final del año fiscal 2018|FY18Q4: Retirar PBX heredado en la oficina de Toronto|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|

<br>

Los KSIs miden la calidad y el éxito de los resultados clave y complementan la naturaleza binaria de los OKR (alcanzados o no alcanzados) detallando los resultados buenos o malos.

Al definir las KSIs, le recomendamos que use criterios "específicos, mensurables, asignables, realistas y relacionados con el tiempo" (SMART):

-   Específico: dirigirse a un área específica para la mejora

-   Mensurables: cuantificar o al menos sugerir un indicador de progreso

-   Asignable: especificar quién lo hará

-   Realista: especificar qué resultados se pueden lograr de forma realista, dados los recursos disponibles

-   Relacionado con el tiempo: especificar cuándo se pueden lograr los resultados

> [!TIP]
> A continuación se muestra un ejemplo de KSI relevantes para este proyecto:
> 
> |Tipo  |Cuestiones y criterios sobre el KSI  |Cómo se miden  |Criterios de éxito  |Medidos  |Responsable  |
> |---------|---------|---------|---------|---------|---------|
> |Uso/adopción|La calidad de las llamadas es igual o mejor que en la solución anterior|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de tecnología de la información|
> |Uso/adopción|El proceso de comunicación fue más sencillo gracias a Microsoft Teams|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de administración de cambios|
> |Uso/adopción|Los usuarios utilizan la solución activamente|Microsoft 365, Panel de calidad de llamadas|El 80 % de los usuarios son usuarios activos diarios|A diario|Equipo de administración de cambios|
> |Uso/calidad|El porcentaje de llamadas/conferencias de mala calidad debe ser mínimo|Panel de calidad de llamadas|Menos del 5 % de llamadas de mala calidad al mes|A diario|Equipo de tecnología de la información|
> |Uso/soporte|Sé cómo conseguir soporte técnico|Encuesta|El 90% de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de administración de cambios|
> |Uso/soporte|Estoy satisfecho con la calidad del soporte técnico|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras cada incidente|Equipo de tecnología de la información|
> |Financiero|Reducción de los minutos de conferencias antiguas|Sistema financiero|Cumplir el ROI definido|Basado en ROI|Equipo de administración de cambios|

Debe identificar los riesgos empresariales como parte de este ejercicio y definir un plan de mitigación para cada riesgo identificado. Esta información se puede capturar en un registro de riesgos.

> [!TIP]
> El registro de riesgos se puede documentar como el ejemplo siguiente:
> 
> |Riesgo  |Probabilidad  |Impacto  |General  |Plan de mitigación  |
> |---------|---------|---------|---------|---------|
> |Con la próxima fusión se sumarán hasta 1000 personas|Alta|Alto|Alto|<ul><li>Para las empresas combinadas, cree un OKR independiente que se aplique a sus propias fases de proyecto (Envision, Onboard, Drive Value)</li><li>No incluya estos OKR en los OKR existentes</li></ul>|
> |La portabilidad de los números de teléfono retrasará la finalización del proyecto.|Alta|Alto|Alto|<ul><li>Preparar toda la información necesaria para admitir la porte de números de teléfono con antelación (registro de servicio al cliente, detalles de facturación, carta de autorización)</li><li>Ajustar la escala de tiempo del proyecto para dar cabida a la hora de entrega de la ejecución de porte de números de teléfono</li><li>Se debe comunicar el uso de los nuevos números de conferencia de acceso telefónico local a los participantes externos.</li><li>Usar números de teléfono temporales con la manipulación del identificador de llamadas</li></ul>|
> |Se ha planificado rediseñar las redes|Alta|Medio|Medio|<ul><li>Antes de implementar Teams como una plataforma moderna de comunicaciones y colaboración, realice una evaluación de preparación de red para los sitios en el ámbito del proyecto</li></ul>|
> |Configuración de SBC|Alto|Alto|Alto|<ul><li>Antes de implementar Teams como reemplazo del PBX existente, confirme que puede cumplir todos los requisitos de configuración de SBC</li><li>Confirmar que los recursos de soporte técnico de SBC tienen el conjunto de aptitudes adecuado para configurar SBC para enrutamiento directo</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Puntos de decisión|<ul><li>¿Cuáles son las&#39;de la organización y los KSIs?</li><li>¿Qué riesgos ha identificado relevantes para la implementación de audioconferencias en su organización? ¿Cuáles son los planes de mitigación para los riesgos identificados?</li><li>¿Qué riesgos ha identificado relevantes para la implementación de planes de llamadas en su organización? ¿Cuáles son los planes de mitigación para los riesgos identificados?</li><li>¿Qué riesgos ha identificado relevantes para la implementación de Enrutamiento directo en su organización? ¿Cuáles son los planes de mitigación para los riesgos identificados?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente los OKR y los KSIs y establezca el registro de riesgos.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Establecer un comité de dirección

Un comité de dirección es un grupo de gobierno de partes interesadas clave y jefes de proyecto que se han reunido para guiar un proyecto o programa hacia sus resultados empresariales definidos. El comité de dirección no es directamente responsable *de* cómo se entrega el proyecto, sino de lo que el proyecto entrega a la empresa. 

Cada proyecto requiere una visión y una carta acordadas. Para ofrecer los resultados que desee del proyecto, la visión debe estar claramente definida y debe supervisarse y mantenerse. Esto se convierte en responsabilidad del comité de dirección: impulsar decisiones, aconsejar, proporcionar supervisión estratégica, servir como defensores de la organización para las iniciativas del proyecto y, cuando sea necesario, quitar bloqueadores.

Su organización debe pensar de forma significativa en la formación del comité de dirección. El comité debe asegurarse de que el proyecto alcance los objetivos empresariales que ha definido para impulsar el cambio en toda la organización, reunirse periódicamente para discutir el pulso actual del proyecto y ayudar a desbloquear los obstáculos que se encuentren en el camino.

El comité debe definir su carta para incluir algunos objetivos clave:

-   Mantenga una alineación sólida entre el equipo del proyecto y el patrocinador ejecutivo o el liderazgo ejecutivo.

-   Proporcione información sobre el estado del proyecto al patrocinador ejecutivo o al liderazgo ejecutivo.

-   Permita que el patrocinador ejecutivo o el equipo de liderazgo ejecutivo proporcionen dirección e información al proyecto y asegúrese de que se alinea con los objetivos empresariales generales, ajustando los planes de proyecto, los resultados clave objetivo (OKR) y otras actividades del proyecto.

El comité de dirección se reúne en un intervalo periódico durante toda la vida de un proyecto para garantizar la alineación entre el liderazgo de la organización y el equipo del proyecto. Esta reunión crítica garantiza que la dirección del proyecto cuenta con el soporte completo de los líderes e incorpora los comentarios proporcionados por los líderes en el proyecto para impulsar el éxito. El comité usa estas reuniones para obtener información sobre el estado del proyecto y para:

-   Ponerse de acuerdo en los resultados empresariales que se alineen con el caso empresarial y para asegurarse de que el proyecto está impulsando la entrega de estos resultados.

-   Compruebe y apruebe el proyecto para comprobar la precisión y el cumplimiento del caso empresarial.

-   Revise y compruebe los cambios realizados en el caso de empresa que podrían afectar a los resultados definidos.

-   Tome decisiones estratégicas con respecto a la priorización de las entregas de proyectos y apruebe entregas provisionales.

-   Identifique, administre y mitigue las deficiencias, riesgos y problemas en los que se requiere una influencia adicional del comité.

-   Reúna el soporte del patrocinador ejecutivo o del equipo de liderazgo ejecutivo para los problemas que requieren escalamiento, priorizar y resolver cualquier conflicto entre las unidades de negocio de las partes interesadas. 

-   Proporcione comentarios y recomendaciones formales a los líderes ejecutivos, al consejo asesor de cambio u otras partes interesadas de negocios y DE.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Puntos de decisión|<ul><li>Decida si es necesario un comité de dirección para su organización.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Identifique a los miembros del comité de dirección.</li><li>Programar reuniones del comité de dirección.</li><li>Prepararse para las reuniones del comité de dirección.</li><li>Celebrar reuniones del comité de dirección.</li><li>Tome medidas basadas en la información de la reunión del comité de dirección.</li></ul>|

Encontrará instrucciones detalladas adicionales sobre cómo operar un comité de dirección adecuado en la [guía del comité de dirección.](envision-steering-committee-complete-guide.md)

<!--ENDOFSECTION-->

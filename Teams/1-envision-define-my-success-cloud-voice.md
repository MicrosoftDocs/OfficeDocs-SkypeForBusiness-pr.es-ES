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
description: Definir una implementación correcta de Audioconferencia, Sistema telefónico con planes de llamadas o Enrutamiento directo de sistema telefónico para su organización.
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

En este artículo se proporciona información general de los requisitos para definir correctamente la implementación de Audioconferencia, Sistema telefónico con planes de llamadas o Enrutamiento directo de sistema telefónico para su organización. Al definir correctamente el resultado obtenido, puede medir los resultados a medida que avanza en la implementación y comprobar que los resultados obtenidos son los deseados.

<!--ENDOFSECTION-->

**Audioconferencia** proporciona a las organizaciones puntos de entrada adicionales a las reuniones (ad hoc o programadas) al permitir que los participantes de la reunión se unan a través de la red telefónica conmutada (RTC) mediante marcado con teléfono fijo tradicional, central de conmutación (PBX) o teléfonos móviles. Esto es útil cuando el organizador o los participantes no están delante de un equipo, cuando las conexiones de datos no están disponibles o son demasiado poco confiables para admitir las comunicaciones de voz, como en un área remota con cobertura de datos móviles manchada o conectada a un servicio Wi-Fi público gratuito con ancho de banda limitado, o cuando los participantes de la reunión prefieren llamar a la reunión con un extremo de telefonía al que puedan acceder fácilmente.

**Sistema telefónico con planes de** llamadas ("Planes de llamadas") ofrece a las organizaciones una manera de modernizar su lugar de trabajo al permitir a los usuarios realizar llamadas telefónicas relacionadas con la empresa desde sus equipos y dispositivos móviles. La modernización del lugar de trabajo puede formar parte de cualquier número de escenarios: una implementación de trabajo basada en la actividad, un movimiento importante de la oficina, una actualización de ajuste de la oficina, la retirada de una solución PBX heredada, la conclusión de un contrato de un proveedor de servicios RTC, y así sucesivamente. Con los planes de llamadas, Microsoft facilita la conectividad con RTC.

El enrutamiento directo de sistema telefónico **("enrutamiento directo")** proporciona a las organizaciones las mismas ventajas enumeradas anteriormente para los planes de llamadas, con la excepción de que la conectividad con RTC la facilita un proveedor de terceros en lugar de Microsoft. Esto permite la implementación en países donde los planes de llamadas no están disponibles o en implementaciones donde es necesario mantener un contrato de proveedor de servicios RTC existente o interoperabilidad con determinados sistemas locales. Un escenario adicional para considerar el enrutamiento directo es la interoperabilidad del sistema de telefonía. Mientras los usuarios están en la transición a llamadas en Teams, es posible que algunos usuarios permanezcan en PBX heredados. El enrutamiento directo permite coexistir en ambos casos. El tráfico de llamadas entre los usuarios de sistemas heredados y los usuarios de Teams permanecen dentro de la organización.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definir casos de uso empresarial para Audioconferencia, Planes de llamadas o Enrutamiento directo

Para comenzar, los participantes principales del proyecto deben definir casos de uso empresarial que admitan la implementación de Audioconferencia, Planes de llamadas o Enrutamiento directo.

Los casos de uso empresarial están diseñados para definir y documentar los resultados empresariales esperados y mensurables, e incluyen lo siguiente:

-   Descripción del proceso empresarial actual

-   Retos con el proceso empresarial existente

-   De qué manera la tecnología puede ayudar a alcanzar estos retos.

-   Los resultados empresariales que se esperan y que se pueden medir si se superan los retos.

> [!TIP]
> El siguiente es un ejemplo de un caso de uso empresarial completo para Audioconferencia:
> 
> |         |
> |---------|
> |**Descripción del proceso de negocio actual**<br>Contoso utiliza en estos momentos los servicios de Conferencia RTC que ofrece el proveedor de telefonía local que le corresponde y que se cobran por minutos de reunión en reuniones internas y reuniones en las que participan usuarios externos.|
> |**Retos que se deben conseguir con el proceso de negocio actual definido**<br>Contoso gasta aproximadamente 1 millón de USD al año para el servicio de conferencias RTC actual, con el 75 % del costo en las reuniones internas. El uso de puntos de conexión de telefonía tradicionales para unirse a las reuniones hospedadas por el servicio de conferencias RTC no está alineado con el plan de la organización para adoptar Teams como una plataforma moderna de comunicaciones y colaboración.|
> |**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>Con la adopción de Microsoft Teams como plataforma moderna de comunicaciones y colaboración, se espera que los usuarios internos se unan principalmente a las reuniones con sus equipos equipados con auriculares optimizados y dispositivos para salas de reuniones. El servicio de Audioconferencia estará disponible para admitir participantes externos o para admitir situaciones en las que el uso del audio del PC no sea prefijo para los participantes internos.|
> |**Propósitos y medición de los resultados de negocio**<br>El cambio a Teams como una plataforma moderna de comunicaciones y colaboración, combinada con el servicio de Audioconferencia, reducirá en gran medida el coste de prestar el servicio de conferencias RTC.|

<br>

> [!TIP]
> A continuación se muestra un ejemplo de un caso de uso empresarial completo para planes de llamadas:
> 
> |         |
> |---------|
> |**Descripción del proceso de negocio actual**<br>La configuración estándar de las áreas de trabajo de Contoso incluye un teléfono de escritorio para cada escritorio. A cada empleado se le ha dado un número de teléfono de marcación directa (DID). Los teléfonos de escritorio están conectados a un sistema PBX y conectados a RTC a través de un tronco de protocolo de inicio de sesión (SIP). Los empleados solo pueden realizar y recibir llamadas telefónicas en los teléfonos de escritorio asignados.|
> |**Retos que se deben conseguir con el proceso de negocio actual definido**<br>El análisis de uso de los teléfonos de escritorio muestra que solo se usa activamente el 10 % de los teléfonos de escritorio y el resto está configurado para reenviar llamadas a teléfonos móviles o para llamar simultáneamente a teléfonos móviles. Mantener el sistema PBX existente y los teléfonos de escritorio asociados contribuye al 20 % del coste del servicio de telefonía mensual de Contoso.|
> |**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>Los planes de llamadas permitirán al equipo personal de un usuario recibir y realizar llamadas telefónicas a través de la red de datos aprovechando la aplicación nativa de Microsoft Teams. Esto elimina la necesidad de implementar y mantener los teléfonos de escritorio y abre la oportunidad de retirar el sistema PBX existente, ya que el servicio de teléfono se puede entregar a través de la nube a través de la red sin dependencia en un sistema telefónico tradicional.|
> |**Propósitos y medición de los resultados de negocio**<br>Quitar los requisitos de mantenimiento y retirar PBX heredados y los teléfonos de escritorio ofrece una reducción del 20 % en los gastos de servicio de telefonía mensuales. Los planes de llamadas simplificarán las áreas de trabajo de las oficinas, lo que permitirá a Contoso expandir sus operaciones estableciendo nuevas oficinas con unos costes de telefonía iniciales mínimos.|

<br>

> [!TIP]
> El siguiente es un ejemplo de un caso de uso empresarial completo para enrutamiento directo:
> 
> |         |
> |---------|
> |**Descripción del proceso de negocio actual**<br>La configuración estándar de las áreas de trabajo de Contoso incluye un teléfono de escritorio para cada escritorio. A cada empleado se le ha dado un número de teléfono de marcación directa (DID). Los teléfonos de escritorio están conectados a un sistema PBX y conectados a RTC a través de un tronco de protocolo de inicio de sesión (SIP). Los empleados solo pueden hacer y recibir llamadas telefónicas en los teléfonos de escritorio asignados.|
> |**Retos que se deben conseguir con el proceso de negocio actual definido**<br>El análisis de uso de los teléfonos de escritorio muestra que solo se usa activamente el 10 % de los teléfonos de escritorio, mientras que el resto está configurado para reenviar llamadas a teléfonos móviles o para llamar simultáneamente a teléfonos móviles. Mantener el sistema PBX existente y los teléfonos de escritorio asociados contribuye al 20 % del coste del servicio de telefonía mensual de Contoso.|
> |**De qué manera la tecnología puede ayudar a alcanzar estos retos**<br>The SIP trunk provider contract was recently signed and will be in place for three years. El enrutamiento directo permite que el proveedor de tronco SIP le dé conectividad RTC y también permitirá al equipo personal del usuario recibir y realizar llamadas telefónicas a través de la red de datos aprovechando la aplicación nativa de Microsoft Teams. Esto elimina la necesidad de implementar y mantener los teléfonos de escritorio y abre la oportunidad de retirar el sistema PBX existente, a la vez que se mantiene una superficie limitada del controlador de borde de sesión local (SBC).|
> |**Propósitos y medición de los resultados de negocio**<br>Quitar los requisitos de mantenimiento y retirar PBX heredados y los teléfonos de escritorio ofrece una reducción del 20 % en los gastos de servicio de telefonía mensuales. El enrutamiento directo simplificará las áreas de trabajo de las oficinas, lo que permitirá a Contoso expandir sus operaciones estableciendo nuevas oficinas con unos costes de telefonía iniciales mínimos.|

Además de definir los casos de uso de la empresa, el objetivo del objetivo es definir los límites del proyecto:

-   **Ámbito organizativo:** La implementación de Audioconferencia, Planes de llamadas o Enrutamiento directo puede abarcar toda la organización o solo unidades de negocio específicas.

-   **Escala de tiempo del proyecto:** La escala de tiempo específica en la que se ejecutará el proyecto.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Puntos de decisión|<ul><li>¿Cuáles son todos los casos de uso empresarial de Audioconferencia que puede identificar en su organización?</li><li>¿Cuáles son todos los casos de uso empresarial de los planes de llamadas que puede identificar en su organización?</li><li>¿Cuáles son todos los casos de uso empresarial de enrutamiento directo que puede identificar en su organización?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente todos los casos de uso empresarial de Audioconferencia para su organización.</li><li>Documente todos los casos de uso empresarial para planes de llamadas para su organización.</li><li>Documente todos los casos de uso empresarial de Enrutamiento directo para su organización.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificar las partes interesadas clave

Los casos de uso empresarial definidos en el paso anterior incluyen un ámbito organizativo para la implementación de Audioconferencia, Planes de llamadas o Enrutamiento directo. En función de esto, puede completar la matriz completa de las partes interesadas para incluir a las personas que deben participar en el proyecto.

> [!TIP]
> A continuación se muestra un ejemplo de plantilla de matriz de participantes que puede usar para documentar los participantes del proyecto:
> 
> |Rol  |Descripción  |Nombre, información de contacto, ubicación  |
> |---------|---------|---------|
> |Patrocinador ejecutivo de proyecto|<ul><li>Tome la autoridad y responsabilidad definitivas para el proyecto y la entrega sobre los objetivos del proyecto.</li><li>Ayude a resolver problemas escalados por el cliente potencial del proyecto.</li><li>Comunicación del patrocinador dentro de la compañía sobre los objetivos del proyecto.</li><li>Tomar decisiones estratégicas clave.</li><li>Asegúrese de la disponibilidad de los recursos y el presupuesto necesarios.</li><li>Liderar revisiones empresariales trimestrales (QBR).</li><li>Impulse la compra y el soporte de los esfuerzos de concienciación de la campaña.</li><li>Servir como patrocinador del proyecto para la implementación del programa.</li></ul>|Por añadir|
> |Responsable de proyecto|<ul><li>Administrar y dirigir el equipo del proyecto.</li><li>Coordine socios y equipos de trabajo involucrados en el proyecto.</li><li>Sea responsable de crear y administrar planes de proyecto para cumplir con los resultados clave trimestrales.</li><li>Resolver problemas de funciones cruzadas.</li><li>Proporcione actualizaciones periódicas para los patrocinadores del proyecto.</li><li>Incorporar los aspectos de adopción en el plan integral del proyecto.</li><li>Lead monthly Business and Operational Reviews (MBR), contribute to QBRs.</li></ul>|Por añadir|
> |Arquitecto/responsable de colaboración|<ul><li>Ejecutar la estrategia de colaboración definida por los ejecutivos de la compañía.</li><li>Analice y elija productos de colaboración que cumplan los objetivos empresariales de la empresa.</li><li>Operaciones de diseño para productos de colaboración.</li><li>Definir modelos de operación y soporte técnico.</li><li>Contribuir a revisiones empresariales mensuales y trimestrales.</li></ul>|Por añadir|
> |Consultor|<ul><li>Sea responsable de los servicios de configuración</li><li>Contribuya a la arquitectura general de la solución.</li></ul>|Por añadir|
> |Jefe de proyecto|<ul><li>Desarrolle y mantenga el plan del proyecto.</li><li>Administre las entregas del proyecto en línea con el plan y el presupuesto del proyecto.</li><li>Registre y administre los problemas del proyecto, incluidas las escalaciones.</li><li>Realice llamadas de llamada de pie semanales.</li><li>Liaar con los patrocinadores ejecutivos del proyecto y ofrecerles actualizaciones.</li><li>Trabaje con el arquitecto para definir el enfoque de administración de cambios y los planes de comunicación.</li></ul>|Por añadir|
> |Especialista en adopción/administración de cambios|<ul><li>Proporcione información durante la fase de Descubrimiento en procesos de adopción y aprendizaje.</li><li>Participe en el taller de estrategia de adopción.</li><li>Desarrollar y tomar la responsabilidad de la estrategia de adopción.</li><li>Desarrolle y ejecute el plan de comunicación.</li><li>Entregar aprendizajes a los usuarios.</li><li>Recopile comentarios y realice encuestas.</li></ul>|Por añadir|
> |Responsable de redes|<ul><li>Proporcione información durante la fase de detección en el diseño de red.</li><li>Participe en la planificación durante el taller de la fase de visión.</li><li>Coordine el trabajo del equipo de redes durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable de seguridad|<ul><li>Proporcione información durante la fase de Detección en el diseño y los procesos de seguridad.</li><li>Participe en la planificación durante el taller de la fase de visión.</li><li>Coordine el trabajo del equipo de seguridad durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable de telefonía|<ul><li>Proporcione información durante la fase de Detección en el diseño de telefonía.</li><li>Participe en la planificación durante el taller de la fase de visión.</li><li>Coordine el trabajo del equipo de telefonía durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable de escritorio|<ul><li>Proporcione información durante la fase de detección en los clientes y el proceso de actualización.</li><li>Participe en la planificación durante el taller de Visión.</li><li>Coordine el trabajo del equipo de escritorio durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Responsable del servicio de asistencia y soporte técnico|<ul><li>Proporcione información durante la fase de Detección en modelos de operaciones y soporte técnico.</li><li>Participe en la planificación durante el taller de la fase de visión.</li><li>Participar en la planificación del modelo de soporte técnico.</li><li>Coordine el trabajo de los equipos de soporte técnico y los recursos durante la ejecución del proyecto.</li></ul>|Por añadir|
> |Representantes de la unidad de negocio|<ul><li>Contribuya a las guías de adopción basadas en el usuario y a sus materiales.</li><li>Colaborar y revisar casos de uso empresarial.</li></ul>|Por añadir|
> |Responsable de implementación|<ul><li>Asegúrese de que se cumplan los requisitos previos de implementación.</li><li>Aborde recursos para participar en las actividades de la fase de incorporación.</li><li>Participe en reuniones para revisar y preparar informes sobre el estado de la implementación.</li></ul>|Por añadir|
> |Administradores de TI|<ul><li>Ayude a planear y ejecutar pruebas. Este rol es para profesionales de TI.</li></ul>|Por añadir|
> |Propietario del servicio|<ul><li>Sea responsable del funcionamiento del servicio de Audioconferencia, Planes de llamadas o Enrutamiento directo, todo en su lugar.</li><li>Es el propietario del servicio audioconferencia, los planes de llamadas o el servicio de enrutamiento directo.</li></ul>|Por añadir|
> |Expertos en calidad|<ul><li>Mejorar la calidad, la confiabilidad y los comentarios de los usuarios.</li><li>Identifique tendencias de calidad e identifique la corrección con los equipos respectivos.</li><li>Informe a la dirección del comité de dirección.</li><li>Informe sobre la calidad, la confiabilidad y los opiniones de los usuarios sobre Rate My Call y Net Promoter Score.</li></ul>|Por añadir|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Puntos de decisión|<ul><li>¿Quién completará cada rol clave de las partes interesadas en su organización?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente todas las partes interesadas clave y comunique las responsabilidades y expectativas del rol a cada persona asignada.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definir los okrs, las KSIs y los riesgos

Con los participantes en el proyecto, puede traducir casos de uso empresarial, ámbitos organizativos y escalas de tiempo del proyecto en objetivos y resultados clave (OKRs), y las medidas de éxito del proyecto pueden definirse como una lista de indicadores clave de éxito (KPI).

La participación total de las partes interesadas del proyecto en la definición de los okrs y las KSIs es esencial para garantizar que se sientan propietarios y alinear estas medidas de éxito a los requisitos empresariales organizativos.

Los okrs contienen los objetivos que estableció al principio del proyecto y usted define los resultados clave mensurables de forma trimestral. Revise los resultados clave mensualmente para realizar un seguimiento del estado del proyecto general y, en función del progreso, ajuste los planes trimestrales según sea necesario.

> [!TIP]
> A continuación se pueden ver ejemplos de aceptar relevantes para una implementación de Audioconferencia:
> <br>
> 
> **Visión: Aumentar la productividad al maximizar las inversiones en Microsoft 365 u Office 365**
> 
> |Objetivos  |Resultados clave  |To do  |
> |---------|---------|---------|
> |Implementar Audioconferencia en Microsoft Teams al final del año fiscal 2018|T1 2018: implementar Audioconferencia en Microsoft Teams globalmente|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
> |Retirar globalmente el servicio de Conferencia RTC antiguo a mediados del año fiscal 2018|T2 2018: retirar globalmente el servicio de Conferencia RTC antiguo|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|

<br>

> [!TIP]
> A continuación se pueden ver ejemplos de aceptar relevantes para una implementación de planes de llamadas:
> <br>
> 
> **Visión: Aumentar la productividad al maximizar las inversiones en Microsoft 365 u Office 365**
> 
> |Objetivos  |Resultados clave  |To do  |
> |---------|---------|---------|
> |Implementar planes de llamadas en sucursales europeas a finales del año fiscal 2018|FY18Q3: Implementar planes de llamadas en la oficina de Londres|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
> |Retirar PBX heredado en la oficina de Londres a finales del año fiscal 2018|FY18Q4: Retirar PBX heredado en la oficina de Londres|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|
> 
> [!TIP]
> A continuación se pueden ver ejemplos de okRs relevantes para una implementación de enrutamiento directo:
> <br>
> 
> **Visión: Aumentar la productividad al maximizar las inversiones en Microsoft 365 u Office 365**
> 
> |Objetivos  |Resultados clave  |To do  |
> |---------|---------|---------|
> |Implementar enrutamiento directo en sucursales canadienses a finales del año fiscal 2018|FY18Q3: Implementar enrutamiento directo en la oficina de Toronto|Enfoque<ul><li>Crear el plan de éxito</li><li>Crear un plan técnico de implementación muy detallado</li></ul><p>Incorporación<ul><li>Ejecutar el plan de éxito</li><li>Ejecutar el plan técnico de implementación</li></ul>|
> |Retirar PBX heredado en la oficina de Toronto a finales del año fiscal 2018|FY18Q4: Retirar PBX heredado en la oficina de Toronto|Nuevos valores<ul><li>Potenciar la participación del usuario e impulsar la adopción</li><li>Administrar y prepararse para el cambio</li><li>Medir, compartir el éxito e iterar</li>|

<br>

Los KSIs miden la calidad y el éxito de los resultados clave, y complementan la naturaleza binaria de los OKR (lo que se consigue o no) detallando los resultados buenos o negativos.

Al definir KSIs, le recomendamos que use criterios "específicos, mensurables, asignables, realistas y relacionados con el tiempo" (SMART):

-   Específico: dirigirse a un área específica para mejorar

-   Mensurables: cuantificar o, al menos, sugerir un indicador de progreso

-   Asignable: especificar quién lo hará

-   Realista: establecer qué resultados pueden lograrse realistamente, teniendo en cuenta los recursos disponibles

-   Relación con el tiempo: especificar cuándo se pueden lograr los resultados

> [!TIP]
> A continuación se muestra un ejemplo de KSI relevantes para este proyecto:
> 
> |Tipo  |Cuestiones y criterios sobre el KSI  |Cómo se miden  |Criterios de éxito  |Medidos  |Responsable  |
> |---------|---------|---------|---------|---------|---------|
> |Uso/adopción|La calidad de las llamadas es igual o mejor que en la solución anterior|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de tecnología de la información|
> |Uso/adopción|El proceso de comunicación fue más sencillo gracias a Microsoft Teams|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de administración de cambios|
> |Uso/adopción|Los usuarios utilizan la solución activamente|Informes de Microsoft 365, panel de calidad de llamadas|El 80 % de los usuarios son usuarios activos diarios|A diario|Equipo de administración de cambios|
> |Uso/calidad|El porcentaje de llamadas/conferencias de mala calidad debe ser mínimo|Panel de calidad de llamadas|Menos del 5 % de llamadas de mala calidad al mes|A diario|Equipo de tecnología de la información|
> |Uso/soporte|Sé cómo conseguir soporte técnico|Encuesta|El 90% de los usuarios está de acuerdo o muy de acuerdo|Tras la habilitación y trimestralmente|Equipo de administración de cambios|
> |Uso/soporte|Estoy satisfecho con la calidad del soporte técnico|Encuesta|El 80 % de los usuarios está de acuerdo o muy de acuerdo|Tras cada incidente|Equipo de tecnología de la información|
> |Financiero|Reducción de los minutos de conferencias antiguas|Sistema financiero|Cumplir el ROI definido|Basado en ROI|Equipo de administración de cambios|

Necesita identificar los riesgos empresariales como parte de este ejercicio y definir un plan de mitigación para cada riesgo identificado. Esta información puede capturarse en un registro de riesgos.

> [!TIP]
> El registro de riesgos se puede documentar como el ejemplo siguiente:
> 
> |Riesgo  |Probabilidad  |Impacto  |General  |Plan de mitigación  |
> |---------|---------|---------|---------|---------|
> |Con la próxima fusión se sumarán hasta 1000 personas|Alta|Alto|Alto|<ul><li>Para las empresas combinadas, cree un okr independiente que se aplique a sus propias fases de proyecto (Visión, Incorporación, Valor de unidad)</li><li>No incluya estos okrs en los okrs existentes</li></ul>|
> |La portabilidad de los números de teléfono retrasará la finalización del proyecto.|Alta|Alto|Alto|<ul><li>Preparar toda la información necesaria para admitir la porvolución de números de teléfono con antelación (registro de servicio al cliente, detalles de facturación, Carta de autorización)</li><li>Ajustar la escala de tiempo del proyecto para dar cabida al tiempo de respuesta de la ejecución de porte de números de teléfono</li><li>Se debe comunicar el uso de los nuevos números de conferencia de acceso telefónico local a los participantes externos.</li><li>Usar números de teléfono temporales con una manipulación de identificación de llamadas</li></ul>|
> |Se ha planificado rediseñar las redes|Alta|Medio|Medio|<ul><li>Antes de implementar Teams como una plataforma moderna de comunicaciones y colaboración, realice una evaluación de la preparación de red para los sitios dentro del ámbito del proyecto</li></ul>|
> |Configuración de SBC|Alto|Alto|Alto|<ul><li>Antes de implementar Teams como sustituto del PBX existente, confirme que puede cumplir todos los requisitos de configuración de SBC</li><li>Confirmar que los recursos de soporte técnico de SBC tienen el conjunto de aptitudes adecuado para configurar SBC para enrutamiento directo</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Puntos de decisión|<ul><li>¿Cuáles son las&#39;de su organización sobre okrs e kpi?</li><li>¿Qué riesgos se han identificado relevantes para la implementación de Audioconferencia en su organización? ¿Cuáles son los planes de mitigación para los riesgos identificados?</li><li>¿Qué riesgos has identificado relevantes para la implementación de planes de llamadas en tu organización? ¿Cuáles son los planes de mitigación para los riesgos identificados?</li><li>¿Qué riesgos se han identificado relevantes para la implementación de enrutamiento directo en su organización? ¿Cuáles son los planes de mitigación para los riesgos identificados?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Documente los okrs y los kpi, y establezca el registro de riesgos.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Establecer un comité de dirección

Un comité de dirección es un grupo de partes interesadas y jefes de proyecto clave que se han unido para guiar un proyecto o programa hacia sus resultados empresariales definidos. El comité de dirección no  es responsable directamente de  cómo se entrega el proyecto, sino de lo que el proyecto entrega a la empresa.

Todos los proyectos necesitan una visión y una carta de con estatutos acordados. Para ofrecer los resultados que desea del proyecto, la visión debe definirse claramente y es necesario supervisarla y mantenerla. Esto se convierte en la responsabilidad del comité de dirección: impulsar decisiones, avisar, ofrecer supervisión estratégica, actuar como defensores de la organización para las iniciativas del proyecto y, cuando sea necesario, quitar los bloqueadores.

Su organización debe pensar mucho en la formación del comité de dirección. El comité debe asegurarse de que el proyecto alcanza los objetivos empresariales que ha definido para impulsar el cambio en toda la organización, reunirse periódicamente para tratar el pulso actual del proyecto y ayudar a desbloquear los obstáculos que se encuentran a lo largo del camino.

El comité debe definir su carta para incluir algunos objetivos clave:

-   Mantenga una alineación sólida entre el equipo del proyecto y el patrocinador ejecutivo o la dirección ejecutiva.

-   Proporcione información sobre el estado del proyecto al patrocinador ejecutivo o la dirección ejecutiva.

-   Permita que el patrocinador ejecutivo o el equipo ejecutivo de liderazgo proporcione dirección e información para el proyecto y asegúrese de que se alinea con objetivos empresariales generales, ajustando los planes de proyecto, los resultados clave objetivo (OKRs) y otras actividades de proyecto.

El comité de dirección se reúne a intervalos periódicos durante toda la vida de un proyecto para asegurar la alineación entre el liderazgo de la organización y el equipo del proyecto. Esta reunión crítica garantiza que la dirección del proyecto tenga el apoyo total del liderazgo y que incorpore los comentarios proporcionados por los líderes en el proyecto para impulsar el éxito. El comité utiliza estas reuniones para obtener información sobre el estado del proyecto y para:

-   Ponerse de acuerdo sobre resultados empresariales que se alineen al caso empresarial y para asegurarse de que el proyecto está avanzando hacia la entrega de estos resultados.

-   Compruebe y apruebe el proyecto para comprobar la precisión y el cumplimiento del caso empresarial.

-   Revise y compruebe los cambios realizados en el caso empresarial que podrían afectar a cualquier resultado definido.

-   Tomar decisiones estratégicas sobre la priorización de las entregas de los proyectos y aprobar las entregas provisionales.

-   Identifique, administre y atenúa las brechas, los riesgos y los problemas en los que se necesita una influencia adicional del comité.

-   Reúna el apoyo del patrocinador ejecutivo o del equipo ejecutivo de liderazgo para los problemas que requieren escalación, priorización y resolución de conflictos entre las unidades de negocio de las partes interesadas. 

-   Proporcione comentarios formales y recomendaciones a la dirección ejecutiva, al consejo asesor de cambios o a otras partes interesadas de LA EMPRESA y DE LA, según corresponda.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Puntos de decisión|<ul><li>Decida si se necesita un comité de dirección para su organización.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Pasos siguientes|<ul><li>Identifique a los miembros del comité de dirección.</li><li>Programe reuniones del comité de dirección.</li><li>Prepárese para las reuniones del comité de dirección.</li><li>Mantenga reuniones del comité de dirección.</li><li>Tome medidas en función de la entrada en la reunión del comité de dirección.</li></ul>|

En la guía del comité de dirección encontrará instrucciones detalladas adicionales sobre cómo dirigir un comité de [dirección adecuado.](envision-steering-committee-complete-guide.md)

<!--ENDOFSECTION-->

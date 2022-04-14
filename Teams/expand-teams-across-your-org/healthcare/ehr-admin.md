---
title: Citas virtuales con Teams - Integración en Epic EHR
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: Obtenga información sobre cómo integrar el conector EHR Teams para permitir que los proveedores de atención médica de su organización lleven a cabo citas virtuales con pacientes u otros proveedores en Teams directamente desde el sistema EPIC EHR.
ms.openlocfilehash: baef8aeda05413ce2f307a4bbea7259490ecfb83
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853061"
---
# <a name="virtual-appointments-with-teams---integration-into-epic-ehr"></a>Citas virtuales con Teams - Integración en Epic EHR

El conector de registro médico electrónico (EHR) Microsoft Teams facilita que los médicos inicien una consulta virtual con un paciente o consultas con otro proveedor en Microsoft Teams directamente desde el sistema Epic EHR. Integrado en la nube Microsoft 365, Teams permite una colaboración y comunicación sencillas y seguras con las herramientas de chat, vídeo, voz y atención sanitaria en un único concentrador que cumple con la certificación HIPAA, HITECH y mucho más.

La plataforma de comunicación y colaboración de Teams facilita que los médicos corten el desorden de los sistemas fragmentados para que puedan concentrarse en proporcionar la mejor atención posible. Con el conector EHR Teams, puede:

- Inicia Teams citas virtuales desde tu sistema Epic EHR con un flujo de trabajo clínico integrado.
- Permitir a los pacientes unirse a Teams citas virtuales desde el portal del paciente o a través de SMS.
- Apoyar otros escenarios, incluidos varios participantes, visitas de grupo y servicios de intérprete.
- Vuelva a escribir metadatos en el sistema EHR sobre Teams citas virtuales para registrar cuándo los asistentes se conectan, desconectan y habilitan la auditoría automática y el mantenimiento de registros.
- Vea informes de datos de consumo e información personalizable de calidad de llamada para citas conectadas con EHR.

Consulte este vídeo para obtener información general sobre cómo administrar citas virtuales desde el portal de EHR.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

En este artículo se describe cómo configurar el conector EHR Teams para que se integre con la plataforma Epic de su organización sanitaria. También te ofrece una visión general de la experiencia de citas virtuales Teams desde el sistema EPIC EHR.

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar, hay algunas cosas que hacer para prepararse para la integración.

### <a name="get-familiar-with-the-integration-process"></a>Familiarizarse con el proceso de integración

Revise la siguiente información para comprender el proceso de integración general.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="Imagen que resume los pasos del proceso de integración general.":::

||||||
|---------|---------|---------|---------|---------|
|**Acción**: [Solicitas acceso a la aplicación Teams](#request-access-to-the-teams-app). <br> **Resultado**: autorizamos a tu organización a realizar pruebas.|**Acción**: Creamos un certificado de clave pública y privada y los cargamos a Epic. <br> **Resultado**: Epic sincroniza el certificado de clave pública.|**Acción**: Usted completa los pasos de configuración en el portal de configuración del conector EHR. <br> **Resultado**: Recibes registros de IED para la configuración épica.| **Acción**: Trabaja con tu especialista técnico de Epic para configurar los registros de IED en Epic.<br> **Resultado**: configuración completada. Listo para probar.|**Acción**: Completa las pruebas en el entorno de prueba.<br> **Resultado**: Validación completa de los flujos y la decisión de pasar a producción.|

### <a name="request-access-to-the-teams-app"></a>Solicitar acceso a la aplicación Teams

Tendrás que solicitar acceso a la aplicación Teams.

1. Solicita descargar la aplicación Teams en epic [app orchard](https://apporchard.epic.com/Gallery?id=6153) marketplace. Al hacerlo, se desencadena una solicitud de Epic al equipo del conector EHR de Microsoft.
1. Después de realizar tu solicitud, envía un correo electrónico a [TeamsForHealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) con el nombre de la organización, el id. de inquilino y la dirección de correo electrónico de tu contacto técnico de Epic.
1. El equipo del conector EHR de Microsoft responderá a su correo electrónico con la confirmación de habilitación.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Revise la guía de integración Epic-Microsoft Teams Telehealth

Revise la [integración de teleasistencia sanitaria de Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) con su especialista técnico profesional. Asegúrese de que se cumplen todos los requisitos previos.

## <a name="prerequisites"></a>Requisitos previos

- Una suscripción activa a Microsoft Cloud for Healthcare o una suscripción a Microsoft Teams oferta independiente del conector EHR (solo se aplica al realizar pruebas en un entorno EHR de producción).
- Versión épica de noviembre de 2018 o posterior.
- Los usuarios tienen una licencia de Microsoft 365 o Office 365 adecuada que incluye Teams reuniones.
- Teams se adopta y se usa en su organización sanitaria.
- Los sistemas cumplen todos [los requisitos de software y explorador](../../hardware-requirements-for-the-teams-app.md) para Teams.

> [!IMPORTANT]
> Asegúrese de completar los pasos previos a la integración y de que se cumplan todos los requisitos previos antes de avanzar con la integración.

Los pasos de integración los realizan los siguientes usuarios de su organización:

- **Microsoft 365 administrador global**: la persona principal responsable de la integración. El administrador configura el conector, habilita el SMS (si es necesario) y agrega al analista de clientes de Epic que aprobará la configuración.
- **Epic analista de clientes**: Una persona de su organización que tiene credenciales de inicio de sesión para Epic. Aprueban los ajustes de configuración introducidos por el administrador y proporcionan los registros de configuración a Epic.

El administrador de Microsoft 365 y el analista de clientes de Epic pueden ser la misma persona.

## <a name="set-up-the-teams-ehr-connector"></a>Configurar el conector EHR Teams

Para la configuración del conector, debe realizar las siguientes acciones:

- [Iniciar el portal de configuración del conector EHR](#launch-the-ehr-connector-configuration-portal)
- [Escribir información de configuración](#enter-configuration-information)
- [Habilitar notificaciones SMS (opcional)](#enable-sms-notifications-optional)
- [Aprobar o ver la configuración](#approve-or-view-the-configuration)
- [Revisar y finalizar la configuración](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>Iniciar el portal de configuración del conector EHR

Para empezar, el administrador de Microsoft 365 inicia el portal de configuración del [conector EHR](https://ehrconnector.teams.microsoft.com) e inicia sesión con sus credenciales de Microsoft 365.

El administrador de Microsoft 365 puede configurar una única organización o varias organizaciones para probar la integración. Configure la dirección URL de prueba y producción en el portal de configuración. Asegúrese de probar la integración desde el entorno de prueba de Epic antes de pasar a la producción.

> [!NOTE]
> Su administrador de Microsoft 365 y analista de clientes de Epic deben completar los pasos de integración en el portal de configuración. Para conocer los pasos de configuración de Epic, ponte en contacto con el especialista técnico de Epic asignado a tu organización.

### <a name="enter-configuration-information"></a>Escribir información de configuración

A continuación, para configurar la integración, el administrador de Microsoft 365 hace lo siguiente:

1. Agrega una dirección URL base de Fast Health Interoperability Resources (FHIR) de su especialista técnico de Epic y especifica el entorno. Configure tantas direcciones URL base de FHIR como sea necesario, según las necesidades de su organización y los entornos que desee probar.

    - La dirección URL base de FHIR es una dirección estática que corresponde al extremo de la API FHIR del servidor. Una dirección URL de ejemplo es `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

    - Puede configurar la integración para entornos de prueba y producción. Para la configuración inicial, le recomendamos que configure el conector desde un entorno de prueba antes de pasar a producción.

1. Agrega el nombre de usuario del analista de clientes de Epic que aprobará la configuración en un paso posterior.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="Captura de pantalla de la página Configuración, en la que se muestra el aprobador que se está agregando." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>Habilitar notificaciones SMS (opcional)

> [!NOTE]
> Las notificaciones SMS solo están disponibles actualmente en el Estados Unidos. Estamos trabajando para que esta característica esté disponible en otras regiones en futuras versiones de Teams y actualizaremos este artículo cuando esté disponible.

Complete este paso si su organización quiere que Microsoft administre las notificaciones de SMS para sus pacientes. Cuando habilite notificaciones SMS, sus pacientes recibirán mensajes de confirmación y recordatorio para las citas programadas.

Para habilitar las notificaciones SMS, el administrador de Microsoft 365 hace lo siguiente:

1. En la página notificaciones sms, selecciona ambas casillas de consentimiento para:

    - Permita que Microsoft envíe notificaciones SMS a los pacientes en nombre de su organización.
    - Confirme que se asegurará de que los asistentes hayan dado su consentimiento para enviar y recibir mensajes SMS.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="Captura de pantalla de la página de notificaciones sms, que muestra las casillas de consentimiento y la opción para generar un número de teléfono." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. En **Sus números de teléfono**, seleccione **Generar un nuevo número de teléfono** para generar un número de teléfono para su organización. Al hacerlo, se inicia el proceso para solicitar y generar un nuevo número de teléfono. Este proceso puede tardar hasta 2 minutos en completarse.

    Una vez generado el número de teléfono, se muestra en la pantalla. Este número se usará para enviar confirmaciones sms y recordatorios a sus pacientes. Se ha aprovisionado el número, pero aún no está vinculado a la dirección URL base de FHIR. Lo hará en el siguiente paso.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="Captura de pantalla que muestra un ejemplo del número de teléfono que se genera." lightbox="media/ehr-connector-epic-phone-number.png":::

    Elija **Listo** y, a continuación, seleccione **Siguiente**.

1. Para vincular el número de teléfono a una dirección URL base de FHIR, en **Teléfono número** en la sección **configuración de SMS**, seleccione el número. Haga esto para cada url base de FHIR para la que desea habilitar las notificaciones SMS.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="Captura de pantalla que muestra cómo vincular un número de teléfono a una dirección URL base FHIR." lightbox="media/ehr-connector-epic-link-phone-number.png":::

    Si es la primera vez que configura el conector, verá la dirección URL base de FHIR que se escribió en el paso anterior. El mismo número de teléfono se puede vincular a varias direcciones URL base FHIR, lo que significa que los pacientes recibirán notificaciones SMS del mismo número de teléfono para diferentes organizaciones y/o departamentos.

1. Seleccione **Configuración de SMS** junto a cada URL base de FHIR para configurar los tipos de notificaciones sms que se enviarán a sus pacientes.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="Captura de pantalla que muestra la configuración de SMS." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **SMS de confirmación**: las notificaciones se envían a los pacientes cuando se programa, actualiza o cancela una cita en el sistema EHR.
    - **SMS de aviso**: Las notificaciones se envían a los pacientes según el intervalo de tiempo que especifique y la hora programada de la cita.

    Elija **Guardar**.

1. Seleccione **Upload certificado** para cargar un certificado de clave pública. Debe cargar un certificado .cer con codificación Base64 (solo clave pública) para cada entorno.

    Se requiere un certificado de clave pública para recibir información de citas para enviar notificaciones SMS. El certificado es necesario para comprobar que la información entrante procede de un origen válido.

    Cuando el conector se utiliza para enviar recordatorios SMS, epic en una carga de HL7v2 envía el número de teléfono del paciente cuando las citas se crean en Epic. Estos números se almacenan para cada cita en la geografía de su organización y se conservan hasta que la cita tiene lugar. Para obtener más información sobre cómo configurar mensajes de HL7v2, consulta la [Guía de integración de Epic-Microsoft Teams Telehealth](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

    Elija **Siguiente**.

> [!NOTE]
> En cualquier momento, el administrador de Microsoft 365 puede actualizar cualquiera de las opciones de configuración de SMS. Ten en cuenta que el cambio de configuración podría dar lugar a una interrupción del servicio de SMS. Para obtener más información sobre cómo ver informes de SMS, consulte [Teams informes de administrador del conector EHR](ehr-admin-reports.md).

### <a name="approve-or-view-the-configuration"></a>Aprobar o ver la configuración

El analista de clientes de Epic de su organización que se agregó como aprobador inicia el [portal de configuración del conector EHR](https://ehrconnector.teams.microsoft.com) e inicia sesión con sus credenciales de Microsoft 365. Después de la validación correcta, se pide al aprobador que inicie sesión con sus credenciales de Epic para validar la organización de Epic.

> [!Note]
> Si el administrador de Microsoft 365 y el analista de clientes de Epic son la misma persona, tendrás que iniciar sesión en Epic para validar tu acceso. El inicio de sesión de Epic solo se usa para validar su URL base de FHIR. Microsoft no almacenará credenciales ni accederá a datos EHR con este inicio de sesión.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="Captura de pantalla de la página Aprobar o Ver configuración, que muestra la opción Iniciar sesión y aprobar." lightbox="media/ehr-connector-epic-login-approve.png":::

Después de iniciar sesión con éxito en Epic, el analista de clientes de Epic **debe** aprobar la configuración. Si la configuración no es correcta, el administrador de Microsoft 365 puede iniciar sesión en el portal de configuración y cambiar la configuración.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="Captura de pantalla de la página Aprobar o Ver configuración, que muestra la opción Aprobar." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>Revisar y finalizar la configuración

Cuando el administrador de Epic apruebe la información de configuración, se le presentarán registros de integración para el inicio de los proveedores y los pacientes. Los registros de integración incluyen:

- Registros de pacientes y proveedores
- Registro SMS directo
- Registro de configuración de SMS
- Registro de configuración de prueba de dispositivo

El analista cliente de Epic debe proporcionar estos registros a Epic para completar la configuración de citas virtuales en Epic. Para obtener más información, consulta la [Guía de integración de Epic-Microsoft Teams Telehealth](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

> [!Note]  
> En cualquier momento, el Microsoft 365 o epic analista de clientes puede iniciar sesión en el portal de configuración para ver los registros de integración y cambiar la configuración de la organización, según sea necesario.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="Captura de pantalla de la página Revisar y finalizar, que muestra información de integración." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> El analista de clientes de Epic debe completar el proceso de aprobación para cada URL base de FHIR configurada por el administrador de Microsoft 365.

## <a name="launch-teams-virtual-appointments"></a>Iniciar Teams citas virtuales

Después de completar los pasos del conector EHR y la configuración de Epic, su organización está lista para admitir citas de vídeo con Teams.

### <a name="virtual-appointments-prerequisites"></a>Requisitos previos de citas virtuales

- Los sistemas deben cumplir todos [los requisitos de software y explorador](../../hardware-requirements-for-the-teams-app.md) para Teams.

- Has completado la configuración de integración entre la organización de Epic y tu organización de Microsoft 365.

### <a name="provider-experience"></a>Experiencia del proveedor

Los proveedores de atención médica de su organización pueden unirse a citas con Teams de sus aplicaciones de proveedores de Epic (Hyperspace, Haiku, Canto). El botón **Iniciar visita virtual** está incorporado en el flujo del proveedor.

Características principales de la experiencia del proveedor:

- Los proveedores pueden unirse a citas mediante exploradores compatibles o la aplicación de Teams.

- Los proveedores deben realizar un inicio de sesión único con su cuenta de Microsoft 365 al unirse a una cita por primera vez.

- Después del inicio de sesión único, el proveedor se lleva directamente a la cita virtual en Teams. (El proveedor debe haber iniciado sesión en Teams).

- Los proveedores pueden ver actualizaciones en tiempo real de los participantes que se conectan y desconectan para una cita determinada. Los proveedores pueden ver cuándo el paciente está conectado a una cita.

  ![Experiencia del proveedor de una cita con un paciente.](media/ehc-provider-experience-6.png)

> [!NOTE]
> Cualquier información introducida en el chat de la reunión que sea necesaria para la continuidad de los registros médicos o con fines de retención debe ser descargada, copiada y anotada por el proveedor de atención médica. El chat no constituye un registro médico legal o un conjunto de registros designados. Los mensajes del chat se almacenan en función de la configuración creada por el administrador de Microsoft Teams.

### <a name="patient-experience"></a>Experiencia del paciente

El conector admite pacientes que se unen a citas a través de MyChart web y móviles. En el momento de la cita, los pacientes pueden iniciar una cita desde MyChart con el botón **Iniciar visita virtual** .

Características principales de la experiencia del paciente:

- Los pacientes pueden unirse a citas desde [exploradores web modernos en equipos de escritorio y móviles sin tener que instalar la aplicación Teams](../browser-join.md).

- Los pacientes pueden unirse a las citas con un solo clic y no se requiere ninguna otra cuenta o inicio de sesión.

- No es necesario que los pacientes creen una cuenta de Microsoft ni que inicien sesión para iniciar una cita.

- Los pacientes se colocan en una sala de espera hasta que el proveedor se une y los admite.

- Los pacientes pueden probar el vídeo y el micrófono en la sala de espera antes de unirse a la cita.

  ![Experiencia del paciente con la cita.](media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku y Canto son marcas comerciales de Epic Systems Corporation.

## <a name="get-insight-into-virtual-appointments-usage"></a>Obtener información sobre el uso de citas virtuales

El [informe uso de visitas virtuales](../../teams-analytics-and-reports/virtual-visits-usage-report.md) del centro de administración de Microsoft Teams ofrece a los administradores información general sobre Teams actividad de citas virtuales en su organización. El informe muestra análisis detallados de citas virtuales, incluidas Teams reuniones integradas de EHR realizadas desde su sistema EHR.

Puede ver métricas clave como el tiempo de espera de la sala de espera y la duración de las citas. Use esta información para obtener información sobre las tendencias de uso para ayudarle a optimizar las citas virtuales y ofrecer mejores resultados empresariales.

### <a name="privacy-and-location-of-data"></a>Privacidad y ubicación de los datos

Teams integración en sistemas EHR optimiza la cantidad de datos que se usan y almacenan durante los flujos de integración y cita virtual. La solución sigue los principios generales de privacidad y administración de datos de Teams, y las directrices estipuladas en Privacidad de Teams.

El conector EHR Teams no almacena ni transfiere datos personales identificables ni registros médicos de pacientes o proveedores sanitarios desde el sistema EHR. El único dato que almacena el conector de EHR es la identificación única del usuario de EHR, que se usa durante la configuración de la reunión de Teams.

La identificación única del usuario de EHR se almacena en una de las tres regiones geográficas que se describen en [¿Dónde se almacenan los datos de los clientes de Microsoft 365?](/microsoft-365/enterprise/o365-data-locations) Todos los chats, grabaciones y otros datos compartidos en Teams por los participantes de la reunión se almacenan de acuerdo con las directivas de almacenamiento existentes. Para obtener más información sobre la ubicación de los datos en Teams, vea [Ubicación de los datos en Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Artículos relacionados

- [Teams informe de uso de visitas virtuales](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams informes de administrador del conector EHR](ehr-admin-reports.md)
- [Comenzar con Teams para organizaciones sanitarias](teams-in-hc.md)

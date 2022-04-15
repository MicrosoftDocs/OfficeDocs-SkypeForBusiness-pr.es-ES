---
title: Citas virtuales con Teams - Integración en Cerner EHR
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
description: Obtenga información sobre cómo integrar el conector EHR Teams para permitir que los proveedores de atención médica de su organización realicen citas virtuales con pacientes u otros proveedores en Teams directamente desde el sistema EHR de Cerner.
ms.openlocfilehash: 8caa80bca9a7b8278aff9133f81bfa807e6727ed
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853301"
---
# <a name="virtual-appointments-with-teams---integration-into-cerner-ehr"></a>Citas virtuales con Teams - Integración en Cerner EHR

El conector de registro médico electrónico (EHR) Microsoft Teams facilita que los médicos inicien una cita virtual con un paciente o consulten con otro proveedor en Microsoft Teams directamente desde el sistema EHR de Cerner. Integrado en la nube Microsoft 365, Teams permite una colaboración y comunicación sencillas y seguras con las herramientas de chat, vídeo, voz y atención sanitaria en un único concentrador que cumple con la certificación HIPAA, HITECH y mucho más.

La plataforma de comunicación y colaboración de Teams facilita que los médicos corten el desorden de los sistemas fragmentados para que puedan concentrarse en proporcionar la mejor atención posible. Con el conector EHR Teams, puede:

- Realice Teams citas virtuales desde su sistema Cerner EHR con un flujo de trabajo clínico integrado.
- Permitir a los pacientes unirse a Teams citas virtuales desde correo electrónico o notificaciones SMS.
- Vea informes de datos de consumo e información personalizable de calidad de llamada para citas conectadas con EHR.

En este artículo se describe cómo configurar el conector EHR Teams para su integración con la plataforma de Cerner. También ofrece una visión general de la experiencia de citas virtuales Teams desde el sistema Cerner EHR.

## <a name="before-you-begin"></a>Antes de empezar

> [!NOTE]
> Asegúrese de hablar con su representante de Cerner y revise su guía de integración de Cerner antes de habilitar la integración.

### <a name="prerequisites"></a>Requisitos previos

Antes de integrar el conector Teams EHR en su organización sanitaria, debe tener lo siguiente:

- Una suscripción activa a Microsoft Teams oferta independiente del conector EHR (solo se aplica durante las pruebas en un entorno EHR de producción).
- Los usuarios tienen una licencia de Microsoft 365 o Office 365 adecuada que incluye Teams reuniones.
- Teams se adopta y se usa en su organización sanitaria.
- Los sistemas cumplen todos [los requisitos de software y explorador](../../hardware-requirements-for-the-teams-app.md) para Teams.
- Versión de Cerner de noviembre de 2018 o posterior

## <a name="set-up-the-teams-ehr-connector"></a>Configurar el conector EHR Teams

Para la configuración del conector, debe realizar las siguientes acciones:

- [Iniciar el portal de configuración del conector EHR](#launch-the-ehr-connector-configuration-portal)
- [Escribir información de configuración](#enter-configuration-information)
- [Habilitar notificaciones SMS (opcional)](#enable-sms-notifications-optional)
- [Revisar y finalizar la configuración](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Estos pasos los debe completar el Microsoft 365 administrador global de su organización.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Iniciar el portal de configuración del conector EHR

Para empezar, el administrador de Microsoft 365 inicia el portal de configuración del [conector EHR](https://ehrconnector.teams.microsoft.com) e inicia sesión con sus credenciales de Microsoft.

El administrador de Microsoft 365 puede configurar un único departamento o varios departamentos para probar la integración. Configure la dirección URL de prueba y producción en el portal de configuración. Asegúrese de probar la integración desde el entorno de prueba de Cerner antes de pasar a producción.

### <a name="enter-configuration-information"></a>Escribir información de configuración

A continuación, para configurar la integración, el administrador de Microsoft 365 agrega una dirección URL base de recursos de interoperabilidad de estado rápido (FHIR) de Cerner y especifica el entorno. Configure tantas direcciones URL base de FHIR como sea necesario, según las necesidades de su organización y los entornos que desee probar.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Captura de pantalla de la página Información de configuración del portal de configuración del conector EHR Teams." lightbox="media/ehr-admin-cerner-configuration.png":::

- La dirección URL base de FHIR es una dirección estática que corresponde al extremo de la API FHIR del servidor. Una dirección URL de ejemplo es `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Puede configurar la integración para entornos de prueba y producción. Para la configuración inicial, le recomendamos que configure el conector desde un entorno de prueba antes de pasar a producción.

Después de validar la dirección URL base de FHIR y seleccionar el entorno, elija **Listo**. A continuación, agregue más direcciones URL base FHIR para otros entornos, según sea necesario.

Seleccione **Siguiente** para ir al paso siguiente.

### <a name="enable-sms-notifications-optional"></a>Habilitar notificaciones SMS (opcional)

Complete este paso si su organización quiere que Microsoft administre las notificaciones de SMS para sus pacientes. Cuando habilite notificaciones SMS, sus pacientes recibirán mensajes de confirmación y recordatorio para las citas programadas.

Para habilitar las notificaciones SMS, el administrador de Microsoft 365 hace lo siguiente:

1. En la página notificaciones sms, selecciona ambas casillas de consentimiento para:

    - Permita que Microsoft envíe notificaciones SMS a los pacientes en nombre de su organización.
    - Confirme que se asegurará de que los asistentes hayan dado su consentimiento para enviar y recibir mensajes SMS.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Captura de pantalla de la página de notificaciones sms, que muestra las casillas de consentimiento y la opción para generar un número de teléfono." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. En **Sus números de teléfono**, seleccione **Generar un nuevo número de teléfono** para generar un número de teléfono para su organización. Al hacerlo, se inicia el proceso para solicitar y generar un nuevo número de teléfono. Este proceso puede tardar hasta 2 minutos en completarse.

    Una vez generado el número de teléfono, se muestra en la pantalla. Este número se usará para enviar confirmaciones sms y recordatorios a sus pacientes. Se ha aprovisionado el número, pero aún no está vinculado a la dirección URL base de FHIR. Lo hará en el siguiente paso.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Captura de pantalla que muestra un ejemplo del número de teléfono que se genera." lightbox="media/ehr-admin-cerner-phone-number.png":::

    Elija **Listo** y, a continuación, seleccione **Siguiente**.

1. Para vincular el número de teléfono a una dirección URL base de FHIR, en **Teléfono número** en la sección **configuración de SMS**, seleccione el número. Haga esto para cada url base de FHIR para la que desea habilitar las notificaciones SMS.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Captura de pantalla que muestra cómo vincular un número de teléfono a una dirección URL base FHIR." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Si es la primera vez que configura el conector, verá la dirección URL base de FHIR que se escribió en el paso anterior. El mismo número de teléfono se puede vincular a varias direcciones URL base FHIR, lo que significa que los pacientes recibirán notificaciones SMS del mismo número de teléfono para diferentes organizaciones y/o departamentos.

     Seleccione **Siguiente**.

### <a name="review-and-finish-the-configuration"></a>Revisar y finalizar la configuración

Se le presentarán registros de integración para el lanzamiento de pacientes y proveedores. Estos registros son necesarios para completar la configuración de citas virtuales en Cerner. Para obtener más información, consulte la guía de integración Cerner-Microsoft Teams Telehealth.

> [!NOTE]
> En cualquier momento, el administrador de Microsoft 365 puede iniciar sesión en el portal de configuración para ver los registros de integración y cambiar la configuración, si es necesario.

## <a name="launch-teams-virtual-appointments"></a>Iniciar Teams citas virtuales

Después de completar los pasos del conector EHR y los pasos de configuración de Cerner, su organización está lista para admitir citas de vídeo con Teams.

### <a name="virtual-appointments-prerequisites"></a>Requisitos previos de citas virtuales

- Los sistemas deben cumplir todos [los requisitos de software y explorador](../../hardware-requirements-for-the-teams-app.md) para Teams.
- Ha completado la configuración de integración entre la organización de Cerner y su organización de Microsoft 365.

### <a name="provider-experience"></a>Experiencia del proveedor

Los proveedores de atención médica de su organización pueden unirse a citas con Teams desde el portal de PowerChart. El proveedor debe ir al panel del paciente donde está disponible la opción Teams.

Desde allí, el proveedor puede ver la información de la cita, unirse a citas y enviar el vínculo de la reunión. Después del inicio de sesión único, el proveedor se lleva directamente a la cita virtual en Teams.

Características principales de la experiencia del proveedor:

- Los proveedores pueden unirse a citas mediante exploradores compatibles o la aplicación de Teams.
- Los proveedores pueden usar todas las características compatibles Teams reuniones, incluido el uso compartido de la pantalla, el fondo personalizado y la grabación.
- Los proveedores pueden ver actualizaciones en tiempo real de pacientes que se conectan a una cita para una cita determinada en PowerChart.
- La información del proveedor no es visible para los pacientes durante la consulta.

> [!NOTE]
> Cualquier información introducida en el chat de la reunión que sea necesaria para la continuidad de los registros médicos o con fines de retención debe ser descargada, copiada y anotada por el proveedor de atención médica. El chat no constituye un registro médico legal o un conjunto de registros designados. Los mensajes del chat se almacenan en función de la configuración creada por el administrador de Microsoft Teams.

### <a name="patient-experience"></a>Experiencia del paciente

El conector admite pacientes que se unen a citas a través de un vínculo en el mensaje de texto SMS. En el momento de la cita, los pacientes pueden iniciar una cita pulsando el vínculo en el mensaje de texto SMS.

Características clave de la experiencia del paciente

- Los pacientes pueden unirse a citas desde [exploradores web modernos en equipos de escritorio y móviles sin tener que instalar la aplicación Teams](../browser-join.md).
- Los pacientes pueden unirse a las citas con un solo clic y no se requiere ninguna otra cuenta o inicio de sesión.
- No es necesario que los pacientes creen una cuenta de Microsoft ni que inicien sesión para iniciar una visita.
- Los pacientes se colocan en una sala de espera hasta que el proveedor se une y los admite.
- Los pacientes pueden probar su vídeo y micrófono en la sala de espera antes de unirse a la cita.

## <a name="get-insight-into-virtual-appointments-usage"></a>Obtener información sobre el uso de citas virtuales

El [informe uso de visitas virtuales](../../teams-analytics-and-reports/virtual-visits-usage-report.md) del centro de administración de Microsoft Teams ofrece a los administradores información general sobre Teams actividad de citas virtuales en su organización. El informe muestra análisis detallados de citas virtuales, incluidas Teams reuniones integradas de EHR realizadas desde su sistema EHR.

Puede ver métricas clave como el tiempo de espera de la sala de espera y la duración de las citas. Use esta información para obtener información sobre las tendencias de uso para ayudarle a optimizar las citas virtuales y ofrecer mejores resultados empresariales.

## <a name="privacy-and-location-of-data"></a>Privacidad y ubicación de los datos

Teams integración en sistemas EHR optimiza la cantidad de datos que se usan y almacenan durante los flujos de integración y cita virtual. La solución sigue los principios generales de privacidad y administración de datos de Teams, y las directrices estipuladas en Privacidad de Teams.

El conector EHR Teams no almacena ni transfiere datos personales identificables ni registros médicos de pacientes o proveedores sanitarios desde el sistema EHR. Los únicos datos que almacena el conector EHR son el id. único del usuario de EHR, que se usa durante Teams configuración de la reunión.

La identificación única del usuario de EHR se almacena en una de las tres regiones geográficas que se describen en [¿Dónde se almacenan los datos de los clientes de Microsoft 365?](/microsoft-365/enterprise/o365-data-locations) Todos los chats, grabaciones y otros datos compartidos en Teams por los participantes de la reunión se almacenan según las directivas de almacenamiento existentes. Para obtener más información sobre la ubicación de los datos en Teams, vea [Ubicación de los datos en Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Artículos relacionados

- [Teams informe de uso de visitas virtuales](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams informes de administrador del conector EHR](ehr-admin-reports.md)
- [Comenzar con Teams para organizaciones sanitarias](teams-in-hc.md)

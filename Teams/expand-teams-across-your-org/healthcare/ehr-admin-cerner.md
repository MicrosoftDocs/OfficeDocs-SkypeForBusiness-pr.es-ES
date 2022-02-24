---
title: 'Visitas virtuales con Teams: integración en Cerner EHR'
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
description: Obtenga información sobre cómo integrar el conector EHR de Teams para permitir que los proveedores de servicios de salud de su organización realicen visitas virtuales con pacientes u otros proveedores en Teams directamente desde el sistema EHR cerner.
ms.openlocfilehash: fd37b32acfd2a33cde61b56c7f17191e7470923e
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929335"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Visitas virtuales con Teams: integración en Cerner EHR

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

El Microsoft Teams registro de salud electrónico (EHR) permite a los médicos iniciar una visita virtual de pacientes o consultar con otro proveedor en Microsoft Teams directamente desde el sistema EHR cerner. Integrada en la nube de Microsoft 365, Teams permite una colaboración y comunicación sencillas y seguras con herramientas de chat, vídeo, voz y atención sanitaria en un único concentrador compatible con el cumplimiento de hipaa, certificación HITECH y mucho más.

La plataforma de comunicación y colaboración de Teams facilita a los médicos cortar el desorden de sistemas fragmentados para que puedan centrarse en proporcionar la mejor atención posible. Con el Teams EHR, puede:

- Realice Teams visitas virtuales desde su sistema EHR cerner con un flujo de trabajo clínico integrado.
- Permitir que los pacientes se unan Teams visitas virtuales desde notificaciones por correo electrónico o SMS.
- Vea informes de datos de consumo e información de calidad de llamada personalizable para las visitas conectadas a EHR.

En este artículo se describe cómo configurar y configurar el Teams EHR para que se integre con la plataforma Cerner. También le ofrece información general sobre la experiencia Teams visitas virtuales desde el sistema EHR cerner.

## <a name="before-you-begin"></a>Antes de empezar

> [!NOTE]
> Asegúrese de hablar con su representante de Cerner y revisar la guía de integración de Cerner antes de habilitar la integración.

### <a name="prerequisites"></a>Requisitos previos

Antes de integrar el Teams EHR en su organización sanitaria, debe tener lo siguiente:

- Una suscripción activa para Microsoft Teams independiente del conector EHR (solo se aplica al realizar pruebas en un entorno EHR de producción).
- Los usuarios tienen una licencia Microsoft 365 o Office 365 que incluye Teams reuniones.
- Teams se adopta y se usa en su organización sanitaria.
- Sus sistemas cumplen todos los [requisitos de software y explorador](../../hardware-requirements-for-the-teams-app.md) para Teams.
- Versión cerner de noviembre de 2018 o posterior

## <a name="set-up-the-teams-ehr-connector"></a>Configurar el conector Teams EHR

Para la configuración del conector, debe realizar las siguientes acciones:

- [Iniciar el portal de configuración del conector EHR](#launch-the-ehr-connector-configuration-portal)
- [Escribir información de configuración](#enter-configuration-information)
- [Habilitar notificaciones SMS (opcional)](#enable-sms-notifications-optional)
- [Revisar y finalizar la configuración](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Estos pasos deben ser completados por el Microsoft 365 global de su organización.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Iniciar el portal de configuración del conector EHR

Para empezar, el administrador de Microsoft 365 inicia el portal de configuración del conector [EHR](https://ehrconnector.teams.microsoft.com) e inicia sesión con sus credenciales de Microsoft.

El Microsoft 365 puede configurar un único departamento o varios departamentos para probar la integración. Configure la dirección URL de prueba y producción en el portal de configuración. Asegúrese de probar la integración desde el entorno de prueba de Cerner antes de pasar a la producción.

### <a name="enter-configuration-information"></a>Escribir información de configuración

A continuación, para configurar la integración, el administrador de Microsoft 365 agrega una dirección URL base de recursos de interoperabilidad de estado rápido (FHIR) de Cerner y especifica el entorno. Configure tantas direcciones URL base de FHIR como sea necesario, según las necesidades de su organización y los entornos que desee probar.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Captura de pantalla de la página Información de configuración del Teams de configuración del conector EHR." lightbox="media/ehr-admin-cerner-configuration.png":::

- La dirección URL base de FHIR es una dirección estática que corresponde al punto de conexión de la API FHIR del servidor. Una dirección URL de ejemplo es `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Puede configurar la integración para entornos de prueba y producción. Para la configuración inicial, le recomendamos que configure el conector desde un entorno de prueba antes de pasar a producción.

Después de validar la dirección URL base de FHIR y seleccionar el entorno, elija **Listo**. A continuación, agregue más DIRECCIONES URL base de FHIR para otros entornos, según sea necesario.

Seleccione **Siguiente** para ir al paso siguiente.

### <a name="enable-sms-notifications-optional"></a>Habilitar notificaciones SMS (opcional)

Complete este paso si su organización quiere que Microsoft administre las notificaciones DE SMS para sus pacientes. Al habilitar las notificaciones POR SMS, los pacientes recibirán mensajes de confirmación y aviso para las visitas programadas.

Para habilitar las notificaciones SMS, Microsoft 365 administrador hace lo siguiente:

1. En la página notificaciones SMS, seleccione ambas casillas de consentimiento para:

    - Permitir que Microsoft envíe notificaciones SMS a los pacientes en nombre de su organización.
    - Confirme que garantizará que los asistentes han dado su consentimiento para enviar y recibir mensajes SMS.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Captura de pantalla de la página de notificaciones SMS, que muestra las casillas de consentimiento y la opción de generar un número de teléfono." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. En **Sus números de teléfono**, seleccione **Generar un nuevo número de teléfono** para generar un número de teléfono para su organización. Al hacerlo, se inicia el proceso para solicitar y generar un nuevo número de teléfono. Este proceso puede tardar hasta 2 minutos en completarse.

    Después de generar el número de teléfono, se muestra en la pantalla. Este número se usará para enviar confirmaciones de SMS y avisos a sus pacientes. El número se ha aprovisionado pero aún no está vinculado a la dirección URL base de FHIR. Lo hará en el paso siguiente.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Captura de pantalla que muestra un ejemplo del número de teléfono que se genera." lightbox="media/ehr-admin-cerner-phone-number.png":::

    Elija **Listo** y, a continuación, **seleccione Siguiente**.

1. Para vincular el número de teléfono a una dirección URL base de FHIR, **en Teléfono número** en la sección configuración de **SMS**, seleccione el número. Haga esto para cada dirección URL base de FHIR para la que desea habilitar las notificaciones SMS.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Captura de pantalla que muestra cómo vincular un número de teléfono a una dirección URL base de FHIR." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Si es la primera vez que configura el conector, verá la dirección URL base de FHIR que se introdujo en el paso anterior. El mismo número de teléfono se puede vincular a varias DIRECCIONES URL base de FHIR, lo que significa que los pacientes recibirán notificaciones SMS del mismo número de teléfono para diferentes organizaciones y/o departamentos.

     Seleccione **Siguiente**.

### <a name="review-and-finish-the-configuration"></a>Revisar y finalizar la configuración

Se le presentarán los registros de integración para el lanzamiento de pacientes y proveedores. Estos registros son necesarios para completar la configuración de visitas virtuales en Cerner. Para obtener más información, vea la Cerner-Microsoft Teams de integración de telesalud.

> [!NOTE]
> En cualquier momento, el Microsoft 365 puede iniciar sesión en el portal de configuración para ver los registros de integración y cambiar la configuración, si es necesario.

## <a name="launch-teams-virtual-visits"></a>Iniciar Teams visitas virtuales

Después de completar los pasos del conector EHR y los pasos de configuración de Cerner, su organización está lista para admitir las visitas de vídeo con Teams.

### <a name="virtual-visits-prerequisites"></a>Requisitos previos de visitas virtuales

- Los sistemas deben cumplir todos los [requisitos de software y explorador](../../hardware-requirements-for-the-teams-app.md) para Teams.
- Completó la configuración de integración entre la organización de Cerner y su Microsoft 365 organización.

### <a name="provider-experience"></a>Experiencia del proveedor

Los proveedores de salud de su organización pueden unirse a las visitas Teams desde el portal de PowerChart. El proveedor debe ir al consejo del paciente donde la Teams está disponible.

Desde allí, el proveedor puede ver la información de las visitas, unirse a las visitas y enviar el vínculo de la reunión. Después del inicio de sesión único, el proveedor se llevará directamente a la cita virtual en Teams.

Características principales de la experiencia del proveedor:

- Los proveedores pueden unirse a las visitas con exploradores compatibles o Teams aplicación.
- Los proveedores pueden usar todas las características Teams reunión, incluido el uso compartido de pantalla, el fondo personalizado y la grabación.
- Los proveedores pueden ver actualizaciones en tiempo real de los pacientes que se conectan a una visita para una cita determinada en PowerChart.
- La información del proveedor no es visible para los pacientes durante la visita.

> [!NOTE]
> Cualquier información que se haya introducido en el chat de reunión que sea necesaria para fines de continuidad o retención de registros médicos debe ser descargada, copiada y anotada por el proveedor de atención sanitaria. El chat no constituye un registro médico legal ni un conjunto de registros designado. Los mensajes del chat se almacenan en función de la configuración creada por el Microsoft Teams usuario.

### <a name="patient-experience"></a>Experiencia del paciente

El conector permite que los pacientes se unan a las visitas a través de un vínculo en el mensaje de texto SMS. En el momento de la cita, los pacientes pueden iniciar una visita pulsando el vínculo en el mensaje de texto SMS.

Características clave de la experiencia del paciente

- Los pacientes pueden unirse a las visitas de exploradores web modernos en equipos de escritorio y móviles [sin tener que instalar la Teams aplicación](../mobile-browser-join.md).
- Los pacientes pueden unirse a las visitas con un solo clic y no se requiere ninguna otra cuenta o inicio de sesión.
- No es necesario que los pacientes creen una cuenta de Microsoft ni inicien sesión para iniciar una visita.
- Los pacientes se colocan en una sala de espera hasta que el proveedor se une y los admite.
- Los pacientes pueden probar el vídeo y el micrófono en la sala de espera antes de unirse a la visita.

## <a name="privacy-and-location-of-data"></a>Privacidad y ubicación de los datos

Teams integración en sistemas EHR optimiza la cantidad de datos que se usan y almacenan durante la integración y los flujos de visitas virtuales. La solución sigue los principios generales de privacidad y administración de datos de Teams, y las directrices estipuladas en Privacidad de Teams.

El Teams EHR no almacena ni transfiere ningún dato personal identificable ni ningún registro de salud de pacientes o proveedores de salud desde el sistema EHR. Los únicos datos que almacena el conector EHR son el id. único del usuario de EHR, que se usa durante la Teams de la reunión.

La identificación única del usuario de EHR se almacena en una de las tres regiones geográficas que se describen en [¿Dónde se almacenan los datos de los clientes de Microsoft 365?](/microsoft-365/enterprise/o365-data-locations) Todos los chats, grabaciones y otros datos compartidos en Teams por los participantes de la reunión se almacenan según las directivas de almacenamiento existentes. Para obtener más información sobre la ubicación de los datos en Teams, vea [Ubicación de los datos en Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Artículos relacionados

- [Teams de uso de visitas virtuales](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams de administrador del conector EHR](ehr-admin-reports.md)
- [Introducción a las Teams para organizaciones sanitarias](teams-in-hc.md)

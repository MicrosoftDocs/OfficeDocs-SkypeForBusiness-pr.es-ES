---
title: Teams para visitas virtuales
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
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
description: Utilice Microsoft Teams para configurar el sistema de visitas virtuales
ms.openlocfilehash: 3ba0ff974f9a8381eab054bb92468762dc1d8cc8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859737"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Visitas virtuales con Teams: integración en EHR

Microsoft Teams El conector de registro de salud electrónico (EHR) facilita a los médicos iniciar una visita virtual a pacientes o consultas con otro proveedor en Teams directamente desde el sistema EHR. Integrado en la nube de Microsoft 365, Microsoft Teams permite colaborar y comunicarse de forma sencilla y segura con herramientas de chat, vídeo, voz y salud en un único sitio central compatible con el cumplimiento de la ley HIPAA, la certificación HITECH y mucho más.
Con la plataforma de comunicación y colaboración de Teams, los profesionales de la medicina pueden poner fin fácilmente al desorden de los sistemas fragmentados y así dedicar su tiempo a proporcionar la mejor atención posible. Microsoft Teams El conector registro de estado electrónico (EHR) puede:

- Inicie Teams visitas virtuales desde el sistema EHR del proveedor con un flujo de trabajo clínico integrado.
- Permitir que los pacientes se unan Teams visitas virtuales desde el portal del paciente.
- Vuelva a escribir metadatos en el sistema EHR con respecto Teams visitas virtuales para grabar cuando los asistentes se conecten y se desconecten y habiliten la auditoría automática y la conservación de registros.

  Vea el vídeo sobre cómo administrar las visitas virtuales desde el portal de EHR.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>Antes de empezar

Debe asegurarse de que cumple los siguientes requisitos previos para poder integrar el conector de EHR:

- Acceso para usar la aplicación Microsoft Teams en [catálogo de App Orchard de Epic](https://apporchard.epic.com/Gallery?id=6153).

- Suscripción activa a Microsoft Cloud para el sector sanitario o suscripción a una Microsoft Teams independiente del conector EHR (solo se aplica durante las pruebas de producción).

- Los usuarios deben tener una licencia adecuada de Microsoft 365 u Office 365 que incluya reuniones de Microsoft Teams.

- Microsoft Teams debe adoptarse y usarse dentro de la organización.

- Las organizaciones deben tener la versión de Epic de noviembre de 2018 o posterior.

- Los sistemas deben cumplir todos los [requisitos previos de software y explorador web](../../hardware-requirements-for-the-teams-app.md).

También necesitará información de las siguientes personas de la organización:

- Administrador de Microsoft 365

- Analista de clientes de Epic

> [!Note]
> Revise la [integración de teleasistencia sanitaria de Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) con su especialista técnico profesional. Asegúrese de que se han completado todos los requisitos previos. 

## <a name="connector-setup"></a>Configuración del conector

Para la configuración del conector, debe realizar las siguientes acciones:

- [Iniciar el portal de configuración del conector EHR](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [Información de configuración](ehr-admin.md#configuration-information)
- [Aprobar o ver configuración](ehr-admin.md#approve-or-view-configuration)
- [Revisar y finalizar la configuración](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[Iniciar el portal de configuración del conector EHR](#launch-the-ehr-connector-configuration-portal)

Configurar su organización sanitaria para iniciar visitas virtuales con Microsoft Teams inicia iniciando el portal de configuración del conector EHR. Configure una o varias organizaciones para probar la integración. Configure la dirección URL de prueba y producción en el portal de configuración. Pruebe la integración del entorno de prueba de Epic antes de pasar a la producción.
  
- URL de configuración del conector de EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

El administrador de Microsoft 365 y el analista de clientes de Epic de su organización deben completar los pasos de información e integración en el portal de configuración. Para obtener los pasos de configuración de Epic, póngase en contacto con el recurso de especialista técnico de Epic asignado a su organización.

### <a name="configuration-information"></a>[Información de configuración](#configuration-information)

El **administrador de Microsoft 365** debe realizar este paso. El administrador de Microsoft 365 debe iniciar el portal de configuración del conector e iniciar sesión con las credenciales de Microsoft para iniciar el proceso de configuración.

Para completar este paso, el administrador de Microsoft 365 debe recibir una URL base válida de los Recursos Rápidos de Interoperabilidad en Salud (FHIR) de su especialista técnico de Epic y el nombre de usuario del analista de clientes de Epic que aprobará la configuración. El administrador de Microsoft 365 debe iniciar la página de configuración del conector e iniciar sesión con las credenciales de Microsoft para iniciar el proceso de configuración.

- La URL base de los FHIR es una dirección estática correspondiente al punto de conexión de API de los FHIR del servidor. Una dirección URL de ejemplo es `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- El nombre del aprobador de la configuración es el nombre del analista de clientes de Epic que será responsable de aprobar la configuración en el siguiente paso. El analista de clientes de Epic es una persona de su organización que tiene acceso de inicio de sesión a Epic.

  ![El nombre del aprobador de la configuración se selecciona en una lista en el conector de EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[Aprobar o ver configuración](#approve-or-view-configuration)

El analista de clientes épicos de su organización sanitaria que se agregó como aprobador ahora debe usar la misma dirección URL del conector EHR del paso anterior para iniciar sesión con sus credenciales Microsoft 365 usuario. Tras una validación correcta, se le pedirá al aprobador que inicie sesión con sus credenciales de Epic para validar la organización de Epic.

> [!Note]
> El administrador de Microsoft 365 y el analista de clientes de Epic de su organización pueden ser la misma persona. En ese caso, agregue su propio nombre de usuario como aprobador. Aun así, tendrá que iniciar sesión en Epic para validar su acceso. El inicio de sesión en Epic solo se usa para validar la URL base de los FHIR. Microsoft no almacenará credenciales ni tendrá acceso a datos de EHR con este inicio de sesión.

  ![Compruebe y apruebe la configuración de las credenciales.](../../media/approve-view-configuration.png)

Una vez que se haya iniciado sesión en Epic correctamente, el analista de clientes de Epic **debe** aprobar la configuración. Si la configuración no es correcta, el administrador de Microsoft 365 podrá modificar las configuraciones originales iniciando sesión de nuevo en el portal del conector de EHR para Microsoft. 

![Confirme que el conector de EHR está configurado y seleccione la opción para cambiar la configuración.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[Revisar y finalizar la configuración](#review-and-finish-the-configuration)

Cuando el administrador de Epic apruebe la información de configuración, se le presentarán registros de integración para el inicio de los proveedores y los pacientes. Estos registros son necesarios para completar la configuración de la visita virtual en Epic. Consulte la Guía de integración de teleasistencia sanitaria de Epic-Microsoft Teams para obtener más información.

> [!Note]  
> El analista de clientes de Epic o Microsoft 365 puede iniciar sesión en cualquier momento en el portal de configuración para ver los registros de integración y modificar la configuración de la organización, si es necesario.

![Se muestra la información de integración.](../../media/finish-configuration.png)

> [!Note]
> El proceso de aprobación debe completarlo el analista de clientes de Epic para cada URL de los FHIR configurada previamente por el administrador de Microsoft.

![Se aprueba la información de configuración.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>Iniciar las visitas virtuales de Teams

Después de completar los pasos del conector EHR y la configuración de Epic, su organización está lista para admitir las visitas de vídeo con Microsoft Teams.

### <a name="virtual-visit-prerequisites"></a>Requisitos previos de la visita virtual

- Los sistemas deben cumplir todos los [requisitos previos de software y explorador web](../../hardware-requirements-for-the-teams-app.md).

- La organización sanitaria debe haber completado la configuración entre la organización de Epic y la organización de Microsoft 365.

### <a name="provider-experience"></a>Experiencia del proveedor

Los proveedores sanitarios de su organización también pueden unirse a visitas virtuales con Microsoft Teams desde sus aplicaciones de proveedor de Epic (Hyperspace, Haiku, Canto). El botón **Iniciar visita virtual** está incorporado en el flujo del proveedor.

Características principales de la experiencia del proveedor:

- Los proveedores pueden unirse a las visitas virtuales con navegadores web compatibles o con la aplicación de Microsoft Teams.

- Los proveedores deben llevar a cabo el inicio de sesión de un solo uso con su cuenta de Microsoft 365 al unirse a una visita virtual por primera vez.

- Después del inicio de sesión único, el proveedor se le llevará directamente a la cita virtual en Microsoft Teams. (El proveedor debe haber iniciado sesión en Microsoft Teams).

- El proveedor puede ver las actualizaciones en tiempo real de los participantes que se conectan y desconectan en una cita determinada. El proveedor puede ver cuándo se conecta el paciente a una visita virtual.

  ![Experiencia del proveedor de una visita virtual con el paciente.](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>Experiencia del paciente

El conector admite a los pacientes que se unen a visitas virtuales a través de la web y la aplicación móvil de MyChart. A la hora de la cita, los pacientes pueden iniciar una visita virtual desde MyChart con el botón **Iniciar visita virtual**.

Características principales de la experiencia del paciente:

- Los pacientes pueden unirse a visitas virtuales desde exploradores web modernos en equipos de escritorio y [móviles sin la instalación de aplicaciones.](../mobile-browser-join.md)

- Los pacientes pueden unirse a las visitas virtuales con un solo clic y no se necesita ninguna otra cuenta ni inicio de sesión.

- No es necesario que los pacientes creen una cuenta de Microsoft ni que inicien sesión para iniciar una visita virtual.

- Los pacientes estarán en una sala de espera hasta que el proveedor sanitario se una a la cita y los admita a la visita virtual.

- Hay pruebas de vídeo y micrófono disponibles en la sala de espera antes de unirse a la visita virtual.

  ![Experiencia del paciente de la visita virtual.](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku y Canto son marcas comerciales de Epic Systems Corporation.

### <a name="privacy-and-location-of-data"></a>Privacidad y ubicación de los datos

La integración de Teams en sistemas de EHR optimiza la cantidad de datos que se usan y almacenan durante los flujos de integración y de visita virtual. La solución sigue los principios generales de privacidad y administración de datos de Teams, y las directrices estipuladas en Privacidad de Teams.

El conector de EHR para Microsoft Teams no almacena ni transfiere ningún dato personal de identificación ni ningún registro médico de pacientes o proveedores sanitarios desde el sistema de EHR. El único dato que almacena el conector de EHR es la identificación única del usuario de EHR, que se usa durante la configuración de la reunión de Teams. La identificación única del usuario de EHR se almacena en una de las tres regiones geográficas que se describen en [¿Dónde se almacenan los datos de los clientes de Microsoft 365?](/microsoft-365/enterprise/o365-data-locations) Todos los chats, las grabaciones y demás datos que introduzcan en Teams los participantes de la reunión se almacenan según las directivas de almacenamiento existentes. Si desea obtener más información sobre la ubicación de los datos en Microsoft Teams, visite [Ubicaciones de los datos en Teams](../../location-of-data-in-teams.md).

## <a name="related-topics"></a>Temas relacionados

[Teams visitas virtuales](ehr-admin-reports.md)
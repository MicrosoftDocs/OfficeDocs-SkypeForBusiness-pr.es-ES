---
title: Teams para visitas virtuales
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usar Microsoft Teams para configurar su sistema de visitas virtuales
ms.openlocfilehash: 2d2be135668bcc45f0054e987a23845e3245c38e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125783"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Visitas virtuales con Teams: integración en EHR

El conector del registro sanitario electrónico (EHR) de Microsoft Teams facilita a los médicos iniciar una visita virtual a un paciente o una consulta con otro proveedor en Teams directamente desde el sistema EHR. Microsoft Teams, integrado en la nube de Microsoft 365, permite una colaboración y comunicación sencillas y seguras con herramientas de chat, vídeo, voz y salud en un único hub que cumple con la certificación HIPAA, HITECH y mucho más.
La plataforma de comunicación y colaboración de Teams facilita a los médicos cortar el desorden de sistemas fragmentados para que puedan dedicar tiempo a proporcionar la mejor atención posible. El conector del registro de salud electrónico (EHR) de Microsoft Teams puede:
- Inicie las visitas virtuales de Teams desde los portales de proveedores y pacientes.
- Reescriba los metadatos EHR en los eventos de conexión y desconexión para habilitar la auditoría automática y la conservación de registros.
- Inténtese en flujos de trabajo existentes de médicos y pacientes al tiempo que les permite usar Microsoft Teams.

  Vea el vídeo sobre cómo administrar las visitas virtuales desde el portal de EHR.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>Antes de comenzar

Debe asegurarse de que tiene los siguientes requisitos previos para poder integrar el conector EHR:

- Acceso para usar en la aplicación Microsoft Teams en [El catálogo de catálogos de aplicaciones de Épico.](https://apporchard.epic.com/Gallery?id=6153)

- Suscripción activa a Microsoft Cloud para el ámbito sanitario o suscripción a la oferta independiente de Microsoft Teams EHR Connector (solo se aplica durante las pruebas de producción).

- Los usuarios deben tener una licencia adecuada de Microsoft 365 u Office 365 que incluya las reuniones de Microsoft Teams.

- Microsoft Teams debe adoptarse y usarse dentro de la organización.

- Las organizaciones deben tener la versión Épicos de noviembre de 2018 o posterior.

- Los sistemas deben cumplir todos los requisitos [previos del software y del explorador.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)

También necesitará información de las siguientes personas de su organización:

- Administrador de Microsoft 365

- Analista de clientes épicos

> [!Note]
> Solicite a su especialista técnico épico que proporcione la guía de Epic-Microsoft integración de Telehealth de Teams en el Catálogo de soluciones épicos.

## <a name="connector-setup"></a>Configuración del conector

La configuración del conector requiere que:

- [Iniciar el portal de configuración del conector EHR](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [Información de configuración](ehr-admin.md#configuration-information)
- [Aprobar o ver la configuración](ehr-admin.md#approve-or-view-configuration)
- [Revisar y finalizar la configuración](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[Iniciar el portal de configuración del conector EHR](#launch-the-ehr-connector-configuration-portal)

La configuración de su organización sanitaria para iniciar visitas virtuales con Microsoft Teams se inicia iniciando el portal de configuración de EHR Connector. Configure una o varias organizaciones para probar la integración. Configure la dirección URL de prueba y producción en el portal de configuración. Pruebe la integración del entorno de prueba de Épico antes de pasar a la producción.
  
- URL de configuración del conector EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

El administrador de Microsoft 365 y analista de clientes De su organización deben completar los pasos de información e integración en el portal de configuración. Para ver los pasos de configuración Épico, póngase en contacto con el recurso de especialista técnico épico asignado a su organización.

### <a name="configuration-information"></a>[Información de configuración](#configuration-information)

Este paso lo completará el administrador **de Microsoft 365.** El administrador de Microsoft 365 debe iniciar el portal de configuración del conector e iniciar sesión con credenciales de Microsoft para iniciar el proceso de configuración.

Para completar este paso, el administrador de Microsoft 365 debe recibir una DIRECCIÓN URL válida de la base de recursos de interoperabilidad de estado rápido (FCONTR) de su especialista épico y el nombre de usuario del analista de clientes Épico que aprobará la configuración. El administrador de Microsoft 365 debe iniciar la página de configuración del conector e iniciar sesión con credenciales de Microsoft para iniciar el proceso de configuración.

- La dirección URL de la base FCONTR es una dirección estática que corresponde al extremo de la API F LDAP del servidor. Una dirección URL de ejemplo `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` es.

- El nombre del aprobador de configuración es el nombre del analista de clientes épicos que será el responsable de aprobar la configuración en el siguiente paso. El analista de clientes épicos es una persona de su organización con acceso de inicio de sesión a Épico.

  ![El nombre del aprobador de configuración se selecciona de una lista en el conector EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[Aprobar o ver la configuración](#approve-or-view-configuration)

La analista de clientes épicos de su organización sanitaria que se agregó como aprobador ahora debe usar la misma URL del conector EHR del paso anterior para iniciar sesión con sus credenciales de Microsoft 365. Después de la validación correcta, se le pedirá al aprobador que inicie sesión con sus credenciales épicos para validar la organización épicos.

> [!Note]
> El administrador de Microsoft 365 y analista de clientes Épicos de su organización pueden ser la misma persona. En ese caso, agregue su propio nombre de usuario como aprobador. Igualmente tendrás que iniciar sesión en Épico para validar tu acceso. El inicio de sesión épico solo se usa para validar la dirección URL de la base FCONTR. Microsoft no almacenará credenciales ni accederá a datos EHR con este inicio de sesión.

  ![Compruebe y apruebe la configuración de credenciales.](../../media/approve-view-configuration.png)

Después de un inicio de sesión épico correcto, el analista de clientes épicos **debe** aprobar la configuración. Si la configuración no es correcta, el administrador de Microsoft 365 podrá modificar las configuraciones originales iniciando sesión de nuevo en el portal del conector EHR de Microsoft. 

![Confirme que el conector EHR está configurado y la opción de cambiar la configuración.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[Revisar y finalizar la configuración](#review-and-finish-the-configuration)

Cuando el administrador épico apruebe la información de configuración, se le presentarán registros de integración para el lanzamiento del paciente y el proveedor. Estos registros son necesarios para completar la configuración de visita virtual en Épico. Consulte la guía Epic-Microsoft integración de Telehealth de Teams para obtener más información.

> [!Note]  
> En cualquier momento, el analista de clientes de Microsoft 365 o Épicos puede iniciar sesión en el portal de configuración para ver los registros de integración y modificar la configuración de la organización, si es necesario.

![Se muestra la información de integración.](../../media/finish-configuration.png)

> [!Note]
> El proceso de aprobación lo debe completar el analista de clientes épicos para cada URL de FCONTR configurada por el administrador de Microsoft anteriormente.

![La información de configuración se ha aprobado.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>Iniciar visitas virtuales de Teams

Después de completar los pasos del conector EHR y la configuración épicos, su organización está lista para admitir las visitas de vídeo con Microsoft Teams.

### <a name="virtual-visit-prerequisites"></a>Requisitos previos de la visita virtual

- Los sistemas deben cumplir todos los requisitos [previos del software y del explorador.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)

- La organización sanitaria debe haber completado la configuración entre la organización Épicos y la organización de Microsoft 365.

### <a name="provider-experience"></a>Experiencia del proveedor

Los proveedores de salud de su organización también pueden unirse a visitas virtuales con Microsoft Teams desde sus aplicaciones de proveedor de épicos (Hyperspace, Havelo, Canton). El **botón Comenzar visita virtual** está insertado en el flujo del proveedor.

Características clave de la experiencia del proveedor:

- Los proveedores pueden unirse a visitas virtuales mediante exploradores compatibles o la aplicación Microsoft Teams.

- Los proveedores deben iniciar sesión una sola vez con su cuenta de Microsoft 365 al unirse a una visita virtual por primera vez.

- Después del inicio de sesión único, el proveedor se le llevará directamente a la cita virtual en Microsoft Teams. (El proveedor debe haber iniciado sesión en Microsoft Teams).

- El proveedor puede ver actualizaciones en tiempo real de los participantes que se conectan y se desconectan para una cita determinada. El proveedor puede ver cuándo está conectado el paciente a una visita virtual.

  ![Experiencia del proveedor de una visita virtual con un paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>Experiencia del paciente

El conector admite a los pacientes que se unen a visitas virtuales a través de MyChart Web y dispositivos móviles. Cuando se haga la cita, los pacientes pueden iniciar una visita virtual desde MyChart con el **botón Comenzar visita virtual.**

Características clave de la experiencia del paciente:

- Los pacientes pueden unirse a visitas virtuales desde exploradores web modernos en equipos de escritorio y dispositivos móviles sin instalación de aplicaciones.

- Los pacientes pueden unirse a visitas virtuales con un solo clic y no se requiere otra cuenta ni inicio de sesión.

- No es necesario que los pacientes creen una cuenta de Microsoft ni que inicien sesión para iniciar una visita virtual.

- Los pacientes se colocarán en una sala de espera hasta que el proveedor de salud se una a la cita y los admita en la visita virtual.

- Las pruebas del vídeo y el micrófono están disponibles en la sala de espera antes de unirse a la visita virtual.

  ![Experiencia del paciente con la visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Épico, MyChart, Halio y Canton son marcas comerciales de Épico Systems Corporation.

### <a name="privacy-and-location-of-data"></a>Privacidad y ubicación de los datos

La integración de Teams en sistemas EHR optimiza la cantidad de datos que se usan y almacenan durante los flujos de integración y visitas virtuales. La solución sigue los principios y directrices generales de privacidad y administración de datos de Teams que se describen en Privacidad de Teams.

El conector EHR de Microsoft Teams no almacena ni transfiere ningún dato personal identificable ni ningún registro de salud de pacientes o proveedores sanitarios desde el sistema EHR. Los únicos datos que se almacenan con el conector EHR son el identificador único del usuario de EHR, que se usa durante la configuración de reuniones de Teams. El id. único del usuario de EHR se almacena en una de las tres regiones geográficas descritas en la que se almacenan los datos de clientes de [Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) Todos los chats, las grabaciones y otros datos escritos en Teams por los participantes de la reunión se almacenan según las directivas de almacenamiento existentes. Si desea obtener más información sobre la ubicación de los datos en Microsoft Teams, visite [Ubicaciones de datos en Teams.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)

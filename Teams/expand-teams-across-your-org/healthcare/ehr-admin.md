---
title: Teams para visitas virtuales
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usar Microsoft Teams para configurar el sistema de visitas virtuales
ms.openlocfilehash: dcf852486d6a7fbace23bea5fb8610c62bdc7e4f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766723"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Visitas virtuales con Teams: integración en EHR

El conector de mantenimiento Electrónico de Microsoft Teams (EHR) facilita el inicio de una visita de pacientes virtuales o la consulta con otro proveedor en Teams directamente desde el sistema HCI. Basado en la nube de Microsoft 365, Microsoft Teams permite una colaboración y una comunicación segura y sencilla con las herramientas de chat, vídeo, voz y atención médica en un único Hub que admite el cumplimiento de la normativa HIPAA, la certificación de alta tecnología y más.

La plataforma de comunicación y colaboración de Teams facilita a los médicos el corte en el desorden de los sistemas fragmentados para que puedan gastar tiempo proporcionando la mejor atención posible. El conector de estado electrónico (EHR) de Microsoft Teams puede:

- Iniciar visitas virtuales de equipos desde portales de proveedores y de pacientes.

- Vuelva a escribir los metadatos de EHR en los eventos Connect y Disconnect para habilitar la auditoría automática y la conservación de registros.

- Integrarse en flujos de trabajo médicos y pacientes existentes, a la vez que permite que usen Microsoft Teams.

## <a name="before-you-begin"></a>Antes de comenzar

Para poder integrar el conector de EHR, debe asegurarse de que tiene los siguientes requisitos previos:

- Suscripción activa a la nube de Microsoft para el cuidado de la salud o suscripción a la oferta independiente del conector de Microsoft Teams HCI.

- Los usuarios deben tener una licencia adecuada de Microsoft 365 o de Office 365 que incluya reuniones de Microsoft Teams.

- Microsoft Teams debe adoptarse y utilizarse dentro de la organización.

- Las organizaciones deben tener una versión de noviembre de 2018 o posterior.

- Sus sistemas deben cumplir con todos los [requisitos previos de software y navegador](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).

También necesitará información de las siguientes personas de su organización:

- Administrador de Microsoft 365

- Administrador de la epopeya

> [!Note]
> Solicite a su administrador de Epic que proporcione la guía de integración de TeleHealth Epic-Microsoft Teams disponible en el Marketplace de la epopeya.

## <a name="connector-setup"></a>Configuración del conector

La configuración del conector requiere que:

- [Iniciar el portal de configuración del conector de EHR](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [Configurar información de la organización del proveedor](ehr-admin.md#configure-provider-organization-information)
- [Comprobar y aprobar la configuración](ehr-admin.md#verify-and-approve-the-configuration)
- [Revisar y finalizar la configuración](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[Iniciar el portal de configuración del conector de EHR](#launch-the-ehr-connector-configuration-portal)

Para configurar su organización de salud para iniciar visitas virtuales con Microsoft Teams, inicie el portal de configuración del conector de EHR. Use la dirección URL de prueba para configurar el conector para el entorno de prueba de Epic. Use la dirección URL de producción cuando esté listo para habilitar el entorno de producción de la epopeya.
  
- Entorno de prueba [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)
- Entorno de producción [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

El administrador de Microsoft 365 administrador y Epic de la organización debe completar la información y los pasos de integración en el portal de configuración. Para conocer los pasos de configuración de la epopeya, póngase en contacto con el recurso Epic asignado a su organización.

### <a name="configure-provider-organization-information"></a>[Configurar información de la organización del proveedor](#configure-provider-organization-information)

Este paso debe completarse con el administrador de Microsoft 365. El administrador de Microsoft 365 debe iniciar el portal de configuración del conector e iniciar sesión con las credenciales de Microsoft para iniciar el proceso de configuración.

Para completar este paso, el administrador de Microsoft 365 debe recibir una dirección URL base válida de interoperabilidad de mantenimiento rápido (FHIR) del administrador de Microsoft 365 y el nombre de usuario del administrador de la epopeya que aprobará la configuración. El administrador de Microsoft 365 debe iniciar la página de configuración del conector e iniciar sesión con las credenciales de Microsoft para iniciar el proceso de configuración.

- La dirección URL base de FHIR es una dirección estática correspondiente a su extremo de la API de FHIR de servidor. Una dirección URL de ejemplo es [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) .

- Nombre del aprobador de configuración es el nombre del administrador del sistema Epic que será responsable de aprobar la configuración.

  ![El nombre del aprobador de configuración se selecciona de una lista en el conector HCI.](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[Comprobar y aprobar la configuración](#verify-and-approve-the-configuration)

El administrador de la epopeya de su organización de cuidado de la salud que se agregó como aprobador debe usar ahora la misma URL de conectores de EHR del paso anterior para iniciar sesión con sus credenciales de 365 de Microsoft. Después de una validación correcta, se le solicitará al aprobador que inicie sesión con sus credenciales de la epopeya para validar la organización de la epopeya.

> [!Note]
> El administrador de Microsoft 365 admin y Epic puede ser la misma persona. En ese caso, agregue su propio nombre de usuario como aprobador en el primer paso. Seguirá necesitando iniciar sesión en Epic para validar el acceso. El inicio de sesión de Epic solo se usa para validar la dirección URL base de FHIR. Microsoft no almacenará credenciales ni accederá a datos de EHR con este inicio de sesión.

  ![Comprobar y aprobar la configuración de credenciales.](../../media/ehc-provider-2.png)

Después de un inicio de sesión de la epopeya, el administrador de la Epic **debe** aprobar la configuración. Si la configuración no es correcta, el administrador de Microsoft 365 tendrá la capacidad de modificar las configuraciones originales iniciando sesión en el portal de conector de Microsoft EHR.

![Confirme que el conector HCI está configurado y opción para cambiar la configuración.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[Revisar y finalizar la configuración](#review-and-finish-the-configuration)

Cuando el administrador de la epopeya apruebe la información de configuración, se le presentarán los registros de integración para el lanzamiento de pacientes y proveedores. Estos registros son necesarios para completar la configuración de la visita virtual en Epic. Para obtener más información, consulta la guía de integración de TeleHealth de Epic-Microsofts Teams.

> [!Note]  
> En cualquier momento, el administrador de Microsoft 365 o Epic puede iniciar sesión en el portal de configuración para ver los registros de integración y modificar la configuración de la organización, si es necesario.

![Se muestra la información de integración.](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a>Iniciar visitas virtuales a equipos

Después de completar los pasos del conector HCI y la configuración de la epopeya, su organización está preparada para admitir las visitas de video con Microsoft Teams.

### <a name="virtual-visit-prerequisites"></a>Requisitos previos de la visita virtual

- Sus sistemas deben cumplir con todos los [requisitos previos de software y navegador](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).

- La organización de cuidado de la salud debe haber completado la configuración entre la organización de la epopeya y la organización de Microsoft 365.

### <a name="provider-experience"></a>Experiencia de proveedor

Los proveedores de asistencia sanitaria de su organización también pueden unirse a visitas virtuales con Microsoft Teams desde sus aplicaciones de proveedor EPIC (hiperespacio, Haiku, canto). El botón **iniciar visita virtual** está incrustado en el flujo del proveedor.

Características clave de la experiencia de proveedor:

- Los proveedores pueden unirse a las visitas virtuales mediante exploradores compatibles o la aplicación Microsoft Teams.

- Los proveedores deben realizar un inicio de sesión único con su cuenta de Microsoft 365 al unirse a una visita virtual por primera vez.

- Después de iniciar sesión una vez, el proveedor se redirigirá directamente a la cita virtual en Microsoft Teams. (El proveedor debe haber iniciado sesión en Microsoft Teams).

- El proveedor puede ver las actualizaciones en tiempo real de los participantes que se conectan y desconectan para una cita determinada. El proveedor puede ver cuándo está conectado el paciente a una visita virtual.

  ![Experiencia de proveedor de una visita virtual con un paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>Experiencia del paciente

El conector permite a pacientes unir a visitas virtuales a través de MyChart web y móviles. En el momento de la cita, los pacientes pueden iniciar una visita virtual de MyChart con el botón **comenzar virtual** .

Características clave de la experiencia del paciente:

- Los pacientes pueden unirse a visitas virtuales desde los exploradores Web modernos en el escritorio y en el móvil sin la instalación de la aplicación.

- Los pacientes pueden unirse a visitas virtuales con un solo clic y no se necesita ninguna cuenta o inicio de sesión adicional.

- No es necesario que los pacientes creen una cuenta de Microsoft ni inicien sesión para iniciar una visita virtual.

- Los pacientes se pondrán en una sala de espera hasta que el proveedor de atención médica se una a la cita y los pueda ir a la visita virtual.

- Las pruebas del video y el micrófono están disponibles en la sala de recepción antes de unirte a la visita virtual.

  ![Experiencia del paciente de la visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku y canto son marcas comerciales de Epic Systems Corporation.

### <a name="privacy-and-location-of-data"></a>Privacidad y ubicación de los datos

La integración de equipos en sistemas HCI optimiza la cantidad de datos que se usan y almacenan durante los flujos de integración y de visitas virtuales. La solución sigue los principios de la privacidad y la administración de datos de todos los equipos, así como las directrices descritas en privacidad de Teams.

El conector de Microsoft Teams EHR no almacena ni transfiere datos personales identificables o registros sanitarios de pacientes o de proveedores sanitarios del sistema HCI. Los únicos datos que se almacenan en el conector HCI son el identificador único del usuario de HCI, que se usa durante la configuración de reunión de Teams. El identificador exclusivo del usuario de HCI se almacena en una de las tres regiones geográficas que se describen en el artículo [donde se almacenan los datos de los clientes de Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) . Todos los chats, las grabaciones y otros datos que los participantes de la reunión hayan introducido se almacenan según las directivas de almacenamiento existentes. Si desea obtener más información sobre la ubicación de los datos en Microsoft Teams, visite [ubicaciones de datos en Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).

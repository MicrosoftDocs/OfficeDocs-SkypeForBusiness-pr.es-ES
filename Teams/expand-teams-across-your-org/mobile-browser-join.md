---
title: Administrar la experiencia de combinación para Teams visitas virtuales en exploradores móviles
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: Obtenga información sobre la experiencia de unirse Teams visitas virtuales en exploradores móviles.
ms.openlocfilehash: 5c4b0f7ac9011d12d12e3076f900880292e72eb1
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288568"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>Administrar la experiencia de combinación para Teams visitas virtuales en exploradores móviles

Microsoft Teams facilita que los usuarios se unan a citas en sus dispositivos móviles sin tener que descargar Teams. Para disfrutar de una experiencia más fluida, los asistentes pueden unirse a citas como visitas sanitarias, consultas financieras, horas de oficina de educadores, etc., desde un explorador móvil. Los asistentes no necesitan instalar la aplicación Teams móvil en sus dispositivos móviles Android o iOS.

Con unirse al explorador móvil, cuando un asistente se une a una cita desde un dispositivo móvil, no se le pedirá que descargue Teams. En su lugar, Teams en un explorador móvil, donde el asistente puede seleccionar **Unirse ahora** para unirse. Con esta característica, tenga en cuenta que si Teams ya está instalado en el dispositivo móvil de un asistente, Teams se abrirá en un explorador móvil y no en la aplicación.

Actualmente, la combinación de exploradores móviles está disponible para las citas programadas a través de lo siguiente:

- [La aplicación Bookings](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- Microsoft Teams de registros de estado electrónicos (EHR)

  - Integración con [Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Integración [con Épico EHR](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>Configurar la combinación de exploradores móviles

### <a name="appointments-scheduled-through-the-bookings-app"></a>Citas programadas a través de la aplicación Bookings

Los programadores de su organización pueden activar esta característica para tipos de citas específicos y para citas individuales en la aplicación Bookings.

Una vez activada esta característica, el correo electrónico de confirmación o el texto SMS que se envía a los asistentes contendrá un vínculo de unirse a la reunión que se abrirá Teams en un explorador móvil. En dispositivos móviles Android, Teams se abre en Chrome. En dispositivos móviles iOS, Teams se abre en Safari.

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>Activar la combinación del explorador móvil para un tipo de cita

En Bookings, vaya a **Configuración** >  **Appointment,** seleccione un tipo de cita [y,](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) después, active Permitir que los asistentes se unan desde **un explorador móvil**. De este modo, se permite la combinación de exploradores móviles para todas las citas de este tipo.

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Captura de pantalla de la configuración Permitir que los asistentes se unan desde un explorador móvil para los tipos de citas en la aplicación Bookings":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>Activar la combinación del explorador móvil para una cita individual

En Bookings, seleccione **Nueva reserva** y, a continuación, active Permitir que los **asistentes se unan desde un explorador móvil**.

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Captura de pantalla de la configuración Permitir que los asistentes se unan desde un explorador móvil en el nuevo formulario de reserva en la aplicación Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Citas programadas a través del conector Teams EHR

No es necesario configurarlo ni usted ni su personal.

**Integración con Cerner EHR**: el Teams EHR permite a los pacientes unirse a visitas virtuales a través de dispositivos móviles. En el momento de la cita, los pacientes pueden unirse a una visita virtual pulsando el vínculo en el mensaje de texto SMS. El paciente elige el explorador que quiere y, a continuación, Teams en ese explorador.

**Integración con Épico EHR**: el Teams ehr es compatible con los pacientes que se unen a las visitas virtuales a través de la web y el móvil de MyChart. En el momento de la cita, los pacientes pueden iniciar una visita virtual desde MyChart con el **botón Iniciar visita virtual** . El paciente elige el explorador que quiere y, a continuación, Teams en ese explorador.

## <a name="supported-mobile-browsers"></a>Exploradores móviles compatibles

Estos son los exploradores móviles compatibles actualmente. Se admite la última versión más dos versiones anteriores, a menos que se indique lo contrario.

|Plataforma  |Chrome |Safari |Borde (Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|macOS     |         |  &#x2714; &sup2;    |         |

&sup1; Las aplicaciones de iOS en Safari no pueden seleccionar dispositivos de micrófono y altavoz. Por ejemplo, Bluetooth dispositivos. Esta es una limitación del sistema operativo, que controla la selección predeterminada del dispositivo.

&sup2; Safari 14+ y macOS 11+ son necesarios para el soporte de vídeo saliente.

## <a name="things-to-consider"></a>Cosas a tener en cuenta

El miembro del personal que realiza la visita virtual puede compartir su pantalla desde su cliente Teams de escritorio, móvil o web con un asistente que se une desde un explorador móvil. Sin embargo, los asistentes no pueden compartir su pantalla desde un explorador móvil.

> [!NOTE]
> Estamos agregando más funcionalidades a la experiencia de unirse a la reunión en futuras versiones de Teams, así que vuelva a consultar la información más actualizada. Para mantenerse al tanto de las próximas Teams características, consulte el [mapa Microsoft 365 ruta](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="related-articles"></a>Artículos relacionados

- [Visitas virtuales con Teams y la aplicación Bookings](bookings-virtual-visits.md)
- [Crear un tipo de cita de Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Unirse a una cita de Bookings como asistente](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Visitas virtuales con Teams: integración en Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Visitas virtuales con Teams: integración en Épico EHR](healthcare/ehr-admin.md)

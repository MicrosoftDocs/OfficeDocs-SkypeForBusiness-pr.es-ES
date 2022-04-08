---
title: Administrar la experiencia de unión para Teams visitas virtuales en exploradores
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
description: Obtenga información sobre la experiencia de unión para Teams visitas virtuales en exploradores.
ms.openlocfilehash: 276e33b16972f0543566014adf264fd12e45c4ae
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703753"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-browsers"></a>Administrar la experiencia de unión para Teams visitas virtuales en exploradores

Microsoft Teams facilita que los usuarios se unan a citas virtuales sin tener que descargar Teams. Para obtener una experiencia más fluida, los asistentes pueden unirse a citas, como visitas médicas y consultas financieras, desde un explorador móvil o de escritorio. Los asistentes no necesitan instalar la aplicación de Teams en su dispositivo.

Con la unión del explorador, cuando un asistente se une a una cita, no se le pide que descargue Teams. En su lugar, Teams se abre en un explorador, donde el asistente puede seleccionar **Unirse ahora** para unirse. Con esta característica, tenga en cuenta que si Teams ya está instalado en el dispositivo, Teams se abrirá en un explorador y no en la aplicación.

Actualmente, la unión al explorador está disponible para las citas programadas a través de los siguientes pasos:

- [La aplicación Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams conector de registro médico electrónico (EHR)

  - Integración con [Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Integración con [Epic EHR](healthcare/ehr-admin.md)

## <a name="set-up-browser-join"></a>Configurar la unión al explorador

### <a name="appointments-scheduled-through-the-bookings-app"></a>Citas programadas a través de la aplicación Bookings

Los programadores de su organización pueden activar esta característica para tipos de citas específicos y para citas individuales en la aplicación Bookings.

Después de activar esta característica, el correo electrónico de confirmación o el texto de SMS que se envía a los asistentes contendrá un vínculo para unirse a la reunión que abre Teams en un explorador móvil o de escritorio. Para obtener una lista de los exploradores compatibles, consulte [Exploradores compatibles](#supported-browsers).

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>Activar la unión al explorador para un tipo de cita

En Bookings, vaya a **ConfiguraciónTipos** >  de correo electrónico, seleccione un tipo de [cita](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) y, a continuación, active **Permitir que los asistentes se unan desde un explorador**. Al hacerlo, se habilita la unión del explorador para todas las citas de este tipo.

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="Captura de pantalla de la configuración Permitir que los asistentes se unan desde un explorador para los tipos de citas en la aplicación Bookings":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>Activar la unión al explorador para una cita individual

En Bookings, seleccione **Nueva reserva** y active **Permitir que los asistentes se unan desde un explorador**.

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="Captura de pantalla de la opción Permitir que los asistentes se unan desde un explorador en el nuevo formulario de reserva de la aplicación Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Citas programadas a través del conector EHR Teams

No es necesaria ninguna configuración para usted ni para su personal.

**Integración con Cerner EHR**: el conector EHR Teams admite pacientes que se unen a citas virtuales a través de un vínculo en el mensaje de texto SMS. En el momento de la cita, los pacientes pueden unirse pulsando el vínculo en el mensaje de texto SMS y Teams se abre en un explorador.

**Integración con Epic EHR**: El conector EHR Teams admite pacientes que se unen a citas virtuales a través de la web y móvil de MyChart. En el momento de la cita, los pacientes pueden iniciar la visita desde MyChart mediante el botón **Iniciar visita virtual** y Teams se abre en un explorador.

## <a name="supported-browsers"></a>Exploradores compatibles

Estos son los exploradores que son compatibles actualmente. Admitimos la versión más reciente más dos versiones anteriores, a menos que se indique lo contrario.

|Plataforma  |Cromo |Safari |Edge (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; El uso compartido de la pantalla saliente no es compatible con iOS o Android.

&sup2; Las aplicaciones de iOS en Safari no pueden seleccionar el micrófono y los dispositivos de altavoz. Por ejemplo, dispositivos Bluetooth. Esta es una limitación del sistema operativo, que controla la selección predeterminada de dispositivos.

## <a name="things-to-consider"></a>Aspectos a tener en cuenta

El miembro del personal que realiza la visita puede compartir su pantalla desde su Teams cliente de escritorio, móvil o web con un asistente que se une desde un explorador móvil o de escritorio. Sin embargo, los asistentes no pueden compartir su pantalla desde un explorador móvil o de escritorio.

## <a name="related-articles"></a>Artículos relacionados

- [Visitas virtuales con Teams y la aplicación Bookings](bookings-virtual-visits.md)
- [Crear un tipo de cita Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Unirse a una cita de Bookings como asistente](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Visitas virtuales con Teams: integración en Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Visitas virtuales con Teams - Integración en Epic EHR](healthcare/ehr-admin.md)

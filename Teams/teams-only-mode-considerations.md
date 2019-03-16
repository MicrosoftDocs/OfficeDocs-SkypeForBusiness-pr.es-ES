---
title: Consideraciones del modo Teams solo
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Preparar la actualización a modo de sólo los equipos de Microsoft
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd0bf20219b8d213c354f5fc239ae3924a0d21c0
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "30649391"
---
# <a name="teams-only-mode-considerations"></a>Consideraciones del modo Teams solo

Si es un administrador en el inquilino de Office 365, ahora verá la opción para actualizar a modo de sólo los equipos en el centro de administración de Microsoft Teams. Con esta funcionalidad puede actualizar ya sea a los usuarios individuales, o bien, el inquilino todo.  

Actualización a los equipos sólo modo ofrece a los usuarios todas las ventajas de Microsoft Teams, el concentrador de trabajo en equipo en Office 365, a través de una experiencia de cliente único. Además, los usuarios en el modo sólo los equipos reciben todas las llamadas y chats en los equipos, independientemente de si el remitente usa Skype para empresariales o de los equipos y se benefician de soporte de interoperabilidad y la federación.

Aunque miles de clientes han actualizado correctamente a Microsoft Teams, existen consideraciones que pueden influir en la organización actualización escala de tiempo y experiencia del usuario a lo largo de la forma. En concreto, tiene la opción de actualización no significa necesariamente que su organización está preparada para que este cambio. Para conseguir la mejor experiencia de usuario posible, confirme que Teams cumple los requisitos de colaboración y comunicación, asegúrese de que su red está lista para dar soporte a Teams e implemente su plan de preparación de usuarios antes de actualizar a los usuarios a Teams. 

> [!IMPORTANT]
> Si están iniciándose a planear la actualización, asegúrese de revisar nuestro instrucciones de actualización completa y recursos de planificación. [Comience por aquí](upgrade-introduction.md). 

**Consideraciones sobre la coexistencia**: las organizaciones que ya utilizan Skype para profesionales en línea o Skype para Business Server puede introducir los equipos en su entorno a un ritmo que satisfaga sus necesidades. Las organizaciones pueden incrementalmente desplegar los equipos a un conjunto de usuarios que desee según sea necesario, y los usuarios que usan los equipos pueden comunicarse con los usuarios que utilizan Skype para la empresa y viceversa. Para administrar esta experiencia, los modos de coexistencia de uso de los administradores, que definen la experiencia del cliente de usuario final, el comportamiento de enrutamiento de entrada de chat y llamadas, así como si se programan las reuniones nuevas en los equipos o Skype para la empresa. Los usuarios pueden federarse con usuarios de otras organizaciones, si el usuario está actualizado a **Sólo los equipos**; Sin embargo, se proporciona la mejor experiencia cuando los dos usuarios utilizan los equipos. Los usuarios que se actualizan a los equipos sólo todavía pueden unirse a Skype para reuniones de negocios. 

> [!NOTE]
> Los usuarios que se actualizan a sólo los equipos no pueden comunicarse con los usuarios que están usando Skype para el consumidor.

> [!IMPORTANT]
> Para obtener información más detallada acerca de la coexistencia, consulte [comprender los equipos de Microsoft](teams-and-skypeforbusiness-coexistence-and-interoperability.md)y Skype para la interoperabilidad y coexistencia de negocio. 

**Consideraciones de todo el inquilino**: estamos trabajando en permitir a los equipos en los siguientes entornos; Sin embargo, por ahora, los administradores no deben actualizar los usuarios de su organización si su Skype para inquilino empresarial está hospedado en uno de los siguientes entornos:

 - Comunidad de gobierno en la nube alta
 - DoD de nube de la Comunidad de gobierno
 - Office 365 operado por 21Vianet
 - Alemania de Office 365
 - Skype para inquilino de negocio se hospeda en Corea del sur **y** que la organización requiere datos de los equipos deben almacenarse en Corea del sur. Actualmente, las organizaciones con Skype para datos profesionales almacenados en Corea del sur que actualizar a los equipos tendrán sus datos de los equipos almacenados en la región de Asia centro de datos, no en el área del centro de datos Corea del sur.

**Consideraciones de específica del usuario**: algunos escenarios de usuario siguen evolucionando, y los administradores pueden decidir temporalmente posponer la actualización de determinados usuarios durante la actualización de los otros usuarios de la organización. Estamos trabajando en hacer frente a estos escenarios; Supervise el sitio de la [Guía básica de Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) para anuncios.

| Escenario | Notas |
|----------|-------|
|Dispositivo de trabajo principal del usuario es un Mac, y el usuario debe ver la disponibilidad de los compañeros en Outlook. | Presencia de Outlook en los equipos no es aún totalmente compatible para dispositivos Mac. |
| Usuario con regularidad está llevando a cabo reuniones con los clientes o socios externos de diferentes regiones internacionales. | Los asistentes externos cuya inquilino reside en una ubicación geográfica diferente no ve la mensajería instantánea conversaciones mientras está en una reunión **federados** . Los participantes todavía pueden unirse a la reunión como los usuarios anónimos. |
| Usuario está llevando a cabo Skype para reuniones profesionales de difusión. |  Mientras que los equipos live eventos (reemplazando la difusión de Skype) ya está en vista previa pública, este usuario que necesite permanecer en Skype para la empresa hasta la disponibilidad general de los equipos eventos en directo.
| Dispositivo principal del usuario está basada en VDI. | |
|||

> [!IMPORTANT]
> **Recordar**: el movimiento a los equipos es mayor que una migración técnica. Una correcta actualización evalúa preparación técnica y preparación del usuario final. Revise nuestra Skype para la empresa a los equipos de [instrucciones de actualización](upgrade-framework.md) para obtener más información acerca de cómo planear una implementación de la actualización a los equipos.  

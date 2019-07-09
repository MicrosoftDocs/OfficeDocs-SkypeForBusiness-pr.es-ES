---
title: Consideraciones del modo Teams solo
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Prepararse para la actualización al modo solo de Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11378d35e042a69c2eff8f171cdc266108505774
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588122"
---
# <a name="teams-only-mode-considerations"></a>Consideraciones del modo Teams solo

Si es un administrador de su inquilino de Office 365, ahora verá la opción actualizar al modo solo de Teams en el centro de administración de Microsoft Teams. Con esta funcionalidad, puede actualizar usuarios individuales o, de forma alternativa, todo el inquilino.  

La actualización al modo solo de Teams ofrece a los usuarios todos los beneficios de Microsoft Teams, el hub para el trabajo en equipo en Office 365, a través de una sola experiencia de cliente. Además, los usuarios del modo solo de equipos recibirán todas las llamadas y chats en Teams, independientemente de si el remitente usa Skype empresarial o Teams, y de las ventajas de la compatibilidad con la interoperabilidad y la Federación.

Aunque miles de clientes se han actualizado correctamente a Microsoft Teams, hay consideraciones que pueden influir en la escala de tiempo de actualización de su organización y en la experiencia del usuario a medida que lo desee. En particular, tener la opción de actualizar no significa necesariamente que su organización esté lista para este cambio. Para conseguir la mejor experiencia de usuario posible, confirme que Teams cumple los requisitos de colaboración y comunicación, asegúrese de que su red está lista para dar soporte a Teams e implemente su plan de preparación de usuarios antes de actualizar a los usuarios a Teams. 

> [!IMPORTANT]
> Si solo está empezando el plan de actualización, asegúrese de revisar la guía de actualización completa y los recursos de planeación. [Comienza aquí](upgrade-start-here.md). 

**Consideraciones**de coexistencia: las organizaciones que ya usan Skype empresarial online o Skype empresarial Server pueden introducir equipos en su entorno a un ritmo que satisfaga sus necesidades. Las organizaciones pueden implementar de manera incremental Teams para un conjunto de usuarios deseado según sea necesario, y los usuarios que usen Teams podrán comunicarse con los usuarios que usen Skype empresarial y viceversa. Para administrar esta experiencia, los administradores usan modos de coexistencia, que definen la experiencia del cliente del usuario final, el comportamiento de enrutamiento de las conversaciones entrantes y las llamadas, así como si se programan nuevas reuniones en Teams o Skype empresarial. Los usuarios pueden federarse a usuarios de otras organizaciones si el usuario solo se actualiza a **Teams**; sin embargo, la mejor experiencia se proporciona cuando ambos usuarios usan Teams. Los usuarios que se actualizan a teams solo pueden unirse a reuniones de Skype empresarial. 

> [!NOTE]
> Los usuarios que se actualizan a teams solo no pueden comunicarse con los usuarios que usan Skype para el consumidor.

> [!IMPORTANT]
> Para obtener información más detallada sobre la coexistencia, consulte [comprender Microsoft Teams y la interoperabilidad y la interoperabilidad de Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md). 

**Consideraciones para todo el inquilino**: estamos trabajando en la habilitación de equipos en los siguientes entornos; sin embargo, por ahora, los administradores no deberían actualizar los usuarios de su organización si su inquilino de Skype empresarial está hospedado en uno de los siguientes entornos:

 - Nube de la comunidad de administración pública alta
 - La nube de la comunidad de administración pública DoD
 - Office 365 operado por 21Vianet
 - Office 365 Germany
 - El inquilino de Skype empresarial se hospeda en Corea del Sur **y** la organización requiere que los datos de Teams se almacenen en Corea del sur. Actualmente, las organizaciones con datos de Skype empresarial almacenados en Corea del sur que actualicen a teams tendrán sus datos de equipo almacenados en la región de Asia Datacenter, no en la región del centro de datos de Corea del sur.

**Consideraciones específicas del usuario**: algunos escenarios de usuario siguen evolucionando, y los administradores pueden decidir aplazar temporalmente la actualización de determinados usuarios al actualizar otros usuarios de la organización. Estamos trabajando para afrontar estos escenarios; Consulte el sitio de la [Guía básica de Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) para obtener anuncios.

> [!NOTE]
> Antes de pasar al modo solo para equipos, necesita reemplazar o actualizar los dispositivos que no son compatibles con Teams. 

| Escenario | Notas |
|----------|-------|
|El dispositivo de trabajo principal del usuario es un Mac y el usuario debe ver la disponibilidad de los compañeros en Outlook. | La presencia de Outlook en Teams aún no es totalmente compatible con los dispositivos Mac. |
| El usuario suele realizar reuniones con clientes o socios externos en diferentes regiones internacionales. | Los asistentes externos cuyo espacio empresarial reside en una ubicación geográfica diferente no ven la conversación de mensajes instantáneos durante una reunión **federada** . Los participantes pueden unirse a la reunión como usuarios anónimos. |
| El usuario está llevando a cabo reuniones de difusión de Skype empresarial. |  Mientras que los eventos en vivo de Teams (que reemplazan la difusión de Skype) ya se encuentra en la versión preliminar pública, es posible que este usuario tenga que mantener Skype empresarial hasta que se encuentre con la disponibilidad general de los eventos de Teams
| El dispositivo principal del usuario es basado en VDI. | |
|||

> [!IMPORTANT]
> **Recuerde**: el cambio a teams es algo más que una migración técnica. Una actualización correcta evalúa tanto la preparación técnica como la preparación para el usuario final. Consulte la [Guía de actualización](upgrade-framework.md) de Skype empresarial para equipos para obtener más información sobre cómo planear una implementación de la actualización a teams.  

---
title: Consideraciones del modo Teams solo
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: El administrador puede obtener información sobre cómo prepararse para una actualización al modo solo de Microsoft Teams en el Centro de administración de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86c27d8619a436c6a77ab435cfcb2cc4133befe0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802380"
---
# <a name="teams-only-mode-considerations"></a>Consideraciones del modo Teams solo

Si es administrador de su organización de Microsoft 365 u Office 365, ahora verá la opción de actualizar al modo solo de Teams en el Centro de administración de Microsoft Teams. Con esta funcionalidad, puede actualizar tanto los usuarios individuales como, como alternativa, todo el espacio empresarial.  

Actualizar al modo Solo equipos ofrece a los usuarios todas las ventajas de Microsoft Teams, el centro para el trabajo en equipo en Microsoft 365 u Office 365, a través de una sola experiencia del cliente. Además, los usuarios en modo Solo equipos recibirán todas las llamadas y chats en Teams, independientemente de si el remitente está usando Skype Empresarial o Teams, y disfrutar de la compatibilidad de interoperabilidad y federación.

A pesar de que miles de clientes han actualizado correctamente a Microsoft Teams, hay consideraciones que pueden influir en la escala de tiempo de actualización de su organización y en la experiencia del usuario a lo largo del proceso. En particular, tener la opción de actualizar no significa necesariamente que su organización esté lista para este cambio. Para conseguir la mejor experiencia de usuario posible, confirme que Teams cumple los requisitos de colaboración y comunicación, asegúrese de que su red está lista para dar soporte a Teams e implemente su plan de preparación de usuarios antes de actualizar a los usuarios a Teams. 

> [!IMPORTANT]
> Si acaba de iniciar la planeación de la actualización, asegúrese de revisar nuestra guía de introducción a [la actualización de Microsoft Teams.](upgrade-start-here.md) 

**Consideraciones de coexistencia:** las organizaciones que ya usan Skype Empresarial Online o Skype Empresarial Server pueden introducir Teams en su entorno al ritmo que se adapte a sus necesidades. Las organizaciones pueden poner Teams en el conjunto de usuarios que desee según sea necesario y los usuarios que usan Teams se pueden comunicar con los usuarios que usan Skype Empresarial y viceversa. Para administrar esta experiencia, los administradores usan modos de coexistencia, que definen la experiencia del cliente del usuario final, el comportamiento de enrutamiento de las llamadas y chats entrantes, así como si se programan nuevas reuniones en Teams o Skype Empresarial. Los usuarios pueden federar con usuarios de otras organizaciones si el usuario se actualiza solo **a Teams;** sin embargo, se proporciona la mejor experiencia cuando ambos usuarios usan Teams. Los usuarios actualizados a Teams solo pueden unirse a las reuniones de Skype Empresarial. 

> [!IMPORTANT]
> Para obtener información más detallada sobre coexistencia, consulte Comprender la coexistencia e interoperabilidad de Microsoft Teams y [Skype Empresarial.](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Para obtener más información sobre Teams y Skype (consumidor), consulte [Teams e interoperabilidad con Skype.](teams-skype-interop.md)

**Consideraciones para todos los inquilinos:** Estamos trabajando para habilitar Teams en los siguientes entornos; sin embargo, por ahora, los administradores no deberían actualizar a los usuarios de su organización si su inquilino de Skype Empresarial está hospedado en uno de los siguientes entornos:

 - Office 365 a través de 21Vianet
 - Office 365 Germany
 - El inquilino de Skype Empresarial se aloja en **Corea** del Sur y la organización requiere que los datos de Teams se almacenen en Corea del Sur. Actualmente, las organizaciones con datos de Skype Empresarial almacenados en Corea del Sur que actualicen a Teams tendrán sus datos de Teams almacenados en la región del centro de datos de Asia, no en la región del centro de datos de Corea del Sur.

**Consideraciones específicas del** usuario: algunos escenarios de usuario siguen evolucionando y los administradores pueden decidir posponer temporalmente la actualización de determinados usuarios mientras se actualizan otros usuarios de la organización. En particular, todavía estamos trabajando en escenarios de direcciones para los usuarios cuyo dispositivo principal está basado en VDI. Supervise el sitio del mapa de ruta de [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver anuncios.

> [!NOTE]
> Antes de pasar al modo solo de Teams, debe reemplazar o actualizar los dispositivos que no son compatibles con Teams. 

> [!IMPORTANT]
> **Recuerde:** La migración a Teams es algo más que una migración técnica. Una actualización correcta evalúa la disponibilidad técnica y la disponibilidad del usuario final. Revise nuestras instrucciones de actualización de Skype Empresarial a [Teams](upgrade-framework.md) para obtener más información sobre cómo planear la implementación de la actualización a Teams.  

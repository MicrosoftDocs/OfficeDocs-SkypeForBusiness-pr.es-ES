---
title: Configurar audioconferencias para pequeñas y medianas empresas
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Aprenda a establecer conferencias de audio en su pequeña o mediana empresa para personas que necesitan usar un teléfono para llamar a reuniones. '
ms.openlocfilehash: 648a6342adf0fc035dcd33c6eb11efb40b0d4eed
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328444"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurar audioconferencias para pequeñas y medianas empresas

Con las conferencias de audio, las personas pueden llamar a las reuniones de Teams con un teléfono en lugar de usar la aplicación de Teams en su dispositivo móvil o desde su equipo.  

Si eres una empresa pequeña o mediana con un máximo de 300 usuarios y actualmente no tienes ninguna licencia de audioconferencia, puedes obtener las conferencias de audio gratis durante un año. Esta oferta gratuita está disponible a partir del 1 de octubre de 2020.

La licencia del complemento audioconferencias se puede aplicar a los usuarios que tengan licencias de Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 o Enterprise E3. Para obtener más información, vea [licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Si tiene Enterprise E5 o Microsoft 365 Business Voice, no podrá usar la oferta de conferencia de audio gratuita porque estas licencias ya incluyen conferencias de audio.

En este artículo, le mostraremos cómo configurar las conferencias de audio. Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones. Los asistentes a la reunión que llaman a reuniones no necesitan licencias ni otra configuración. Para obtener más información, consulte [audioconferencia](audio-conferencing-in-office-365.md).

## <a name="step-1-get-audio-conferencing-licenses"></a>Paso 1: obtener licencias de audioconferencia

Obtenga una licencia de audioconferencia por cada persona que le llevará a reuniones. Use el centro de administración de Microsoft 365 para hacerlo.

1. En el centro de administración de Microsoft 365, vaya a servicios de compra de **facturación**  >  **Purchase services**y, a continuación, en la parte inferior de la página, seleccione **Complementos**. 
2. Seleccione detalles de promoción de la **adopción de audioconferencias de Microsoft 365**  >  **Details**.
3. Escriba el número de licencias que necesita para los organizadores de reuniones y, a continuación, complete su pedido.

> [!NOTE]
> Active o desactive la casilla **asignar automáticamente a todos los usuarios sin licencia**, en función de si desea asignar automáticamente una licencia de conferencia de audio a todos los usuarios que no tengan esta licencia.

## <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Paso 2: asignar una licencia de audioconferencia a los usuarios que dirigen reuniones

Asignar una licencia a cada persona que le lleve a reuniones. Use el centro de administración de Microsoft 365 para hacerlo.

### <a name="assign-a-license-to-one-user"></a>Asignar una licencia a un usuario

1. En el centro de administración de Microsoft 365, **vaya a usuarios**  >  **activos**.  
2. Seleccione la fila del usuario a la que desea asignar la licencia y, a continuación, en el panel, seleccione **licencias y aplicaciones**.
3. Seleccione la casilla **Microsoft 365 audio audioconferencia** y, después, haga clic en **Guardar cambios**. 

### <a name="assign-a-license-to-multiple-users"></a>Asignar una licencia a varios usuarios

1. En el centro de administración de Microsoft 365, **vaya a usuarios**  >  **activos**.  
2. Seleccione los círculos que se encuentra junto a los usuarios a los que desea asignar la licencia y, a continuación, seleccione **administrar licencias de producto**.
3. En el panel **administrar licencias de producto** , seleccione **asignar más**.
4. Seleccione la casilla **Microsoft 365 audio audioconferencia** y, después, haga clic en **Guardar cambios**.  

## <a name="step-3-find-or-get-a-phone-number-for-your-conferencing-bridge"></a>Paso 3: buscar u obtener un número de teléfono para el puente de conferencia

Necesitará un número de teléfono (también denominado número de servicio) para su puente de conferencia para que se pueda usar en las invitaciones a reuniones. Puedes elegir usar un **número compartido** o un **número específico**. Cualquier persona que llama puede usar ambos tipos de números para unirse a una reunión.

### <a name="use-a-shared-number"></a>Usar un número compartido

Un número compartido es un número que se comparte entre todas las organizaciones. Los números compartidos se asignan automáticamente al configurar las conferencias de audio. Estos números compartidos son números de pago, en los que pueden aplicarse cargos de larga distancia.

Para buscar el número predeterminado asignado a su puente de conferencia, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a puentes de conferencia de **reuniones**  >  **Conference bridges**y, después, busque el número de la ubicación más cercana.

### <a name="get-a-dedicated-number"></a>Obtener un número dedicado

Un número específico es un número que solo está disponible para los usuarios. Un número específico puede ser un número de teléfono gratuito o un número gratuito. Para usar un número dedicado, tendrá que obtener primero el número y, a continuación, asignarlo a su puente de conferencia.  

Hay un par de formas para obtener un número específico. Puede obtener un número de Microsoft o transferir (puerto) un número existente de su proveedor de servicios actual a Microsoft. Para obtener más información sobre cómo hacer esto, consulta [obtener números de servicio](getting-service-phone-numbers.md).

> [!NOTE]
> Si usa un número gratuito, primero tiene que asignar una licencia de crédito de comunicaciones a cada persona que llevará a reuniones. Para obtener más información, consulte [configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).

Una vez que tenga el número, asígnelo a su puente de conferencia. Use el centro de administración de Microsoft Teams para hacerlo.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a reuniones de conferencia de **reuniones**  >  **Conference bridges**.
2. Seleccione **Agregar**y, a continuación, seleccione **número de pago** o **número gratuito**.
3. En el panel **Agregar número de teléfono** , seleccione el número y, después, haga clic en **aplicar**.

## <a name="step-4-assign-a-dial-in-number-to-users-who-lead-meetings"></a>Paso 4: asignar un número de acceso telefónico a los usuarios que dirigen reuniones

Asigne un número de acceso telefónico para cada una de las personas que llevarán a reuniones. Use el centro de administración de Microsoft Teams para hacerlo.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**, haga clic en el nombre para mostrar del usuario y seleccione **Editar**.
2. Seleccione **Editar**   junto a **audioconferencia**y, en el panel **audioconferencia**   , seleccione un número en las listas número de **teléfono de pago**   o número **gratuito**   y, a continuación, seleccione **aplicar**.

## <a name="step-5-schedule-a-teams-meeting-in-outlook"></a>Paso 5: programar una reunión de Teams en Outlook

Para programar una reunión, en Outlook, vaya a **calendario**y, a continuación, seleccione el botón **nueva reunión de equipos** . Los números de acceso telefónico local establecidos para el usuario y el identificador de conferencia se agregan automáticamente a la invitación a la reunión que se envía a los asistentes a la reunión.

Para obtener más información, consulte [programar una reunión de Teams en Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> Si lo desea, puede personalizar las invitaciones a reuniones para agregar el logotipo de su empresa, vínculos a su sitio web de soporte técnico y renuncia legal, y un pie de página de solo texto. Vea [Personalizar invitaciones a reuniones](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="related-topics"></a>Temas relacionados

- [Audioconferencia](audio-conferencing-in-office-365.md)
- [Configurar audioconferencias para equipos](set-up-audio-conferencing-in-teams.md)
- [Preguntas frecuentes sobre Audioconferencia](audio-conferencing-common-questions.md)
- [Obtener números de servicio](getting-service-phone-numbers.md)
- [Licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

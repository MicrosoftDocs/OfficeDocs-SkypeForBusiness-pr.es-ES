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
ms.openlocfilehash: 13dd6812d6eaf51d2f88ac6d8831552cb63d5a9d
ms.sourcegitcommit: 48cb3cdd69558ec80f8f25f870b302a65280ce5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "48389948"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurar audioconferencias para pequeñas y medianas empresas

Con las conferencias de audio, las personas pueden llamar a las reuniones de Teams con un teléfono en lugar de usar la aplicación de Teams en su dispositivo móvil o desde su equipo.  

Si eres una empresa pequeña o mediana con un máximo de 300 usuarios y actualmente no tienes ninguna licencia de audioconferencia, puedes obtener las conferencias de audio gratis durante un año. Esta oferta gratuita está disponible a partir del 1 de octubre de 2020.

La licencia del complemento audioconferencias se puede aplicar a los usuarios que tengan licencias de Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 o Enterprise E3. Para obtener más información, vea [licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Si tiene Enterprise E5 o Microsoft 365 Business Voice, no podrá usar la oferta de conferencia de audio gratuita porque estas licencias ya incluyen conferencias de audio.

En este artículo, le mostraremos cómo configurar las conferencias de audio. Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones. Los asistentes a la reunión que llaman a reuniones no necesitan licencias ni otra configuración. Para obtener más información, consulte [audioconferencia](audio-conferencing-in-office-365.md).

## <a name="set-up-audio-conferencing"></a>Configurar Audioconferencia

Al configurar las conferencias de audio, se asigna automáticamente un número de teléfono al puente de conferencia para que pueda usarse en las invitaciones a reuniones. El número de teléfono asignado como número predeterminado de su puente de conferencia será uno del país o de la región de su organización. Este número de teléfono es un número de teléfono de pago, que puede ser aplicable a las tarifas de larga distancia.

> [!NOTE]
> También puede usar un número gratuito, que requiere algunos pasos adicionales. Para obtener más información sobre los números de teléfono de su puente de conferencia, consulte [números de teléfono de audioconferencias](#audio-conferencing-phone-numbers) más adelante en este artículo.

### <a name="step-1-get-audio-conferencing-licenses"></a>Paso 1: obtener licencias de audioconferencia

Obtenga una licencia de audioconferencia por cada persona que le llevará a reuniones. Use el centro de administración de Microsoft 365 para hacerlo.

1. En el centro de administración de Microsoft 365, vaya a servicios de compra de **facturación**  >  **Purchase services**y, a continuación, en la parte inferior de la página, seleccione **Complementos**.
2. Seleccione detalles de la **promoción de conferencias de audio de Microsoft 365**  >  **Details**y, a continuación, seleccione **obtener ahora**.
3. Escriba el número de licencias que necesita para los organizadores de reuniones y, a continuación, complete su pedido.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Captura de pantalla de la licencia de promoción de conferencia de audio":::

    > [!NOTE]
    > Active o desactive la casilla **asignar automáticamente a todos los usuarios sin licencia**, en función de si desea asignar automáticamente una licencia de conferencia de audio a todos los usuarios que no tengan esta licencia.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Paso 2: asignar una licencia de audioconferencia a los usuarios que dirigen reuniones

Asignar una licencia a cada persona que le lleve a reuniones. Use el centro de administración de Microsoft 365 para hacerlo.

#### <a name="assign-a-license-to-one-user"></a>Asignar una licencia a un usuario

1. En el centro de administración de Microsoft 365, **vaya a usuarios**  >  **activos**.  
2. Seleccione la fila del usuario a la que desea asignar la licencia y, a continuación, en el panel, seleccione **licencias y aplicaciones**.
3. Seleccione la casilla **Microsoft 365 audio audioconferencia** y, después, haga clic en **Guardar cambios**.

#### <a name="assign-a-license-to-multiple-users"></a>Asignar una licencia a varios usuarios

1. En el centro de administración de Microsoft 365, **vaya a usuarios**  >  **activos**.  
2. Seleccione los círculos que se encuentra junto a los usuarios a los que desea asignar la licencia y, a continuación, seleccione **administrar licencias de producto**.
3. En el panel **administrar licencias de producto** , seleccione **asignar más**.
4. Seleccione la casilla **Microsoft 365 audio audioconferencia** y, después, haga clic en **Guardar cambios**.  

## <a name="schedule-teams-meetings-in-outlook"></a>Programar reuniones de Teams en Outlook

Los organizadores de reuniones ya pueden programar reuniones en Outlook. En Outlook, vaya a **calendario**y, a continuación, seleccione el botón de **reunión de nuevos equipos** . Los números de acceso telefónico de la reunión y el identificador de la Conferencia se agregan automáticamente a la invitación a la reunión que se envía a los asistentes a la reunión. Para obtener más información, consulte [programar una reunión de Teams en Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> Si lo desea, puede personalizar las invitaciones a reuniones para agregar el logotipo de su empresa, vínculos a su sitio web de soporte técnico y renuncia legal, y un pie de página de solo texto. Para obtener más información, consulte [personalizar invitaciones a reuniones](meeting-settings-in-teams.md#customize-meeting-invitations).

## <a name="audio-conferencing-phone-numbers"></a>Números de teléfono de audioconferencias

Existen dos tipos de números que puede usar para su puente de conferencia. Puede usar **números compartidos** (descritos anteriormente en este artículo) o **números dedicados**. Para obtener más información sobre cada uno de ellos.

### <a name="shared-numbers"></a>Números compartidos

Un número compartido es un número que se comparte entre todas las organizaciones. Los números compartidos son números de teléfono de pago y se asignan automáticamente al configurar las conferencias de audio.

Para ver el número predeterminado asignado a su puente de conferencia, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a puentes de conferencia de **reuniones**  >  **Conference bridges**y, después, busque el número de la ubicación más cercana.

### <a name="dedicated-numbers"></a>Números especializados

Un número específico es un número que solo está disponible para los usuarios. Un número específico puede ser un número de teléfono gratuito o un número gratuito. Para usar un número dedicado, tendrá que obtener primero el número, asignarlo a su puente de conferencia y, a continuación, asignar el número a cada una de las personas responsables de las reuniones.

Hay un par de formas para obtener un número específico. Puede obtener un número de Microsoft o transferir (puerto) un número existente de su proveedor de servicios actual a Microsoft. Para obtener más información sobre cómo hacer esto, consulta [obtener números de servicio](getting-service-phone-numbers.md).

Tenga en cuenta que si usa un número gratuito, primero tiene que asignar una licencia de crédito de comunicaciones a cada persona que vaya a realizar reuniones. Para obtener más información, consulte [configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).

Una vez que tenga el número, asígnelo a su puente de conferencia. Use el centro de administración de Microsoft Teams para hacerlo.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a reuniones de conferencia de **reuniones**  >  **Conference bridges**.
2. Seleccione **Agregar**y, a continuación, seleccione **número de pago** o **número gratuito**.
3. En el panel **Agregar número de teléfono** , seleccione el número y, después, haga clic en **aplicar**.

A continuación, asigne el número a cada una de las personas responsables de las reuniones. Use el centro de administración de Microsoft Teams para hacerlo.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**, haga clic en el nombre para mostrar del usuario y seleccione **Editar**.
2. Seleccione **Editar**   junto a **audioconferencia**y, en el panel **audioconferencia**   , seleccione un número en las listas número de **teléfono de pago**   o número **gratuito**   y, a continuación, seleccione **aplicar**.

## <a name="related-topics"></a>Temas relacionados

- [Audioconferencia](audio-conferencing-in-office-365.md)
- [Configurar audioconferencias para equipos](set-up-audio-conferencing-in-teams.md)
- [Números de teléfono para Audioconferencia](phone-numbers-for-audio-conferencing-in-teams.md)
- [Preguntas frecuentes sobre Audioconferencia](audio-conferencing-common-questions.md)
- [Obtener números de servicio](getting-service-phone-numbers.md)
- [Licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

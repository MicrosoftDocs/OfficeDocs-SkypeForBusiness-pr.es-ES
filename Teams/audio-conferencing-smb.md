---
title: Configurar la Audioconferencia para empresas pequeñas y medianas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo configurar las audioconferencias en su pequeña o mediana empresa para las personas que necesitan usar un teléfono para llamar a las reuniones. '
ms.openlocfilehash: e7a3461453255a7a61f6a1095e9cb9697070771c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122354"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurar la Audioconferencia para empresas pequeñas y medianas

Con las audioconferencias, los usuarios pueden llamar a reuniones de Teams con un teléfono en lugar de usar la aplicación Teams en su dispositivo móvil o desde su equipo.  

Si es una pequeña o mediana empresa con hasta 300 usuarios y actualmente no tiene ninguna licencia de Conferencias de audio, puede obtener Conferencias de audio gratis durante un año. Esta oferta gratuita está disponible a partir del 1 de octubre de 2020.

La licencia de complemento de audioconferencia se puede aplicar a los usuarios que tengan licencias de Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 o Enterprise E3. Para obtener más información, vea [Licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Si tiene Enterprise E5 o Microsoft 365 Business Voice, no podrá usar la oferta de audioconferencia gratuita porque estas licencias ya incluyen Audioconferencias.

En este artículo, le explicamos cómo configurar audioconferencias. Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones. Los asistentes a la reunión que llaman a las reuniones no necesitan licencias u otra configuración. Para obtener más información, vea [Audioconferencia.](audio-conferencing-in-office-365.md)

## <a name="set-up-audio-conferencing"></a>Configurar Audioconferencia

Al configurar audioconferencias, se asigna automáticamente un número de teléfono al puente de conferencias para que se pueda usar en invitaciones a reuniones. El número de teléfono asignado como número predeterminado del puente de conferencia será uno del país o región de su organización. Este número de teléfono es un número de pago, en el que se pueden aplicar cargos de larga distancia.

> [!NOTE]
> También puede usar un número gratuito, que requiere algunos pasos adicionales. Para obtener más información sobre los números de teléfono para el puente de conferencias, vea Números de teléfono de [audioconferencia](#audio-conferencing-phone-numbers) más adelante en este artículo.

### <a name="step-1-get-audio-conferencing-licenses"></a>Paso 1: Obtener licencias de audioconferencia

Obtenga una licencia de audioconferencia para cada persona que dirigirá las reuniones. Use el Centro de administración de Microsoft 365 para ello.

1. En el Centro de administración de Microsoft 365, vaya a Servicios de compra de facturación y, a continuación, en la parte inferior de la página, seleccione  >   **Complementos.**
2. Seleccione Detalles de promoción de adopción de audioconferencias de **Microsoft 365** y, a  >  continuación, seleccione **Obtener ahora.**
3. Escriba el número de licencias que necesita para los organizadores de la reunión y, a continuación, complete el pedido.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Captura de pantalla de la licencia de promoción de adopción de audioconferencias":::

    > [!NOTE]
    > Desactive o seleccione asignar automáticamente a todos los usuarios sin licencias, dependiendo de si desea asignar automáticamente una licencia de audioconferencia a todos los usuarios que **no** tengan esta licencia.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Paso 2: Asignar una licencia de audioconferencia a los usuarios que conducen reuniones

Asigne una licencia a cada persona que dirigirá las reuniones. Use el Centro de administración de Microsoft 365 para ello.

#### <a name="assign-a-license-to-one-user"></a>Asignar una licencia a un usuario

1. En el Centro de administración de Microsoft 365, vaya a **Usuarios**  >  **usuarios activos.**  
2. Seleccione la fila del usuario al que desea asignar la licencia y, a continuación, en el panel, seleccione **Licencias y aplicaciones.**
3. Active la casilla De audioconferencia de **Microsoft 365** y, a continuación, **seleccione Guardar cambios.**

#### <a name="assign-a-license-to-multiple-users"></a>Asignar una licencia a varios usuarios

1. En el Centro de administración de Microsoft 365, vaya a **Usuarios**  >  **usuarios activos.**  
2. Seleccione los círculos junto a los usuarios a los que desea asignar la licencia y, a continuación, seleccione **Administrar licencias de producto.**
3. En el **panel Administrar licencias de producto,** seleccione Asignar **más**.
4. Active la casilla De audioconferencia de **Microsoft 365** y, a continuación, **seleccione Guardar cambios.**  

## <a name="schedule-teams-meetings-in-outlook"></a>Programar reuniones de Teams en Outlook

Los organizadores de la reunión ahora pueden programar reuniones en Outlook. En Outlook, vaya **a Calendario** y, a continuación, seleccione el botón Nueva reunión **de Teams.** Los números de acceso telefónico de la reunión y el id. de conferencia se agregan automáticamente a la invitación de reunión que se envía a los asistentes a la reunión. Para obtener más información, vea [Programar una reunión de Teams en Outlook.](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)

> [!NOTE]
> Si lo desea, puede personalizar invitaciones a reuniones para agregar el logotipo de su empresa, vínculos a su sitio web de soporte técnico y declinación de responsabilidades legales y un pie de página de solo texto. Para obtener más información, vea [Personalizar invitaciones a reuniones.](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="audio-conferencing-phone-numbers"></a>Números de teléfono de audioconferencia

Hay dos tipos de números que puede usar para el puente de conferencias. Puede usar números **compartidos** (como en la sección Configurar audioconferencias anteriores en este artículo) o **números dedicados.** [](#set-up-audio-conferencing) Aquí encontrará más información sobre cada uno de ellos.

### <a name="shared-numbers"></a>Números compartidos

Un número compartido es un número que se comparte en todas las organizaciones. Los números compartidos son números de pago y se asignan automáticamente al configurar las audioconferencias.

Para ver el número predeterminado asignado al puente de conferencias, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Puentes** de conferencia de reuniones y, a continuación, busque el número de la ubicación más cercana  >  a usted.

### <a name="dedicated-numbers"></a>Números dedicados

Un número dedicado es un número que solo está disponible para los usuarios. Un número dedicado puede ser un número de pago o un número gratuito. Para usar un número dedicado, primero tendrá que obtener el número, asignarlo al puente de conferencias y, a continuación, asignar el número a cada persona que dirigirá las reuniones.

Hay un par de formas de obtener un número dedicado. Puede obtener un número de Microsoft o transferir (puerto) un número existente de su proveedor de servicios actual a Microsoft. Para obtener más información sobre cómo hacerlo, vea [Obtener números de servicio.](getting-service-phone-numbers.md)

Tenga en cuenta que si usa un número gratuito, primero tiene que asignar una licencia de créditos de comunicaciones a cada persona que dirigirá las reuniones. Para obtener más información, vea [Configurar créditos de comunicaciones para su organización.](set-up-communications-credits-for-your-organization.md)

Después de tener su número, asígnelo al puente de conferencia. Use el Centro de administración de Microsoft Teams para ello.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Puentes de**  >  **conferencia de reuniones.**
2. Seleccione **Agregar** y, a continuación, **seleccione Número de pago** o Número **gratuito.**
3. En el **panel Agregar número de** teléfono, seleccione el número y, a continuación, seleccione **Aplicar**.

A continuación, asigne el número a cada persona que dirigirá las reuniones. Use el Centro de administración de Microsoft Teams para ello.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Usuarios,** haga clic en el nombre para mostrar del usuario y seleccione **Editar.**
2. Seleccione **Editar** junto a **Audioconferencia** y, a continuación, en el  panel  **Audioconferencia,** seleccione un número en las listas Número de pago o Número gratuito y, a continuación, seleccione **Aplicar.**

## <a name="related-topics"></a>Temas relacionados

- [Audioconferencia](audio-conferencing-in-office-365.md)
- [Configurar audioconferencias para Teams](set-up-audio-conferencing-in-teams.md)
- [Números de teléfono para Audioconferencia](phone-numbers-for-audio-conferencing-in-teams.md)
- [Preguntas frecuentes sobre Audioconferencia](audio-conferencing-common-questions.md)
- [Obtener números de servicio](getting-service-phone-numbers.md)
- [Licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Asignar licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users)
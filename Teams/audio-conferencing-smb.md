---
title: Configurar Audioconferencia para pequeñas y medianas empresas
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
description: 'Aprenda a configurar Audioconferencia en su pequeña o mediana empresa para que las personas que necesitan usar un teléfono para llamar a las reuniones. '
ms.openlocfilehash: 80e372e62ffdac9907521eb9426b465c9d0b6e92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821290"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurar Audioconferencia para pequeñas y medianas empresas

Con Audioconferencia, las personas pueden llamar a las reuniones de Teams con un teléfono en lugar de usar la aplicación de Teams en su dispositivo móvil o desde su equipo.  

Si es una empresa pequeña o mediana con hasta 300 usuarios y actualmente no tiene ninguna licencia de Audioconferencia, puede conseguir Audioconferencia gratuita durante un año. Esta oferta gratuita está disponible a partir del 1 de octubre de 2020.

La licencia del complemento Audioconferencia se puede aplicar a los usuarios que tengan licencias de Microsoft 365 Empresa Basic, Business Standard, Empresa Premium, Enterprise E1 o Enterprise E3. Para obtener más información, consulte [Licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Si tiene Enterprise E5 o Microsoft 365 Business Voice, no podrá usar la oferta gratuita de Audioconferencia porque estas licencias ya incluyen Audioconferencia.

En este artículo le explicamos cómo configurar Audioconferencia. Solo debe configurar las audioconferencias para los usuarios que van a programar o dirigir las reuniones. Los asistentes a las reuniones que llaman a las reuniones no necesitan licencias ni ninguna otra configuración. Para obtener más información, [consulte Audioconferencia.](audio-conferencing-in-office-365.md)

## <a name="set-up-audio-conferencing"></a>Configurar Audioconferencia

Al configurar Audioconferencia, se asigna automáticamente un número de teléfono al puente de conferencia para que se pueda usar en las invitaciones a reuniones. El número de teléfono que se asigna como el número predeterminado del puente de conferencia será uno del país o la región de la organización. Este número de teléfono es un número de pago, en el que pueden aplicarse cargos de larga distancia.

> [!NOTE]
> También puede usar un número gratuito, que requiere algunos pasos adicionales. Para obtener más información sobre los números de teléfono para el puente de conferencia, vea Números de teléfono de [Audioconferencia](#audio-conferencing-phone-numbers) más adelante en este artículo.

### <a name="step-1-get-audio-conferencing-licenses"></a>Paso 1: Obtener licencias de Audioconferencia

Obtenga una licencia de Audioconferencia para cada persona que dirigirá las reuniones. Use el Centro de administración de Microsoft 365 para hacerlo.

1. En el Centro de administración de Microsoft 365, vaya a Servicios de compra de facturación y, a continuación, en la parte inferior de la  >  página, **seleccione Complementos.**
2. Seleccione Detalles de promoción de adopción de **audioconferencia de Microsoft 365** y, a continuación, seleccione Obtener  >   **ahora.**
3. Escriba el número de licencias que necesita para los organizadores de la reunión y, a continuación, complete el pedido.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Captura de pantalla de la licencia de promoción de adopción de Audioconferencia":::

    > [!NOTE]
    > Desactive o seleccione la asignación automática a todos los usuarios sin **licencia,** dependiendo de si quiere asignar automáticamente una licencia de Audioconferencia a todos los usuarios que no tengan esta licencia.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Paso 2: Asignar una licencia de Audioconferencia a los usuarios que lideran las reuniones

Asigne una licencia a cada persona que dirigirá las reuniones. Use el Centro de administración de Microsoft 365 para hacerlo.

#### <a name="assign-a-license-to-one-user"></a>Asignar una licencia a un usuario

1. En el Centro de administración de Microsoft 365, vaya a **Usuarios**  >  **activos.**  
2. Seleccione la fila del usuario al que desea asignar la licencia y, a continuación, en el panel, **seleccione Licencias y aplicaciones.**
3. Seleccione la **casilla de verificación Audioconferencia de Microsoft 365** y, a continuación, seleccione Guardar **cambios.**

#### <a name="assign-a-license-to-multiple-users"></a>Asignar una licencia a varios usuarios

1. En el Centro de administración de Microsoft 365, vaya a **Usuarios**  >  **activos.**  
2. Seleccione los círculos junto a los usuarios a los que desea asignar la licencia y, a continuación, **seleccione Administrar licencias de producto.**
3. En el **panel Administrar licencias de** producto, seleccione Asignar **más.**
4. Seleccione la **casilla de verificación Audioconferencia de Microsoft 365** y, a continuación, seleccione Guardar **cambios.**  

## <a name="schedule-teams-meetings-in-outlook"></a>Programar reuniones de Teams en Outlook

Los organizadores de la reunión ahora pueden programar reuniones en Outlook. En Outlook, vaya a **Calendario y, a** continuación, seleccione el **botón Nueva reunión de Teams.** Los números de acceso telefónico y el identificador de conferencia se agregan automáticamente a la invitación de reunión que se envía a los asistentes a la reunión. Para obtener más información, vea [Programar una reunión de Teams en Outlook.](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)

> [!NOTE]
> Si lo desea, puede personalizar invitaciones a reuniones para agregar el logotipo de su empresa, vínculos a su sitio web de soporte técnico y aviso legal, y un pie de página de solo texto. Para obtener más información, consulte [Personalizar invitaciones a reuniones.](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="audio-conferencing-phone-numbers"></a>Números de teléfono de Audioconferencia

Existen dos tipos de números que puede usar para el puente de conferencia. Puede usar números **compartidos (como** se muestra en la sección Configurar [audioconferencias](#set-up-audio-conferencing) anteriores en este artículo) o números **dedicados.** Aquí tiene más información sobre cada una de ellas.

### <a name="shared-numbers"></a>Números compartidos

Un número compartido es un número que se comparte en todas las organizaciones. Los números compartidos son números de pago y se asignan automáticamente al configurar Audioconferencia.

Para ver el número predeterminado que está asignado a su puente de conferencia, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **puentes** de conferencias de reuniones y, a continuación, busque el número de la ubicación más cercana a  >  usted.

### <a name="dedicated-numbers"></a>Números dedicados

Un número dedicado es un número que solo está disponible para los usuarios. Un número dedicado puede ser un número de pago o un número gratuito. Para usar un número dedicado, primero tendrá que obtener el número, asignarlo al puente de conferencia y, a continuación, asignar el número a cada persona que dirigirá las reuniones.

Hay varias maneras de obtener un número dedicado. Puede obtener un número de Microsoft o transferir (transferir) un número existente de su proveedor de servicios actual a Microsoft. Para obtener más información sobre cómo hacerlo, vea Obtener [números de servicio.](getting-service-phone-numbers.md)

Tenga en cuenta que, si usa un número gratuito, primero tiene que asignar una licencia de Créditos de comunicaciones a cada persona que dirigirá las reuniones. Para obtener más información, consulta [Configurar créditos de comunicaciones para tu organización.](set-up-communications-credits-for-your-organization.md)

Una vez que tenga el número, asígnelo al puente de conferencia. Use el Centro de administración de Microsoft Teams para hacerlo.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **puentes de conferencia**  >  **de reuniones.**
2. Seleccione **Agregar** y, a continuación, seleccione **Número de pago** o Número **gratuito.**
3. En el **panel Agregar número de** teléfono, seleccione el número y, a continuación, seleccione **Aplicar.**

Después, asigne el número a cada persona que dirigirá las reuniones. Use el Centro de administración de Microsoft Teams para hacerlo.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Usuarios,** haga clic en el nombre para mostrar del usuario y seleccione **Editar.**
2. Seleccione **Editar** junto a **Audioconferencia** y, a continuación, en el  panel  **Audioconferencia,** seleccione un número en las listas de números de pago o gratuitos y, a continuación, seleccione **Aplicar.**

## <a name="related-topics"></a>Temas relacionados

- [Audioconferencia](audio-conferencing-in-office-365.md)
- [Configurar Audioconferencia para Teams](set-up-audio-conferencing-in-teams.md)
- [Números de teléfono para Audioconferencia](phone-numbers-for-audio-conferencing-in-teams.md)
- [Preguntas frecuentes sobre Audioconferencia](audio-conferencing-common-questions.md)
- [Obtener números de servicio](getting-service-phone-numbers.md)
- [Licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

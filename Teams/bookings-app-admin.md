---
title: Visitas virtuales con Microsoft Teams y la aplicación Bookings
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams y visitas virtuales con la aplicación Bookings
ms.openlocfilehash: 7cb948e020d27ccee396aebb8d1b36b022160a75
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598609"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visitas virtuales con Microsoft Teams y la aplicación Bookings

La aplicación Bookings en Microsoft Teams ofrece una forma sencilla de programar citas en persona y virtuales, como visitas médicas, consultas financieras, entrevistas, asistencia al cliente, horarios de trabajo educativo y mucho más.

Los programadores pueden administrar varios calendarios de departamento y de personal, así como las comunicaciones con los asistentes internos y externos desde una sola experiencia. Las citas virtuales se mantienen a través de las reuniones de Microsoft Teams, que ofrece sólidas funcionalidades para videoconferencias.

> [!NOTE]
> Solo los programadores necesitan tener instalada la aplicación Bookings en Teams. El personal que realice o participe en citas virtuales no necesita la aplicación. Pueden unirse a citas simplemente desde su calendario de Outlook o Teams, o bien desde un vínculo en su correo electrónico de confirmación de reserva.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Requisitos previos para usar la aplicación Bookings en Teams

- El buzón de Exchange debe estar en Exchange Online. Los buzones locales de Exchange Server no son compatibles.

- Microsoft Bookings debe estar activado para la organización.

- Los usuarios deben tener una licencia adecuada. Se admiten Office 365 A3, A5, E3 y E5, así como Microsoft 365 Empresa Estándar, A3, A5, E3 y E5.

- Todos los usuarios de la aplicación de Bookings y todo el personal que participe en las reuniones debe tener una licencia que admita la programación de reuniones de Teams.

- Los sistemas deben cumplir todos los [Requisitos previos software y explorador web](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidad de Bookings en Teams

La aplicación Microsoft Bookings para Teams está disponible en el escritorio y en la Web. Puede encontrarla en [Aplicaciones dentro de Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) y en **Administrar aplicaciones** en el Centro de administración de Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controlar el acceso a Bookings en su organización

Hay varias formas de controlar quién tiene acceso a la aplicación de Bookings y a características específicas de la aplicación. Para obtener información sobre cómo activar o desactivar Microsoft Bookings en el Centro de administración de Microsoft 365, así como para crear una directiva de aplicación de Bookings para permitir que los usuarios seleccionados creen calendarios de Bookings, consulte [Obtener acceso a Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). También puede obtener información sobre cómo [Crear una directiva de aplicación de Teams para anclar la aplicación de Bookings para usuarios determinados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configuración de directiva de reunión recomendada

Para habilitar la mejor experiencia para Bookings, cree una directiva de reunión de personal para admitir automáticamente a **Todos los usuarios de su organización**. Esto permitirá al personal unirse a la cita automáticamente y habilitar la experiencia de sala de espera para los asistentes externos. Puede obtener más información sobre la [admisión automática de personas a las reuniones](meeting-policies-participants-and-guests.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Configuración opcional de aprobaciones para personal

Como configuración de privacidad adicional, puede optar por requerir que el personal opte por participar antes de que se comparta la información de disponibilidad de su programación a través de Bookings y antes de que se puedan reservar para una cita.  

Para habilitar esta configuración, vaya al **Centro de administración de Microsoft 365** \> **Configuración** \> **Configuración** y seleccione **Bookings**.

Con esta configuración activada, el personal recibirá un correo electrónico en el que se le pedirá que apruebe su pertenencia a un calendario de reservas.  

Esta característica se está implantando gradualmente en todo el mundo para los clientes de Microsoft 365 y Office 365. Si todas las opciones todavía no están disponibles en su entorno, vuelva a comprobarlo próximamente.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Cambiar el dominio predeterminado al configurar los buzones de Bookings

Al configurar un buzón de Bookings, se usa el dominio de correo electrónico predeterminado de su organización de Microsoft 365 u Office 365. Pero esto puede provocar problemas al enviar invitaciones a reuniones a destinatarios externos; es posible que la invitación se marque como correo no deseado y se mueva a la carpeta de correo no deseado del destinatario, por lo que quizá nunca vea la invitación.

Le recomendamos que cambie el dominio predeterminado antes de crear el buzón de Bookings. Para obtener información sobre cómo hacerlo, consulte la sección [Preguntas más frecuentes de dominios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Si necesita cambiar el dominio predeterminado después de crear el buzón de Bookings, puede hacerlo con PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Para más información, consulte la documentación de PowerShell del cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.

> [!NOTE]
> Si usa una configuración híbrida de Exchange, le recomendamos que pruebe cuidadosamente el flujo de correo entre la implementación local de Exchange y Exchange Online al cambiar el dominio predeterminado.

## <a name="sending-feedback"></a>Enviar comentarios

Agradecemos sus comentarios sobre:

  - Experiencia del usuario o facilidad de uso
  - Fallos de características o funcionalidad que falta
  - Errores o problemas
  
Para enviar comentarios, haga clic en el botón **Ayuda**, situado cerca de la parte inferior de la barra de navegación izquierda de Teams y haga clic en **Informar de un problema** para **TODOS** los problemas. Al principio del informe de comentarios, informe de que está enviando comentarios sobre "Bookings" para que podamos identificar fácilmente los problemas de Bookings.

## <a name="related-topics"></a>Temas relacionados


  [Documentación de Bookings para usuarios finales](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
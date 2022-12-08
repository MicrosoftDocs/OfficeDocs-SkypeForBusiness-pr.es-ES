---
title: Administrar la aplicación Bookings en Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: how-to
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
- m365-frontline
- tier2
- highpri
- m365initiative-meetings
ms.reviewer: ''
description: Obtenga información sobre cómo administrar la aplicación Bookings en Teams para los usuarios de su organización.
ms.openlocfilehash: abcd906f18b10b7d82b67682de439f1eb6592cd6
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307525"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Administrar la aplicación Bookings en Microsoft Teams

La aplicación Bookings en Microsoft Teams ofrece una forma sencilla de programar citas virtuales y en persona. Por ejemplo, visitas médicas, consultas financieras, entrevistas, atención al cliente y horario de oficina para educación. Para obtener más información, consulte [Citas virtuales con Teams y la aplicación bookings](/microsoft-365/frontline/bookings-virtual-appointments).

Los programadores pueden administrar los calendarios y las comunicaciones de varios departamentos y miembros del personal con asistentes internos y externos, desde una única experiencia. Las citas virtuales se realizan a través de reuniones de Teams que ofrecen sólidas capacidades de videoconferencia.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Requisitos previos para usar la aplicación Reservas en Teams

* El buzón de Exchange está en Exchange Online. No se admiten buzones de Exchange Server locales.
* Microsoft Bookings está disponible para la organización.
* Los usuarios tienen una licencia adecuada. se admiten Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 y Estándar empresarial.
* Todos los usuarios de la aplicación Bookings y todo el personal que participe en las reuniones tienen una licencia compatible con la programación de reuniones de Teams.
* [Requisitos previos de software y explorador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidad de Bookings en Teams

La aplicación Bookings para Teams está disponible en el escritorio y en la Web. Puede encontrarse [en Aplicaciones en Teams y en](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) **Administrar aplicaciones** en el Centro de administración de Teams.

## <a name="control-access-to-bookings-within-your-organization"></a>Controlar el acceso a Bookings en su organización

Hay varias formas de controlar quién tiene acceso a la aplicación de Bookings y a características específicas de la aplicación. Puedes hacer que Microsoft Bookings aplicación esté disponible o deshabilitarla de Centro de administración de Microsoft 365. También puede crear una directiva de aplicación de Bookings para permitir que determinados usuarios puedan crear calendarios de Bookings. Consulta [Obtener acceso a Microsoft Bookings](/microsoft-365/bookings/get-access).

También puede [crear una directiva de configuración de aplicaciones de Teams para anclar la aplicación bookings para usuarios seleccionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configuración recomendada de la directiva de reunión

Para habilitar la mejor experiencia para Bookings, cree una directiva de reunión de Teams para admitir automáticamente a **todos los miembros de su organización** y asignar la directiva a su personal. La directiva permite al personal unirse a la cita automáticamente y habilitar la experiencia de sala de espera para los asistentes externos. Vea [cómo admitir automáticamente a personas a las reuniones](meeting-policies-participants-and-guests.md#automatically-admit-people).

Para obtener más información sobre las directivas de reunión, consulte [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md) y [directivas de reunión y expiración de reuniones en Teams](meeting-expiration.md).

## <a name="sms-text-notifications"></a>Notificaciones de texto SMS

![Icono](media/info.png) de información **Esta característica se está moviendo a [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (versión preliminar). Los usuarios pueden seguir usando esta característica durante el período de vista previa. Después de la versión preliminar, los usuarios necesitan una licencia de Teams Premium.**

Puede controlar si se pueden enviar notificaciones de texto SMS a los asistentes externos para las citas virtuales programadas por el personal de su organización.

De forma predeterminada, esta configuración está activada y las notificaciones de texto SMS están habilitadas para todos los calendarios de Bookings de su organización. Tenga en cuenta que los administradores y programadores de Bookings pueden elegir más adelante desactivar o activar las notificaciones sms según sea necesario en [los tipos de citas programadas](/microsoft-365/frontline/bookings-virtual-appointments#scheduled-appointment-type) y en las citas individuales programadas.

Para configurar esta configuración, vaya a la **configuración** de organización **configuración** \> Centro de administración de Microsoft 365 \> y, a continuación, elija **Bookings**. Active o desactive la casilla **Permitir que los Microsoft envíen notificaciones de mensajes de texto SMS**.

Obtenga más información sobre cómo [configurar notificaciones de texto SMS para su organización](/microsoft-365/bookings/turn-bookings-on-or-off).

## <a name="optional-staff-approvals-setting"></a>Configuración opcional de aprobaciones para personal

Puede requerir que el personal opte por participar antes de que Bookings comparta su información de disponibilidad de la programación y antes de que otros puedan programar una cita con ellos.

Para habilitar esta configuración, vaya a la **configuración** de la organización **de configuración** \> de Centro de administración de Microsoft 365 \> y, a continuación, elija **Bookings**. Active la casilla **Requerir aprobaciones del personal** .

Con esta configuración activada, el personal recibirá un correo electrónico en el que se le pedirá que apruebe la pertenencia a un calendario de reservas.  

Obtenga más información sobre [cómo configurar la configuración de aprobaciones del personal](/microsoft-365/bookings/turn-bookings-on-or-off).

## <a name="changing-your-default-domain-when-setting-up-a-bookings-mailbox"></a>Cambiar el dominio predeterminado al configurar un buzón de Bookings

Al configurar un buzón de Bookings, se usa el dominio de correo electrónico predeterminado de su organización de Microsoft 365 u Office 365. Sin embargo, el dominio predeterminado puede causar problemas al enviar invitaciones a reuniones a destinatarios externos. Por ejemplo, es posible que la invitación se marque como correo no deseado y se mueva a la carpeta de correo no deseado del destinatario, por lo que es posible que no vea nunca la invitación.

Le recomendamos que cambie el dominio predeterminado antes de crear el buzón de Bookings. Consulte [Preguntas más frecuentes sobre dominios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365).

Si necesita cambiar el dominio predeterminado después de crear el buzón de Bookings, use PowerShell.

```powerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Para obtener más información, vea [Establecer buzón](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Si usa una configuración híbrida de Exchange, le recomendamos que pruebe a fondo el flujo de correo entre exchange local y Exchange Online al cambiar el dominio predeterminado.

## <a name="send-feedback"></a>Enviar comentarios

Agradecemos sus comentarios sobre:

* Experiencia del usuario o facilidad de uso
* Fallos de características o funcionalidad que falta
* Errores o problemas
  
Para enviar comentarios, seleccione la opción **Ayuda** en la parte inferior de la barra de navegación izquierda de Teams y, a continuación, seleccione **Informar de un problema** para **TODOS los** problemas. Indique al principio del informe de comentarios que va a enviar comentarios sobre "Bookings" para que podamos identificar fácilmente los problemas de Bookings.

## <a name="related-articles"></a>Artículos relacionados

[Administrar la experiencia de unirse a Teams Citas virtuales en exploradores](/microsoft-365/frontline/browser-join)


  [Documentación de Bookings para usuarios finales](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)

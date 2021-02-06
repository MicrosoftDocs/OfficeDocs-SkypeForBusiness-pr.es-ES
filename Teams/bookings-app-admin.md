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
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125753"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visitas virtuales con Microsoft Teams y la aplicación Bookings

La aplicación Bookings de Microsoft Teams ofrece una forma sencilla de programar citas en persona y virtuales, como visitas médicas, consultas financieras, entrevistas, soporte al cliente, horarios de oficina para educación y mucho más.

Los programadores pueden administrar calendarios de varios departamentos y de personal, así como las comunicaciones con asistentes internos y externos, desde una única experiencia. Las propias citas virtuales se mantienen a través de reuniones de Microsoft Teams, que ofrece sólidas capacidades de videoconferencia.

> [!NOTE]
> Solo los programadores deben tener la aplicación Bookings instalada en Teams. El personal que dirige o participa en citas virtuales no necesita la aplicación. Simplemente pueden unirse a citas desde su calendario de Outlook o Teams o desde un vínculo en el correo electrónico de confirmación de reserva.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Requisitos previos para usar la aplicación Bookings en Teams

- El buzón de Exchange debe estar en Exchange Online. Los buzones de correo Exchange Server local no son compatibles.

- Microsoft Bookings debe estar activado para la organización.

- Los usuarios deben tener una licencia apropiada. Office 365 A3, A5, E3 y E5, así como Microsoft 365 Empresa Estándar, A3, A5, E3 y E5 son compatibles.

- Todos los usuarios de la aplicación Bookings y todos los miembros del personal que participen en las reuniones deben tener una licencia compatible con la programación de reuniones de Teams.

- Los sistemas deben cumplir todos los requisitos [previos del software y del explorador.](hardware-requirements-for-the-teams-app.md)

## <a name="availability-of-bookings-in-teams"></a>Disponibilidad de Bookings en Teams

La aplicación de Microsoft Bookings para Teams está disponible en el escritorio y en la web. Puede encontrarse en Aplicaciones de [Microsoft Teams y](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) en Administrar aplicaciones **en** el Centro de administración de Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controlar el acceso a Bookings dentro de su organización

Hay varias formas de controlar quién tiene acceso a la aplicación de Bookings y a características específicas de la aplicación. Para obtener información sobre cómo activar o desactivar Microsoft Bookings en el Centro de administración de Microsoft 365, así como cómo crear una directiva de aplicación de Bookings para permitir a los usuarios seleccionados crear calendarios de Bookings, vea Obtener acceso a [Microsoft Bookings.](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce) También puede aprender a crear una [directiva de aplicación de Teams para anclar la aplicación Bookings para usuarios seleccionados.](teams-app-setup-policies.md)

## <a name="recommended-meeting-policy-settings"></a>Configuración de directiva de reunión recomendada

Para habilitar la mejor experiencia para Bookings, cree una directiva de reunión de personal para admitir automáticamente a **todos los usuarios de su organización.** Esto permitirá al personal unirse a la cita automáticamente y habilitar la experiencia de sala de espera para los asistentes externos. Puede obtener más información sobre [cómo admitir automáticamente a las personas a las reuniones.](meeting-policies-in-teams.md#automatically-admit-people)

### <a name="optional-staff-approvals-setting"></a>Configuración opcional de aprobaciones de personal

Como configuración de privacidad adicional, puede optar por requerir que el personal opte por participar antes de compartir la información de disponibilidad de su programación a través de Bookings y antes de que se puedan reservar para una cita.  

Para habilitar esta configuración, vaya a Configuración del centro de administración de **Microsoft 365** \>  \> y seleccione **Bookings.**

Con esta configuración activada, el personal recibirá un correo electrónico en el que se le pedirá que aprueben la pertenencia como miembro a un calendario de reservas.  

Esta característica se está implantando gradualmente en todo el mundo para los clientes de Microsoft 365 y Office 365. Si todas las opciones aún no están disponibles en su entorno, vuelva a comprobarlo pronto.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Cambiar el dominio predeterminado al configurar buzones de Bookings

Al configurar un buzón de Bookings, se usa el dominio de correo electrónico predeterminado de su organización de Microsoft 365 u Office 365. Sin embargo, esto puede provocar problemas al enviar invitaciones a reuniones a destinatarios externos; Es posible que su invitación se haya marcado como correo no deseado y se haya movido a la carpeta de correo no deseado del destinatario, por lo que es posible que nunca vea la invitación.

Le recomendamos que cambie el dominio predeterminado antes de crear el buzón de Bookings. Para obtener información sobre cómo hacerlo, consulte Preguntas más frecuentes [sobre dominios.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)

Si necesita cambiar el dominio predeterminado después de que su buzón de Bookings ya se haya creado, puede hacerlo con PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Para obtener más información, consulte la documentación de PowerShell para el cmdlet [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

> [!NOTE]
> Si usa una configuración híbrida de Exchange, le recomendamos que pruebe a fondo el flujo de correo entre exchange local y Exchange Online al cambiar el dominio predeterminado.

## <a name="sending-feedback"></a>Enviar comentarios

Agradecemos sus comentarios sobre:

  - Experiencia de usuario o facilidad de uso
  - Funcionalidad que falta o falta de funcionalidad
  - Errores o problemas
  
Para enviar comentarios,  haga clic en el botón Ayuda cerca de la parte inferior de la barra de navegación izquierda de Teams y, **a** continuación, haga clic en Informar de un problema **para TODOS los** problemas. Al principio de su informe de comentarios, tenga en cuenta que va a enviar comentarios sobre "Bookings" para que podamos identificar fácilmente los problemas de Bookings.

## <a name="related-topics"></a>Temas relacionados

[Documentación de Bookings para usuarios finales](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)

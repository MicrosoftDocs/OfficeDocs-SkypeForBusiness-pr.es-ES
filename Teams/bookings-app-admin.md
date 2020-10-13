---
title: Aplicación de las reservas y visitas virtuales en Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: Microsoft Teams y visitas virtuales con la aplicación bookings
ms.openlocfilehash: c60993b57233c0c526e1770c1d3d414a73fcc42a
ms.sourcegitcommit: a043bde507a9f6747fdd2063dd085edb3c1d6c3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "48427685"
---
# <a name="bookings-app-and-virtual-visits-in-microsoft-teams"></a>Aplicación de las reservas y visitas virtuales en Microsoft Teams

La aplicación de reservas de Microsoft Teams ofrece una forma sencilla de programar citas en persona y virtuales, como visitas de asistencia sanitaria, consultas financieras, entrevistas, asistencia al cliente, horas de oficina de educación y mucho más.

Los programadores pueden administrar varios calendarios de departamentos y personal, así como comunicaciones con asistentes internos y externos, desde una sola experiencia. Las citas virtuales en sí se mantienen a través de las reuniones de Microsoft Teams, lo que ofrece sólidas capacidades de videoconferencia.

> [!NOTE]
> Solo los programadores necesitan tener la aplicación de las reservas instalada en Teams. El personal que lleva a cabo o participa en citas virtuales no necesita la aplicación. Simplemente pueden unirse a citas desde el calendario de Outlook o Teams o desde un vínculo en el correo electrónico de confirmación de reserva.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Requisitos previos para usar la aplicación de reservas en Teams

- El buzón de Exchange debe estar en Exchange Online. No se admiten los buzones de Exchange Server locales.

- Microsoft bookings debe estar activado para la organización.

- Los usuarios deben tener una licencia adecuada. Office 365 a3, A5, E3 y E5, así como Microsoft 365 Business Standard, a3, A5, E3 y E5.

- Todos los usuarios de la aplicación de reservas y todo el personal que participe en las reuniones deben tener una licencia que admita la programación de reuniones de equipos.

- Sus sistemas deben cumplir con todos los [requisitos previos de software y navegador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidad de las reservas en Teams

La aplicación Microsoft bookings para Teams está disponible en el escritorio y en la Web. Puede encontrarla en [aplicaciones de Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) y en **Administrar aplicaciones** dentro del centro de administración de Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controlar el acceso a las reservas de la organización

Hay varias maneras de controlar quién tiene acceso a la aplicación de las reservas y a características específicas de la aplicación. Para obtener información sobre cómo activar o desactivar Microsoft Books en el centro de administración de Microsoft 365, así como la forma de crear una directiva de aplicación de reservas para permitir que los usuarios seleccionados creen calendarios de reservas, vea [obtener acceso a Microsoft bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). También puede obtener información sobre cómo [crear una directiva de la aplicación de Teams para anclar la aplicación de las reservas a los usuarios seleccionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configuración de directiva de reunión recomendada

Para habilitar la mejor experiencia para las reservas, cree una directiva de reunión de personal para admitir automáticamente a **todos los usuarios de su organización**. Esto permitirá al personal unirse a la cita automáticamente y habilitar la experiencia de la sala de espera para los asistentes externos. Puede obtener más información sobre la [admisión automática de personas a las reuniones](meeting-policies-in-teams.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Configuración opcional de aprobaciones de personal

Como configuración de privacidad adicional, puede decidir requerir que el personal participe antes de que la información de disponibilidad de programación se comparta con las reservas y antes de que se pueda reservar para una cita.  

Para habilitar esta configuración, vaya a configuración del **centro de administración de Microsoft 365** \> **Settings** \> **Settings**y seleccione **reservas**.

Con esta configuración activada, el personal recibirá un mensaje de correo electrónico en el que se le solicitará que apruebe la pertenencia a un calendario de reserva.  

Esta característica se está implementando gradualmente en todo el mundo para los clientes de Microsoft 365 y Office 365. Si todas las opciones aún no están disponibles en su entorno, vuelva a consultar pronto.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Cambiar el dominio predeterminado al configurar los buzones de las reservas

Al configurar un buzón de reservas, se usa el dominio de correo electrónico predeterminado de su organización de Microsoft 365 u Office 365. Sin embargo, esto puede causar problemas al enviar invitaciones a reuniones a destinatarios externos; es posible que su invitación se marque como correo no deseado y se mueva a la carpeta de correo no deseado del destinatario, de modo que el destinatario nunca verá su invitación.

Le recomendamos que cambie el dominio predeterminado antes de crear el buzón de las reservas. Para obtener más información sobre cómo hacerlo, consulte las [preguntas más frecuentes](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)sobre los dominios.

Si necesita cambiar el dominio predeterminado una vez que ya se ha creado el buzón de las reservas, puede hacerlo con PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Para obtener más información, consulte la documentación de PowerShell para el cmdlet [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Si usa una configuración híbrida de Exchange, le recomendamos que pruebe minuciosamente el flujo de correo entre Exchange local y Exchange Online al cambiar el dominio predeterminado.

## <a name="sending-feedback"></a>Enviar comentarios

Le agradecemos sus comentarios sobre:

  - Experiencia del usuario o facilidad de uso
  - Brechas de características o funcionalidad perdida
  - Errores o problemas
  
Para enviar comentarios, haga clic en el botón **ayuda** situado cerca de la parte inferior de la barra de navegación izquierda de Teams y, a continuación, haga clic en **informar de un problema** para **todos los** problemas. Nota al principio de su informe de comentarios le enviamos comentarios sobre "reservas" para que podamos identificar fácilmente los problemas relacionados con las reservas.

## <a name="related-topics"></a>Temas relacionados

[Documentación de las reservas para usuarios finales](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)

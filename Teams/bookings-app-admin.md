---
title: Administrar la aplicación Bookings en Microsoft Teams
author: dmaguire
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
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
ms.reviewer: ''
description: Obtenga información sobre cómo administrar la aplicación Bookings en Teams usuarios de su organización.
ms.openlocfilehash: 2bbc671b1054cfa4340abf7656e17939d147dea2
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288348"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Administrar la aplicación Bookings en Microsoft Teams

La aplicación Bookings en Microsoft Teams ofrece una forma sencilla de programar citas en persona y virtuales, como visitas médicas, consultas financieras, entrevistas, asistencia al cliente, horarios de trabajo educativo y mucho más. Para obtener más información, vea [Visitas virtuales con Teams y la aplicación Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Los programadores pueden administrar varios calendarios de departamento y de personal, así como las comunicaciones con los asistentes internos y externos desde una sola experiencia. Las propias citas virtuales se celebrarán Microsoft Teams reuniones, lo que ofrece sólidas capacidades de videoconferencia.

> [!NOTE]
> Solo los programadores necesitan tener instalada la aplicación Bookings en Teams. El personal que dirige o participa en citas virtuales no necesita la aplicación. Simplemente pueden unirse a citas desde su calendario Outlook o Teams o desde el vínculo Teams reunión en su correo electrónico de confirmación de reserva.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Requisitos previos para usar la aplicación Bookings en Teams

- El buzón de Exchange debe estar en Exchange Online. Los buzones Exchange Server locales no son compatibles.

- Microsoft Bookings debe estar activado para la organización.

- Los usuarios deben tener una licencia adecuada. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 y Business Standard son compatibles.

- Todos los usuarios de la aplicación Bookings y todo el personal que participe en las reuniones deben tener una licencia que admita Teams programación de reuniones.

- Los sistemas deben cumplir todos los [requisitos previos de software y explorador web](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidad de Bookings en Teams

La aplicación Microsoft Bookings para Teams está disponible en el escritorio y la web. Se puede encontrar en [Aplicaciones en Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) y en Administrar **aplicaciones** en el centro Teams administración.

### <a name="control-access-to-bookings-within-your-organization"></a>Controlar el acceso a Bookings en su organización

Hay varias formas de controlar quién tiene acceso a la aplicación de Bookings y a características específicas de la aplicación.

Para obtener información sobre cómo activar o desactivar Microsoft Bookings en el Centro de administración de Microsoft 365 y cómo crear una directiva de aplicación de Bookings para permitir a los usuarios seleccionados crear calendarios de Bookings, vea Obtener acceso a [Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).

También puede crear [una directiva de configuración Teams aplicación para anclar la aplicación Bookings para usuarios seleccionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configuración de directiva de reunión recomendada

Para habilitar la mejor experiencia para Bookings, cree una directiva de reunión Teams para admitir automáticamente a todos los  usuarios de su organización y asignar la directiva a su personal. Esto permite al personal unirse a la cita automáticamente y habilitar la experiencia de la sala de espera para los asistentes externos. Obtenga más información sobre cómo admitir [automáticamente a las personas a las reuniones](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Configuración opcional de aprobaciones para personal

Como configuración de privacidad adicional, puede optar por requerir que el personal opte por participar antes de que se comparta la información de disponibilidad de su programación a través de Bookings y antes de que se puedan reservar para una cita.  

Para habilitar esta configuración, vaya **a Centro de administración de Microsoft 365** \> **Configuración** \> **Configuración** y, a continuación, seleccione **Bookings**.

Con esta configuración activada, el personal recibirá un correo electrónico en el que se les pedirá que aprueben la pertenencia a un calendario de reserva.  

Esta característica se está implantando gradualmente en todo el mundo para los clientes de Microsoft 365 y Office 365. Si todas las opciones aún no están disponibles en su entorno, vuelva a comprobarlo pronto.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Cambiar el dominio predeterminado al configurar los buzones de Bookings

Al configurar un buzón de Bookings, se usa el dominio de correo electrónico predeterminado de su organización de Microsoft 365 u Office 365. Pero esto puede provocar problemas al enviar invitaciones a reuniones a destinatarios externos; es posible que la invitación se marque como correo no deseado y se mueva a la carpeta de correo no deseado del destinatario, por lo que quizá nunca vea la invitación.

Le recomendamos que cambie el dominio predeterminado antes de crear el buzón de Bookings. Para obtener información sobre cómo hacerlo, consulte la sección [Preguntas más frecuentes de dominios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Si necesita cambiar el dominio predeterminado después de crear el buzón de Bookings, puede hacerlo con PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Para más información, consulte la documentación de PowerShell del cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.

> [!NOTE]
> Si usa una configuración híbrida Exchange, le recomendamos que pruebe a fondo el flujo de correo entre las Exchange locales y Exchange Online al cambiar el dominio predeterminado.

## <a name="sending-feedback"></a>Enviar comentarios

Agradecemos sus comentarios sobre:

  - Experiencia del usuario o facilidad de uso
  - Fallos de características o funcionalidad que falta
  - Errores o problemas
  
Para enviar comentarios, **seleccione el botón** Ayuda cerca de la parte inferior de la barra de navegación Teams izquierda y, a continuación, seleccione Informar de **un** problema para **todos los** problemas. Indica al principio de tu informe de comentarios que estás enviando comentarios sobre "Bookings" para que podamos identificar fácilmente los problemas de Bookings.

## <a name="related-articles"></a>Artículos relacionados

[Administrar la experiencia de combinación para Teams visitas virtuales en exploradores móviles](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentación de Bookings para usuarios finales](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)

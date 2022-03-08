---
title: Administrar la aplicación Bookings en Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.openlocfilehash: 3032704fe935f1d4d316741400e8a4b5841f8685
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070589"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Administrar la aplicación Bookings en Microsoft Teams

La aplicación Bookings en Microsoft Teams ofrece una forma sencilla de programar citas en persona y virtuales. Por ejemplo, visitas sanitarias, consultas financieras, entrevistas, atención al cliente y horas de oficina de educación. Para obtener más información, consulte [Visitas virtuales con Teams y la aplicación Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Los programadores pueden administrar varios calendarios de departamento y personal y comunicaciones con asistentes internos y externos, desde una sola experiencia. Las citas virtuales se mantienen Microsoft Teams reuniones que ofrecen funciones de videoconferencia sólidas.

> [!NOTE]
> Solo los programadores necesitan tener instalada la aplicación Bookings en Teams. El personal que dirige o participa en citas virtuales no necesita la aplicación. Simplemente pueden unirse a citas desde su Outlook o Teams calendario o desde el vínculo Teams reunión en el correo electrónico de confirmación de la reserva.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Requisitos previos para usar la aplicación Bookings en Teams

* El Exchange buzón de correo está en Exchange Online. Los buzones Exchange Server locales no son compatibles.
* Microsoft Bookings está disponible para la organización.
* Los usuarios tienen una licencia adecuada. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 y Business Standard son compatibles.
* Todos los usuarios de la aplicación Bookings y todo el personal que participe en las reuniones tienen una licencia que admite Teams programación de reuniones.
* [Requisitos previos de software y explorador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidad de Bookings en Teams

La aplicación Microsoft Bookings para Teams está disponible en el escritorio y la web. Se puede encontrar en [Aplicaciones en Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) y en Administrar **aplicaciones** en el centro Teams administración.

### <a name="control-access-to-bookings-within-your-organization"></a>Controlar el acceso a Bookings en su organización

Hay varias formas de controlar quién tiene acceso a la aplicación de Bookings y a características específicas de la aplicación. Puede hacer que la aplicación Microsoft Bookings esté disponible o deshabilitarla desde Centro de administración de Microsoft 365. Como alternativa, puede crear una directiva de aplicación de Bookings para permitir a los usuarios seleccionados crear calendarios de Bookings. Consulte [Obtener acceso a Microsoft Bookings](/microsoft-365/bookings/get-access).

También puede crear [una directiva de Teams de configuración de aplicaciones para anclar la aplicación Bookings para usuarios seleccionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configuración de directiva de reunión recomendada

Para habilitar la mejor experiencia para Bookings, cree una directiva de reunión de Teams para admitir automáticamente a todos  los miembros de su organización y asignar la directiva a su personal. La directiva permite al personal unirse a la cita automáticamente y habilitar la experiencia de la sala de espera para los asistentes externos. Vea [cómo admitir automáticamente a las personas a las reuniones](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Configuración opcional de aprobaciones para personal

Puede requerir que el personal opte antes de que Bookings comparta su información de disponibilidad de programación y antes de que otros puedan programar una cita con ellos.

Para habilitar esta configuración, vaya **a Centro de administración de Microsoft 365** \> **Configuración** \> **Configuración** y, a continuación, seleccione **Bookings**.

Con esta configuración activada, el personal recibe un correo electrónico en el que se les solicita que aprueben la pertenencia a un calendario de reserva.  

Esta característica se está implantando gradualmente en todo el mundo para los clientes de Microsoft 365 y Office 365. Si todas las opciones aún no están disponibles en su entorno, vuelva a comprobarlo pronto.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Cambiar el dominio predeterminado al configurar el buzón de Bookings

Al configurar un buzón de Bookings, se usa el dominio de correo electrónico predeterminado de su organización de Microsoft 365 u Office 365. Sin embargo, el dominio predeterminado puede causar problemas al enviar invitaciones a reuniones a destinatarios externos. Por ejemplo, es posible que la invitación se marca como correo no deseado y se mueve a la carpeta de correo no deseado del destinatario, por lo que es posible que el destinatario nunca vea la invitación.

Le recomendamos que cambie el dominio predeterminado antes de crear el buzón de Bookings. Vea las preguntas [más frecuentes sobre dominios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Si necesita cambiar el dominio predeterminado después de crear el buzón de Bookings, use PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Consulte la documentación de PowerShell para Establecer el cmdlet [Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Si usa una configuración híbrida Exchange, le recomendamos que pruebe a fondo el flujo de correo entre las Exchange locales y Exchange Online al cambiar el dominio predeterminado.

## <a name="send-feedback"></a>Enviar comentarios

Agradecemos sus comentarios sobre:

* Experiencia del usuario o facilidad de uso
* Fallos de características o funcionalidad que falta
* Errores o problemas
  
Para enviar comentarios, **seleccione la opción** Ayuda en la parte inferior de la barra de navegación Teams izquierda y, a continuación, seleccione Informar de **un** problema para **todos los** problemas. Indica al principio de tu informe de comentarios que estás enviando comentarios sobre "Bookings" para que podamos identificar fácilmente los problemas de Bookings.

## <a name="related-articles"></a>Artículos relacionados

[Administrar la experiencia de combinación para Teams visitas virtuales en exploradores móviles](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentación de Bookings para usuarios finales](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)

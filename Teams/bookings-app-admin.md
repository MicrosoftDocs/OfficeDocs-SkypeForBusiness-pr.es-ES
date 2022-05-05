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
description: Obtenga información sobre cómo administrar la aplicación Bookings en Teams para los usuarios de su organización.
ms.openlocfilehash: 5740da885fb271af212ba755d7db0228a996b429
ms.sourcegitcommit: e102d72e67ab1c440c29ae6a048fc2cf8545fe01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "65217934"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Administrar la aplicación Bookings en Microsoft Teams

La aplicación Bookings de Microsoft Teams ofrece una forma sencilla de programar citas virtuales y en persona. Por ejemplo, visitas médicas, consultas financieras, entrevistas, atención al cliente y horario de oficina para educación. Para obtener más información, consulta [Citas virtuales con Teams y la aplicación Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Los programadores pueden administrar los calendarios y las comunicaciones de varios departamentos y miembros del personal con asistentes internos y externos, desde una única experiencia. Las citas virtuales se realizan a través de reuniones Microsoft Teams que ofrecen sólidas capacidades de videoconferencia.

> [!NOTE]
> Solo los programadores necesitan tener instalada la aplicación Bookings en Teams. El personal que realiza o participa en citas virtuales no necesita la aplicación. Solo tienen que unirse a citas desde su Outlook o Teams calendario o desde el vínculo de reunión Teams de su correo electrónico de confirmación de reserva.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Requisitos previos para usar la aplicación Bookings en Teams

* El buzón de Exchange está en Exchange Online. No se admiten buzones de Exchange Server locales.
* Microsoft Bookings está disponible para la organización.
* Los usuarios tienen una licencia adecuada. se admiten Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 y Estándar empresarial.
* Todos los usuarios de la aplicación Bookings y todo el personal que participe en las reuniones tienen una licencia compatible con Teams programación de reuniones.
* [Requisitos previos de software y explorador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidad de Bookings en Teams

Microsoft Bookings aplicación para Teams está disponible en el escritorio y en la Web. Puede encontrarse [en Aplicaciones en Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) y en **Administrar aplicaciones** en el Centro de administración de Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controlar el acceso a Bookings en su organización

Hay varias formas de controlar quién tiene acceso a la aplicación de Bookings y a características específicas de la aplicación. Puedes hacer que Microsoft Bookings aplicación esté disponible o deshabilitarla de Centro de administración de Microsoft 365. Como alternativa, puede crear una directiva de aplicación de Bookings para permitir que determinados usuarios puedan crear calendarios Bookings. Consulta [Obtener acceso a Microsoft Bookings](/microsoft-365/bookings/get-access).

También puedes [crear una directiva de configuración de aplicaciones de Teams para anclar la aplicación de Bookings para determinados usuarios](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configuración recomendada de la directiva de reunión

Para habilitar la mejor experiencia para Bookings, cree una directiva de reunión de Teams para admitir automáticamente **a todos los miembros de su organización** y asignar la directiva a su personal. La directiva permite al personal unirse a la cita automáticamente y habilitar la experiencia de sala de espera para los asistentes externos. Vea [cómo admitir automáticamente a personas a las reuniones](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Configuración opcional de aprobaciones para personal

Puede requerir que el personal opte por participar antes de Bookings comparta su información de disponibilidad de la programación y antes de que otros puedan programar una cita con ellos.

Para habilitar esta configuración, ve a **Centro de administración de Microsoft 365** \> **Configuración** \> **Configuración** y, a continuación, selecciona **Bookings**.

Con esta configuración activada, el personal recibe un correo electrónico en el que se le solicita que apruebe la pertenencia a un calendario de reservas.  

Esta característica se está implantando gradualmente en todo el mundo para los clientes de Microsoft 365 y Office 365. Si todas las opciones aún no están disponibles en su entorno, vuelva a comprobarlo pronto.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Cambiar el dominio predeterminado al configurar Bookings buzón

Al configurar un buzón de Bookings, se usa el dominio de correo electrónico predeterminado de su organización de Microsoft 365 u Office 365. Sin embargo, el dominio predeterminado puede causar problemas al enviar invitaciones a reuniones a destinatarios externos. Por ejemplo, es posible que la invitación se marque como correo no deseado y se mueva a la carpeta de correo no deseado del destinatario, por lo que es posible que no vea nunca la invitación.

Le recomendamos que cambie el dominio predeterminado antes de crear el buzón de Bookings. Consulte las [Preguntas más frecuentes sobre dominios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Si necesita cambiar el dominio predeterminado después de crear el buzón de Bookings, use PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Consulte la documentación de PowerShell para [establecer cmdlet de buzón](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Si usa una configuración híbrida Exchange, le recomendamos que pruebe a fondo el flujo de correo entre Exchange local y Exchange Online al cambiar el dominio predeterminado.

## <a name="send-feedback"></a>Enviar comentarios

Agradecemos sus comentarios sobre:

* Experiencia del usuario o facilidad de uso
* Fallos de características o funcionalidad que falta
* Errores o problemas
  
Para enviar comentarios, selecciona la opción **Ayuda** en la parte inferior de la Teams barra de navegación izquierda y, a continuación, selecciona **Informar de un problema** para **TODOS los** problemas. Indica al principio del informe de comentarios que estás enviando comentarios sobre "Bookings" para que podamos identificar fácilmente Bookings problemas.

## <a name="related-articles"></a>Artículos relacionados

[Administrar la experiencia de unión para Teams citas virtuales en exploradores](expand-teams-across-your-org/browser-join.md)


  [Documentación de Bookings para usuarios finales](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)

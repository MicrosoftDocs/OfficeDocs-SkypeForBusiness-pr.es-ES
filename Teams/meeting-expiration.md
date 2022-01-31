---
title: Directivas de reunión y expiración de la reunión en Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Obtenga información sobre cómo usar la configuración de directiva de reunión para controlar la expiración de la reunión en Microsoft Teams.
ms.openlocfilehash: 8c8a5603aea6ac65a2cd35b12eca9250debc7c51
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279177"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Directivas de reunión y expiración de la reunión en Microsoft Teams

[Las directivas](meeting-policies-overview.md) de reunión de Microsoft Teams se usan para controlar si los usuarios de su organización pueden iniciar y programar reuniones y las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Las directivas de reunión se administran en el centro de administración de Microsoft Teams o mediante los cmdlets de PowerShell [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy.

La configuración de directiva de reunión que controla si los usuarios pueden iniciar y programar reuniones, así como controlar la expiración de las reuniones programadas por los usuarios. Cuando un vínculo de unirse a una reunión y el id. de conferencia de una reunión expiran, nadie puede unirse a la reunión. La siguiente configuración de directiva de reunión determina si los usuarios pueden iniciar y programar reuniones en Teams. En este artículo se explica la configuración de la reunión.

- [Reunirse ahora en canales](meeting-policies-in-teams-general.md#meet-now-in-channels): controla si un usuario puede iniciar una reunión improvisada en un canal.
- [Programación de reuniones del canal](meeting-policies-in-teams-general.md#channel-meeting-scheduling): controla si un usuario puede programar una reunión en un canal.
- [Programación de reuniones privada](meeting-policies-in-teams-general.md#private-meeting-scheduling): controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Outlook agregar](meeting-policies-in-teams-general.md#outlook-add-in): Controla si un usuario puede programar una reunión privada desde Outlook. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Reunirse ahora en reuniones privadas](meeting-policies-in-teams-general.md#meet-now-in-private-meetings): controla si un usuario puede iniciar una reunión privada improvisada.

De forma predeterminada, esta configuración está en. Cuando cualquiera de estas opciones de configuración está desactivada, cualquier usuario al que se le haya asignado la directiva no puede iniciar ni programar nuevas reuniones de ese tipo. Al mismo tiempo, la reunión une vínculos e id. de conferencia de todas las reuniones existentes de ese tipo que el usuario inició o programó anteriormente expiran.

Por ejemplo, si a un usuario se le asigna una directiva de reunión en la que esta configuración de directiva de reunión está establecida en Activar y, después, desactiva la configuración Permitir reunión ahora en canales, ese usuario ya no puede iniciar reuniones improvisadas en canales y el canal Reunirse ahora se une a vínculos que el usuario creó anteriormente han expirado. El usuario puede seguir iniciando y programando otros tipos de reunión y unirse a reuniones organizadas por otras personas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>¿Qué sucede cuando expira el vínculo de unirse a la reunión y el id. de conferencia?

Cuando el vínculo de unirse a la reunión y el id. de conferencia de una reunión expiran, nadie puede unirse a la reunión. Cuando un usuario intenta unirse a la reunión a través del vínculo o por teléfono, recibe un mensaje que indica que la reunión ya no está disponible. Las conversaciones, los archivos, las pizarras, las grabaciones, las transcripciones y otros contenidos relacionados con la reunión se conservan y los usuarios pueden seguir accediendo a ellas.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>¿Qué sucede cuando activa y desactiva una configuración de directiva de reunión?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Cambiar una configuración de directiva de reunión de activar a desactivar

Cuando una configuración de directiva de reunión se establece en **En**, los usuarios a los que se les asigna la directiva pueden iniciar o programar reuniones de ese tipo y todos los usuarios pueden unirse. Al cambiar la configuración de directiva de reunión a **Desactivado, los** usuarios a los que se les ha asignado la directiva no pueden iniciar ni programar nuevas reuniones de ese tipo, y los vínculos de combinación de reuniones y los id. de conferencia de las reuniones existentes que el usuario programó previamente expiran.

Tenga en cuenta que el usuario todavía puede unirse a reuniones organizadas por otras personas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Cambiar una configuración de directiva de reunión de desactivado a encendido

Al cambiar una configuración de directiva de reunión de **Desactivado** a **Activar**, los usuarios que tienen asignada la directiva pueden iniciar o programar reuniones de ese tipo. Si una configuración de directiva de reunión está desactivada y, a continuación, se vuelve a activar para un usuario, todas las reuniones programadas previamente (y expiradas) organizadas por el usuario se activarán y las personas podrán unirse a ellas mediante el vínculo de unirse a la reunión o por teléfono.  

## <a name="meeting-expiration-scenarios"></a>Escenarios de expiración de la reunión

Este es un resumen de cómo funciona la expiración de la reunión para cada una de las configuraciones de directiva de reunión que se debate en este artículo.

|Si desea...&nbsp;&nbsp; |Haga esto&nbsp;&nbsp;&nbsp;&nbsp;  |Comportamiento de unirse a la reunión&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Expirar reuniones privadas de Reunirse ahora iniciadas por un usuario&nbsp;&nbsp;|Desactive **Reunirse ahora en reuniones privadas**.&nbsp;&nbsp;|Nadie puede unirse a reuniones **privadas de Reunirse** ahora iniciadas por el usuario.|
|Expirar reuniones privadas programadas por un usuario&nbsp;&nbsp;|Desactive la **programación de reuniones privadas** _y_ **desactive Outlook complemento**. &nbsp;&nbsp;|Nadie puede unirse a reuniones privadas programadas por el usuario. Esto impide que las personas se unan a las siguientes reuniones:<ul><li>Reuniones privadas que tuvieron lugar en el pasado.</li><li>Reuniones privadas programadas para el futuro y que aún no se han producido.</li><li>Futuras instancias de reuniones privadas periódicas.</li></ul><br>Tanto **la programación de** reuniones privadas **como Outlook complemento** deben estar desactivados para expirar las reuniones privadas programadas por un usuario. Si una configuración está desactivada y la otra está activada, los vínculos de combinación de reuniones y los IDs de conferencia de las reuniones existentes permanecen activos y no expirarán.|
|Expire channel **Meet now** meetings started by a user&nbsp;&nbsp;|Desactive **Reunirse ahora en canales** _y_ desactive la **programación de reuniones del canal**.&nbsp;&nbsp;|Nadie puede unirse al canal **Reunirse ahora** las reuniones iniciadas por el usuario.|
|Expirar reuniones del canal programadas por un usuario&nbsp;&nbsp;|Desactivar la **programación de reuniones del Canal**.&nbsp;&nbsp;|Nadie puede unirse a las reuniones del canal programadas por el usuario. Esto impide que las personas se unan a las siguientes reuniones:<ul><li>Reuniones del canal que se produjeron en el pasado.</li><li>Reuniones de canal que están programadas para el futuro y que aún no se han producido.</li><li>Futuras instancias de reuniones periódicas del canal.</li></ul>|

Si desea que los usuarios accedan a las reuniones programadas o iniciadas previamente por un usuario determinado, puede:

- Active la configuración de directiva de reunión para ese usuario.
- Desactive la configuración de directiva de reunión para ese usuario y haga que otro usuario que tenga habilitada la configuración de directiva cree una nueva reunión para reemplazar la reunión expirada.

> [!NOTE]
> Si la reunión fue enviada por un delegado, a quien se le otorgaron permisos para enviar invitaciones de reunión en nombre de otra persona, como un administrador, la configuración de directiva de reunión se aplica a la persona que ha concedido permiso (el administrador).

## <a name="changes-to-meeting-expiration"></a>Cambios en la expiración de la reunión

> [!IMPORTANT]
> Si desea habilitar la expiración de Teams reunión en su inquilino antes de tiempo, aplique al programa de Microsoft Teams de adopción anticipado de la expiración [de la reunión](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR8YMDA0A9INMv_DZ8yW5uG1URDc3U1VVMklPTzVMS0RLR0pUQTlWU1BEVC4u).

Todas las grabaciones Teams reunión (TMR) tendrán una expiración predeterminada de 60 días. Esta opción está predeterminada para todos los inquilinos. Esto significa que, de forma predeterminada, todos los  TMR creados después de que esta característica se haya activado se eliminarán 60 días después de su fecha de creación. Los administradores también pueden establecer reuniones para **que nunca expiren automáticamente**. El OneDrive y SharePoint supervisará la fecha de expiración establecida en todos los TMR y moverá automáticamente los TMR a la papelera de reciclaje en su fecha de expiración.

La expiración automática de reuniones es un mecanismo de limpieza ligero para reducir el desorden de almacenamiento creado por tmr antiguos. En promedio, en todos los clientes, el 96 % de los TMR no se ven después de 60 días y el 99 % no se ven después de 110 días. Creemos que casi todos los clientes se beneficiarán de la carga de almacenamiento reducida en su inquilino quitando las grabaciones que probablemente no se volverán a ver después de 60 días. Nuestro objetivo es proporcionar una experiencia lo más limpia posible para todos los clientes de forma predeterminada.

Use la expiración de la reunión para limitar OneDrive o SharePoint para el consumo de almacenamiento en la nube impulsado por Teams de reunión. Una grabación de reunión típica consume unos 400 MB por hora de grabación.

> [!NOTE]
> La fecha de expiración predeterminada máxima para los usuarios de A1 es de 30 días.

### <a name="expiration-date"></a>Fecha de expiración

- La fecha de expiración se calcula como el **día** en que se creó más el número predeterminado de días establecido en la **Teams directiva por el administrador**.
- La reproducción no afecta a la fecha de expiración.

### <a name="change-the-default-expiration-date"></a>Cambiar la fecha de expiración predeterminada

Los administradores pueden editar la configuración de expiración predeterminada en PowerShell o Teams centro de administración. Los cambios solo tendrán efecto *en los* TMR recién creados a partir de ese momento. No afectará a las grabaciones creadas antes de esa fecha. Los administradores no pueden cambiar la fecha de expiración de los TMR existentes. Esto se hace para proteger la decisión del usuario propietario del TMR. Esta configuración puede controlar tanto las reuniones como las llamadas.

El valor de fecha de expiración se puede establecer de la siguiente manera:

- Valor mínimo: **1 día**
- Valor máximo: **99.999 días**
- También puede establecer la fecha de expiración en **-1** para que las grabaciones nunca expiren.

Ejemplo de comando de PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

Puede establecer la fecha de expiración en el centro de Teams en **Directivas de reunión.** Después de activar **Reuniones expira automáticamente,** tendrá la opción de establecer la expiración de la grabación.

![Captura de pantalla del Centro de administración de la directiva de expiración de la reunión.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>Seguridad y cumplimiento

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>¿Debo confiar en esta característica para una estricta seguridad y cumplimiento normativo?

No, no debe confiar en esto para la protección legal, ya que los usuarios finales pueden modificar la fecha de expiración de las grabaciones que controlan.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>¿Una directiva de retención o eliminación que he establecido en el Centro de cumplimiento de seguridad & invalidará la configuración de expiración de la grabación Teams reunión?

Sí, todas las directivas que haya establecido en el centro de cumplimiento tendrán prioridad completa.

Por ejemplo:

- Si tiene una directiva que indica que todos los archivos de un sitio deben conservarse durante 100 días y la configuración de expiración para una grabación de reunión de Teams es de 30 días, la grabación se conservará durante los 100 días completos.
- Si tiene una directiva de eliminación que indica que todas las grabaciones de reunión de Teams se eliminarán después de cinco días y tiene una configuración de expiración para una grabación de reunión de Teams de 30 días, la grabación se eliminará después de cinco días.

### <a name="will-this-feature-enforce-file-retention"></a>¿Esta característica exigirá la retención de archivos?

No, los archivos no se conservarán debido a esta característica o a su configuración. Si un usuario con permisos de eliminación intenta eliminar un TMR que tiene una configuración de expiración, se ejecutará la acción de eliminación de ese usuario.

### <a name="what-skus-are-required-for-this-feature"></a>¿Qué SKU se requieren para esta función?

- Todas las SKU tendrán esta característica de forma predeterminada.
- Los usuarios de A1 se establecerán de forma predeterminada en un período máximo de expiración de 30 días, pero pueden cambiar la fecha de expiración según sea necesario.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>¿Qué sucede si quiero que el administrador tenga control total sobre el ciclo de vida de las grabaciones de reuniones y no quiera dar a los usuarios finales la capacidad de invalidar la fecha de expiración?

Se recomienda usar las directivas de retención y/o eliminación de seguridad y cumplimiento. Esta oferta está destinada a resolver problemas administrativos complejos basados en políticas y acuerdos de nivel de servicio.

La característica de expiración automática está pensada únicamente como un mecanismo de limpieza ligero para reducir el desorden de almacenamiento creado a partir de Teams grabaciones de reuniones.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>Si se migran futuros TMR de Classic Stream después de publicar esta característica, también se les ha aplicado la expiración automática?

No, los TMR migrados no tendrán una expiración establecida. En su lugar, recomendamos a los administradores que solo migren los TMR que quieran conservar. Se proporcionarán más detalles en la documentación de migración.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>¿En qué se diferencia esta característica del mensaje de expiración que veo cuando se carga una TMR en OneDrive y SharePoint error?

Cuando una grabación no se carga en OneDrive o SharePoint, la aplicación de Teams muestra un mensaje en el chat en el que los usuarios tienen hasta 21 días para descargar el TMR antes de que se elimine permanentemente del servidor Teams. Esta experiencia de expiración existente debido a cargas TMR fallida no está relacionada con la característica de OneDrive y SharePoint de expiración automática que se describe en el documento de ayuda.

## <a name="related-topics"></a>Temas relacionados

[Cambiar la fecha de expiración de la reunión: controles de usuario final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Administración de directivas de reunión en Teams](meeting-policies-overview.md)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)



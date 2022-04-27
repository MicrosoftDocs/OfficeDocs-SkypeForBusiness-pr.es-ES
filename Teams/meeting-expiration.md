---
title: Directivas de reunión y expiración de reuniones en Microsoft Teams
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
description: Obtenga información sobre cómo usar la configuración de la directiva de reunión para controlar la expiración de las reuniones en Microsoft Teams.
ms.openlocfilehash: 4496896cc86cfd64f175b9cab7c58c3798b9249f
ms.sourcegitcommit: 20d44ce9a62ba2fb60f989d2e7bbc9333055e783
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65063251"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Directivas de reunión y expiración de reuniones en Microsoft Teams

[Las directivas de reunión](meeting-policies-overview.md) de Microsoft Teams se usan para controlar si los usuarios de su organización pueden iniciar y programar reuniones, así como las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Puede administrar las directivas de reunión en el centro de administración de Microsoft Teams o mediante los cmdlets de PowerShell [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy.

La configuración de la directiva de reunión que controla si los usuarios pueden iniciar y programar reuniones, así como controlar la expiración de las reuniones programadas por los usuarios. Cuando expira el vínculo para unirse a una reunión y el id. de conferencia de una reunión, nadie puede unirse a la reunión. La siguiente configuración de directiva de reunión determina si los usuarios pueden iniciar y programar reuniones en Teams. En este artículo se explica la configuración de la reunión.

- [Reunirse ahora en canales](meeting-policies-in-teams-general.md#meet-now-in-channels): controla si un usuario puede iniciar una reunión no planeada en un canal.
- [Programación de reuniones](meeting-policies-in-teams-general.md#channel-meeting-scheduling) de canal: controla si un usuario puede programar una reunión en un canal.
- [Programación de reuniones privadas](meeting-policies-in-teams-general.md#private-meeting-scheduling): controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Outlook agregar](meeting-policies-in-teams-general.md#outlook-add-in): controla si un usuario puede programar una reunión privada desde Outlook. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Reunirse ahora en reuniones privadas](meeting-policies-in-teams-general.md#meet-now-in-private-meetings): controla si un usuario puede iniciar una reunión privada no planeada.

De forma predeterminada, esta configuración está activada. Cuando cualquiera de estos ajustes está desactivado, cualquier usuario al que se le asigne la directiva no podrá iniciar ni programar nuevas reuniones de ese tipo. Al mismo tiempo, la reunión se une a vínculos e identificadores de conferencia de todas las reuniones existentes de ese tipo que el usuario ya había iniciado o programado expirar.

Por ejemplo, si se asigna a un usuario una directiva de reunión en la que esta configuración de directiva de reunión se establece en **Activado** y, a continuación, desactiva la opción **Permitir reunirse ahora en canales** , ese usuario ya no podrá iniciar reuniones no planeadas en canales y los vínculos de unión del canal Reunirse ahora que creó el usuario expiraron. El usuario aún puede iniciar y programar otros tipos de reuniones y unirse a reuniones organizadas por otras personas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>¿Qué sucede cuando expiran el vínculo para unirse a la reunión y el id. de conferencia?

Cuando el vínculo para unirse a la reunión y el id. de conferencia de una reunión expiran, nadie puede unirse a la reunión. Cuando un usuario intenta unirse a la reunión a través del vínculo o por teléfono, recibirá un mensaje que indica que la reunión ya no está disponible. Las conversaciones, los archivos, las pizarras, las grabaciones, las transcripciones y otro contenido relacionado con la reunión se conservan y los usuarios aún pueden acceder a ellas.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>¿Qué sucede al activar y desactivar una configuración de directiva de reunión?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Activar y desactivar una configuración de directiva de reunión

Cuando una configuración de directiva de reunión se establece **en Activado**, los usuarios que tienen asignada la directiva pueden iniciar o programar reuniones de ese tipo y todos pueden unirse. Al cambiar la configuración de la directiva de reunión a **Desactivado**, los usuarios que tienen asignada la directiva no pueden iniciar ni programar nuevas reuniones de ese tipo, y los vínculos para unirse a la reunión y los identificadores de conferencia de las reuniones existentes que el usuario programó anteriormente expiran.

Tenga en cuenta que el usuario aún puede unirse a reuniones organizadas por otras personas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Cambiar una configuración de directiva de reunión de desactivado a activado

Al cambiar la configuración de una directiva de reunión de **Desactivado** a **Activado**, los usuarios asignados a la directiva pueden iniciar o programar reuniones de ese tipo. Si se desactiva una configuración de directiva de reunión y se vuelve a activar para un usuario, todas las reuniones programadas (y expiradas) previamente organizadas por el usuario se activan y las personas pueden unirse a ellas mediante el vínculo para unirse a la reunión o por teléfono.  

## <a name="meeting-expiration-scenarios"></a>Escenarios de expiración de reuniones

Este es un resumen de cómo funciona la expiración de las reuniones para cada una de las opciones de configuración de la directiva de reunión que se describen en este artículo.

|Si quieres...&nbsp;&nbsp; |Haz esto&nbsp;&nbsp;&nbsp;&nbsp;  |Comportamiento de unión a la reunión&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Expira las reuniones privadas de Reunirse ahora iniciadas por un usuario&nbsp;&nbsp;|Desactive **Reunirse ahora en reuniones privadas**.&nbsp;&nbsp;|Nadie puede unirse a reuniones privadas **de Reunirse ahora** iniciadas por el usuario.|
|Expirar reuniones privadas programadas por un usuario&nbsp;&nbsp;|Desactive la **programación de reuniones privadas** _y_ desactive **Outlook complemento**. &nbsp;&nbsp;|Nadie puede unirse a reuniones privadas programadas por el usuario. Esto impide que los usuarios se unan a las siguientes reuniones:<ul><li>Reuniones privadas que tuvieron lugar en el pasado.</li><li>Reuniones privadas que están programadas para el futuro y aún no se han producido.</li><li>Instancias futuras de reuniones privadas periódicas.</li></ul><br>Tanto **la programación de reuniones privadas** como **Outlook complemento** deben estar desactivados para que expiren las reuniones privadas programadas por un usuario. Si una opción está desactivada y la otra está activada, los vínculos para unirse a reuniones y los identificadores de conferencia de las reuniones existentes permanecen activos y no expirarán.|
|Canal de expiración **Reunirse ahora** reuniones iniciadas por un usuario&nbsp;&nbsp;|Desactive **Reunirse ahora en canales** _y_ desactive **la programación de reuniones del canal**.&nbsp;&nbsp;|Nadie puede unirse al canal **Reunirse ahora** las reuniones iniciadas por el usuario.|
|Expirar las reuniones del canal programadas por un usuario&nbsp;&nbsp;|Desactive la **programación de reuniones del canal**.&nbsp;&nbsp;|Nadie puede unirse a las reuniones del canal programadas por el usuario. Esto impide que los usuarios se unan a las siguientes reuniones:<ul><li>Reuniones de canal que tuvieron lugar en el pasado.</li><li>Reuniones de canal que están programadas para el futuro y aún no se han producido.</li><li>Instancias futuras de reuniones de canal periódicas.</li></ul>|

Si quiere que los usuarios tengan acceso a reuniones programadas o iniciadas previamente por un usuario determinado, puede:

- Active la configuración de la directiva de reunión para ese usuario.
- Desactive la configuración de la directiva de reunión para ese usuario y haga que otro usuario que tenga habilitada la configuración de directiva cree una nueva reunión para reemplazar la reunión expirada.

> [!NOTE]
> Si la reunión la envió un delegado, al que se le dio permiso para enviar invitaciones a reuniones en nombre de otra persona, como un jefe, la configuración de la directiva de reunión se aplicará a la persona que le concedió permiso (el jefe).

## <a name="changes-to-meeting-expiration"></a>Cambios en la expiración de la reunión

Todas las grabaciones de reuniones Teams recién creadas (TMR) tendrán una expiración predeterminada de 120 días. Esta opción está activada de forma predeterminada para todos los inquilinos. Esto significa que por defecto, todas las TMR *creadas después de activar esta característica* se eliminarán 120 días después de su fecha de creación. Los administradores también pueden configurar las reuniones para **que nunca expiren automáticamente**. El sistema de OneDrive y SharePoint supervisará la fecha de expiración establecida en todas las TMR y moverá automáticamente las TMR a la papelera de reciclaje en su fecha de expiración.

> [!NOTE]
> Una copia de la transcripción de la reunión se guarda en OneDrive SharePoint y una segunda copia se guarda en Exchange en almacenamiento temporal. La copia OSDP expira cuando el TMR expira automáticamente.

La expiración automática de las reuniones es un mecanismo ligero de limpieza para reducir el desorden de almacenamiento creado por los tmrs más antiguos. En promedio, en todos los clientes, el 96 % de los TMRs no se miran después de 60 días y el 99 % no se observa después de 110 días. Creemos que casi todos los clientes se beneficiarán de la menor carga de almacenamiento en su inquilino mediante la eliminación de grabaciones que probablemente no se volverán a ver después de 60 días. Nuestro objetivo es proporcionar una experiencia lo más limpia posible a todos los clientes de forma predeterminada.

Use la expiración de la reunión para limitar la OneDrive o SharePoint para el consumo de almacenamiento en la nube controlado por Teams registros de reunión. Una grabación de reunión típica consume alrededor de 400 MB por hora de grabación.

> [!NOTE]
> La fecha de expiración predeterminada máxima para los usuarios de A1 es de 30 días.

### <a name="expiration-date"></a>Fecha de expiración

- La fecha de expiración se calcula como el **día en que se crea** más el **número predeterminado de días establecido en la directiva de Teams por el administrador**.
- La reproducción no afecta a la fecha de expiración.

### <a name="change-the-default-expiration-date"></a>Cambiar la fecha de expiración predeterminada

Los administradores pueden editar la configuración de expiración predeterminada en PowerShell o en el centro de administración de Teams. Cualquier cambio sólo afectará a los R TMR *recién creados* a partir de ese momento. No afectará a las grabaciones creadas antes de esa fecha. Los administradores no pueden cambiar la fecha de expiración en los TMR existentes. Esto se hace para proteger la decisión del usuario propietario de la TMR. Esta configuración puede controlar las reuniones y las llamadas.

El valor de la fecha de expiración se puede establecer de la siguiente manera:

- Valor mínimo: **1 día**
- Valor máximo: **99.999 días**
- También puede establecer la fecha de expiración en **-1** para que las grabaciones nunca expiren.

Ejemplo de comando de PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

Puede establecer la fecha de expiración en el Teams centro de administración en **Directivas de reunión.** Después de activar **reuniones expiran automáticamente,** obtendrá la opción de establecer una expiración de la grabación.

![Captura de pantalla del Centro de administración de la directiva de expiración de la reunión.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>Seguridad y cumplimiento

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>¿Debo confiar en esta característica para una estricta conformidad y seguridad?

No, no debe confiar en esto para la protección legal, ya que los usuarios finales pueden modificar la fecha de expiración de las grabaciones que controlan.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>¿Una directiva de retención o eliminación que he establecido en el Centro de cumplimiento de & de seguridad invalidará la configuración de expiración de la grabación de Teams reunión?

Sí, todas las directivas que haya establecido en el Centro de cumplimiento tendrán prioridad completa.

Por ejemplo:

- Si tiene una directiva que indica que todos los archivos de un sitio deben conservarse durante 100 días y la configuración de expiración de una Teams grabación de una reunión es de 30 días, la grabación se conservará durante los 100 días completos.
- Si tiene una directiva de eliminación que indica que todas las grabaciones de Teams reunión se eliminarán después de cinco días y tiene una configuración de expiración para una Teams grabación de la reunión de 30 días, la grabación se eliminará después de cinco días.

### <a name="will-this-feature-enforce-file-retention"></a>¿Esta característica exigirá la retención de archivos?

No, los archivos no se conservarán debido a esta característica o su configuración. Si un usuario con permisos de eliminación intenta eliminar un TMR que tiene una configuración de expiración, se ejecutará la acción de eliminación de ese usuario.

### <a name="what-skus-are-required-for-this-feature"></a>¿Qué SKU se requieren para esta función?

- Todas las SKU tendrán esta característica de forma predeterminada.
- De forma predeterminada, los usuarios de A1 tendrán un período de expiración máximo de 30 días, pero pueden cambiar la fecha de expiración según sea necesario.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>¿Qué ocurre si deseo que el administrador tenga control total sobre el ciclo de vida de las grabaciones de las reuniones y no quiera ofrecer a los usuarios finales la posibilidad de invalidar la fecha de expiración?

Se recomienda usar las directivas de retención y eliminación de seguridad y cumplimiento. Esta oferta está destinada a resolver problemas administrativos complejos basados en políticas y acuerdos de nivel de servicio.

La característica de expiración automática se ha diseñado únicamente como un mecanismo ligero de limpieza para reducir el desorden de almacenamiento creado a partir de grabaciones de reuniones de Teams antiguas.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>Si se migran futuros TMR de Classic Stream después de publicar esta característica, también se les ha aplicado la expiración automática?

No, los TMR migrados no tendrán una expiración establecida. En su lugar, recomendamos a los administradores que solo migren los TMR que quieran conservar. Se proporcionarán más detalles en la documentación de migración.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>¿Cómo es diferente esta característica del mensaje de expiración que veo cuando una carga TMR a OneDrive y SharePoint falla?

Cuando una grabación no se puede cargar en OneDrive o SharePoint, la aplicación Teams muestra un mensaje en el chat de que los usuarios tienen hasta 21 días para descargar la TMR antes de que se elimine permanentemente del servidor Teams. Esta experiencia de expiración existente debido a las cargas de TMR erróneas no está relacionada con el OneDrive y SharePoint característica de expiración automática que se trata en el documento de ayuda.

### <a name="how-do-i-know-the-distribution-of-tmr-playbacks-so-i-know-what-the-optimal-auto-expiration-default-should-be-for-my-tenant"></a>Cómo conozco la distribución de las reproducciones TMR para saber cuál debe ser el valor predeterminado de expiración automática óptima para mi inquilino?

1. Busque el vídeo en la biblioteca.
1. Seleccione **...** >  **Detalles**
1. Seleccione el número de vistas en la parte superior del panel de detalles.

Verá las estadísticas de archivo que muestran:

- El número de visores únicos
- El número de vistas totales
- La tendencia de los espectadores y las vistas día a día de los últimos 90 días
- Retención de visualización (qué parte del vídeo se ha visto o no)

### <a name="when-will-the-file-be-deleted"></a>¿Cuándo se eliminará el archivo?

El archivo se eliminará dentro de los cinco días posteriores a la fecha de expiración, aunque esto no es una garantía estricta. El propietario del archivo recibirá una notificación por correo electrónico cuando expire la grabación y se le dirigirá a la papelera de reciclaje para recuperar la grabación.

> [!NOTE]
> En la fecha de expiración, la grabación se mueve a la Papelera de reciclaje y se borra el campo de fecha de expiración. Si recupera la grabación de la Papelera de reciclaje, esta característica no la eliminará de nuevo porque se ha borrado la fecha de expiración.

## <a name="related-topics"></a>Temas relacionados

[Cambiar la fecha de expiración de la reunión: controles del usuario final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Administración de directivas de reunión en Teams](meeting-policies-overview.md)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

---
title: Administrar las directivas de reunión para la grabación y la transcripción
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: Aprenda a administrar la configuración de directivas de reuniones en Teams para la grabación y la transcripción.
ms.openlocfilehash: 57e90984cde312f1804d5d2144c82a4d252822b6
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466208"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Configuración de la directiva de reunión para grabar & transcripción

En este artículo se describe la configuración de la directiva de reunión específica para la grabación y la transcripción en una reunión de Teams. Esta configuración puede encontrarse en el Centro de administración del equipo en **Directivas** >  de **reunión de reuniones**.

## <a name="transcription"></a>Transcripción

Esta es una combinación de directiva por organizador y por usuario. Esta configuración controla si se pueden usar las características de subtítulos y transcripción durante la reproducción de las grabaciones de la reunión. La persona que inició la grabación necesita esta configuración activada para que estas características funcionen con su grabación.

Al activar esta opción, se crea una copia de la transcripción que se almacena con la grabación de la reunión, lo que habilita **Búsqueda**, **CC** y **transcripciones** en la grabación de la reunión.

La transcripción para las reuniones grabadas actualmente solo se admite para los usuarios que establecen su idioma o hablan inglés en las reuniones de Teams.

## <a name="cloud-recording"></a>Grabación en la nube

Esta configuración es una combinación de una directiva por organizador y por usuario, y controla si se pueden grabar las reuniones. La grabación la puede iniciar el organizador de la reunión u otro participante de la reunión si la configuración de directiva está activada para el participante y si es un usuario autenticado de la misma organización.

Las personas de fuera de su organización, como los usuarios federados y anónimos, no pueden iniciar la grabación. Los invitados no pueden iniciar ni detener la grabación.

![Captura de pantalla que muestra las opciones de grabación](media/meeting-policies-recording.png)

Veamos el ejemplo siguiente.

| Usuario                 | Directiva de reuniones         | Permitir la grabación en la nube |
|----------------------|------------------------|-----------------------|
| Daniela              | Global                 | Desactivado                   |
| Amanda               | Location1MeetingPolicy | Activado                    |
| Juan (externo) | No aplicable         | No aplicable        |

- Las reuniones organizadas por Daniela no se pueden grabar.
- Amanda no puede grabar reuniones organizadas por Daniela.
- Las reuniones organizadas por Amanda se pueden grabar.
- Daniela no puede grabar reuniones organizadas por Amanda.
- John no puede grabar reuniones organizadas por Amanda.

Para más información sobre la grabación de reuniones en la nube, consulte [Grabación de reuniones en la nube de Teams](cloud-recording.md).

## <a name="meetings-automatically-expire"></a>Las reuniones expiran automáticamente

Esta configuración controla si las grabaciones de reuniones expiran automáticamente. Después de activar esta configuración, obtendrá la opción de establecer un tiempo de expiración predeterminado, medido en días.

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="Captura de pantalla del Centro de administración de Teams de la configuración de expiración automática de reuniones.":::

Esta configuración proporciona una herramienta sencilla que reduce la cantidad de almacenamiento que usan las grabaciones anteriores. El sistema OneDrive y SharePoint supervisará el conjunto de expiración de todas las grabaciones de reuniones y moverá automáticamente las grabaciones a la papelera de reciclaje en su fecha de expiración.

### <a name="default-expiration-time"></a>Hora de expiración predeterminada

Todas las grabaciones de reuniones recién creadas tendrán una expiración predeterminada de 120 días; todas las grabaciones creadas después de activar esta función se eliminarán 120 días después de su fecha de creación.

> [!NOTE]
> El tiempo máximo de expiración predeterminado para los usuarios de A1 es de 30 días.

#### <a name="changing-default-expiration-time"></a>Cambiar la hora de expiración predeterminada

Los administradores pueden editar la configuración De expiración predeterminada en PowerShell o en el Centro de administración de Teams. Cualquier cambio solo afectará a las grabaciones de reuniones recién creadas a partir de ese momento; no afectarán a las grabaciones creadas antes de esa fecha.

Los administradores no pueden cambiar la fecha de expiración de las grabaciones de reuniones existentes. Esto se hace para proteger la decisión del usuario propietario de la grabación. Esta configuración puede controlar las reuniones y las llamadas.

El valor de expiración es un entero para días.  Esto se puede establecer de la siguiente manera:

- Valor mínimo: **1**
- Valor máximo: **99999**
- También puede establecer la fecha de expiración en **-1** en PowerShell para que las grabaciones nunca expiren.

Ejemplo de comando de PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>Cumplimiento

No debe confiar en la configuración de expiración de la reunión para la protección legal, ya que los usuarios finales pueden modificar la fecha de expiración de las grabaciones que controlan.

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Registrar la configuración de expiración y las directivas de retención de Microsoft 365 en Microsoft Purview

La retención de archivos tiene prioridad sobre la eliminación de archivos. Una directiva de expiración de la grabación de reuniones de Teams con una directiva de retención de Purview no puede eliminarse hasta después de completar el período de retención. Por ejemplo, si tiene una directiva de retención de Purview que indica que se conservará un archivo durante cinco años y una directiva de expiración de registro de la reunión de Teams establecida durante 60 días, la directiva de expiración de la grabación de la reunión de Teams eliminará la grabación después de cinco años.

Si tiene una reunión de Teams en la que se registra la directiva de expiración y la directiva de eliminación de Purview con fechas de eliminación diferentes, el archivo se eliminará lo antes posible de las dos fechas. Por ejemplo, si tiene una directiva de eliminación de Purview que indica que se eliminará un archivo después de un año y una reunión de Teams con la fecha de expiración establecida durante 120 días, la directiva de expiración de la grabación de la reunión de Teams eliminará el archivo pasados 120 días.

Los usuarios pueden eliminar manualmente sus grabaciones antes de la fecha de expiración, a menos que exista una directiva de retención de Purview que lo impida.

### <a name="deletion-of-recordings"></a>Eliminación de grabaciones

La grabación suele eliminarse en el plazo de un día después de la fecha de expiración, pero en raras ocasiones podría tardar hasta cinco días. El propietario del archivo recibirá una notificación por correo electrónico cuando expire la grabación y se le dirigirá a la papelera de reciclaje para recuperar la grabación.

> [!NOTE]
> En la fecha de expiración, la grabación se mueve a la Papelera de reciclaje y se borra el campo de fecha de expiración. Si recupera la grabación de la Papelera de reciclaje, esta característica no la eliminará de nuevo porque se ha borrado la fecha de expiración.

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>Expiración de las grabaciones migradas de Stream (Clásico)

Las grabaciones migradas desde Stream (Clásico) no incluirán un conjunto de expiración en ellas. En su lugar, recomendamos a los administradores que solo migren las grabaciones que quieran conservar. Encontrará más detalles en [la documentación de migración Stream (Clásico)](/stream/streamnew/stream-classic-to-new-migration-overview).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Almacenar grabaciones fuera de su país o región

Esta directiva controla si los registros de reunión se pueden almacenar de forma permanente en otro país o región. Si está habilitada, las grabaciones no se pueden migrar. Para obtener más información sobre las reuniones en la nube y dónde se almacenan las grabaciones, consulte Grabación de reuniones en la [nube de Teams](cloud-recording.md).

## <a name="related-topics"></a>Temas relacionados

- [Administración de directivas de reunión en Teams](meeting-policies-overview.md)
- [Asignar directivas a usuarios en Teams](policy-assignment-overview.md)
- [Grabación de reuniones en la nube](cloud-recording.md)
- [Administrar quién puede programar reuniones](manage-who-can-schedule-meetings.md)

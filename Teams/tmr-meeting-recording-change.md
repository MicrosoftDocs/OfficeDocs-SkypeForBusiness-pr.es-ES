---
title: Usar OneDrive para la empresa y SharePoint para grabaciones de reuniones
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo cambiar de flujo a OneDrive para la empresa y el almacenamiento de grabaciones de reuniones de SharePoint en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce6c5cc546c3c2e8b8369247de38e0f734b9b467
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739228"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar OneDrive para la empresa y SharePoint o Stream para grabaciones de reuniones

> [!Note]
> El cambio de usar Microsoft Stream a OneDrive para la empresa y a Microsoft SharePoint para las grabaciones de la reunión será un enfoque por fases.


|Fecha|Produce|
|---|-----------------|
|Principios del cuarto trimestre de CY20|**Los equipos que se registran en OneDrive para la empresa y SharePoint están disponibles para participar o para anular la suscripción.**<br> Los administradores de inquilinos pueden optar por OneDrive para la empresa o no participar en la configuración de la Directiva de Teams de PowerShell|
|CY20 Trim Trim|**Los equipos graban el registro de OneDrive para la empresa y SharePoint como predeterminado para los inquilinos que no se desactivan**<br> Esta es la ruta recomendada para la mayoría de los clientes|
|T1 CY21|**Guardar equipos ya no se permite la grabación de reuniones en una secuencia clásica**<br>Todos los inquilinos guardarán los equipos de la grabación de reuniones en OneDrive para la empresa y SharePoint|


Microsoft Teams tiene un nuevo método para guardar las grabaciones de la reunión. Como primera fase de una transición de la secuencia clásica de Microsoft a la [nueva secuencia](https://docs.microsoft.com/stream/streamnew/new-stream), este método almacena las grabaciones en Microsoft OneDrive para la empresa y SharePoint en Microsoft 365 y ofrece muchas ventajas.

Entre las ventajas de usar OneDrive para la empresa y SharePoint para almacenar grabaciones, se incluyen:

- Directivas de retención para la grabación de reuniones de Teams (TMR) (etiquetas de autoretención S + C E5)
- Beneficios de OneDrive para la empresa y SharePoint Information Governance
- Fácil de establecer permisos y compartir
- Compartir grabaciones con invitados (usuarios externos) solo con recursos compartidos explícitos
- Solicitar el flujo de acceso
- Proporcionar vínculos compartidos de OneDrive para la empresa y SharePoint
- Mayor cuota
- Las grabaciones de reunión están disponibles más rápido
- **Ir** a soporte técnico de inquilino local
- Compatibilidad con múltiples geografías: las grabaciones se almacenan en una región específica para ese usuario.
- Ofrece tu propia clave (BYOK)
- Mejora de la calidad de la transcripción y atribución del altavoz

Hay algunas limitaciones que debe tener en cuenta:

- Habrá subtítulos y transcripciones solo en inglés.
- No podrás buscar transcripciones ni su contenido.
- No podrá modificar las transcripciones, pero podrá activar o desactivar las leyendas....
- Puede controlar con quién comparte la grabación, pero no podrá bloquear a los usuarios con acceso compartido para que no descarguen la grabación.
- No recibirá un correo electrónico cuando la grabación termine de guardar, pero la grabación aparecerá en la conversación de la reunión una vez que haya finalizado. Esto se hará mucho más rápido de lo que hacía en la secuencia anteriormente

Vea "grabación de reuniones" para obtener más información.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurar la opción de grabación de la reunión para OneDrive para la empresa y SharePoint

> [!Note]
> La opción de grabación de la reunión es una opción del nivel de directiva de Teams. En el ejemplo siguiente se muestra cómo establecer la directiva global. Asegúrese de establecer la opción de grabación de la reunión para la Directiva o las directivas que ha asignado a los usuarios. Los cambios en la política de reunión de Teams tardan unos minutos en propagarse. Vuelva a consultar después de unas pocas horas de configuración y, después, cierre sesión e inicie sesión de nuevo.

1. Instalar Skype empresarial online PowerShell. 
**Nota**: el conector de Skype empresarial online actualmente forma parte del último módulo de PowerShell. Si está usando la versión pública de Teams más reciente de PowerShell, no necesita instalar el conector de Skype empresarial online. Consulte [administrar Skype empresarial online con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

    a. Descargue [Skype empresarial online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true). 

    b. Siga las indicaciones para instalarlo.

    c. Reinicie el equipo.

2. Iniciar PowerShell como administrador

3. Importe el conector SkypeOnline e inicie sesión como administrador de equipos.

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true) para configurar una directiva de reunión de Teams para que pase de almacenamiento de flujo a OneDrive para la empresa y SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>No se puede elegir OneDrive para la empresa y SharePoint para seguir usando Stream

Incluso si una directiva dice que está configurada para **transmitirse**, es posible que no esté configurada. Normalmente, si no se establece la Directiva, la configuración predeterminada es **transmitir**. Sin embargo, con este nuevo cambio, si desea optar por no usar SharePoint o OneDrive, debe restablecer la Directiva en **Stream** para asegurarse de que es la opción predeterminada.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Permisos o acceso basado en roles


|Tipo de reunión                               | ¿Quién hizo clic en grabar?| ¿Dónde se encuentran las tierras de la grabación?                               |¿Quién tiene acceso? Lectura/escritura, d o compartida                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|llamada de 1:1 con partes internas             |Autor de llamada                 |Cuenta de OneDrive para la empresa del autor de la llamada                        |-La persona que llama es propietaria, tiene derechos completos: el destinatario de la llamada (si está en el mismo inquilino) tiene acceso de solo lectura, sin acceso de uso compartido (si se encuentra en un inquilino diferente). La persona que llama debe compartirla con el destinatario|
|llamada de 1:1 con partes internas             |Destinatario de la llamada                 |Cuenta de OneDrive para la empresa de la persona que llama                        |-La persona que llama es propietario, tiene un llamador de derechos completos (si en el mismo inquilino tiene acceso de solo lectura, sin acceso compartido, el autor de la llamada (si se encuentra en un inquilino diferente) no tiene acceso. La persona que llama debe compartirla con el destinatario de la llamada|
|llamada de 1:1 con una llamada externa             |Autor de llamada                 |Cuenta de OneDrive para la empresa del autor de la llamada                        |-Quien llama es propietario, tiene derechos completos; la llamada no tiene acceso. La persona que llama debe compartirla con el destinatario|
|llamada de 1:1 con una llamada externa             |Destinatario de la llamada                 |Cuenta de OneDrive para la empresa del autor de la llamada                        |-Quien llama es propietario, tiene derechos plenos; el autor de la llamada no tiene acceso. La persona que llama debe compartirla con quien llama|
|Llamada grupal                                 |Cualquier miembro de la llamada |Miembro que hizo clic en la cuenta de OneDrive para la empresa del registro  |-El miembro que hizo clic en el registro tiene derechos completos; otros miembros del mismo inquilino tienen derechos de lectura; otros miembros de inquilinos diferentes no tienen derechos.|
|Reunión programada/ad hoc                    |Organizador              |Cuenta de OneDrive para la empresa del organizador                     |-Organizer tiene derechos plenos para la grabación; todos los demás miembros de la reunión tienen acceso de lectura|
|Reunión programada/ad hoc                    |Otro miembro de la reunión   |Miembro que hizo clic en el registro                                  |-El miembro que hizo clic en el registro tiene derechos plenos para que el organizador de grabaciones tenga derechos de edición y se pueda compartir; todos los demás miembros tienen acceso de lectura|
|Reunión ad hoc o programada con usuarios externos|Organizador              |Cuenta de OneDrive para la empresa del organizador                     |-Organizer tiene derechos plenos en la grabación: todos los demás miembros de la reunión desde el mismo inquilino que el organizador tienen acceso de lectura; todos los demás miembros externos no tienen acceso y el organizador debe compartirlo.|
|Reunión ad hoc o programada con usuarios externos|Otro miembro de la reunión   |Miembro que hizo clic en el registro                                  |-El miembro que hizo clic en el registro tiene derechos plenos para que el organizador de grabaciones tenga derechos de edición y se pueda compartir: todos los demás miembros de la reunión desde el mismo inquilino como el organizador tienen acceso de lectura; todos los demás miembros externos no tienen acceso y el organizador debe compartirlos.|
|Reunión de canal                            |Miembro del canal         |Ubicación de SharePoint de los equipos de ese canal                   |-El miembro que hizo clic en el registro tiene derechos de edición para la grabación; los permisos de todos los miembros se basan en los permisos de SharePoint de canal|


## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Dónde se almacenará la grabación de la reunión?**

- Para las reuniones que no son de canal, la grabación se almacena en una carpeta denominada **grabaciones** que se encuentra en el nivel superior de OneDrive para la empresa, que pertenece a la persona que inició la grabación de la reunión. Ejemplo

  <i>OneDrive para la empresa</i> / de la grabadora **Grabaciones**

- Para las reuniones de canal, la grabación se almacena en la biblioteca de documentación del sitio de Teams en una carpeta denominada **grabaciones**. Ejemplo

  <i>Equipos nombre: nombre</i> / del canal **Documentos** / **Grabaciones**

**¿Cómo puedo controlar las grabaciones de antiguos empleados?**

Puesto que los vídeos son como cualquier otro archivo de OneDrive para la empresa y SharePoint, controlar la propiedad y la retención después de que un empleado deje de pertenecer seguirá el [proceso normal de onedrive para la empresa y SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).

**¿Quién tiene permisos para ver la grabación de la reunión?**

- Para las reuniones que no son de canal, todas las invitaciones a reuniones, excepto los usuarios externos, obtendrán automáticamente un vínculo compartido personalmente. Los usuarios externos tendrán que agregarlos explícitamente a la lista compartida por el organizador de la reunión o la persona que inició la grabación de la reunión.

- Para las reuniones de canal, los permisos se heredan de la lista de propietarios y miembros en el canal.

**¿Cómo puedo administrar transcripciones?**

Los clientes que opten por esta versión preliminar no tendrán subtítulos disponibles en las grabaciones de reuniones de sus equipos que se migren a OneDrive para la empresa y SharePoint.Estamos trabajando para agregar subtítulos, empezando con los subtítulos en inglés, para hacer una reunión de las grabaciones en octubre de 2020.

Los subtítulos cerrados estarán disponibles en las grabaciones de reuniones de Teams para los clientes que hayan optado por permitir transcripciones según se describe en las [grabaciones en la nube de Teams](cloud-recording.md) .

Los subtítulos ayudan a crear contenido inclusivo para los visores de todas las capacidades. Como propietario, puede ocultar los subtítulos, aunque la transcripción seguirá estando disponible en Teams, a menos que elimine los subtítulos de Teams. Ver [Cómo activar o desactivar las grabaciones de reuniones](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Los subtítulos se admiten para las grabaciones de reuniones de equipos por 60 días desde que se grabó la reunión.

Los subtítulos cerrados no son totalmente compatibles si el registro de reuniones de Teams se mueve o se copia desde su ubicación original en OneDrive o SharePoint.

**¿Cómo se verá afectada mi cuota de almacenamiento**

Los equipos que reunión graban archivos en OneDrive para la empresa y SharePoint se incluyen en su cuota para esos servicios. Consulte [cuota de SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) y [cuota de OneDrive para la empresa] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .

**¿Cómo puedo reproducir una grabación de reuniones de Teams?**

El vídeo se reproducirá en el reproductor de vídeo de OneDrive para la empresa o SharePoint según dónde se obtenga acceso al archivo.

**Si tiene previsto agregar a la transmisión, ¿los vídeos existentes se mantendrán como están y durante cuánto tiempo?**

La secuencia como plataforma no quedará obsoleta en un futuro próximo. Los vídeos que actualmente viven en la secuencia permanecerán allí hasta que empiece la migración. Después de la migración, esos vídeos también se migrarán a ODSP. Para obtener más información, consulta [aquí](https://docs.microsoft.com/stream/streamnew/classic-migration) .

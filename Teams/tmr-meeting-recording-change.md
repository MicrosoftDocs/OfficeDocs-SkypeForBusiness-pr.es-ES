---
title: Usar OneDrive y SharePoint para grabaciones de reuniones
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
ms.openlocfilehash: 83a7a0628d76a96318081ec51a039d458ea1570f
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444236"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar OneDrive para la empresa y SharePoint o Stream para grabaciones de reuniones

> [!Note]
> El cambio de usar Microsoft Stream a OneDrive para la empresa y a Microsoft SharePoint para las grabaciones de la reunión será un enfoque por fases.

|||
|---|-----------------|
|Fecha|Produce|
|Principios del cuarto trimestre de CY20|**Los equipos que se registran en OneDrive para la empresa y SharePoint están disponibles para participar o para anular la suscripción.**<br> Los administradores de inquilinos pueden optar por OneDrive para la empresa o no participar en la configuración de la Directiva de Teams de PowerShell|
|CY20 Trim Trim|**Los equipos graban el registro de OneDrive para la empresa y SharePoint como predeterminado para los inquilinos que no se desactivan**<br> Esta es la ruta recomendada para la mayoría de los clientes|
T1 CY21|**Guardar equipos ya no se permite la grabación de reuniones en una secuencia clásica**<br>Todos los inquilinos guardarán los equipos de la grabación de reuniones en OneDrive para la empresa y SharePoint|
|||

Microsoft Teams tiene un nuevo método para guardar las grabaciones de la reunión. Como primera fase de una transición de la secuencia clásica de Microsoft a la [nueva secuencia](https://docs.microsoft.com/stream/streamnew/new-stream), este método almacena las grabaciones en Microsoft OneDrive y SharePoint en Microsoft 365 y ofrece muchas ventajas.

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

1. Instale la consola de administración de PowerShell de Skype empresarial online.

    a. Descargue [Skype empresarial online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).

    b. Siga las indicaciones para instalarlo.

    c. Reinicie el equipo.

2. Iniciar PowerShell como administrador

3. Importe el conector SkypeOnline e inicie sesión como administrador de equipos.

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para configurar una directiva de reunión de Teams para que pase de la secuencia de almacenamiento a la de ODSP.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>No se puede elegir OneDrive para la empresa y SharePoint para seguir usando Stream

Incluso si una directiva dice que está configurada para **transmitirse**, es posible que no esté configurada. Normalmente, si no se establece la Directiva, la configuración predeterminada es **transmitir**. Sin embargo, con este nuevo cambio, si desea optar por no usar SharePoint o OneDrive, debe restablecer la Directiva en **Stream** para asegurarse de que es la opción predeterminada.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Dónde se almacenará la grabación de la reunión?**

- Para las reuniones que no son de canal, la grabación se almacena en una carpeta denominada **grabaciones** que se encuentra en el nivel superior de OneDrive que pertenece a la persona que inició la grabación de la reunión. Ejemplo

  <i>OneDrive para la empresa</i> / de la grabadora **Grabaciones**

- Para las reuniones de canal, la grabación se almacena en la biblioteca de documentación del sitio de Teams en una carpeta denominada **grabaciones**. Ejemplo

  <i>Equipos nombre: nombre</i> / del canal **Documentos** / **Grabaciones**

**¿Cómo puedo controlar las grabaciones de antiguos empleados?**

Puesto que los vídeos son como cualquier otro archivo de OneDrive y SharePoint, la administración de la propiedad y la retención después de que un empleado salga el proceso normal de [onedrive y SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).

**¿Quién tiene permisos para ver la grabación de la reunión?**

- Para las reuniones que no son de canal, todas las invitaciones a reuniones, excepto los usuarios externos, obtendrán automáticamente un vínculo compartido personalmente. Los usuarios externos tendrán que agregarlos explícitamente a la lista compartida por el organizador de la reunión o la persona que inició la grabación de la reunión.

- Para las reuniones de canal, los permisos se heredan de la lista de propietarios y miembros en el canal.

**¿Cómo puedo administrar transcripciones?**

Los clientes que opten por esta versión preliminar no tendrán subtítulos disponibles en las grabaciones de reuniones de sus equipos que se migren a OneDrive y SharePoint.Estamos trabajando para agregar subtítulos, empezando con los subtítulos en inglés, para hacer una reunión de las grabaciones en octubre de 2020.

Los subtítulos cerrados estarán disponibles en las grabaciones de reuniones de Teams para los clientes que hayan optado por permitir transcripciones según se describe en las [grabaciones en la nube de Teams](cloud-recording.md) .

Los subtítulos ayudan a crear contenido inclusivo para los visores de todas las capacidades. Como propietario, puede ocultar los subtítulos, aunque la transcripción seguirá estando disponible en Teams, a menos que elimine los subtítulos de Teams. Ver [Cómo activar o desactivar las grabaciones de reuniones](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Los subtítulos se admiten para las grabaciones de reuniones de equipos por 60 días desde que se grabó la reunión.

**¿Cómo se verá afectada mi cuota de almacenamiento**

Los equipos que reunión graban archivos en OneDrive para la empresa y SharePoint se incluyen en su cuota para esos servicios. Consulte [cuota de SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) y [cuota de OneDrive para la empresa] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .

**¿Cómo puedo reproducir una grabación de reuniones de Teams?**

El vídeo se reproducirá en el reproductor de vídeo de OneDrive para la empresa o SharePoint según dónde se obtenga acceso al archivo.

**Si tiene previsto agregar a la transmisión, ¿los vídeos existentes se mantendrán como están y durante cuánto tiempo?**

La secuencia como plataforma no quedará obsoleta en un futuro próximo. Los vídeos que actualmente viven en la secuencia permanecerán allí hasta que empiece la migración. Después de la migración, esos vídeos también se migrarán a ODSP. Para obtener más información, consulta [aquí](https://docs.microsoft.com/stream/streamnew/classic-migration) .

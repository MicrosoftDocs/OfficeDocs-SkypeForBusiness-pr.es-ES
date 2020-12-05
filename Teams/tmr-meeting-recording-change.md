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
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46d3b53f62a3bb497f173c9efd418b7ed88444c7
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578513"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar OneDrive para la empresa y SharePoint o Stream para grabaciones de reuniones

> [!Note]
> El cambio de usar Microsoft Stream a OneDrive para la empresa y a Microsoft SharePoint para las grabaciones de la reunión será un enfoque por fases.

|<div style="width:290px">Posteriormente&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Produce&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 de octubre de 2020 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Puede habilitar la Directiva de reunión de Teams para que se guarden las grabaciones de reunión en OneDrive para la empresa y en SharePoint en lugar de en Microsoft Stream (clásico).|
|Cómo empezar el 11 de enero de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todos los nuevos equipos se guardarán grabaciones de reuniones en OneDrive para la empresa y SharePoint a menos que retrase este cambio modificando las directivas de reunión de los equipos de su organización y configurarlas de forma explícita en **flujo**. Ver el informe de directiva como una transmisión no es suficiente. Debe establecer de forma explícita el valor de la Directiva en **Stream**.|
|Despliegue a partir del 1 de marzo de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clientes empresariales**<br>No se pueden guardar nuevas grabaciones de reuniones en Microsoft Stream (clásico); todos los clientes guardarán automáticamente las grabaciones de la reunión en OneDrive para la empresa y SharePoint, incluso si han cambiado las políticas de reunión de sus equipos para **transmitirse**. Recomendamos que los clientes destaquen esta característica antes de esta fecha para poder controlar la temporización de la versión. |
|Cómo empezar el 7 de julio de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clientes de educación**<br>No se pueden guardar nuevas grabaciones de reuniones en Microsoft Stream (clásico); todos los clientes guardarán automáticamente las grabaciones de la reunión en OneDrive para la empresa y SharePoint, incluso si han cambiado las políticas de reunión de sus equipos para **transmitirse**. Recomendamos que los clientes destaquen esta característica antes de esta fecha para poder controlar la temporización de la versión. Hemos actualizado esta programación para ofrecer a los clientes de educación la capacidad de completar los semestres en curso. |

> [!Note]
> Recomendamos que los clientes empresariales y educativos, para controlar mejor el cambio de su organización, participen siempre que se sienta cómodo con el cambio en lugar de esperar a que se produzca.

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

La opción de grabación de la reunión es una opción del nivel de directiva de Teams. En el ejemplo siguiente se muestra cómo establecer la directiva global. Asegúrese de establecer la opción de grabación de la reunión para la Directiva o las directivas que ha asignado a los usuarios.

> [!Note]
> Los cambios en la política de reunión de Teams tardan unos minutos en propagarse. Vuelva a consultar después de unas pocas horas de configuración y, después, cierre sesión e inicie sesión de nuevo.

1. Instalar Skype empresarial online PowerShell.
**Nota**: el conector de Skype empresarial online actualmente forma parte del último módulo de PowerShell. Si está usando la versión pública de Teams más reciente de PowerShell, no necesita instalar el conector de Skype empresarial online. Consulte [administrar Skype empresarial online con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

    a. Descargue [Skype empresarial online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

    b. Siga las indicaciones para instalarlo.

    c. Reinicie el equipo.

2. Iniciar PowerShell como administrador

3. Importe el conector SkypeOnline e inicie sesión como administrador de Teams.

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Use [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) para configurar una directiva de reunión de Teams para que pase de almacenamiento de flujo a OneDrive para la empresa y SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Si algunos de sus usuarios han asignado una directiva por organizador o por usuario, debe establecer esta configuración en esta Directiva si quiere que también almacene las grabaciones de la reunión en OneDrive para la empresa y SharePoint. Para obtener más información, vea [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md).

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>No se puede elegir OneDrive para la empresa y SharePoint para seguir usando Stream

Incluso si una directiva dice que está configurada para **transmitirse**, es posible que no esté configurada. Normalmente, si no se establece la Directiva, la configuración predeterminada es **transmitir**. Sin embargo, con este nuevo cambio, si desea optar por no usar SharePoint o OneDrive para la empresa, debe restablecer la Directiva en **streaming** para asegurarse de que es la opción predeterminada.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Permisos o acceso basado en roles

> [!Note]
> Recomendamos que el destinatario sea un usuario conectado al compartir grabaciones de reuniones de Teams. Esto se puede lograr seleccionando la opción **personas de (su organización)** al compartir el archivo según se describe en [compartir archivos o carpetas de SharePoint](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US). El uso compartido externo no está diseñado para la distribución de archivos grandes o de un gran número de archivos. Para evitar situaciones de fraude y abuso, es posible que experimente problemas al compartir una gran cantidad de datos con usuarios externos.

|Tipo de reunión                               | ¿Quién hizo clic en grabar?| ¿Dónde se encuentran las tierras de la grabación?                               |¿Quién tiene acceso? R/W, R o compartida                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|llamada de 1:1 con partes internas             |Autor de llamada                 |Cuenta de OneDrive para la empresa del autor de la llamada                        |La persona que llama es propietaria y tiene derechos completos. <br /><br />El destinatario de la llamada (si está en el mismo inquilino) tiene acceso de solo lectura. Sin acceso compartido. <br /><br /> El destinatario de la llamada (si se trata de un inquilino diferente) no tiene acceso. La persona que llama debe compartirla con el destinatario.|
|llamada de 1:1 con partes internas             |Destinatario de la llamada                 |Cuenta de OneDrive para la empresa de la persona que llama                        |El destinatario de la llamada es propietario y tiene plenos derechos. <br /><br />La persona que llama (si está en el mismo inquilino tiene acceso de solo lectura. Sin acceso compartido. <br /><br />La persona que llama (si se trata de un inquilino diferente) no tiene acceso. La persona que llama debe compartirla con quien llama.|
|llamada de 1:1 con una llamada externa             |Autor de llamada                 |Cuenta de OneDrive para la empresa del autor de la llamada                        |La persona que llama es propietaria y tiene derechos completos.<br /> <br />El destinatario de la llamada no tiene acceso. La persona que llama debe compartirla con el destinatario.|
|llamada de 1:1 con una llamada externa             |Destinatario de la llamada                 |Cuenta de OneDrive para la empresa de la persona que llama                        |El destinatario de la llamada es propietario y tiene plenos derechos.<br /><br />La persona que llama no tiene acceso. La persona que llama debe compartirla con quien llama.|
|Llamada grupal                                 |Cualquier miembro de la llamada |Miembro que hizo clic en la cuenta de OneDrive para la empresa del registro  |El miembro que hizo clic en el registro tiene derechos completos. <br /><br /> Otros miembros del mismo inquilino tienen derechos de lectura. <br /><br /> Otros miembros de un inquilino diferente no tienen derechos.|
|Reunión programada/ad hoc                    |Organizador              |Cuenta de OneDrive para la empresa del organizador                     |El organizador tiene plenos derechos en la grabación. <br /><br /> Todos los demás miembros de la reunión tienen acceso de lectura.|
|Reunión programada/ad hoc                    |Otro miembro de la reunión   |Miembro que hizo clic en el registro                                  |El miembro que hizo clic en el registro tiene derechos plenos en la grabación. <br /><br />Organizer tiene derechos de edición y puede compartir.<br /><br /> El resto de miembros tienen acceso de lectura.|
|Reunión ad hoc o programada con usuarios externos|Organizador              |Cuenta de OneDrive para la empresa del organizador                     |El organizador tiene plenos derechos en la grabación.<br /> <br /> Todos los demás miembros de la reunión desde el mismo inquilino que el organizador tienen acceso de lectura. <br /><br /> Los demás miembros externos no tienen acceso y el organizador debe compartirlo.|
|Reunión ad hoc o programada con usuarios externos|Otro miembro de la reunión   |Miembro que hizo clic en el registro                                  |El miembro que hizo clic en el registro tiene derechos plenos en la grabación. Organizer tiene derechos de edición y puede compartir. <br /><br /> Todos los demás miembros de la reunión desde el mismo inquilino que el organizador tienen acceso de lectura. <br /><br />Los demás miembros externos no tienen acceso y el organizador debe compartirlo.|
|Reunión de canal                            |Miembro del canal         |Ubicación de SharePoint de los equipos de ese canal                   |El miembro que hizo clic en registro tiene derechos de edición en la grabación. <br /> <br />Los permisos de todos los demás miembros se basan en los permisos de SharePoint de canal.|

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

Los clientes que opten por esta versión preliminar no tendrán subtítulos disponibles en las grabaciones de reuniones de sus equipos que se migren a OneDrive para la empresa y SharePoint.Estamos trabajando para agregar títulos, comenzando con subtítulos en inglés, para hacer una reunión de las grabaciones en el cuarto trimestre de CY2020.

Los subtítulos cerrados estarán disponibles en las grabaciones de reuniones de Teams para los clientes que hayan optado por permitir transcripciones según se describe en las [grabaciones en la nube de Teams](cloud-recording.md) .

Los subtítulos ayudan a crear contenido inclusivo para los visores de todas las capacidades. Como propietario, puede ocultar los subtítulos, aunque la transcripción seguirá estando disponible en Teams, a menos que elimine los subtítulos de Teams. Ver [Cómo activar o desactivar las grabaciones de reuniones](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Los subtítulos se admiten para las grabaciones de reuniones de equipos por 60 días desde que se grabó la reunión.

Los subtítulos cerrados no son totalmente compatibles si el registro de reuniones de equipos se mueve o se copia desde su ubicación original en OneDrive para la empresa o SharePoint.

**¿Cómo se verá afectada mi cuota de almacenamiento?**

Los equipos que reunión graban archivos en OneDrive para la empresa y SharePoint se incluyen en su cuota para esos servicios. Consulte cuota de [SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) y [cuota de OneDrive para la empresa](https://docs.microsoft.com/onedrive/set-default-storage-space).

Obtendrá más almacenamiento con [OneDrive para la empresa](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) en comparación con la transmisión y más almacenamiento de fungible con SharePoint.

**¿Cómo puedo reproducir una grabación de reuniones de Teams?**

El vídeo se reproducirá en el reproductor de vídeo de OneDrive para la empresa o SharePoint según dónde se obtenga acceso al archivo.

**Si tiene previsto agregar a la transmisión, ¿los vídeos existentes se mantendrán como están y durante cuánto tiempo?**

La secuencia como plataforma no quedará obsoleta en un futuro próximo. Los vídeos que actualmente viven en la secuencia permanecerán allí hasta que empiece la migración. Después de la migración, esos vídeos también se migrarán a OneDrive para la empresa o SharePoint. Para obtener más información, consulta [aquí](https://docs.microsoft.com/stream/streamnew/classic-migration) .

**¿Cómo se aplica una etiqueta de retención?**

Vea [Cómo aplicar automáticamente una etiqueta de retención](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).

**¿Cómo puedo asignar directivas a mis usuarios en Microsoft Teams y qué directivas tienen prioridad?**

Consulte [¿qué directiva tiene prioridad?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence).

---
title: Usar OneDrive para la Empresa y SharePoint para grabaciones de reuniones
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo cambiar de Stream a OneDrive para la Empresa y al almacenamiento de grabaciones de reuniones de SharePoint en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3b7a3917f47bd07bd5d66ce5fdb524b91b0299e
ms.sourcegitcommit: d5732f043b7b5aa9b889aae185a7bc7e6ffad409
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49979757"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar OneDrive para la Empresa, SharePoint o Stream para grabaciones de reuniones

> [!Note]
> El cambio del uso de Microsoft Stream a OneDrive para la Empresa y Microsoft SharePoint para las grabaciones de reuniones será un enfoque por fases.

|<div style="width:290px">Fecha&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 de octubre de 2020 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Puede habilitar la directiva de reunión de Teams para que las grabaciones de reuniones se guarden en OneDrive para la Empresa y SharePoint en lugar de en Microsoft Stream (clásico).|
|Implementarse a partir del 7 de enero de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todas las nuevas grabaciones de reuniones de Teams se guardarán en OneDrive para la Empresa y SharePoint a menos que retrase este cambio modificando las directivas de reuniones de Teams de su organización y estableciendo explícitamente en **Stream.** No basta con ver los informes de directivas como Stream. Es necesario establecer explícitamente el valor de la directiva en **Stream.**|
|Implementarse a partir del 11 de enero de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC**<br> While GCC customers can opt out starting October 5, you're unable to opt in. Esta característica se llevará a cabo para todos los clientes de GCC a partir del 11 de enero de 2021, a menos que se haya dado de baja.<br>  <br>A partir del 11 de enero de 2021, todas las nuevas grabaciones de reuniones de Teams para clientes GCC se guardarán en OneDrive para la Empresa y SharePoint a menos que retrase este cambio modificando las directivas de reuniones de Teams de su organización y estableciendo explícitamente en **Stream.** <br><br>Si ha optado por no participar, pero está listo para activar esta característica, puede hacerlo configurando explícitamente la directiva de reunión de Teams en **OneDrive para la Empresa.** |
|Implementarse a partir del 1 de marzo de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clientes & GCC de Enterprise**<br>No se pueden guardar nuevas grabaciones de reuniones en **Microsoft Stream (clásico);** todos los clientes tendrán automáticamente las grabaciones de reuniones guardadas en OneDrive para la Empresa y SharePoint incluso si han cambiado sus directivas de reuniones de Teams a Stream.<br><br> Recomendamos que los clientes presenten esta característica antes de esta fecha para que puedan controlar los intervalos del lanzamiento. |
|Implementarse a partir del 7 de julio de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clientes del sector educativo**<br>No se pueden guardar nuevas grabaciones de reuniones en **Microsoft Stream (clásico);** todos los clientes tendrán automáticamente las grabaciones de reuniones guardadas en OneDrive para la Empresa y SharePoint incluso si han cambiado sus directivas de reuniones de Teams a Stream.<br><br> Recomendamos que los clientes presenten esta característica antes de esta fecha para que puedan controlar los intervalos del lanzamiento. Hemos actualizado esta programación para ofrecer a los clientes de educación la capacidad de completar semestres en curso. |

> [!Note]
> Recomendamos a los clientes empresariales y educativos que, para controlar mejor el cambio en su organización, opten siempre que se sienta cómodo con el cambio en lugar de esperar a que se haga.

Microsoft Teams tiene un nuevo método para guardar las grabaciones de reuniones. Como la primera fase de una transición de Microsoft Stream clásica a la nueva [Stream,](https://docs.microsoft.com/stream/streamnew/new-stream)este método almacena las grabaciones en Microsoft OneDrive para la Empresa y SharePoint en Microsoft 365 y ofrece muchas ventajas.

Entre las ventajas de usar OneDrive para la Empresa y SharePoint para almacenar grabaciones se incluyen:

- Directivas de retención para la grabación de reuniones de Teams (TMR) (etiquetas de autoredición S+C E5)
- Ventajas de OneDrive para la Empresa y gobierno de información de SharePoint
- Fácil establecer permisos y uso compartido
- Compartir grabaciones con invitados (usuarios externos) solo con uso compartido explícito
- Solicitar flujo de acceso
- Proporcionar vínculos compartidos de OneDrive para la Empresa y SharePoint
- Cuota aumentada
- Las grabaciones de reuniones están disponibles más rápido
- **Ir al soporte técnico local** de inquilinos
- Compatibilidad multigeográfica: las grabaciones se almacenan en una región específica de ese usuario
- Traer su propia clave (BYOK) soporte técnico
- Mejora de la calidad de la transcripción y la atribución del orador

Hay algunas limitaciones que debe tener en cuenta:

- Solo habrá subtítulos y transcripciones en inglés.
- No podrá buscar transcripciones ni su contenido.
- No podrá editar las transcripciones, pero podrá activar o desactivar los subtítulos.
- Puede controlar con quién comparte la grabación, pero no podrá impedir que los usuarios con acceso compartido descarguen la grabación.
- No recibirá un correo electrónico cuando la grabación termine de guardarse, pero la grabación aparecerá en el chat de la reunión cuando haya terminado. Esto ocurrirá mucho más rápido que en Stream anteriormente

Vea "Grabación de la reunión" para obtener más información.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurar la opción de grabación de la reunión para OneDrive para la Empresa y SharePoint

La opción de grabación de la reunión es una configuración en el nivel de directiva de Teams. En el ejemplo siguiente se muestra cómo establecer la directiva Global. Asegúrese de establecer la opción de grabación de la reunión para la directiva o directivas que asignó a los usuarios.

> [!Note]
> Los cambios en la directiva de reunión de Teams llevan un tiempo en propagarse. Vuelve a comprobarlo tras unas horas de configuración y, a continuación, vuelve a cerrar la sesión y a iniciarla.

1. Instale PowerShell de Skype Empresarial Online.
**Nota:** Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente. Si usa la versión pública más reciente de PowerShell de Teams, no es necesario instalar Skype Empresarial Online Connector. Consulte [Administrar Skype Empresarial Online con PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    a. Descargue [PowerShell de Skype Empresarial Online.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    b. Siga las indicaciones para instalarlo.

    c. Reinicia el equipo.

2. Iniciar PowerShell como administrador

3. Importe SkypeOnline Connector e inicie sesión como administrador de Teams.

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Use [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) para establecer una directiva de reunión de Teams para la transición del almacenamiento de Stream a OneDrive para la Empresa y SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Si algunos de los usuarios han asignado una directiva por organizador o por usuario, debe establecer esta configuración en esta directiva si desea que también almacenen las grabaciones de la reunión en OneDrive para la Empresa y SharePoint. Para obtener más información, vea [Administrar directivas de reuniones en Teams.](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Optar por no participar en OneDrive para la Empresa y SharePoint para seguir usando Stream

Incluso si una directiva dice que está establecida en **Stream,** es posible que no esté establecida. Normalmente, si la directiva no está establecida, la configuración predeterminada es **Stream.** Sin embargo, con este nuevo cambio, si quiere dejar de usar SharePoint o OneDrive para la Empresa, debe restablecer la directiva a **Stream** para asegurarse de que **Stream** sea la predeterminada.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Permisos o acceso basado en roles

> [!Note]
> Se recomienda que el destinatario sea un usuario con sesión iniciada al compartir las grabaciones de reuniones de Teams. Seleccione la **opción Personas de (su organización)** al compartir el archivo como se documenta en archivos o carpetas de [SharePoint.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) El uso compartido externo no está diseñado para la distribución de archivos grandes o un gran número de archivos. Para evitar situaciones de fraude y abuso, es posible que experimente problemas al compartir una gran cantidad de datos con usuarios externos.

|Tipo de reunión                               | ¿Quién hizo clic en Grabar?| ¿Dónde se incluye la grabación?                               |¿Quién tiene acceso? R/W, R o uso compartido                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Llamada 1:1 con partes internas             |Autor de llamada                 |Cuenta de OneDrive para la Empresa del autor de la llamada                        |El autor de la llamada es propietario y tiene todos los derechos. <br /><br />El destinatario de la llamada (si está en el mismo espacio empresarial) tiene acceso de solo lectura. Sin acceso para compartir. <br /><br /> El destinatario de la llamada (si se encuentra en otro espacio empresarial) no tiene acceso. El autor de la llamada debe compartirlo con el destinatario de la llamada.|
|Llamada 1:1 con partes internas             |Destinatario de la llamada                 |Cuenta del destinatario de la llamada OneDrive para la Empresa                        |El destinatario de la llamada es el propietario y tiene todos los derechos. <br /><br />Autor de la llamada (si está en el mismo espacio empresarial tiene acceso de solo lectura. Sin acceso para compartir. <br /><br />El autor de la llamada (si se encuentra en otro espacio empresarial) no tiene acceso. El destinatario de la llamada debe compartirlo con el autor de la llamada.|
|Llamada 1:1 con una llamada externa             |Autor de llamada                 |Cuenta de OneDrive para la Empresa del autor de la llamada                        |El autor de la llamada es propietario y tiene todos los derechos.<br /> <br />El destinatario de la llamada no tiene acceso. El autor de la llamada debe compartirlo con el destinatario de la llamada.|
|Llamada 1:1 con una llamada externa             |Destinatario de la llamada                 |Cuenta del destinatario de la llamada OneDrive para la Empresa                        |El destinatario de la llamada es el propietario y tiene todos los derechos.<br /><br />El autor de la llamada no tiene acceso. El destinatario de la llamada debe compartirlo con el autor de la llamada.|
|Llamada grupal                                 |Cualquier miembro de la llamada |Miembro que hizo clic en la cuenta de OneDrive para la Empresa de Record  |El miembro que hizo clic en Registro tiene derechos completos. <br /><br /> Otros miembros del mismo espacio empresarial tienen derechos de lectura. <br /><br /> Otros miembros de diferentes inquilinos no tienen derechos sobre él.|
|Adoc/Reunión programada                    |Organizador              |Cuenta de OneDrive para la Empresa del organizador                     |El organizador tiene todos los derechos sobre la grabación. <br /><br /> El resto de los miembros de la reunión tienen acceso de lectura.|
|Adoc/Reunión programada                    |Otro miembro de la reunión   |Miembro que hizo clic en Grabar                                  |El miembro que hizo clic en Grabar tiene todos los derechos sobre la grabación. <br /><br />El organizador tiene derechos de edición y puede compartirlos.<br /><br /> El resto de los miembros tienen acceso de lectura.|
|Adoc/Reunión programada con usuarios externos|Organizador              |Cuenta de OneDrive para la Empresa del organizador                     |El organizador tiene todos los derechos sobre la grabación.<br /> <br /> El resto de los miembros de la reunión del mismo espacio empresarial que el organizador tienen acceso de lectura. <br /><br /> El resto de los miembros externos no tienen acceso y el Organizador debe compartirlo con ellos.|
|Adoc/Reunión programada con usuarios externos|Otro miembro de la reunión   |Miembro que hizo clic en Grabar                                  |El miembro que hizo clic en Grabar tiene todos los derechos sobre la grabación. El organizador tiene derechos de edición y puede compartirlos. <br /><br /> El resto de los miembros de la reunión del mismo espacio empresarial que el organizador tienen acceso de lectura. <br /><br />El resto de los miembros externos no tienen acceso y el Organizador debe compartirlo con ellos.|
|Reunión del canal                            |Miembro del canal         |Ubicación de SharePoint de Teams para ese canal                   |El miembro que hizo clic en Grabar tiene derechos de edición para la grabación. <br /> <br />Los permisos de todos los demás miembros se basan en los permisos de SharePoint del canal.|

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Dónde se almacenará la grabación de la reunión?**

- Para reuniones que no son de canal,  la grabación se almacena en una carpeta denominada Grabaciones que está en el nivel superior de OneDrive para la Empresa que pertenece a la persona que inició la grabación de la reunión. Ejemplo:

  <i>OneDrive para la Empresa del grabador</i> / **Grabaciones**

- Para las reuniones de canal, la grabación se almacena en la biblioteca de documentación del sitio de Teams en una carpeta denominada **Grabaciones.** Ejemplo:

  <i>Nombre de los equipos: nombre del canal</i> / **Documentos** / **Grabaciones**

**Cuando los archivos de Stream (como las grabaciones) se almacenan en SharePoint o OneDrive, ¿cómo se decide dónde van? ¿El administrador puede cambiar a dónde va?**

De forma predeterminada, todos los archivos de grabación irán a la cuenta de OneDrive del usuario que seleccionó **Grabar.** Para las reuniones del canal, la grabación siempre irá al sitio de SharePoint del canal. El administrador no puede cambiar el lugar donde se almacena la grabación.

**¿Cómo controlo las grabaciones de antiguos empleados?**

Puesto que los vídeos son iguales que cualquier otro archivo en OneDrive para la Empresa y SharePoint, la administración de la propiedad y la retención después de que un empleado abandone seguirá el proceso normal de OneDrive para la Empresa y [SharePoint.]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**¿Quién tiene los permisos para ver la grabación de la reunión?**

- En las reuniones que no son de canal, todos los invitados a las reuniones, excepto los usuarios externos, recibirán automáticamente un vínculo compartido personalmente. Los usuarios externos deben agregarse explícitamente a la lista compartida por el organizador de la reunión o por la persona que inició la grabación de la reunión.

- Para las reuniones de canal, los permisos se heredan de la lista de propietarios y miembros del canal.

**¿Cómo puedo administrar las transcripciones?**

Los clientes que opten por esta versión preliminar no tendrán subtítulos disponibles en sus grabaciones de reuniones de Teams que se migran a OneDrive para la Empresa y SharePoint.Estamos trabajando para agregar subtítulos, comenzando por subtítulos en inglés, a las grabaciones de reuniones en Q4 CY2020.

Los subtítulos estarán disponibles en las grabaciones de reuniones de Teams para los clientes que se han decidido por permitir las transcripciones como se describe en las grabaciones en la [nube de Teams.](cloud-recording.md)

Los títulos ayudan a crear contenido inclusivo para los visores de todas las capacidades. Como propietario, puede ocultar los subtítulos, aunque la transcripción seguirá estando disponible en Teams a menos que elimine los subtítulos de Teams. Vea [cómo activar o desactivar las grabaciones de reuniones.](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Los subtítulos son compatibles con las grabaciones de reuniones de Teams durante 60 días desde el momento en que se graba la reunión.

Los subtítulos no son totalmente compatibles si la grabación de reuniones de Teams se mueve o se copia desde su ubicación original en OneDrive para la Empresa o SharePoint.

**¿Cómo se verá afectada mi cuota de almacenamiento?**

Los archivos de las reuniones de Teams se graban en directo en OneDrive para la Empresa y SharePoint y se incluyen en su cuota para esos servicios. Vea [cuota de SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) y [cuota de OneDrive para la Empresa.](https://docs.microsoft.com/onedrive/set-default-storage-space)

Obtiene más almacenamiento con [OneDrive para la Empresa en](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) comparación con Stream y un almacenamiento más retorcida con SharePoint.

**¿Cómo puedo reproducir la grabación de una reunión de Teams?**

El vídeo se reproducirá en el reproductor de vídeo de OneDrive para la Empresa o SharePoint en función del lugar en el que acceda al archivo.

**Si planea no agregar a Stream, ¿los vídeos existentes permanecerán tal y como están y durante cuánto tiempo?**

La transmisión en secuencias como plataforma no estará en desuso en un futuro próximo. Los vídeos que actualmente se encuentran en Stream permanecerán allí hasta que se inicie la migración. Tras la migración, estos vídeos también se migrarán a OneDrive para la Empresa o SharePoint. Compruebe [la migración clásica de Stream](https://docs.microsoft.com/stream/streamnew/classic-migration) para obtener más información.

**¿Cómo puedo aplicar una etiqueta de retención?**

Vea [Cómo aplicar automáticamente una etiqueta de retención.](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**¿Cómo puedo asignar directivas a mis usuarios en Microsoft Teams y qué directivas tendrán prioridad?**

Vea [¿Qué directiva tiene prioridad?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence).

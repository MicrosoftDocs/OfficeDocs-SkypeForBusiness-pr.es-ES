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
description: Obtenga información sobre cómo cambiar de Stream a OneDrive para la Empresa y almacenamiento de grabación de reuniones de SharePoint en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d18f6b5ef5b4668324a68b4456cd3ad5aa4b7364
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50507983"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar OneDrive para la Empresa y SharePoint o Stream para grabaciones de reuniones

> [!Note]
> El cambio de usar Microsoft Stream a OneDrive para la Empresa y Microsoft SharePoint para grabaciones de reuniones será un enfoque por fases.

|<div style="width:290px">Fecha&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 de octubre de 2020<br> <br>*(Completado)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Habilitar la directiva de reunión de Teams para que las grabaciones de reuniones se guarden en OneDrive para la Empresa y SharePoint en lugar de Microsoft Stream (clásico)|
|Se está implementando a partir del 7 de enero de 2021<br> <br>*(Completado)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todas las nuevas grabaciones de reunión de Teams se guardarán en OneDrive para la Empresa y SharePoint a menos que retrase este cambio modificando las directivas de reunión de Teams de su organización y estableciendo explícitamente en **Stream**. Ver los informes de directivas como Stream no es suficiente. Debe establecer explícitamente el valor de directiva en **Stream**.|
|Puesta en marcha a partir del 11 de enero de 2021<br> <br>*(Completado)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC**<br> Aunque los clientes de GCC pueden optar por no participar a partir del 5 de octubre, no puede participar. Esta característica se llevará a cabo para todos los clientes de GCC a partir del 11 de enero de 2021, a menos que haya optado por no participar.<br>  <br>A partir del 11 de enero de 2021, todas las nuevas grabaciones de reunión de Teams para clientes de GCC se guardarán en OneDrive para la Empresa y SharePoint a menos que retrase este cambio modificando las directivas de reunión de Teams de su organización y estableciendo explícitamente en **Stream.** <br><br>Si ha optado por no participar, pero está listo para activar esta característica, puede hacerlo estableciendo su directiva de reunión de Teams explícitamente en **OneDrive para la Empresa.** |
|A partir del 1 de marzo de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC-High y DoD**<br> Los clientes ahora pueden habilitar las grabaciones de reuniones en la nube en Microsoft Teams por primera vez. Estas grabaciones se almacenarán y reproducirán en OneDrive y SharePoint de forma predeterminada. |
|Implementación incremental a partir del 7 de julio de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos los clientes (Empresa, Educación y GCC)**<br>No se pueden guardar nuevas grabaciones de reunión en **Microsoft Stream (clásico);** todos los clientes guardarán automáticamente las grabaciones de reuniones en OneDrive para la Empresa y SharePoint, incluso si han cambiado sus directivas de reunión de Teams a Stream.<br><br> Se recomienda a los clientes que arrojen esta característica antes de esta fecha para que puedan controlar los intervalos de la versión. |

> [!Note]
> Le recomendamos a los clientes empresariales y educativos que, para controlar mejor el cambio en su organización, opten siempre que se sientan cómodos con el cambio en lugar de esperar a que se haga.

Microsoft Teams tiene un nuevo método para guardar grabaciones de reuniones. Como primera fase de una transición de Microsoft Stream clásica a la nueva [Stream,](https://docs.microsoft.com/stream/streamnew/new-stream)este método almacena grabaciones en Microsoft OneDrive para la Empresa y SharePoint en Microsoft 365 y ofrece muchas ventajas.

Las ventajas de usar OneDrive para la Empresa y SharePoint para almacenar grabaciones incluyen:

- Directivas de retención para la grabación de reuniones de Teams (TMR) (etiquetas de autoretención S+C E5)
- Beneficiarse del gobierno de información de OneDrive para la Empresa y SharePoint
- Fácil de establecer permisos y uso compartido
- Compartir grabaciones con invitados (usuarios externos) solo con uso compartido explícito
- Solicitar flujo de acceso
- Proporcionar vínculos compartidos de OneDrive para la Empresa y SharePoint
- Las grabaciones de reuniones están disponibles más rápido
- **Go local** tenant support
- Compatibilidad multigeográfica: las grabaciones se almacenan en una región específica de ese usuario
- Traer su propia clave (BYOK) soporte técnico

Hay algunas limitaciones que debe tener en cuenta:

- Habrá subtítulos solo en inglés y podrás activar o desactivar los subtítulos.
- Inicialmente no *podrá* ver, editar y buscar una transcripción completa (sin embargo, estamos trabajando en agregar esta funcionalidad próximamente).
- No podrá editar las transcripciones, pero podrá activar o desactivar los subtítulos.
- Puede controlar con quién comparte la grabación, pero no podrá bloquear que las personas con acceso compartido descarguen la grabación.
- No recibirá un correo electrónico cuando la grabación termine de guardarse, pero la grabación aparecerá en el chat de la reunión una vez que haya terminado. Esto ocurrirá mucho más rápido que en Stream anteriormente

Vea "Grabación de reuniones" para obtener más información.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurar la opción de grabación de reuniones para OneDrive para la Empresa y SharePoint

La opción de grabación de reuniones es una configuración en el nivel de directiva de Teams. En el ejemplo siguiente se muestra cómo establecer la directiva global. Asegúrese de establecer la opción de grabación de la reunión para la directiva o directivas que ha asignado a los usuarios.

> [!Note]
> Los cambios en la directiva de reunión de Teams pueden tardar un tiempo en propagarse. Vuelva a comprobarlo después de unas horas de configurarlo y, a continuación, cerrar la sesión e iniciar sesión de nuevo.

1. Instale Skype Empresarial Online PowerShell.

   > [!NOTE]
   > Skype Empresarial Online Connector forma parte actualmente del último módulo de PowerShell de Teams. Si usa la última versión pública de PowerShell de Teams, no es necesario instalar Skype Empresarial Online Connector. Vea [Administrar Skype Empresarial Online con PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    1. Descargar [PowerShell de Skype Empresarial Online.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    1. Siga las indicaciones para instalarlo.

    1. Reinicie el equipo.

2. Inicie PowerShell como administrador.

3. Importe SkypeOnline Connector e inicie sesión como administrador de Teams.

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Use [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) para establecer una directiva de reunión de Teams para que pase del almacenamiento de la transmisión a OneDrive para la Empresa y SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Si algunos usuarios han asignado una directiva por organizador o por usuario, debe establecer esta configuración en esta directiva si quiere que también almacenen las grabaciones de la reunión en OneDrive para la Empresa y SharePoint. Para obtener más información, vea [Administrar directivas de reunión en Teams.](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Optar por no participar en OneDrive para la Empresa y SharePoint para seguir usando Stream

Incluso si una directiva dice que está establecida en **Stream,** es posible que no esté establecida. Normalmente, si la directiva no está establecida, la configuración predeterminada es **Stream**. Sin embargo, con este nuevo cambio, si desea no usar SharePoint o OneDrive para  la Empresa, debe restablecer la directiva a Stream para asegurarse de que **Stream** es el valor predeterminado.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Permisos o acceso basado en roles

> [!Note]
> Se recomienda que el destinatario sea un usuario que haya iniciado sesión al compartir grabaciones de reuniones de Teams. Seleccione la **opción Contactos en (su organización)** al compartir el archivo como se documenta en archivos o carpetas de [Share SharePoint.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) El uso compartido externo no está diseñado para la distribución de archivos grandes o un gran número de archivos. Para evitar situaciones de fraude y abuso, es posible que experimente problemas al compartir una gran cantidad de datos con usuarios externos.

|Tipo de reunión                               | ¿Quién hizo clic en Grabar?| ¿Dónde se realiza la grabación?                               |¿Quién tiene acceso? R/W, R o uso compartido                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Llamada 1:1 con partes internas             |Autor de llamada                 |Cuenta de OneDrive para la Empresa del autor de la llamada                        |El autor de la llamada es propietario y tiene todos los derechos. <br /><br />Callee (si está en el mismo espacio empresarial) tiene acceso de solo lectura. No hay acceso compartido. <br /><br /> Callee (si está en un espacio empresarial diferente) no tiene acceso. El autor de la llamada debe compartirlo con el Destinatario.|
|Llamada 1:1 con partes internas             |Destinatario de la llamada                 |Cuenta de OneDrive para la Empresa de Callee                        |Callee es el propietario y tiene todos los derechos. <br /><br />Autor de la llamada (si en el mismo espacio empresarial tiene acceso de solo lectura). No hay acceso compartido. <br /><br />La persona que llama (si está en un espacio empresarial diferente) no tiene acceso. Callee debe compartirlo con el autor de la llamada.|
|Llamada 1:1 con una llamada externa             |Autor de llamada                 |Cuenta de OneDrive para la Empresa del autor de la llamada                        |El autor de la llamada es propietario y tiene todos los derechos.<br /> <br />Callee no tiene acceso. El autor de la llamada debe compartirlo con el Destinatario.|
|Llamada 1:1 con una llamada externa             |Destinatario de la llamada                 |Cuenta de OneDrive para la Empresa de Callee                        |Callee es el propietario y tiene todos los derechos.<br /><br />La persona que llama no tiene acceso. Callee debe compartirlo con el autor de la llamada.|
|Llamada grupal                                 |Cualquier miembro de la llamada |Miembro del grupo que hizo clic en la cuenta de OneDrive para la Empresa de Record  |El miembro que hizo clic en Grabar tiene todos los derechos. <br /><br /> Otros fr del mismo inquilino tienen derechos de lectura. <br /><br /> Otros miembros del grupo de inquilinos diferentes no tienen derechos sobre él.|
|Adhoc/Reunión programada                    |Organizador              |Cuenta de OneDrive para la Empresa del organizador                     |El organizador tiene todos los derechos sobre la grabación. <br /><br /> Todos los demás miembros de la reunión tienen acceso de lectura.|
|Adhoc/Reunión programada                    |Otro miembro de la reunión   |Miembro de la reunión que hizo clic en Grabar                                  |El miembro que hizo clic en Grabar tiene todos los derechos sobre la grabación. <br /><br />El organizador tiene derechos de edición y puede compartirlos.<br /><br /> Todos los demás miembros de la reunión tienen acceso de lectura.|
|Adhoc/Reunión programada con usuarios externos|Organizador              |Cuenta de OneDrive para la Empresa del organizador                     |El organizador tiene todos los derechos sobre la grabación.<br /> <br /> Todos los demás miembros de la reunión del mismo inquilino que el organizador tienen acceso de lectura. <br /><br /> Todos los demás miembros externos no tienen acceso y el Organizador debe compartirlo con ellos.|
|Adhoc/Reunión programada con usuarios externos|Otro miembro de la reunión   |Miembro que hizo clic en Grabar                                  |El miembro que hizo clic en Grabar tiene todos los derechos sobre la grabación. El organizador tiene derechos de edición y puede compartirlos. <br /><br /> Todos los demás miembros de la reunión del mismo inquilino que el organizador tienen acceso de lectura. <br /><br />Todos los demás miembros externos no tienen acceso y el Organizador debe compartirlo con ellos.|
|Reunión del canal                            |Miembro del canal         |Ubicación de SharePoint de Teams para ese canal                   |El miembro que hizo clic en Grabar tiene derechos de edición para la grabación. <br /> <br />Los permisos de todos los demás miembros se basan en los permisos de SharePoint del canal.|

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Dónde se almacenará la grabación de la reunión?**

- Para reuniones que no son de canal,  la grabación se almacena en una carpeta denominada Grabaciones que se encuentra en el nivel superior de OneDrive para la Empresa que pertenece a la persona que inició la grabación de la reunión. Ejemplo:

  <i>OneDrive para la Empresa de la grabadora</i> / **Grabaciones**

- Para las reuniones del canal, la grabación se almacena en la biblioteca de documentación del sitio de Teams en una carpeta denominada **Grabaciones.** Ejemplo:

  <i>Nombre de los equipos: nombre del canal</i> / **Documentos** / **Grabaciones**

**Cuando los archivos stream (como las grabaciones) se almacenan en SharePoint/OneDrive, ¿cómo se decide dónde van? ¿El administrador tiene la capacidad de cambiar a dónde va?**

De forma predeterminada, todos los archivos de grabación irán a la cuenta de OneDrive del usuario que seleccionó **Grabar.** Para las reuniones de canal, la grabación siempre irá al sitio de SharePoint del canal. El administrador no puede cambiar dónde se almacena la grabación.

**¿Cómo puedo controlar las grabaciones de antiguos empleados?**

Puesto que los vídeos son como cualquier otro archivo en OneDrive para la Empresa y SharePoint, la administración de la propiedad y la retención después de que un empleado se vaya seguirá el proceso normal de OneDrive para la Empresa y [SharePoint.]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**¿Quién tiene los permisos para ver la grabación de la reunión?**

- En las reuniones que no son del canal, todos los invitados a la reunión, excepto los usuarios externos, recibirán automáticamente un vínculo compartido personalmente. Los usuarios externos tendrán que agregarse explícitamente a la lista compartida por el organizador de la reunión o la persona que inició la grabación de la reunión.

- Para las reuniones del Canal, los permisos se heredan de la lista de propietarios y miembros del canal.

**¿Cómo puedo administrar transcripciones?**

Los clientes que opten por esta versión preliminar no tendrán subtítulos disponibles en sus grabaciones de reunión de Teams que se migran a OneDrive para la Empresa y SharePoint.Estamos trabajando para agregar subtítulos, empezando por subtítulos en inglés, a las grabaciones de reuniones en Q4 CY2020.

Los subtítulos estarán disponibles en Grabaciones de reunión de Teams para los clientes que han optado por permitir transcripciones como se describe en Grabaciones en la [nube de Teams.](cloud-recording.md)

Los subtítulos ayudan a crear contenido inclusivo para los visores de todas las capacidades. Como propietario, puede ocultar subtítulos, aunque la transcripción seguirá estando disponible en Teams a menos que elimine los subtítulos de Teams. Vea cómo activar o desactivar [las grabaciones de reuniones.](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Los subtítulos son compatibles con las grabaciones de reuniones de Teams durante 60 días desde que se graba la reunión.

Los subtítulos no son totalmente compatibles si la grabación de reunión de Teams se mueve o copia desde su ubicación original en OneDrive para la Empresa o SharePoint.

**¿Cómo se verá afectada mi cuota de almacenamiento?**

Los archivos de grabación de reuniones de Teams están en directo en OneDrive para la Empresa y SharePoint y se incluyen en la cuota de esos servicios. Vea [Cuota de SharePoint y](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) Cuota de [OneDrive para la Empresa.](https://docs.microsoft.com/onedrive/set-default-storage-space)

Obtiene más almacenamiento con [OneDrive para la Empresa](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) en comparación con Stream y más almacenamiento fungible con SharePoint.

**¿Cómo puedo reproducir una grabación de reunión de Teams?**

El vídeo se reproducirá en el reproductor de vídeo de OneDrive para la Empresa o SharePoint dependiendo de dónde acceda al archivo.

**Si planeas no agregar a Stream, ¿los vídeos existentes permanecerán tal y como están y durante cuánto tiempo?**

Stream as a platform won't be deprecated in the near future. Los vídeos que actualmente viven en Stream permanecerán allí hasta que empiecemos a migrar. Tras la migración, esos vídeos también se migrarán a OneDrive para la Empresa o SharePoint. Compruebe [La migración clásica de Stream](https://docs.microsoft.com/stream/streamnew/classic-migration) para obtener más información.

**¿Cómo puedo aplicar una etiqueta de retención?**

Vea [Cómo aplicar automáticamente una etiqueta de retención.](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**¿Cómo puedo asignar directivas a mis usuarios en Microsoft Teams y qué directivas tienen prioridad?**

Vea [¿Qué directiva tiene prioridad?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence).

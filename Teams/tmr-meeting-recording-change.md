---
title: Usar OneDrive para la Empresa y SharePoint para grabar las reuniones
author: CarolynRowe
ms.author: crowe
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo cambiar de Stream a OneDrive para la Empresa y el almacenamiento de grabaciones de reuniones de SharePoint en Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e78cbb4740b5839af7c6c2d09450220a080d036f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466119"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar OneDrive para la Empresa y SharePoint o Stream para grabar las reuniones

> [!NOTE]
> El cambio de almacenamiento de las grabaciones de reuniones de Teams de Classic Stream a OneDrive y SharePoint (ODSP) se ha completado el 30 de agosto de 2021. Todas las grabaciones se almacenan ahora en ODSP. Este cambio reemplaza la directiva RecordingStorageMode y la modificación de la configuración en PowerShell ya no tiene ningún impacto.

|Fecha&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 de octubre de 2020<br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Habilite la directiva de reuniones de Teams para que las grabaciones de reuniones se guarden en OneDrive para la Empresa y SharePoint en lugar de Microsoft Stream (clásico)|
|Implementación a partir del 7 de enero de 2021<br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todas las grabaciones de reuniones nuevas de Teams se guardarán en OneDrive para la Empresa y SharePoint, a menos que retrase este cambio modificando las directivas de reuniones de Teams de su organización y estableciéndolas explícitamente en **Stream**. Ver los informes de directivas como Stream no es suficiente. Debe establecer explícitamente el valor de la directiva en **Stream**.|
|Implementación a partir del 11 de enero de 2021<br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC**<br> Aunque los clientes de GCC pueden dejar de participar a partir del 5 de octubre, no puede optar por participar. Esta característica se implementará para todos los clientes de GCC a partir del 11 de enero de 2021, a menos que haya optado por no participar.<br>  <br>A partir del 11 de enero de 2021, todas las grabaciones de reuniones nuevas de Teams para clientes de GCC se guardarán en OneDrive para la Empresa y SharePoint, a menos que retrase este cambio modificando las directivas de reuniones de Teams de su organización y estableciéndolas explícitamente en **Stream**. <br><br>Si ha optado por no participar, pero está listo para activar esta característica, puede hacerlo configurando explícitamente la directiva de reunión de Teams en **OneDrive para la Empresa**. |
|Implementación a partir del 1 de marzo de 2021 <br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC High y DoD**<br> Los clientes ahora pueden habilitar las grabaciones de reuniones en la nube en Microsoft Teams por primera vez. Estas grabaciones se almacenarán y reproducirán en OneDrive y SharePoint de forma predeterminada. |
|Implementación incremental a partir del 16 de agosto de 2021 <br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos los clientes (Enterprise, Educación y GCC)**<br>No se pueden guardar nuevas grabaciones de reuniones en Microsoft Stream (clásico); todos los clientes guardarán automáticamente las grabaciones de las reuniones en OneDrive para la Empresa y SharePoint incluso si han cambiado sus directivas de reuniones de Teams a Stream.<br><br> Recomendamos a los clientes que, para controlar mejor el cambio de la organización, opten por participar cuando se sientan cómodos con el cambio, en lugar de esperar a que se realice. |

Microsoft Teams tiene un nuevo método para guardar las grabaciones de reuniones. Como primera fase de una transición del Microsoft Stream clásico al [ nuevo Stream](/stream/streamnew/new-stream), este método almacena grabaciones en Microsoft OneDrive para la Empresa y SharePoint en Microsoft 365 y ofrece muchas ventajas.

> [!NOTE]
> Si una grabación de una reunión de Teams no se puede cargar correctamente en OneDrive/SharePoint, aparecerá el mensaje de error "La grabación finalizó inesperadamente" y la grabación se guardará temporalmente en Azure Media Services (AMS). Una vez almacenada en AMS, no se realizan intentos de reintento para cargar automáticamente la grabación en OneDrive/SharePoint o Stream.

Las grabaciones de reuniones almacenadas en AMS estarán disponibles durante 21 días antes de eliminarse automáticamente. Los usuarios pueden descargar el vídeo de AMS si necesitan guardar una copia.

Las ventajas de usar OneDrive para la Empresa y SharePoint para almacenar grabaciones son:

- Directivas de retención para la grabación de reuniones de Teams (TMR) (etiquetas de autoretención S+C E5)
- Ventaja de OneDrive para la Empresa y gobierno de información de SharePoint
- Fácil de establecer permisos y uso compartido
- Compartir grabaciones con invitados solo con uso compartido explícito
- Solicitar flujo de acceso
- Proporcionar OneDrive para la Empresa y vínculos compartidos de SharePoint
- Las grabaciones de las reuniones están disponibles más rápido
- **Ir a local** soporte para espacio empresarial
- Soporte para Multi-Geo: las grabaciones se almacenan en una región específica de ese usuario
- Soporte para Bring your own key (BYOK)

Vea la lista completa de las [características disponibles actualmente y las perspectivas para el futuro](/stream/streamnew/features-new-version-stream).

Vea "Novedades de las grabaciones de reuniones de Microsoft Teams" para obtener más información.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurar la opción de grabación de la reunión en OneDrive para la Empresa y SharePoint

La opción de grabación de la reunión es una configuración en el nivel de directiva de Teams. En el ejemplo siguiente se muestra cómo establecer la directiva global. Asegúrese de establecer la opción de grabación de la reunión para la directiva o las directivas que haya asignado a los usuarios.

> [!NOTE]
> Los cambios en la directiva de reunión de Teams tardan un tiempo en propagarse. Vuelva a comprobarlo después de unas horas de configuración, cierre la sesión y vuelva a iniciar sesión en la aplicación de escritorio de Teams o simplemente reinicie el equipo.

1. Instale Teams PowerShell.

   > [!NOTE]
   > El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial. Consulte [Administrar Skype Empresarial Online con PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Inicie PowerShell como administrador.

3. Instale el [módulo de PowerShell para Teams](./teams-powershell-install.md).

4. Importe el módulo MicrosoftTeams e inicie sesión como administrador de Teams.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

5. Use [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para establecer una directiva de reunión de Teams para realizar la transición del almacenamiento de Stream a OneDrive para la Empresa y SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!NOTE]
> Si algunos de los usuarios han asignado una directiva por organizador o por usuario, debe establecer esta configuración en esta directiva si quiere que también almacenen las grabaciones de reuniones en OneDrive para la Empresa y SharePoint. Para más información, consulte [Administrar directivas de reunión en Teams](meeting-policies-overview.md).

## <a name="permissions-or-role-based-access"></a>Permisos y acceso basado en roles

> [!NOTE]
> Se recomienda que el destinatario sea un usuario con sesión iniciada al compartir grabaciones de reuniones de Teams. Seleccione la opción **Contactos en (su organización)** cuando comparta el archivo como se documentó en [los archivos o las carpetas de SharePoint](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c). El uso compartido externo no está diseñado para la distribución de archivos de gran tamaño o para un gran número de archivos.

|Tipo de reunión                               | ¿Quién ha hecho clic en Grabar?| ¿Dónde está la grabación?                               |¿Quién tiene acceso? R/W, R o uso compartido                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Llamada uno a uno con partes internas             |Autor de la llamada                 |Cuenta de OneDrive para la Empresa del autor de la llamada                        |El autor de la llamada es propietario y tiene todos los derechos. <br /><br />El destinatario (si está en el mismo espacio empresarial) tiene acceso de solo lectura. Sin acceso de uso compartido. <br /><br /> El destinatario (si está en otro espacio empresarial) no tiene acceso. El autor de la llamada debe compartirlo con el destinatario.|
|Llamada uno a uno con partes internas             |Destinatario                 |Cuenta de OneDrive para la Empresa del destinatario                        |El destinatario es propietario y tiene todos los derechos. <br /><br />El autor de la llamada (si está en el mismo espacio empresarial) tiene acceso de solo lectura. Sin acceso de uso compartido. <br /><br />El autor de la llamada (si está en otro espacio empresarial) no tiene acceso. El destinatario debe compartirlo con el autor de la llamada.|
|Llamada uno a uno con llamada externa             |Autor de la llamada                 |Cuenta de OneDrive para la Empresa del autor de la llamada                        |El autor de la llamada es propietario y tiene todos los derechos.<br /> <br />El destinatario no tiene acceso. El autor de la llamada debe compartirlo con el destinatario.|
|Llamada uno a uno con llamada externa             |Destinatario                 |Cuenta de OneDrive para la Empresa del destinatario                        |El destinatario es propietario y tiene todos los derechos.<br /><br />El autor de la llamada no tiene acceso. El destinatario debe compartirlo con el autor de la llamada.|
|Llamada grupal                                 |Cualquier miembro de la llamada |El miembro del grupo que hizo clic en la cuenta de OneDrive para la Empresa de la grabación  |El miembro que hizo clic en la grabación tiene todos los derechos. <br /><br /> Otros miembros del grupo del mismo inquilino tienen derechos de lectura. <br /><br /> Otros miembros del grupo de otro espacio empresarial no tienen derechos sobre él.|
|Reunión programada/adhoc                    |Organizador              |Cuenta de OneDrive para la Empresa del organizador                     |El organizador tiene todos los derechos de la grabación. <br /><br /> El resto de los miembros de la reunión tienen acceso de lectura.|
|Reunión programada/adhoc                    |Otro miembro de la reunión   |El miembro de la reunión que hizo clic en la grabación                                  |El miembro que hizo clic en la grabación tiene todos los derechos de la grabación. <br /><br />El organizador tiene derechos de edición y puede compartir.<br /><br /> El resto de los miembros de la reunión tienen acceso de lectura.|
|Reunión programada/addhoc con participantes externos|Organizador              |Cuenta de OneDrive para la Empresa del organizador                     |El organizador tiene todos los derechos de la grabación.<br /> <br /> Todos los demás miembros de la reunión del mismo espacio empresarial que el organizador tienen acceso de lectura. <br /><br /> El resto de participantes externos no tienen acceso y el organizador debe compartirlo con ellos.|
|Reunión programada/addhoc con participantes externos|Otro miembro de la reunión   |El miembro que hizo clic en la grabación                                  |El miembro que hizo clic en la grabación tiene todos los derechos de la grabación. El organizador tiene derechos de edición y puede compartir. <br /><br /> Todos los demás miembros de la reunión del mismo espacio empresarial que el organizador tienen acceso de lectura. <br /><br />El resto de participantes externos no tienen acceso y el organizador debe compartirlo con ellos.|
|Reunión de canal                            |Miembro de canal         |Ubicación de SharePoint de Teams para ese canal. **Nota**: La carga de la grabación de reuniones de canal en SharePoint no es compatible con las restricciones basadas en IP. Se recomienda usar el [acceso condicional de Azure](/azure/active-directory/conditional-access/overview). |El miembro que hizo clic en la grabación tiene derechos de edición de la grabación. <br /> <br />Los permisos de todos los demás miembros se basan en los permisos de SharePoint del canal.|

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Dónde se almacenará la grabación de la reunión?**

- Para reuniones que no son de canal, la grabación se almacena en una carpeta denominada **Grabaciones** que se encuentra en el nivel superior de OneDrive para la Empresa y que pertenece a la persona que inició la grabación de la reunión. Ejemplo:

  *OneDrive para la Empresa de la persona que inició la grabación*/**Grabaciones**

- Para las reuniones de canal, la grabación se almacena en la biblioteca de documentación del sitio de Teams, en una carpeta denominada **Grabaciones**. Ejemplo:

  *Nombre de Teams: nombre del canal*/**Documentos**/**Grabaciones**

**Cuando los archivos de Stream (por ejemplo, las grabaciones) se almacenan en SharePoint o OneDrive, ¿cómo se decide a dónde van? ¿Puede el administrador cambiar el lugar donde se guardan?**

De forma predeterminada, todos los archivos de grabación se guardan en la cuenta de OneDrive del usuario que seleccionó **Grabar**. Para las reuniones de canal, la grabación siempre se guardará en el sitio de SharePoint del canal. El administrador no puede cambiar el lugar donde se almacena la grabación.

**¿Cómo administro las grabaciones de antiguos empleados?**

Dado que los vídeos son iguales que cualquier otro archivo de OneDrive para la Empresa y SharePoint, el control de la propiedad y la retención después de que un empleado se va seguirá el proceso normal de [OneDrive para la Empresa y SharePoint](/onedrive/retention-and-deletion).

**¿Quién tiene los permisos para ver la grabación de la reunión?**

- Para las reuniones que no sean del Canal, todos los invitados a la reunión, excepto los participantes externos, recibirán automáticamente un vínculo compartido personalmente. El organizador de la reunión o la persona que inició la grabación de la reunión deberá agregar explícitamente a la lista compartida a los participantes externos.

- Para las reuniones de canal, los permisos se heredan de los propietarios y miembros de la lista de miembros en el canal.

> [!NOTE]
> No recibirá un correo electrónico cuando la grabación termine de guardarse, pero la grabación aparecerá en el chat de la reunión una vez finalizada. Esto ocurrirá mucho más rápido que en Stream anteriormente.

**¿Cómo puedo administrar los subtítulos?**

Los subtítulos para las grabaciones de reuniones de Teams solo estarán disponibles durante la reproducción si el usuario tenía activada la transcripción en el momento de la grabación. Los administradores deben [activar la transcripción de la grabación](meetings-policies-recording-and-transcription.md#transcription) para asegurarse de que sus usuarios tienen la opción de grabar reuniones con transcripción.

Los subtítulos ayudan a crear contenido inclusivo para espectadores de todas las capacidades. Como propietario, puede ocultar los subtítulos en la grabación de la reunión, aunque la transcripción de la reunión seguirá estando disponible en Teams a menos que la elimine de allí.

Los subtítulos son compatibles con las grabaciones de reuniones de Teams durante 60 días desde que se graba la reunión.

Los subtítulos no son compatibles por completo si la grabación de la reunión de Teams se mueve o se copia desde su ubicación original en OneDrive para la Empresa o SharePoint.

> [!NOTE]
> Los subtítulos estarán solo en inglés (la transcripción de reuniones aún no está disponible en GCC).

**¿Cómo se verá afectada mi cuota de almacenamiento?**

Los archivos de las grabaciones de reuniones de Teams están en OneDrive para la Empresa y SharePoint, y se incluyen en la cuota de esos servicios. Consulte [Cuota de SharePoint](/sharepoint/sites/plan-site-maintenance-and-management#quotas) y [Cuota de OneDrive para la Empresa](/onedrive/set-default-storage-space).

Obtenga más almacenamiento con [OneDrive para la Empresa](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits), en comparación con Stream y un almacenamiento más intercambiable con SharePoint.

**¿Cómo puedo reproducir una grabación de reunión de Teams?**

El vídeo se reproducirá en el reproductor de vídeo de OneDrive para la Empresa o SharePoint según el sitio desde donde acceda al archivo.

**Si se planea dejar de usar Stream, ¿se mantendrán como están los vídeos existentes? ¿Durante cuánto tiempo?**

Stream como plataforma no quedará en desuso en un futuro próximo. Los vídeos que están actualmente en Stream permanecerán allí hasta que empecemos a migrar. Tras la migración, esos vídeos también se migrarán a OneDrive para la Empresa o SharePoint. Consulte [Detalles de la migración](/stream/streamnew/migration-details) para obtener más información.

**Cómo aplicar una etiqueta de retención a las grabaciones de reuniones de Microsoft Teams?**

Consulte [Cómo aplicar automáticamente una etiqueta de retención](/microsoft-365/compliance/apply-retention-labels-automatically).

**¿Cómo asigno directivas a mis usuarios en Microsoft Teams y qué directivas tienen prioridad?**

Consulte [¿Qué directivas tienen prioridad?](./policy-assignment-overview.md#which-policy-takes-precedence).

**¿Dónde va la grabación si el usuario no tiene OneDrive para la Empresa o SharePoint, o si la cuota de almacenamiento está llena?**

La grabación se situará en nuestra ubicación de almacenamiento temporal, donde se mantendrá durante 21 días. Durante ese tiempo, el organizador debe descargar la grabación. Si no se descarga en un plazo de 21 días, la grabación se elimina.

---
title: Usar OneDrive para la Empresa y SharePoint Online para grabar las reuniones
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo cambiar de Stream a OneDrive para la Empresa y el almacenamiento de grabaciones de reuniones de SharePoint en Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53cc427c1db87a2d0296384d5d0c67e7e7996a
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506329"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Usar OneDrive para la Empresa y SharePoint Online o Stream para grabar las reuniones

> [!Note]
> El cambio del uso de Microsoft Stream a OneDrive para la Empresa y Microsoft Office SharePoint Online para grabaciones de reuniones estará basado en fases.

|<div style="width:290px">Fecha&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5 de octubre de 2020<br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Habilite la directiva de reuniones de Teams para que las grabaciones de reuniones se guarden en OneDrive para la Empresa y SharePoint Online en lugar de Microsoft Stream (Clásico)|
|Implementación a partir del 7 de enero de 2021<br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todas las grabaciones de reuniones nuevas de Teams se guardarán en OneDrive para la Empresa y SharePoint Online, a menos que retrase este cambio modificando las directivas de reuniones de Teams de su organización y estableciéndolas explícitamente en **Stream**. Ver los informes de directivas como Stream no es suficiente. Debe establecer explícitamente el valor de la directiva en **Stream**.|
|Implementación a partir del 11 de enero de 2021<br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC**<br> Aunque los clientes de GCC pueden dejar de participar a partir del 5 de octubre, no puede optar por participar. Esta característica se implementará para todos los clientes de GCC a partir del 11 de enero de 2021, a menos que haya optado por no participar.<br>  <br>A partir del 11 de enero de 2021, todas las grabaciones de reuniones nuevas de Teams para clientes de GCC se guardarán en OneDrive para la Empresa y SharePoint Online, a menos que retrase este cambio modificando las directivas de reuniones de Teams de su organización y estableciéndolas explícitamente en **Stream**. <br><br>Si ha optado por no participar, pero está listo para activar esta característica, puede hacerlo configurando explícitamente la directiva de reunión de Teams en **OneDrive para la Empresa**. |
|Implementación a partir del 1 de marzo de 2021 <br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC High y DoD**<br> Los clientes ahora pueden habilitar las grabaciones de reuniones en la nube en Microsoft Teams por primera vez. Estas grabaciones se almacenarán y reproducirán en OneDrive y SharePoint Online de forma predeterminada. |
|Implementación incremental a partir del 7 de julio de 2021 <br> *(Completar)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos los clientes (Enterprise, Educación y GCC)**<br> Si tiene una reunión de Teams grabada en OneDrive y SharePoint Online que se transcribiera en directo, ahora puede usar la transcripción para encontrar el archivo de grabación de la reunión en Búsqueda de Microsoft. |
|Implementación incremental a partir del 16 de agosto de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos los clientes (Enterprise, Educación y GCC)**<br>No se pueden guardar nuevas grabaciones de reuniones en Microsoft Stream (Clásico); todos los clientes guardarán automáticamente las grabaciones de las reuniones en OneDrive para la Empresa y SharePoint Online incluso si han cambiado sus directivas de reuniones de Teams a Stream.<br><br> Recomendamos a los clientes que, para controlar mejor el cambio de la organización, opten por participar cuando se sientan cómodos con el cambio, en lugar de esperar a que se realice. |

Microsoft Teams tiene un nuevo método para guardar las grabaciones de reuniones. Como primera fase de una transición del Microsoft Stream clásico al [nuevo Stream](/stream/streamnew/new-stream), este método almacena grabaciones en Microsoft OneDrive para la Empresa y SharePoint en Microsoft 365 y ofrece muchas ventajas.

Stream (Clásico) como plataforma no quedará en desuso en un futuro próximo. Los vídeos que se encuentran actualmente en Stream (clásico) permanecerán allí hasta que haya disponible una herramienta de migración futura para moverlos a OneDrive y SharePoint Online. Consulte [Migración de Stream clásico](/stream/streamnew/classic-migration) para obtener más información sobre nuestros planes para el futuro.

> [!NOTE]
> Si una grabación de reunión de Teams no se carga correctamente en OneDrive o SharePoint Online, la grabación se guardará temporalmente en Azure Media Services (AMS). Una vez almacenada en AMS, no se realizará ningún reintento para cargar automáticamente la grabación en OneDrive, SharePoint Online o Stream.

Las grabaciones de reuniones almacenadas en AMS estarán disponibles durante 21 días antes de eliminarse automáticamente. Los usuarios pueden descargar el vídeo de AMS si necesitan guardar una copia.

Las ventajas de usar OneDrive para la Empresa y SharePoint Online para almacenar grabaciones son las siguientes:

- Directivas de retención para la grabación de reuniones de Teams (TMR) (etiquetas de autorretención S+C E5)
- Ventaja del gobierno de información de OneDrive para la Empresa y SharePoint Online
- Fácil de establecer permisos y uso compartido
- Compartir grabaciones con invitados (usuarios externos) solo con uso compartido explícito
- Solicitar flujo de acceso
- Proporcionar vínculos compartidos de OneDrive para la Empresa y SharePoint Online
- Las grabaciones de las reuniones están disponibles más rápido
- Buscar transcripción de base grabada en la reunión
- **Ir a local** soporte para espacio empresarial
- Soporte para Multi-Geo: las grabaciones se almacenan en una región específica de ese usuario
- Soporte para Bring your own key (BYOK)

Vea la lista completa de las [características disponibles actualmente y las perspectivas para el futuro](/stream/streamnew/features-new-version-stream).

Vea "Novedades de las grabaciones de reuniones de Microsoft Teams" para obtener más información.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Configurar la opción de grabación de la reunión en OneDrive para la Empresa y SharePoint Online

La opción de grabación de la reunión es una configuración en el nivel de directiva de Teams. En el ejemplo siguiente se muestra cómo establecer la directiva global. Asegúrese de establecer la opción de grabación de la reunión para la directiva o las directivas que haya asignado a los usuarios.

> [!Note]
> Los cambios en las directivas de reunión de Teams pueden tardar un tiempo en propagarse. Vuelva a echar un vistazo unas horas después de aplicarlos, cierre la sesión e iníciela otra vez en la aplicación de escritorio de Teams, o simplemente reinicie el equipo.

1. Instale PowerShell para Teams.

   > [!NOTE]
   > El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial. Consulte [Administrar Skype Empresarial Online con PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Inicie PowerShell como administrador.

3. Instale el [módulo de PowerShell para Teams](./teams-powershell-install.md).

4. Importe el módulo MicrosoftTeams e inicie sesión como administrador de Teams.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Use [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para establecer una directiva de reunión de Teams para realizar la transición del almacenamiento de Stream a OneDrive para la Empresa y SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Si algunos de los usuarios han asignado una directiva por organizador o por usuario, debe establecer esta configuración en esta directiva si quiere que también almacenen las grabaciones de reuniones en OneDrive para la Empresa y SharePoint Online. Para más información, consulte [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md).

## <a name="learn-more"></a>Más información

Para más información sobre la grabación de reuniones en la nube de Teams, consulte [Grabación de reuniones en la nube de Teams](cloud-recording.md). En este artículo podrá obtener más información sobre la configuración, la administración, la gobernanza, los permisos y el almacenamiento de las grabaciones.

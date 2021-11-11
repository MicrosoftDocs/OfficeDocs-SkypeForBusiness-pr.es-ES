---
title: Administrar componentes activos en Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo administrar componentes activos en Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c05888191c98e2b7fe11637ad8fe5ba8a8c1132
ms.sourcegitcommit: 2ce417430b2aac770997daaf5ef5d844aa97fd84
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2021
ms.locfileid: "60911864"
---
# <a name="manage-live-components-in-teams"></a>Administrar componentes activos en Teams

Los componentes activos de Teams chat ofrecen una nueva forma de idear, crear y tomar decisiones juntos. Envíe un componente (como una tabla, una lista de tareas o un párrafo) donde todos los usuarios del chat puedan editarlos en línea y ver los cambios a medida que se realicen. Esto significa que puede recopilar ideas y comentarios de su equipo mientras mantiene menos reuniones y minimiza la necesidad de conversaciones largas.
> [!Note]
> Los componentes activos son la primera característica de la [aplicación Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) que está disponible en Teams. Tenga en cuenta que "Componentes activos" se cambiará a "Componentes de bucle" a principios de 2022.

**Haga las tareas más rápido juntos.** Abarrote una agenda, realice un seguimiento de los elementos de acción de un grupo o tome notas de forma colectiva. Estos son solo algunos escenarios que se facilitan con los componentes activos.

**Compartir componentes.** En esta versión, puede compartir componentes en directo en diferentes Teams chats. Los destinatarios pueden editar desde cualquier lugar y ver actualizaciones al instante, independientemente de dónde se realizaron los cambios. En versiones futuras, los componentes activos serán compatibles con Teams y canales de reunión, Outlook y, finalmente, en todas Microsoft 365 aplicaciones.

**Empiece en el chat, cree desde allí.** Todos los componentes que cree Teams chat se guardarán automáticamente en un archivo en OneDrive. Por lo tanto, es posible que empiece a colaborar en el chat y, posteriormente, se mueva al archivo, donde tiene un espacio visual más grande para editar y puede agregar tantos componentes como quiera.

## <a name="clients-and-platforms"></a>Clientes y plataformas

Disponible en Teams aplicaciones en Windows, Mac, Linux, iOS y Android.

## <a name="settings-management"></a>Configuración administración de aplicaciones

Los componentes activos se han creado con Microsoft Fluid Framework en Microsoft 365 suite y se controlan desde SharePoint Online y no desde el centro Teams administración.

Necesitará la última versión de SharePoint módulo de [PowerShell](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) en línea para habilitar o deshabilitar todas las experiencias fluidas en su Office 365 inquilino. Microsoft Fluid Framework predeterminado es **ON para** todos los inquilinos de la versión dirigida. Como los componentes activos están diseñados para la colaboración, los componentes siempre se comparten como editables por otros usuarios, incluso si el espacio empresarial está establecido como predeterminado en solo visualización para otros tipos de archivo. Vea el **vínculo Más** información junto a la configuración para obtener más información.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Comprobar si el Fluid Framework está habilitado mediante el cmdlet SharePoint PowerShell en línea

1. [Conectar para SharePoint PowerShell en línea](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Compruebe si Fluid Framework está habilitado ejecutando el cmdlet Get-SPOTenant sin ningún argumento.

3. Compruebe que el valor de IsFluidEnabled es **verdadero.**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Habilitar el Fluid Framework el cmdlet SharePoint PowerShell en línea

1. [Conectar para SharePoint PowerShell en línea](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Habilitar Fluid con el cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   El cambio llevará poco tiempo en aplicarse en toda la tenencia. 

La característica estará disponible en Teams Windows escritorio, Mac, iOS y Android. Cuando esté habilitado, los usuarios verán una nueva opción para insertar componentes activos en la experiencia de redacción de mensajes para estos clientes.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Deshabilitar Fluid Framework a través SharePoint cmdlet de PowerShell en línea

1. [Conectar para SharePoint PowerShell en línea](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

2. Deshabilite Fluid con Set-SPOTenant cmdlet Set-SPOTenant -IsFluidEnabled $false. 

   El cambio llevará poco tiempo en aplicarse en toda la tenencia. 

Si necesita volver a habilitar esta funcionalidad, puede usar SharePoint cmdlets de PowerShell en línea.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $true
PS C:\\WINDOWS\\system32&gt;
```
## <a name="known-issues"></a>Problemas conocidos

- Los componentes en directo del chat no se pueden editar Aplicación de Office al usar Teams en Android.

- Si los permisos de archivo predeterminados del inquilino se establecen en Personas específicas (solo las personas que especifica el **usuario)** y el remitente quita algunos usuarios de la lista Personas específicas en el cuadro de diálogo permisos al crear un componente, es posible que esos usuarios todavía tengan acceso al contenido. Este problema se debe a la limitación de administración de acceso del cuadro de diálogo de permisos y se solucionará en la versión futura.

- Si la configuración de la directiva de acceso condicional del inquilino impide que la red cliente se conecte a, los componentes activos no funcionarán según lo esperado para ahorrar cambios en tiempo `https://pushchannel.1drv.ms` real en el servicio.

## <a name="known-limitations"></a>Limitaciones conocidas

- La búsqueda de componentes activos en Teams búsqueda devolverá un vínculo al componente en office.com, no en el mensaje de chat en sí.

- Los componentes activos están deshabilitados en chats federados.

- Los invitados B2B no podrán colaborar en componentes activos que se comparten con ellos a través de Company Share Link a menos que el inquilino establece la opción de acceso externo para permitir que los invitados B2B tengan el mismo nivel de acceso que los miembros del inquilino.

- Teams La compatibilidad completa del cliente web con los componentes de Live estará disponible próximamente.

- Los componentes activos aún no son compatibles Teams canales, pero su edición en línea en canales está planeada para más experiencias en el futuro.

- Con los permisos de archivo predeterminados del inquilino establecidos en Personas específicas (solo las personas que especifica el **usuario),** copiar el vínculo al componente activo y pegarlo en otro chat requiere que el remitente use el cuadro de diálogo permisos y agregue los destinatarios en la opción Personas específicas para conceder acceso correctamente.

- Con los permisos de archivo predeterminados del inquilino establecidos en Personas específicas (solo las personas que especifica el **usuario),** la creación de un componente activo en el chat grupal con más de 20 miembros requerirá que el remitente seleccione manualmente las opciones de permisos para el componente.

- Los componentes activos del chat no se cargarán solo si el archivo se movió a otra biblioteca. Si el archivo se mueve a otra carpeta, se seguirá cargando en el chat.

## <a name="how-to-check-your-tenants-default-file-permissions"></a>Cómo comprobar los permisos de archivo predeterminados del inquilino

1. Vaya a la [Centro de administración de Microsoft 365](https://admin.microsoft.com/).

2. A la izquierda, en **Centros de administración,** **seleccione SharePoint**.

3. Seleccione **Directivas**  >  **compartidas** y, en **Vínculos a archivos y** carpetas, vea los permisos de archivo predeterminados de su inquilino.

## <a name="storage-of-fluid-files"></a>Storage de `.fluid` archivos

**¿Cómo `.fluid` se almacenan?**

Los componentes activos creados en Teams están con el respaldo de un archivo almacenado en el `.fluid` OneDrive para la Empresa. Ser un archivo en OneDrive para la Empresa significa que los usuarios pueden crear, detectar y administrar componentes activos (archivos) tan fácilmente como cualquier `.fluid` documento Office usuario.

Los usuarios pueden buscar contenido en `.fluid` archivos desde Office.com y OneDrive para la Empresa.
`.fluid` Los archivos funcionan con características de gobierno de datos como exhibición de documentos electrónicos, auditoría, informes y retención legal.

`.fluid`Los archivos ahora aparecerán en Office.com y OneDrive para la Empresa, como en las áreas Recientes y Recomendados.
`.fluid`los archivos se pueden restaurar a versiones anteriores desde OneDrive para la Empresa.

Los participantes de chat deben tener una OneDrive para crear componentes activos. Sin una cuenta OneDrive, es posible que los participantes del chat puedan colaborar en un componente creado por otros usuarios que tengan una cuenta OneDrive válida, pero no puedan crear su propia cuenta.

[Al](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) mover un archivo de OneDrive a un SharePoint web, el componente activo no se carga en `.fluid` Teams chat.

**¿Qué sucede si el propietario del archivo abandona la empresa?**

[OneDrive directivas de retención se](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) aplican a los archivos igual que a otros `.fluid` contenidos creados por el usuario.

**¿Cómo se `.fluid` comparten los archivos?**

Los componentes activos se pueden insertar en Teams chat o copiarse de un chat a otro. (Los componentes activos aún no son compatibles con los canales). Son los permisos existentes del inquilino de forma predeterminada, pero los usuarios pueden cambiar los permisos antes de enviarlos para asegurarse de que todos los usuarios tienen acceso.

Abrir componentes desde Teams chat en Office.com ofrece funcionalidad de uso compartido en la parte superior de la ventana, similar a las opciones de uso compartido que se ofrecen para otros Office documentos.

**¿Qué sucede `.fluid` si un archivo se daña o se daña?**

El Historial de versiones le permite revisar y copiar desde versiones anteriores del archivo.

**¿Qué aplicaciones pueden abrir y editar `.fluid` archivos?**

`.fluid`Los archivos solo se pueden abrir como vínculos en el explorador, como Office.com, y como componentes activos en Teams chat. Si se descargan, no se pueden abrir de nuevo sin cargarlas primero en OneDrive para la Empresa o SharePoint Online.

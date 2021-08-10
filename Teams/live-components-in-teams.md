---
title: Administrar componentes activos en Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
localization_priority: Normal
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
ms.openlocfilehash: cb472822f7d55636bfd5ee4c48e7c962a705f6e05fd65b263952895040d69f7c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305022"
---
# <a name="manage-live-components-in-teams"></a>Administrar componentes activos en Teams

Los componentes activos Teams chat ofrecen una nueva forma de idear, crear y tomar decisiones juntos. Envíe un componente ,como una tabla, una lista de tareas o un párrafo, donde todos los usuarios del chat puedan editarlos en línea y ver los cambios que se realicen. Esto significa que puedes recopilar ideas y comentarios de tu equipo mientras celebras menos reuniones y minimizas la necesidad de largos subprocesos de chat.

**Haga las tareas más rápido juntos.** Una agenda de origen de multitudes, un seguimiento de los elementos de acción de un grupo o tomar notas de forma colectiva. Estos son solo algunos escenarios que se facilitan con componentes activos.

**Compartir componentes.** En esta versión, puedes compartir componentes activos en diferentes Teams chats. Los destinatarios pueden editar desde cualquier lugar y ver actualizaciones al instante, independientemente de dónde se realicen los cambios. En versiones futuras, los componentes activos se admiten en Teams y canales de reunión, Outlook y, finalmente, en todas Microsoft 365 aplicaciones.

**Comience en el chat, cree desde allí.** Cada componente que cree a Teams chat se guarda automáticamente en un archivo de OneDrive. Por lo tanto, es posible que empieces a colaborar en el chat y luego te muevas al archivo, donde tienes un espacio visual más grande para editar y puedes agregar tantos componentes como quieras.

## <a name="clients-and-platforms"></a>Clientes y plataformas

Disponible en Teams aplicaciones en Windows, Mac, Linux, iOS y Android.

A partir de principios de septiembre, los componentes activos estarán disponibles globalmente. A finales de septiembre, estará disponible para Government Community Cloud Mod (GCC).

## <a name="settings-management"></a>Configuración administración

Los componentes activos se Microsoft Fluid Framework admiten en Microsoft 365 suite y se controlan desde SharePoint Online y no desde Teams centro de administración.

Necesitará la versión más reciente de SharePoint módulo de [PowerShell](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) en línea para habilitar o deshabilitar todas las experiencias fluidas en su Office 365 inquilino. Microsoft Fluid Framework en **ON** para todos los inquilinos de versión de destino. Dado que los componentes activos están diseñados para la colaboración, los componentes siempre se comparten como editables por otros usuarios, incluso si el espacio empresarial está establecido como predeterminado en solo vista para otros tipos de archivo. Consulta el **vínculo Obtener más información** junto a la configuración para obtener más información.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Comprobar si el Fluid Framework está habilitado mediante el cmdlet SharePoint PowerShell en línea

1. [Conectar a SharePoint PowerShell en línea](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Compruebe si Fluid Framework está habilitado ejecutando el cmdlet Get-SPOTenant sin argumentos.

3. Compruebe que el valor de IsFluidEnabled es **true**.

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Habilitar el Fluid Framework a través del cmdlet SharePoint Online PowerShell 

1. [Conectar a SharePoint PowerShell en línea](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Habilitar Fluid con el cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   El cambio llevará poco tiempo en aplicarse en todo el arrendamiento. 

La característica estará disponible en Teams Windows Escritorio, Mac, iOS, Android. Cuando se habilita, los usuarios verán una nueva opción para insertar componentes activos en la experiencia de redacción de mensajes para estos clientes.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Deshabilitar Fluid Framework a través SharePoint cmdlet de PowerShell en línea

1. [Conectar a SharePoint PowerShell en línea](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

2. Deshabilite Fluid con el cmdlet Set-SPOTenant Set-SPOTenant -IsFluidEnabled $false. 

   El cambio llevará poco tiempo en aplicarse en todo el arrendamiento. 

Si necesita volver a habilitar esta funcionalidad, puede usar SharePoint cmdlets de PowerShell en línea.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Limitaciones conocidas

- Crear una tabla o una lista de tareas como el primer componente después de reiniciar Teams aplicación puede tardar algo más de tiempo.

- Otros miembros del chat recibirán una notificación por correo electrónico cuando se mencione con un símbolo at (@). (Las notificaciones de menciones en la Teams de actividad estarán disponibles próximamente).

- La búsqueda de componentes activos dentro Teams búsqueda devolverá un vínculo al componente en office.com, no en el propio mensaje de chat.

- Los componentes activos están deshabilitados en chats federados y habilitados para chats regulares con una cuenta de invitado con Azure B2B.

- Aunque puedes compartir un componente en Teams canales y otras aplicaciones Microsoft 365, los destinatarios obtienen un vínculo en la mayoría de los lugares en este momento. La edición en línea está planeada para más experiencias en el futuro.

## <a name="storage-of-fluid-files"></a>Storage de `.fluid` archivos

**¿Cómo `.fluid` se almacena?**

Los componentes activos creados en Teams están con la copia de seguridad de un archivo almacenado en el `.fluid` OneDrive para la Empresa del creador. Ser un archivo en OneDrive para la Empresa significa que los usuarios pueden crear, detectar y administrar componentes activos (archivos) tan fácilmente como cualquier `.fluid` Office documento.

Los usuarios pueden buscar contenido `.fluid` en archivos de Office.com y OneDrive para la Empresa.
`.fluid` los archivos funcionan con características de gobierno de datos como exhibición de documentos electrónicos, auditoría, informes y retención legal.

`.fluid`los archivos ahora aparecerán en Office.com y OneDrive para la Empresa, como en las áreas Reciente y Recomendado.
`.fluid`los archivos se pueden restaurar a versiones anteriores desde OneDrive para la Empresa.

Los participantes de chat deben tener OneDrive cuenta para crear componentes activos. Sin una cuenta OneDrive válida, es posible que los participantes del chat aún puedan colaborar en un componente creado por otros usuarios que tengan una cuenta OneDrive válida, pero que no puedan crear su propia cuenta.

[Si](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) se mueve un archivo OneDrive a un SharePoint, el componente activo no se puede cargar en `.fluid` Teams chat.

**¿Qué sucede si el propietario del archivo deja la empresa?**

[OneDrive directivas de retención se](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) aplican a los archivos tal como lo hacen con otros `.fluid` contenidos creados por el usuario.

**¿Cómo se `.fluid` comparten los archivos?**

Los componentes activos se pueden insertar en Teams chat o copiarse de un chat a otro. (Los componentes activos aún no se admiten en canales). Son los permisos existentes del inquilino de forma predeterminada, pero los usuarios pueden cambiar los permisos antes de enviarlos para garantizar que todos tienen acceso.

Abrir componentes desde Teams chat en Office.com ofrece funcionalidad de uso compartido en la parte superior de la ventana, similar a las opciones de uso compartido que se ofrecen para otros Office documentos.

**¿Qué ocurre `.fluid` si un archivo se daña o se daña?**

Historial de versiones permite revisar y copiar desde versiones anteriores del archivo.

**¿Qué aplicaciones pueden abrir y editar `.fluid` archivos?**

`.fluid`los archivos solo se pueden abrir como vínculos en el explorador, como Office.com, y como componentes activos en Teams chat. Si se descargan, no se pueden abrir de nuevo sin volver a cargarlos en OneDrive para la Empresa o SharePoint Online.

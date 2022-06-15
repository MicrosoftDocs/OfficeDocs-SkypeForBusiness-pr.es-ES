---
title: Información general sobre los componentes de Loop en Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo administrar componentes Loop en Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fb436ef2e8b32f737fcfa10823b54dc0e6a7cca
ms.sourcegitcommit: 07abd8fdb653e57a839ded72620d0179049f25dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66088586"
---
# <a name="overview-of-loop-components-in-teams"></a>Información general sobre los componentes de Loop en Teams

Loop componentes de Teams chat ofrecen una nueva forma de idear, crear y tomar decisiones conjuntamente. Envíe un componente (como una tabla, una lista de tareas o un párrafo) donde todos los usuarios de su chat pueden editar en línea y ver los cambios a medida que se realizan. 

> [!Note]
> Loop componentes es la primera característica de la [aplicación de Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) que está disponible en Teams. 

**Haga las tareas más rápidamente juntos.** Crear una agenda, realizar un seguimiento de los elementos de acción de un grupo o tomar notas colectivamente. Estos son solo algunos escenarios que se facilitan con Loop componentes.

**Compartir componentes.** En esta versión, puede compartir Loop componentes en diferentes chats Teams. Los destinatarios pueden editar desde cualquier lugar y ver las actualizaciones al instante, independientemente de dónde se realizaron los cambios.

**Empieza en el chat y crea desde allí.** Todos los componentes que cree a partir de Teams chat se guardarán automáticamente en un archivo de OneDrive. Por lo tanto, puede empezar a colaborar en el chat y, después, desplazarse al archivo, donde tiene un espacio visual más grande para editar y puede agregar tantos componentes como desee.

Para obtener información sobre la configuración de administración de los componentes de Loop en Teams, vea [Administrar componentes de Loop en SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clientes y plataformas

Disponible en Teams aplicaciones en Windows, Mac, Linux, iOS y Android.

## <a name="loop-components-and-fluid-files"></a>Loop componentes y archivos .fluid

Loop componentes creados en Teams están respaldados por un archivo .fluid almacenado en el OneDrive del creador. Ser un archivo en OneDrive significa que los usuarios pueden crear, descubrir y administrar componentes de Loop (archivos .fluid) tan fácilmente como cualquier documento Office. 

## <a name="how-are-fluid--files-stored"></a>¿Cómo se almacenan los archivos .fluid?

Los archivos .fluid aparecen en Office.com y OneDrive, por ejemplo, en las áreas Recientes y Recomendadas. Los usuarios pueden buscar contenido en archivos .fluid de Office.com y OneDrive. Los archivos .fluid se pueden restaurar a versiones anteriores de OneDrive. Para crear Loop componentes, los participantes del chat deben tener una cuenta de OneDrive. Sin una cuenta de OneDrive válida, es posible que los participantes del chat puedan colaborar en un componente creado por otros usuarios que tengan una cuenta de OneDrive válida, pero que no puedan crear la suya propia. 

Mover un archivo .fluid de OneDrive a un sitio de SharePoint provocará que el componente en directo no se cargue en Teams chat.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>¿Qué sucede si el propietario del archivo deja la empresa?

OneDrive directivas de retención se aplican a los archivos .fluid igual que a otros contenidos creados por el usuario.

## <a name="how-are-fluid-files-shared"></a>¿Cómo se comparten los archivos .fluid?

Loop componentes se pueden insertar en Teams chat o copiar de un chat a otro. (Loop componentes aún no son compatibles con los canales). De forma predeterminada, se usan los permisos existentes de la organización, pero los usuarios pueden cambiar los permisos antes de enviarlos para asegurarse de que todos los usuarios tienen acceso.

Abrir componentes de Teams chat en Office.com ofrece funcionalidad de uso compartido en la parte superior de la ventana, similar a las opciones de uso compartido que se ofrecen para otros documentos Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>¿Qué sucede si un archivo .fluid resulta dañado o dañado?

Historial de versiones le permite revisar y copiar de versiones anteriores del archivo.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>¿Qué aplicaciones pueden abrir y editar archivos .fluid?

Los archivos .fluid solo se pueden abrir como vínculos en el explorador, como Office.com, y como Loop componentes en Teams chat. Si se descargan, no se pueden volver a abrir sin volver a cargarlos en OneDrive o SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>¿Los archivos .fluid admiten eDiscovery?

Los archivos .fluid son reconocibles, pero tienen compatibilidad limitada con el flujo de trabajo de eDiscovery. Actualmente, los archivos .fluid se almacenan en el OneDrive del creador y están disponibles para búsqueda y recopilación tanto en eDiscovery (Estándar) como en eDiscovery (Premium). Sin embargo, no se representan en vista previa y el formato de exportación para revisión no es consumible por las herramientas existentes. Para ver el contenido exportado, cárguelos en cualquier OneDrive. Si lo desea, puede deshabilitar temporalmente estas experiencias como se describe en la sección [Administración de Configuración](/sharepoint/manage-loop-components#settings-management).

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Si Loop está deshabilitado del cambio de administrador, ¿cuál será la experiencia del usuario?

Si deshabilita estas experiencias como se describe en la sección [Administración de Configuración](/sharepoint/manage-loop-components#settings-management), se aplicarán los siguientes cambios en la experiencia:

- El punto de entrada para crear e insertar dentro de Teams mensajes se ocultará. Los usuarios no podrán crear nuevos archivos .fluid.
- Los mensajes existentes que anteriormente se representaban como un componente de Loop interactivo se representarán en su lugar como un hipervínculo "componente Loop". No se mostrará ningún contenido interactivo en Teams.
- Cuando un usuario final hace clic en el hipervínculo "componente Loop" o busca un archivo .fluid en OneDrive para la Empresa y hace clic para abrirlo, se abrirá el archivo en una pestaña del explorador independiente, pero los usuarios finales no podrán editar el archivo.

## <a name="known-issues"></a>Problemas conocidos

- Loop componentes del chat no se pueden editar a través de Aplicación de Office al usar Teams en Android.
- Si los permisos de archivo predeterminados del espacio empresarial se establecen en *Usuarios específicos* (solo los usuarios especificados por el usuario) y el remitente quita algunos usuarios de la lista *Personas específicas* del cuadro de diálogo de permisos al crear un componente, es posible que esos usuarios sigan teniendo acceso al contenido.
- Con los permisos de archivo predeterminados del espacio empresarial establecidos en *Personas específicas* (solo las personas que especifique el usuario), copiar el vínculo al componente en directo y pegar en otro chat requiere que el remitente use el cuadro de diálogo de permisos y agregue los destinatarios en la opción Personas específicas para conceder acceso correctamente.
- Con los permisos de archivo predeterminados del inquilino establecidos en *Personas específicas* (solo las personas que especifique el usuario), la creación de un componente en directo en el chat grupal con más de 20 miembros requerirá que el remitente seleccione manualmente las opciones de permisos para el componente.
- La búsqueda de Loop componentes en Teams búsqueda devolverá un vínculo al componente de office.com, no al mensaje de chat en sí.
- Loop componentes están deshabilitados en los chats federados.
- Los invitados B2B no podrán colaborar en un componente en directo compartido con ellos a través de Company Share Link. Establezca permisos **en Personas que están actualmente en este chat** para compartir componentes con invitados B2B.
- los componentes Loop no son compatibles con los canales de Teams.
- Loop componentes del chat no se cargarán solo si el archivo se ha movido a otra biblioteca. Si el archivo se mueve a otra carpeta, seguirá cargándose en el chat.

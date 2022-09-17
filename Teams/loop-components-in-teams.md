---
title: Información general sobre los componentes del bucle en Teams
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
description: Obtenga información sobre cómo administrar los componentes del bucle en Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e0b9c5a7ffef07a1d9245d2b1266a071b4ee0c2
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67795059"
---
# <a name="overview-of-loop-components-in-teams"></a>Información general sobre los componentes del bucle en Teams

Los componentes de bucle en el chat de Teams ofrecen una nueva forma de idear, crear y tomar decisiones conjuntamente. Envíe un componente (como una tabla, una lista de tareas o un párrafo) donde todos los usuarios de su chat pueden editar en línea y ver los cambios a medida que se realizan. 

> [!Note]
> Los componentes de bucle son la primera característica de la [aplicación de Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) que está disponible en Teams. 

**Haga las tareas más rápidamente juntos.** Crear una agenda, realizar un seguimiento de los elementos de acción de un grupo o tomar notas colectivamente. Estos son solo algunos escenarios que se facilitan con los componentes loop.

**Compartir componentes.** En esta versión, puede compartir componentes del bucle en diferentes chats de Teams. Los destinatarios pueden editar desde cualquier lugar y ver las actualizaciones al instante, independientemente de dónde se realizaron los cambios.

**Empieza en el chat y crea desde allí.** Todos los componentes que cree desde el chat de Teams se guardarán automáticamente en un archivo en OneDrive. Por lo tanto, puede empezar a colaborar en el chat y, después, desplazarse al archivo en Office.com, donde tiene un espacio visual más grande para editar y puede agregar tantos componentes como desee.

Para obtener información sobre la configuración de administración de componentes de bucle en Teams, vea [Administrar componentes de bucle en SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clientes y plataformas

Disponible en aplicaciones de Teams en Windows, Mac, Linux, iOS y Android.

## <a name="loop-components-and-fluid-files"></a>Componentes de bucle y archivos .fluid

Los componentes de bucle creados en Teams están respaldados por un archivo .fluid (se cambiará a .loop en un futuro próximo) almacenado en el OneDrive del creador. Ser un archivo en OneDrive significa que los usuarios pueden crear, descubrir y administrar componentes de bucle (archivos .fluid) tan fácilmente como cualquier documento de Office. 

## <a name="how-are-fluid-files-stored"></a>¿Cómo se almacenan los archivos .fluid?

Los archivos .fluid aparecen en Office.com y OneDrive, como en las áreas Recientes y Recomendadas. Los usuarios pueden buscar contenido en archivos .fluid de Office.com y OneDrive. Los archivos .fluid se pueden restaurar a versiones anteriores de OneDrive. Para crear componentes de bucle, los participantes del chat deben tener una cuenta de OneDrive. Sin una cuenta de OneDrive válida, es posible que los participantes del chat puedan colaborar en un componente creado por otros usuarios que tengan una cuenta de OneDrive válida, pero que no puedan crear su propia cuenta. 

Mover un archivo .fluid de OneDrive a un sitio de SharePoint provocará que el componente en directo no se cargue en el chat de Teams.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>¿Qué sucede si el propietario del archivo deja la empresa?

Las directivas de retención de OneDrive se aplican a los archivos .fluid igual que a otros contenidos creados por el usuario.

## <a name="how-are-fluid-files-shared"></a>¿Cómo se comparten los archivos .fluid?

Los componentes de bucle se pueden insertar en el chat de Teams o copiarse de un chat a otro. (Los componentes de bucle aún no son compatibles con los canales). De forma predeterminada, se usan los permisos existentes de la organización, pero los usuarios pueden cambiar los permisos antes de enviarlos para asegurarse de que todos los usuarios tienen acceso.

Abrir componentes del chat de Teams en Office.com ofrece funciones de uso compartido en la parte superior de la ventana, de forma similar a las opciones de uso compartido que se ofrecen para otros documentos de Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>¿Qué sucede si un archivo .fluid resulta dañado o dañado?

Historial de versiones le permite revisar, restaurar o copiar de versiones anteriores del archivo.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>¿Qué aplicaciones pueden abrir y editar archivos .fluid?

Los archivos .fluid solo se pueden abrir como vínculos en el explorador, como Office.com y como componentes de bucle en el chat de Teams. Si se descargan, no se pueden volver a abrir sin cargarlos de nuevo en OneDrive o SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>¿Los archivos .fluid admiten eDiscovery?

Los archivos .fluid son reconocibles, pero tienen compatibilidad limitada con el flujo de trabajo de eDiscovery. Actualmente, los archivos .fluid se almacenan en el OneDrive del creador y están disponibles para búsqueda y recopilación tanto en eDiscovery (Estándar) como en eDiscovery (Premium). Sin embargo, no se representan en vista previa y el formato de exportación para revisión no es consumible por las herramientas existentes. Para ver el contenido exportado, cárgalo en cualquier OneDrive. Si lo desea, puede deshabilitar temporalmente estas experiencias como se describe en la sección [Administración de configuración](/sharepoint/manage-loop-components#settings-management) .

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Si loop está deshabilitado del modificador admin, ¿cuál será la experiencia del usuario?

Si deshabilita estas experiencias como se describe en la sección [Administración de configuración](/sharepoint/manage-loop-components#settings-management) , se aplicarán los siguientes cambios de experiencia:

- El punto de entrada para crear o insertar en la mensajería de Teams se ocultará. Los usuarios no podrán crear nuevos archivos .fluid.
- Los mensajes existentes que anteriormente se habrían representado como un componente de bucle interactivo se representarán en su lugar como un hipervínculo "Componente de bucle". No se mostrará ningún contenido interactivo en Teams.
- Cuando un usuario final hace clic en el hipervínculo "Componente de bucle" o busca un archivo .fluid en OneDrive para la Empresa y hace clic para abrirlo, se abrirá el archivo en una pestaña del explorador independiente. Los usuarios finales aún podrán editar el archivo.

## <a name="known-issues"></a>Problemas conocidos

- Con los permisos de archivo predeterminados del espacio empresarial establecidos en *Usuarios específicos* (solo los usuarios especificados por el usuario), copiar el vínculo al componente Loop y pegarlo en otro chat requiere que el remitente use el cuadro de diálogo de permisos y agregue a los destinatarios en la opción Personas específicas para conceder acceso correctamente.
- Con los permisos de archivo predeterminados del inquilino establecidos en *Personas específicas* (solo las personas que especifique el usuario), la creación de un componente en directo en el chat grupal con más de 20 miembros requerirá que el remitente seleccione manualmente las opciones de permisos para el componente.
- Si busca Componentes de bucle en la búsqueda de Teams, se devolverá un vínculo al componente de office.com, no al mensaje de chat en sí.
- Los componentes del bucle se deshabilitan en los chats federados.
- Los invitados no podrán colaborar en un componente en directo que se comparte con ellos a través de Company Share Link. Establezca permisos para **Personas actualmente en este chat** para compartir componentes con invitados.
- Los componentes de bucle no son compatibles con los canales de Teams.
- Los componentes del bucle en el chat no se cargarán solo si el archivo se ha movido a otra biblioteca. Si el archivo se mueve a otra carpeta, seguirá cargándose en el chat.

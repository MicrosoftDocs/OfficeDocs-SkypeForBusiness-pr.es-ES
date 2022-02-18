---
title: Información general sobre los componentes de bucle en Teams
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
description: Obtenga información sobre cómo administrar los componentes de bucle en Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7264d7f08342121a862943dd8b063fe904c87072
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893733"
---
# <a name="overview-of-loop-components-in-teams"></a>Información general sobre los componentes de bucle en Teams

Los componentes de bucle Teams chat ofrecen una nueva forma de idear, crear y tomar decisiones juntos. Envíe un componente , como una tabla, una lista de tareas o un párrafo, donde todos los usuarios del chat puedan editar en línea y ver los cambios a medida que se realicen. 

> [!Note]
> Los componentes de bucle son la primera característica de la [aplicación Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) que está disponible en Teams. 

**Haga las tareas más rápido juntos.** Abarrote una agenda, realice un seguimiento de los elementos de acción de un grupo o tome notas de forma colectiva. Estos son solo algunos escenarios que se facilitan con los componentes Bucle.

**Compartir componentes.** En esta versión, puede compartir componentes loop en diferentes Teams chats. Los destinatarios pueden editar desde cualquier lugar y ver actualizaciones al instante, independientemente de dónde se realizaron los cambios.

**Empiece en el chat, cree desde allí.** Todos los componentes que cree Teams chat se guardarán automáticamente en un archivo en OneDrive. Por lo tanto, es posible que empiece a colaborar en el chat y, posteriormente, se mueva al archivo, donde tiene un espacio visual más grande para editar y puede agregar tantos componentes como quiera.

## <a name="clients-and-platforms"></a>Clientes y plataformas

Disponible en Teams aplicaciones en Windows, Mac, Linux, iOS y Android.

## <a name="loop-components-and-fluid-files"></a>Bucle de componentes y archivos .fluid

Los componentes de bucle creados en Teams están a los que se les hace una copia de seguridad de un archivo .fluid almacenado en el OneDrive. Ser un archivo en OneDrive significa que los usuarios pueden crear, detectar y administrar componentes de bucle (archivos .fluid) tan fácilmente como cualquier documento Office usuario. Los archivos .fluid funcionan con características de gobierno de datos como eDiscovery, auditoría, informes y retención legal.

## <a name="how-are-fluid--files-stored"></a>¿Cómo se almacenan los archivos .fluid?

Los archivos .fluid aparecen en Office.com y OneDrive, como en las áreas Recientes y Recomendados. Los usuarios pueden buscar contenido en archivos .fluid desde Office.com y OneDrive. Los archivos .fluid se pueden restaurar a versiones anteriores desde OneDrive. Para crear componentes de bucle, los participantes de chat deben tener OneDrive cuenta. Sin una cuenta OneDrive, es posible que los participantes del chat puedan colaborar en un componente creado por otros usuarios que tengan una cuenta OneDrive válida, pero no puedan crear su propia cuenta. 

Al mover un archivo .fluid OneDrive a un SharePoint web, el componente activo no se carga en Teams chat.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>¿Qué sucede si el propietario del archivo abandona la empresa?

OneDrive directivas de retención se aplican a los archivos .fluid igual que a otros contenidos creados por el usuario.

## <a name="how-are-fluid-files-shared"></a>¿Cómo se comparten los archivos .fluid?

Los componentes de bucle se pueden insertar en Teams chat o copiarse de un chat a otro. (Los componentes de bucle aún no son compatibles con los canales). Son los permisos existentes de la organización de forma predeterminada, pero los usuarios pueden cambiar los permisos antes de enviarlos para asegurarse de que todos los usuarios tienen acceso.

Abrir componentes desde Teams chat en Office.com ofrece funcionalidad de uso compartido en la parte superior de la ventana, similar a las opciones de uso compartido que se ofrecen para otros Office documentos.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>¿Qué sucede si un archivo .fluid se daña o se daña?

El Historial de versiones le permite revisar y copiar desde versiones anteriores del archivo.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>¿Qué aplicaciones pueden abrir y editar archivos .fluid?

Los archivos .fluid solo se pueden abrir como vínculos en el explorador, como Office.com, y como componentes de bucle en Teams chat. Si se descargan, no se pueden abrir de nuevo sin cargarlas primero en OneDrive o SharePoint.

## <a name="known-issues"></a>Problemas conocidos

- Los componentes de bucle en el chat no se pueden editar Aplicación de Office al usar Teams en Android.
- Si los permisos de archivo predeterminados del inquilino se establecen en Personas *específicas (solo* las personas que especifica el usuario) y el remitente quita algunos usuarios de  la lista Personas específicas en el cuadro de diálogo permisos al crear un componente, es posible que esos usuarios todavía tengan acceso al contenido.
- Con los permisos de archivo predeterminados del inquilino establecidos en Personas *específicas (solo* las personas que especifica el usuario), copiar el vínculo al componente activo y pegar en otro chat requiere que el remitente use el cuadro de diálogo permisos y agregue los destinatarios en la opción Personas específicas para conceder acceso correctamente.
- Con los permisos de archivo predeterminados del inquilino establecidos en Personas *específicas (solo* las personas que especifica el usuario), la creación de un componente activo en el chat grupal con más de 20 miembros requerirá que el remitente seleccione manualmente las opciones de permisos para el componente.
- Buscar componentes de bucle en Teams búsqueda devolverá un vínculo al componente en office.com, no en el mensaje de chat en sí.
- Los componentes de bucle están deshabilitados en chats federados.
- Los invitados B2B no podrán colaborar en un componente en directo que se comparta con ellos a través de Company Share Link. Establezca permisos en **Personas que se encuentran actualmente en este chat** para compartir componentes con invitados B2B.
- Los componentes de bucle no son compatibles Teams canales.
- Los componentes de bucle en el chat no se cargarán solo si el archivo se movió a una biblioteca diferente. Si el archivo se mueve a otra carpeta, se seguirá cargando en el chat.

## <a name="related-topics"></a>Temas relacionados

[Administrar componentes de bucle en SharePoint](/sharepoint/manage-loop-components)

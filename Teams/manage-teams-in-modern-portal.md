---
title: Administrar los equipos de Microsoft Teams & Skype para el centro de administración de negocio
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Obtenga información sobre cómo ver o actualizar los equipos en el Microsoft Teams & Skype para el centro de administración de negocio.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14ab474289e5a677e1125df7146ba7c5a6fc2ca1
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539060"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a>Administrar los equipos de Microsoft Teams & Skype para el centro de administración de negocio
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a>Información general

Como un administrador de TI, es posible que necesite vista o actualización de los equipos de su organización ha configurado para la colaboración o necesite para llevar a cabo las acciones de corrección, como la asignación de propietarios de los equipos sin dueño. Puede administrar los equipos que se usan en la organización a través del módulo de PowerShell de los equipos de Microsoft y el Microsoft Teams & Skype para el centro de administración de negocio. Para las capacidades de administración completa con estos dos conjuntos de herramientas, debe asegurarse de que se le asigna uno de los siguientes roles:

- Administrador global
- Administrador de servicios de Teams

También debe asegurarse de que su cuenta se ha asignado una licencia de los equipos que no sean de prueba para la administración. Como parte de un problema conocido, debe asegurarse de que su cuenta tiene sólo **una** función Administrador asignada.  Encontrará más información acerca de las funciones de administración en Microsoft Teams en [roles de administrador de utilizar equipos de Microsoft para administrar los equipos](using-admin-roles.md)y puede leer más información acerca de cómo usar los cmdlets de PowerShell para la administración de equipos en la [referencia del cmdlet de equipos de Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).  

En este artículo se proporciona una visión general de las herramientas de administración de equipos en el Microsoft Teams & Skype para el centro de administración de negocio.

## <a name="teams-overview-grid"></a>Cuadrícula de visión general de los equipos

Herramientas de administración de los equipos se encuentran en el nodo de **los equipos** en el Microsoft Teams & Skype para el centro de administración de negocio. (En el centro de administración, seleccione **los equipos** > **administrar equipos**.) Cada equipo se respaldadas por un grupo de Office 365, y este nodo proporciona una vista de grupos que se han habilitado para los equipos de la organización de Microsoft.

> [!NOTE]
> Estamos en el proceso de recuperación de información creado previamente equipos para asegurarse de que se mostrará en esta vista.

![Cuadrícula de visión general de los equipos](media/manage-teams-in-modern-portal-image1.png)  

La cuadrícula muestra las siguientes propiedades:

- **Nombre del equipo**
- **Canales** : un recuento de todos los canales en el equipo, incluido el canal General de forma predeterminada.
- **Los usuarios** : un recuento del total de usuarios, incluidos los propietarios, los invitados y miembros desde el inquilino.
- **Los propietarios de** -un recuento de los propietarios de este equipo.
- **Los invitados** - un recuento de los usuarios de invitado de Azure Active Directory B2B que son miembros de este equipo.
- **Privacidad** - la AccessType del grupo de realizar la copia de Office 365.

### <a name="search"></a>Buscar.

Búsqueda actualmente es compatible con la cadena "Comienza por" y busca en el campo **nombre del equipo** .

### <a name="edit"></a>Editar

Puede editar la configuración específica de equipo y grupo seleccionando un equipo de la cuadrícula y, a continuación, seleccionando el botón **Editar** .

![Editar equipo](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>Perfiles de equipo

Puede navegar a la página de perfil de equipo de cualquier equipo de la cuadrícula de visión general de los equipos principal haciendo clic en el nombre de equipo. La página de perfil de equipo muestra los miembros, los propietarios y los invitados que pertenecen al equipo (y su copia de grupo de Office 365), así como canales y la configuración del grupo. Desde la página de perfil del equipo, se puede:

- Agregar o quitar miembros y propietarios.
- Agregar o quitar canales (tenga en cuenta que no se puede quitar el canal General).
- Actualización del equipo y configuración de grupo.
 
![Perfiles de equipo](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>Realizar cambios en los equipos

Puede cambiar los siguientes elementos de un equipo:
- **Los usuarios en el equipo** , puede agregar o quitar miembros y promover o disminuir el nivel de los propietarios de
- **Canales** : puede agregar nuevos canales o quitar canales existentes.  No se puede eliminar el canal "General" de forma predeterminada y una vez creados sólo se puede editar el nombre del canal, no descripción.
- **Nombre del equipo**
- **Descripción de equipo**
- **Privacidad del equipo** - público o privado
- **Clasificación de equipo** - respaldados por sus clasificaciones de grupo de Office 365
- **Configuración del miembro de equipo** : configuración de miembro de equipo seleccione


Se registran los cambios que realice en un equipo. Si modifica la configuración de grupo (cambiar el nombre, descripción, foto, privacidad, clasificación o los miembros del equipo), estos cambios se expresarán a usted a través de la canalización de auditoría. Si va a realizar acciones contra la configuración específica de los equipos, los cambios se realiza un seguimiento y se expresarán en el canal general del equipo.


## <a name="learn-more"></a>Más información

[Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Roles de administrador en Microsoft Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->


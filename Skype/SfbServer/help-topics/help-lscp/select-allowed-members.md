---
title: Seleccionar los miembros permitidos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir AllowedMembers y Creators para cada categoría y también puede definir la configuración y comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat creados en la categoría. Los administradores de chat persistente crean y administran categorías mediante el panel de control o Windows PowerShell cmdlets.
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107996"
---
# <a name="select-allowed-members"></a>Seleccionar los miembros permitidos

Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir **AllowedMembers** y Creators para cada categoría y también puede definir la configuración y comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat **creados** en la categoría. Los administradores de chat persistente crean y administran categorías mediante el panel de control o Windows PowerShell cmdlets.

Los usuarios, las unidades organizativas (OU) y los grupos de usuarios identificados como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría. Una vez creada la categoría, pueden elegir usuarios, US y grupos de usuarios de la lista **AllowedMembers** de la categoría como administradores y miembros del salón de chat para administrar y participar en la sala.

## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Seleccionar los miembros permitidos**:

- [Configurar categorías](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [Nuevas características de servidor de conversaciones en grupo](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

Para obtener información detallada sobre los diferentes procedimientos que puede realizar mediante el Panel de control de Skype Empresarial Server, vea [Manage Skype for Business Server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorías para salones de chat

En **Pertenencia**,  en la sección Miembros permitidos, agregue o quite usuarios y otras entidades de seguridad de servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, entre otras) que puedan agregarse como miembros de salas de chat pertenecientes a la categoría. Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).


Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) en la documentación sobre planeación. Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistente, consulte [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) en la documentación sobre implementación y [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) en la documentación sobre operaciones.

## <a name="see-also"></a>Ver también

[Descripción de la pertenencia a chat persistente](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)
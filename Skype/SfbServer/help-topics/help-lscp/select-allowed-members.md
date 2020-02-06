---
title: Seleccionar los miembros permitidos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Crear y administrar salones de chat persistentes es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir AllowedMembers y creadores de cada categoría, y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salones de chat creados en la categoría. Los administradores de chats persistentes crean y administran categorías con el panel de control o los cmdlets de Windows PowerShell.
ms.openlocfilehash: ad371fada6bbb7e8c9a2620eb5ec533cc60a0673
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822303"
---
# <a name="select-allowed-members"></a>Seleccionar los miembros permitidos

Crear y administrar salones de chat persistentes es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir **AllowedMembers** y **creadores** de cada categoría, y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salones de chat creados en la categoría. Los administradores de chats persistentes crean y administran categorías con el panel de control o los cmdlets de Windows PowerShell.

Los usuarios, las unidades organizativas (UO) y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría. Después de crear la categoría, pueden elegir usuarios, unidades organizativas y grupos de usuarios de la lista de **AllowedMembers** de la categoría como administradores y miembros de los salones de chat para administrar y participar en el salón.

## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

En la página **Seleccionar los miembros permitidos** puede realizar las siguientes tareas:

- [Configure Categories](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [New Persistent Chat Server Features](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Para obtener más información sobre los distintos procedimientos que puede realizar con el panel de control de Skype empresarial Server, consulte [Manage Skype empresarial server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>Configuración de las categorías de los salones de chat

En **pertenencia**, en la sección **miembros permitidos** , agregue o quite usuarios y otros principios de los servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, etc.) que pueden agregarse como miembros de los salones de chat que pertenecen a la categoría. Las entidades de seguridad permitidas por una categoría pueden buscar los salones de la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón podrán encontrarlo en el directorio).


Para obtener más información sobre las funciones y características del servidor de chat persistentes, vea [información general sobre el servidor de chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación de planificación. Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistentes, vea [configurar el servidor de chat persistente](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) en la documentación de implementación y [administrar Lync Server 2013, servidor de chat persistente](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) en la documentación de operaciones.

## <a name="see-also"></a>Vea también

[Understanding Persistent Chat Membership](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

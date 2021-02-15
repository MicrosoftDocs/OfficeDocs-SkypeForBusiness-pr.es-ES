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
description: Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir AllowedMembers y Creators para cada categoría y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat creados en la categoría. Los administradores de chat persistente crean y administran categorías mediante el panel de control o Windows PowerShell cmdlets.
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829140"
---
# <a name="select-allowed-members"></a>Seleccionar los miembros permitidos

Crear y administrar salas de chat persistente es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir **AllowedMembers** y Creators para cada categoría y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salón de chat **creados** en la categoría. Los administradores de chat persistente crean y administran categorías mediante el panel de control o Windows PowerShell cmdlets.

Los usuarios, las unidades organizativas (OU) y los grupos de usuarios identificados como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría. Una vez creada la categoría, pueden elegir usuarios, us y grupos de usuarios de la lista **AllowedMembers** de la categoría como administradores y miembros del salón de chat para administrar y participar en el salón.

## <a name="tasks-that-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Seleccionar los miembros permitidos**:

- [Configurar categorías](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [Nuevas características de servidor de conversaciones en grupo](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Para obtener más información sobre los distintos procedimientos que puede realizar con el Panel de control de Skype Empresarial Server, consulte Administrar Skype Empresarial [Server 2015.](../../manage/manage.md)

## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorías para salones de chat

En Pertenencia **,** en la sección Miembros permitidos, agregue o quite usuarios y otras entidades de seguridad de Servicios de dominio de Active Directory (usuarios, grupos de distribución, unidades organizativas, entre otros) que puedan agregarse como miembros de los salón de chat que pertenecen a la categoría.  Los elementos principales permitidos por una categoría pueden buscar salones en la categoría (a menos que el salón esté oculto, en cuyo caso solo los miembros del salón pueden buscarlo en el directorio).


Para obtener más información sobre las características y capacidades del servidor de chat persistente, consulte Información general sobre el servidor [de chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) en la documentación sobre planeación. Para obtener más información sobre cómo trabajar con configuraciones de servidor de chat persistente, consulte [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.

## <a name="see-also"></a>Vea también

[Descripción de la pertenencia al chat persistente](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

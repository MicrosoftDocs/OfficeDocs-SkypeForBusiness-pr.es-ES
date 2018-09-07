---
title: Configurar los permisos de Quién
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Guía práctica para implementar características de voz en la nube en Microsoft Teams.
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc8fe9a21cdfa4d1df0bf3f11631d103a13fe94b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860218"
---
<a name="configure-permissions-for-who"></a>Configurar los permisos de Quién
=============================

Los usuarios pueden usar la aplicación Quién con Microsoft Teams para realizar preguntas y buscar a personas en la organización en función de la tarea que estén realizando y con quién trabajen.

Para garantizar que los usuarios sacan el máximo partido de Quién, debe activar los siguientes permisos de miembros en Microsoft Graph.

- Calendarios.Lectura

- Calendarios.Lectura.Compartidos

- Correo.Lectura

- ConfiguraciónBuzón.LecturaEscritura

- Contactos.Lectura

- Contactos.Lectura.Todos

- Sitios.Lectura.Todos

- Usuario.Lectura.Todos

Para obtener información sobre cómo gestionar el ámbito de los permisos de Microsoft Graph, consulte [Ámbito de permisos](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).
 
Para obtener información sobre los permisos de Microsoft Graph, consulte [Referencia de permisos de Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).
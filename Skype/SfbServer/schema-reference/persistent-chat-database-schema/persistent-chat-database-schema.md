---
title: Esquema de la base de datos de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Esto documenta el esquema de la base de datos de chat persistente en Skype empresarial Server.
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295618"
---
# <a name="persistent-chat-database-schema"></a>Esquema de la base de datos de chat persistente
 
Esto documenta el esquema de la base de datos de chat persistente en Skype empresarial Server.
  
La base de datos de chat persistente se refiere a la base de datos correspondiente a las funciones del servidor back-end de Skype empresarial Server **PersistentChatStore** (correspondiente a la base de datos MGC) y **PersistentChatComplianceStore** (correspondiente al base de datos mgccomp). El objetivo de publicar este esquema es permitirle crear consultas y obtener información útil para crear informes útiles sobre el uso de la conversación, las salas activas, los pósteres principales, etc.
  
> [!IMPORTANT]
> Nos reservamos el derecho de desarrollar este esquema. Microsoft no ofrece ninguna garantía de mantener la compatibilidad total con este esquema publicado. 
  
Siga estos procedimientos recomendados:
  
- No se\* admite Select//porque la lista de columnas puede crecer.
    
- No se admiten modificaciones de esquema generadas por el usuario.
    
- No se admiten las operaciones de escritura.
    
- Pruebe las consultas que cree en bases de datos de tamaño representativas para asegurarse de que las consultas pueden realizarse en un nivel que satisfaga sus necesidades.
    
## <a name="in-this-section"></a>En esta sección

- [Lista de tablas de servidores de chat persistente](list-of-persistent-chat-server-tables.md)
    
- [Lista de tablas de cumplimiento del servidor de chat persistente en Skype empresarial Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Detalles de la tabla del servidor de chat persistente](persistent-chat-server-table-details.md)
    
- [Consultas de base de datos del chat persistente de ejemplo](sample-persistent-chat-database-queries.md)
    


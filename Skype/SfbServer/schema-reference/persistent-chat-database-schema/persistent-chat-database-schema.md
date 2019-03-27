---
title: Esquema de la base de datos de chat persistente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Documenta el esquema de la base de datos de Chat persistente en Skype para Business Server.
ms.openlocfilehash: 37b22077157def7ea25a5cf70b23a0272a58956e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874061"
---
# <a name="persistent-chat-database-schema"></a>Esquema de la base de datos de chat persistente
 
Documenta el esquema de la base de datos de Chat persistente en Skype para Business Server.
  
La base de datos de Chat persistente hace referencia a la base de datos correspondiente a la Skype para funciones de servidor de Business Server Back-End **PersistentChatStore** (correspondiente a la base de datos de CGM) y **PersistentChatComplianceStore** (correspondiente a la base de datos de mgccomp). El objetivo de este esquema de publicación es que le permite generar consultas y obtener algunos entendimiento de creación de informes útiles alrededor de uso de chat, salones de activos, Pósteres superiores y así sucesivamente.
  
> [!IMPORTANT]
> Nos reservamos el derecho a evolucionar este esquema. Microsoft no realiza ninguna garantía para mantener la compatibilidad con versiones anteriores completa con este esquema publicado. 
  
Siga estos procedimientos recomendados:
  
- No seleccione\* / / se admite porque la lista de columnas puede crecer.
    
- No se admiten modificaciones del esquema generados por el usuario.
    
- No hay ninguna operación de escritura se admite.
    
- Pruebe las consultas que genere sobre bases de datos de tamaño representativo para asegurarse de que las consultas se pueden realizar a un nivel para satisfacer sus necesidades.
    
## <a name="in-this-section"></a>En esta sección

- [Lista de tablas de servidores de chat persistente](list-of-persistent-chat-server-tables.md)
    
- [Lista de tablas de cumplimiento del servidor de Chat persistente en Skype para Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Detalles de la tabla del servidor de chat persistente](persistent-chat-server-table-details.md)
    
- [Consultas de base de datos del chat persistente de ejemplo](sample-persistent-chat-database-queries.md)
    


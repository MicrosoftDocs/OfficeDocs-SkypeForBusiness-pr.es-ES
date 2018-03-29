---
title: Esquema de la base de datos de chat persistente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Esto documenta el esquema de la base de datos persistente Chat de Skype para Business Server.
ms.openlocfilehash: 1c78ea53438484fb0ad573a815c10ad76f08edca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-database-schema"></a>Esquema de la base de datos de chat persistente
 
Esto documenta el esquema de la base de datos persistente Chat de Skype para Business Server.
  
La base de datos persistente charla hace referencia a la base de datos correspondiente a la Skype para funciones de Business Server atrás End Server **PersistentChatStore** (correspondiente a la base de datos de CGM) y **PersistentChatComplianceStore** (correspondiente a la base de datos de mgccomp). El objetivo de la publicación de este esquema es que le permite generar consultas y tener algunos conocimientos a la creación de informes útiles alrededor de uso de chat, salas de activos, publicadores principales y así sucesivamente.
  
> [!IMPORTANT]
> Nos reservamos el derecho a evolucionar este esquema. Microsoft no realiza garantía alguna para mantener la compatibilidad completa con este esquema publicado. 
  
Siga estas recomendaciones:
  
- No seleccione\* / / se admite porque puede aumentar la lista de columnas.
    
- No se admiten modificaciones de esquema generados por el usuario.
    
- No hay ninguna operación de escritura se admite.
    
- Probar todas las consultas que se generación en tamaño representativo de bases de datos para asegurarse de que las consultas se pueden realizar en un nivel para satisfacer sus necesidades.
    
## <a name="in-this-section"></a>En esta sección

- [Lista de tablas del servidor de Chat persistentes](list-of-persistent-chat-server-tables.md)
    
- [Lista de tablas de cumplimiento de normas de servidor de charla persistente en Skype para Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Detalles de tabla de servidor de charla persistentes](persistent-chat-server-table-details.md)
    
- [Ejemplos de consultas de base de datos persistente de charla](sample-persistent-chat-database-queries.md)
    


---
title: Esquema de la base de datos de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Esto documenta el esquema de la base de datos de chat persistente en Skype Empresarial Server.
ms.openlocfilehash: 673cca8acf2ecad76c578ba05d8d22a20a253a9c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610587"
---
# <a name="persistent-chat-database-schema"></a>Esquema de la base de datos de chat persistente
 
Esto documenta el esquema de la base de datos de chat persistente en Skype Empresarial Server.
  
La base de datos de chat persistente hace referencia a la base de datos correspondiente a los roles de servidor back-end de Skype Empresarial Server **PersistentChatStore** (correspondiente a la base de datos mgc) y **PersistentChatComplianceStore** (correspondiente a la base de datos mgccomp). El objetivo de publicar este esquema es permitirle crear consultas y obtener información sobre cómo crear informes útiles sobre el uso de chat, salas activas, pósteres principales, entre otros.
  
> [!IMPORTANT]
> Nos reservamos el derecho de desarrollar este esquema. Microsoft no ofrece ninguna garantía para mantener la compatibilidad total con versiones anteriores con este esquema publicado. 
  
Siga estos procedimientos recomendados:
  
- No se \* admite SELECT // porque la lista de columnas puede crecer.
    
- No se admiten modificaciones de esquema generadas por el usuario.
    
- No se admite ninguna operación de escritura.
    
- Pruebe las consultas que cree en bases de datos de tamaño representativo para asegurarse de que las consultas pueden realizarse en un nivel que satisfaga sus necesidades.
    
## <a name="in-this-section"></a>En esta sección

- [Lista de tablas de servidores de chat persistente](list-of-persistent-chat-server-tables.md)
    
- [Lista de tablas de cumplimiento del servidor de chat persistente en Skype Empresarial Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Detalles de la tabla del servidor de chat persistente](persistent-chat-server-table-details.md)
    
- [Consultas de base de datos del chat persistente de ejemplo](sample-persistent-chat-database-queries.md)
    


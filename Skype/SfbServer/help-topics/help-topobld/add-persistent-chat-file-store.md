---
title: Agregar almacén de archivos de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: f11443f8c10db35d5ffb8bfdbfc03d9826700b7c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820682"
---
# <a name="add-persistent-chat-file-store"></a>Agregar almacén de archivos de chat persistente
 
Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
  
> [!IMPORTANT]
> El recurso compartido de archivos de Skype empresarial Server no se puede ubicar en el servidor de aplicaciones para el usuario de Enterprise Edition, pero puede estar ubicado en un servidor Standard Edition. 
  
> [!IMPORTANT]
> El recurso compartido de archivos se puede definir en el Generador de topologías antes de crearlo; sin embargo, el recurso compartido de archivos se debe crear en la ubicación indicada antes de publicar la topología 
  
> [!IMPORTANT]
> Al agregar un servidor de chat persistente o un grupo de servidores de chat persistente a su topología, el generador de topología debe poder configurar el almacén de archivos y configurar listas de control de acceso discrecional (DACL) en el recurso compartido de archivos para usarlos en el almacén de archivos. Esto implica que, al ejecutar el Generador de topologías para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos. 
  
## <a name="see-also"></a>Vea también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Conceptos básicos de topología de Skype Empresarial Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)

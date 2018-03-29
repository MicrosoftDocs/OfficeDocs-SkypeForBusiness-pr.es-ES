---
title: Agregar almacén de archivos de chat persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: 76b116d469bf6369174815d6b396a64149518f17
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-file-store"></a>Agregar almacén de archivos de chat persistente
 
Debe especificar el recurso compartido de archivos que se debe usar como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
  
> [!IMPORTANT]
> El recurso compartido de archivos de Skype para Business Server no se encuentra en el servidor de extremo frontal de Enterprise Edition, pero puede estar ubicado en un servidor Standard Edition. 
  
> [!IMPORTANT]
> El recurso compartido de archivos se puede definir en el Generador de topologías antes de crearlo; sin embargo, el recurso compartido de archivos se debe crear en la ubicación indicada antes de publicar la topología 
  
> [!IMPORTANT]
> Al agregar un servidor de charla persistente o persistente servidor de charla de grupo de la topología, el generador de topología debe ser capaz de configurar el archivo almacenar y configurar el control de acceso discrecional (DACL) se enumeran en el recurso compartido de archivo que se utilizará para el almacén de archivos. Esto implica que, al ejecutar el Generador de topologías para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos. 
  
## <a name="see-also"></a>Vea también

#### 

[Plan para el servidor de charla persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar servidor de Chat persistentes a su Skype para la topología de servidor de negocios 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Conceptos básicos de topología para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)


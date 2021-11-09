---
title: Agregar almacén de archivos de chat persistente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Debe especificar el recurso compartido de archivos que debe usarse como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end de Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
ms.openlocfilehash: 528c1e2d78f67391af0536296588f6b047ee1c87
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850063"
---
# <a name="add-persistent-chat-file-store"></a>Agregar almacén de archivos de chat persistente
 
Debe especificar el recurso compartido de archivos que debe usarse como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end de Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.
  
> [!IMPORTANT]
> El recurso compartido de Skype Empresarial Server no se puede encontrar en el servidor front-end Enterprise Edition, pero se puede encontrar en un Standard Edition servidor. 
  
> [!IMPORTANT]
> El recurso compartido de archivos puede definirse en Topology Builder antes de crearlo; sin embargo, el recurso compartido de archivos debe crearse en la ubicación indicada antes de publicar la topología. 
  
> [!IMPORTANT]
> Al agregar un servidor de chat persistente o un grupo de servidores de chat persistente a la topología, el Generador de topologías debe poder configurar el almacén de archivos y configurar listas de control de acceso discrecional (DACL) en el recurso compartido de archivos para que se usen para el almacén de archivos. Esto implica que, al ejecutar el Topology Builder para publicar la nueva topología, debe haber iniciado sesión en una cuenta que tenga todos los permisos de control (lectura/escritura/modificación) respecto al recurso compartido de archivos. 
  
## <a name="see-also"></a>Consulte también

[Planear el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar servidor de chat persistente a la topología Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Conceptos básicos de topología para Skype Empresarial Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)

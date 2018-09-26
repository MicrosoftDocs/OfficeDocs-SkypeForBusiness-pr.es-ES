---
title: Configurar servidores de aplicaciones de confianza
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el próximo salto para ser un Skype para el grupo de servidores de Business Server 2019. En un entorno mixto, el grupo heredado y el Skype para el grupo de servidores de Business Server 2019 aparecen en la lista desplegable. No se admite la selección del grupo heredado.
ms.openlocfilehash: d1c79e044145a4739cf1b7bfb3992320be1e4ab3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027749"
---
# <a name="configure-trusted-application-servers"></a>Configurar servidores de aplicaciones de confianza

En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el próximo salto para ser un Skype para el grupo de servidores de Business Server 2019. En un entorno mixto, el grupo heredado y el Skype para el grupo de servidores de Business Server 2019 aparecen en la lista desplegable. No se admite la selección del grupo heredado.
  
> [!IMPORTANT]
> Si va a migrar un servidor de aplicaciones de confianza, también deberá actualizar la versión de UCMA está utilizando. Si se crea un nuevo grupo de aplicaciones de confianza para Skype para Business Server 2019, deberá actualizar UCMA a la versión que se incluye con Skype para Business Server 2019 o la versión más reciente disponible. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Seleccione Skype para Business Server 2019 como próximo salto al crear un servidor de aplicaciones de confianza

1. Abra el generador de topología.
    
2. En el panel izquierdo, haga clic en **servidores de aplicaciones de confianza** y haga clic en **Nuevo grupo de aplicaciones de confianza**.
    
3. Escriba el **FQDN del grupo de servidores** del grupo de aplicaciones de confianza y seleccione si será un único servidor o varios servidores. 
    
4. Haga clic en **Siguiente**.
    
5. En la página **Seleccionar el próximo salto** , en la lista, seleccione el Skype para el grupo de servidores Front-End de Business Server 2019. 
    
6. Haga clic en **Finalizar**.
    
7. Seleccione el nodo superior **Skype para Business Server**y, en el menú **acción** , seleccione **Publicar**.
    
    Compruebe que el **Grupo de aplicaciones de confianza** se ha creado correctamente y está asociado con el grupo de servidores Front-End correcto. 
    


---
title: Configurar servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe configurar el grupo de próximos saltos para que sea un grupo de servidores de Skype empresarial 2019. En un entorno mixto, tanto el grupo heredado como el grupo de servidores de Skype empresarial 2019 aparecen en la lista desplegable. No se puede seleccionar el grupo heredado.
ms.openlocfilehash: b715cd7f3f067c5e54dbc085350fcc7f96b5c4be
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239301"
---
# <a name="configure-trusted-application-servers"></a>Configurar servidores de aplicaciones de confianza

En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe configurar el grupo de próximos saltos para que sea un grupo de servidores de Skype empresarial 2019. En un entorno mixto, tanto el grupo heredado como el grupo de servidores de Skype empresarial 2019 aparecen en la lista desplegable. No se puede seleccionar el grupo heredado.
  
> [!IMPORTANT]
> Si va a migrar un servidor de aplicaciones de confianza, también debe actualizar la versión de UCMA que está usando. Si crea un nuevo grupo de aplicaciones de confianza para Skype empresarial Server 2019, debe actualizar UCMA a la versión que se incluye con Skype empresarial Server 2019 o a la versión más reciente disponible. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Seleccione Skype empresarial Server 2019 como próximo salto al crear un servidor de aplicaciones de confianza

1. Abra el generador de topologías.
    
2. En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza** y haga clic en **nuevo grupo de aplicaciones de confianza**.
    
3. Escriba el **FQDN del grupo** del grupo de aplicaciones de confianza y seleccione si será de servidor único o de varios servidores. 
    
4. Haga clic en **Siguiente**.
    
5. En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo front-end de Skype empresarial Server 2019. 
    
6. Haga clic en **Finalizar**.
    
7. Seleccione el nodo superior **de Skype empresarial Server**y, en el menú **acción** , seleccione **publicar**.
    
    Compruebe que el **grupo de aplicaciones de confianza** se haya creado correctamente y que esté asociado al grupo de servidores front-end correcto. 
    


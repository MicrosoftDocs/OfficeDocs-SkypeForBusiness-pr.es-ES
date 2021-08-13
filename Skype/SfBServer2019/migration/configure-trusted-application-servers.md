---
title: Configuración de servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el grupo de servidores del próximo salto como un grupo de servidores Skype Empresarial Server 2019. En un entorno mixto, tanto el grupo heredado como el grupo de servidores Skype Empresarial Server 2019 aparecen en la lista desplegable. No se admite la selección del grupo heredado.
ms.openlocfilehash: 6db3aaadfe028e6d1975521ecacb52ad26754b7bcf8766af345d4786bc825f31
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296097"
---
# <a name="configure-trusted-application-servers"></a>Configuración de servidores de aplicaciones de confianza

En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el grupo de servidores del próximo salto como un grupo de servidores Skype Empresarial Server 2019. En un entorno mixto, tanto el grupo heredado como el grupo de servidores Skype Empresarial Server 2019 aparecen en la lista desplegable. No se admite la selección del grupo heredado.
  
> [!IMPORTANT]
> Si va a migrar un servidor de aplicaciones de confianza, también debe actualizar la versión de UCMA que está usando. Si crea un nuevo grupo de aplicaciones de confianza para Skype Empresarial Server 2019, debe actualizar UCMA a la versión que se incluye con Skype Empresarial Server 2019 o la versión más reciente disponible. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Seleccione Skype Empresarial Server 2019 como próximo salto al crear un servidor de aplicaciones de confianza

1. Abra el Generador de topologías.
    
2. En el panel izquierdo, haga clic con el botón secundario en **Servidores de aplicaciones de confianza** y haga clic en Nuevo grupo de aplicaciones de **confianza.**
    
3. Escriba el **FQDN del grupo de** servidores del grupo de aplicaciones de confianza y seleccione si será de un solo servidor o de varios servidores. 
    
4. Haga clic en **Siguiente**.
    
5. En la **página Seleccionar el próximo salto,** en la lista, seleccione el grupo de servidores Skype Empresarial Server front-end de 2019. 
    
6. Haga clic en **Finalizar**.
    
7. Seleccione el nodo superior **Skype Empresarial Server** y, en el **menú Acción,** seleccione **Publicar**.
    
    Compruebe que el **grupo de aplicaciones de confianza** se ha creado correctamente y está asociado con el grupo de servidores front-end correcto. 
    


---
title: Agregar las bases de datos a un grupo de disponibilidad AlwaysOn en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: Obtenga información sobre cómo agregar más Skype para bases de datos de Business Server a un grupo de disponibilidad AlwaysOn existente de Skype para Business Server.'
ms.openlocfilehash: e5217ba16234ea96f205d8ee89b6d31ac6b2df6c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372063"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a>Agregar las bases de datos a un grupo de disponibilidad AlwaysOn en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo agregar más Skype para bases de datos de Business Server a un grupo de disponibilidad AlwaysOn existente de Skype para Business Server.
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>Adición de bases de datos a un grupo de disponibilidad AlwaysOn

1. Abra SQL Server Management Studio y navegue hasta el grupo de disponibilidad AlwaysOn. Conmutación por error se a la réplica principal.
    
2. En el generador de topología, establezca el FQDN del grupo de disponibilidad AlwaysOn de SQL Server en el FQDN del nodo principal de ese grupo.
    
   - Abra el generador, seleccione **Descargar topología de la implementación existente**y haga clic en **Aceptar**.
    
   - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. Haga clic en el almacén de SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.
    
   - En la parte inferior de la página, en el cuadro **FQDN de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.
    
3. Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.
    
4. Use SQL Server Management Studio para agregar la nueva base de datos para el grupo de disponibilidad AlwaysOn.
    


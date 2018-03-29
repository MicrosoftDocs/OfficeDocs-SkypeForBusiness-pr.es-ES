---
title: Agregar bases de datos a un grupo de disponibilidad AlwaysOn en Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Resumen: Conozca cómo agregar más Skype para bases de datos de Business Server a un grupo existente de disponibilidad AlwaysOn en Skype para Business Server 2015.'
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>Agregar bases de datos a un grupo de disponibilidad AlwaysOn en Skype para Business Server 2015
 
**Resumen:** Aprenda a agregar más Skype para bases de datos de Business Server a un grupo existente de disponibilidad AlwaysOn en Skype para Business Server 2015.
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>Agregar bases de datos a un grupo de disponibilidad AlwaysOn

1. Abra SQL Server Management Studio y vaya hasta el grupo de disponibilidad AlwaysOn. Conmutarla a la réplica principal.
    
2. Generador de topología, establezca el nombre completo de SQL Server del grupo de disponibilidad AlwaysOn en el FQDN del nodo principal de ese grupo.
    
  - Abrir el generador de topología, seleccione **Descargar la topología de implementación existente**y haga clic en **Aceptar**.
    
  - Expanda Skype Empresarial Server, expanda la topología y expanda **Almacenes de SQL Server**. (Ratón) en el almacén SQL del nuevo grupo de disponibilidad AlwaysOn y haga clic en **Editar propiedades**.
    
  - En la parte inferior de la página, en el cuadro **Nombre de dominio completo de SQL Server** , escriba el FQDN del nodo principal del grupo de disponibilidad AlwaysOn.
    
3. Publique la topología. En el menú **Acción** haga clic en **Topología** y luego en **Publicar**. Después, en la página de confirmación haga clic en **Siguiente**.
    
4. Para agregar la nueva base de datos para el grupo de disponibilidad AlwaysOn, utilice SQL Server Management Studio.
    


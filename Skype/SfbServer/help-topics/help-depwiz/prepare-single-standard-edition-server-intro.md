---
title: Preparar un servidor único de Standard Edition (introducción)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Para comenzar la instalación de un Skype para servidor 2015 Business Server Standard Edition que contendrá el almacén de Administración Central y otros servicios colocadas que seleccione, debe iniciar sesión como miembro del grupo de administradores local en el servidor que será se convierten en el servidor Standard Edition. La página de preparar estándar single Server Edition detalla los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
ms.openlocfilehash: 9c43f3bc4574d35577b483cf1ca0748f78f3d04a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparar un servidor único de Standard Edition (introducción)
 
Para comenzar la instalación de un Skype para servidor 2015 Business Server Standard Edition que contendrá el almacén de Administración Central y otros servicios colocadas que seleccione, debe iniciar sesión como miembro del grupo de administradores local en el servidor que será se convierten en el servidor Standard Edition. En la página de **preparación de un solo servidor Standard Edition** se detallan los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
  
El objetivo de esta tarea específica es configurar un servidor Standard Edition como primer servidor de la infraestructura. Esta tarea instala el almacén de Administración Central, que es SQL Server Express, en el servidor Standard Edition. Si ya tiene implementado otro servidor Standard Edition u otro grupo de servidores front-end, debe hacer clic en **Cancelar**.
  
> [!NOTE]
> Después de completar esta tarea, instalará al generador de topología (si no se ha instalado ya) y configurar el documento de la topología. No podrá publicar el documento de topología hasta que tenga un almacén de administración central disponible, que se implementa completando la tarea descrita en este tema. 
  


---
title: Preparar un servidor único de Standard Edition (introducción)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Para comenzar la instalación de un Skype para servidor Business Server Standard Edition que contendrá el almacén de Administración Central y otros servicios combinados que seleccione, debe haber iniciado sesión como miembro del grupo Administradores local en el servidor que se convertirá en el servidor Standard Edition. En la página de preparación de un solo servidor Standard Edition se detallan los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
ms.openlocfilehash: b4b211899ba907a20d11f8adf4d2640599dc6f91
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216588"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparar un servidor único de Standard Edition (introducción)
 
Para comenzar la instalación de un Skype para servidor Business Server Standard Edition que contendrá el almacén de Administración Central y otros servicios combinados que seleccione, debe haber iniciado sesión como miembro del grupo Administradores local en el servidor que se convertirá en el servidor Standard Edition. En la página de **preparación de un solo servidor Standard Edition** se detallan los requisitos para la instalación inicial. El equipo debe ser miembro del dominio en el que se va a implementar, y el usuario debe haber completado correctamente la preparación del esquema, el bosque y el dominio para el bosque.
  
El objetivo de esta tarea específica es configurar un servidor Standard Edition como primer servidor de la infraestructura. Esta tarea instala el almacén de Administración Central, que es SQL Server Express, en el servidor Standard Edition. Si ya tiene implementado otro servidor Standard Edition u otro grupo de servidores front-end, debe hacer clic en **Cancelar**.
  
> [!NOTE]
> Después de completar esta tarea, va a instalar al generador de topología (si no se ha instalado ya) y configure su documento de topología. No podrá publicar el documento de topología hasta que tenga un almacén de administración central disponible, que se implementa completando la tarea descrita en este tema. 
  

